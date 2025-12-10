---
title: "High-Performance VQE: 117× Speedup for Quantum Chemistry"
date: 2025-11-15
draft: false
tags: ["Quantum Computing", "HPC", "VQE", "GPU", "PennyLane", "JAX"]
summary: "GPU-accelerated Variational Quantum Eigensolver achieving 117× speedup on quantum chemistry simulations through JIT compilation, GPU parallelization, and MPI scaling."
weight: 2
---

**Status:** Technical Report (ERAU, Fall 2025)

## Overview

GPU-accelerated Variational Quantum Eigensolver (VQE) for quantum chemistry simulations. Achieved **117× speedup** through a 4-phase optimization pipeline, reducing H2 potential energy surface computation from 593.95s to 5.04s while maintaining near-exact accuracy.

## Key Results

| Metric | Value |
|--------|-------|
| Speedup | 117× |
| Original Time | 593.95s |
| Optimized Time | 5.04s |
| Ground State Energy | -1.137 Ha (at equilibrium) |
| Bond Lengths Computed | 100 |

## Optimization Pipeline

### Phase 1: JIT Compilation
- Just-in-time compilation of quantum circuit operations
- Eliminates Python interpreter overhead

### Phase 2: GPU Acceleration  
- Single-GPU parallelization of quantum state evolution
- CUDA-accelerated matrix operations

### Phase 3: Multi-GPU Scaling
- Distributed computation across 4× NVIDIA H100 GPUs
- Efficient memory management for large state vectors

### Phase 4: MPI Parallelization
- OpenMPI distribution across 192 AMD EPYC cores
- Hybrid CPU-GPU workload balancing

## Hardware

Computed on **ERAU Vega HPC Cluster**:
- 4× NVIDIA H100 GPUs
- 192 AMD EPYC CPU cores
- High-bandwidth interconnect

## Application

Computed the **H2 molecular potential energy surface**—the ground state energy of molecular hydrogen across 100 different bond lengths. This is a standard benchmark for quantum chemistry methods and demonstrates the practical utility of VQE for molecular simulation.

The 117× speedup enables **interactive exploration** of quantum chemistry problems that would otherwise require batch processing.

## Technology Stack

- **Quantum Framework:** PennyLane
- **GPU Acceleration:** JAX, CUDA
- **Parallelization:** OpenMPI (mpi4py)
- **HPC:** SLURM, Linux cluster

## Links

- [GitHub Repository](https://github.com/rylanmalarchick/QuantumVQE)
- Technical Report: "Parallelizing the Variational Quantum Eigensolver" (ERAU, 2025)
