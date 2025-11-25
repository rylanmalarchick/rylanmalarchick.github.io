---
title: "Why I'm Moving My Quantum Simulator to an FPGA"
date: 2025-11-24
draft: false
tags: ["FPGA", "Quantum Computing", "Hardware", "Performance"]
summary: "The shift from Python-based simulation to Hardware-in-the-Loop using the Lattice ECP5."
---

## The Problem with Software

When I started building QubitPulseOpt, Python was the obvious choice. NumPy, SciPy, great ecosystem, fast prototyping. But as soon as you try to do real-time quantum control, you hit a wall.

The bottleneck? Matrix multiplication.

Quantum state evolution requires computing matrix exponentials and propagating state vectors through unitary operators. On a CPU, this is fine for offline optimization. But if you want to generate RF pulses in real-time, respond to measurement outcomes, and close the feedback loop at microsecond timescales, Python becomes a liability.

## Enter the FPGA

I'm moving the computational core to a Lattice ECP5 FPGA. Not because it's trendy, but because it's the only way to achieve the performance I need.

### Why FPGA?

- **Parallel Processing**: Matrix operations map naturally to hardware
- **Deterministic Timing**: No operating system jitter
- **Real-time RF Generation**: Direct control over signal generation
- **Low Latency**: Sub-microsecond response times

## The "Headless" Architecture

The architecture I'm building is what I call "headless" quantum control:

1. **Python Frontend**: High-level optimization, pulse design, calibration
2. **FPGA Backend**: Real-time pulse execution, state propagation, feedback
3. **USB/PCIe Interface**: Fast parameter updates from host

The FPGA doesn't need to know about GRAPE algorithms or optimization strategies. It just needs to execute pulse sequences and report measurement results. The intelligence stays in software, but the grunt work moves to hardware.

## Hardware-in-the-Loop

This isn't just about speed. It's about building a platform that can eventually interface with real quantum hardware. The same FPGA code that runs the simulation can drive actual RF generators, read out qubits, and implement feedback protocols.

Hardware-in-the-Loop (HIL) means you develop your control system against a high-fidelity simulator, then swap the simulator for real hardware with minimal changes.

## Current Progress

Right now I'm:
- Porting matrix operations to Verilog/VHDL
- Building a USB interface for host communication
- Benchmarking fixed-point arithmetic for quantum operators
- Designing the pulse generation pipeline

The goal is to match or exceed the 99.14% fidelity I achieved in software, but at rates that make closed-loop control practical.

## Why Lattice ECP5?

The ECP5 is cheap, well-documented, and has fully open-source tooling (Yosys, nextpnr). I don't want to be locked into vendor tools or expensive development boards. This is research hardware, not a product—I need flexibility.

Plus, it has enough resources (85k LUTs, DSP blocks, block RAM) to implement a full quantum state simulator without breaking the bank.

## What's Next

Once the core simulator is stable on the FPGA, I'll start working on the RF frontend. That means DACs, mixers, and eventually coupling to a physical qubit. But that's a story for another post.

For now, the transition from Python to FPGA is the critical step. Software got me to 99% fidelity. Hardware will get me to real-time control.
