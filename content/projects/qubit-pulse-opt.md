---
title: "QubitPulseOpt: Verified GRAPE Optimization"
date: 2025-11-24
draft: false
tags: ["Quantum Computing", "Python", "Optimal Control", "GRAPE"]
summary: "A Python framework for quantum optimal control, demonstrating 99.14% fidelity in closed-loop simulation."
---

## Overview

QubitPulseOpt is a Python framework implementing the GRAPE (Gradient Ascent Pulse Engineering) algorithm for quantum optimal control. The project demonstrates that high-fidelity quantum gate operations can be achieved through systematic pulse optimization, reaching 99.14% fidelity in closed-loop simulation.

## Key Features

- **GRAPE Algorithm Implementation**: Full implementation of gradient-based pulse optimization
- **High Fidelity Results**: Achieved 99.14% gate fidelity in simulation
- **Closed-Loop Optimization**: Iterative refinement of control pulses
- **Modular Architecture**: Easy to extend for different quantum systems
- **Hardware-Ready**: Designed with eventual FPGA implementation in mind

## Technical Details

The framework uses:
- Numerical quantum state evolution
- Gradient computation for pulse optimization
- Matrix exponential methods for unitary propagation
- Optimization algorithms (gradient descent, L-BFGS)

## Applications

- Quantum gate synthesis
- Pulse sequence optimization
- Control calibration for real quantum hardware
- Foundation for Hardware-in-the-Loop testing

## Links

- [GitHub Repository](https://github.com/rylanmalarchick/QubitPulseOpt)
- [Preprint Paper](https://github.com/rylanmalarchick/QubitPulseOpt/blob/main/preprint.pdf) (if available)

## Future Work

The next phase involves porting key computational kernels to FPGA hardware using the Lattice ECP5, enabling real-time pulse generation and optimization for physical quantum systems.
