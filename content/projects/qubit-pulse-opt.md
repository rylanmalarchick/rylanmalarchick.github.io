---
title: "QubitPulseOpt: GRAPE Pulse Optimization for Quantum Gates"
date: 2025-12-01
draft: false
tags: ["Quantum Computing", "Optimal Control", "GRAPE", "Python", "QuTiP"]
summary: "Python framework for quantum gate optimization using GRAPE with realistic noise modeling. Achieved 99.14% fidelity through microwave control pulse optimization. Preprint on arXiv (Dec 2025)."
weight: 1
---

**Status:** Preprint on arXiv (December 2025)

## Overview

QubitPulseOpt is a Python framework for quantum gate optimization using GRAPE (Gradient Ascent Pulse Engineering) with realistic noise modeling. The project demonstrates that high-fidelity quantum gate operations can be achieved through systematic pulse optimization, reaching **99.14% X-gate fidelity** in 20ns simulations—a **77% error reduction** compared to Gaussian baseline pulses.

## Key Results

| Metric | Value |
|--------|-------|
| X-gate Fidelity | 99.14% |
| Error Reduction | 77% vs. Gaussian baseline |
| Simulation Time | 20ns |
| Unit Tests | 864 |
| Code Coverage | 74% |

## Technical Approach

### Noise Modeling
- **Lindblad master equation** for realistic T1/T2 decoherence effects
- Hardware-representative workflow via API connectivity to **IQM Garnet 20-qubit processor** for calibration retrieval
- Microwave control pulse optimization for transmon qubits

### Optimization
- GRAPE algorithm with gradient-based pulse refinement
- Numerical quantum state evolution using matrix exponentials
- Multiple optimization backends (gradient descent, L-BFGS)

### Software Engineering
- Engineered following **NASA JPL Power-of-10** coding standards
- CI/CD pipeline with GitHub Actions
- 864 unit tests, 74% code coverage
- Modular architecture for extensibility

## Technology Stack

- **Quantum Simulation:** QuTiP, NumPy, SciPy
- **Optimization:** GRAPE, L-BFGS, gradient descent
- **Testing:** pytest, GitHub Actions CI/CD
- **Hardware Integration:** IQM Garnet API

## Links

- [GitHub Repository](https://github.com/rylanmalarchick/QubitPulseOpt)
- [arXiv Preprint (arXiv:2511.12799)](https://arxiv.org/abs/2511.12799)

## Citation

Malarchick, R. (2025). "GRAPE Pulse Optimization for Quantum Gates with Hardware-Representative Noise." arXiv:2511.12799.
