# Numerical Solutions to Differential Equations

> Euler, Runge-Kutta, and stability analysis applied to real physical systems.

**Live Project Page:** [coyjohnson25.github.io/numerical-differential-equations](https://coyjohnson25.github.io/numerical-differential-equations)  
**Portfolio:** [coyjohnson25.github.io](https://coyjohnson25.github.io)

---

## Overview

Most real-world ODEs have no closed-form solution, making numerical methods essential. This project implements a suite of solvers from scratch, applies them to physically meaningful systems, and rigorously analyzes accuracy and stability — drawing directly from a background in classical mechanics and thermodynamics.

---

## What's Inside

```
numerical-differential-equations/
├── README.md
├── requirements.txt
├── notebooks/
│   └── numerical_odes.ipynb         ← Full walkthrough with visualizations
├── src/
│   ├── solvers.py                   ← Euler, RK2, RK4 implementations
│   ├── systems.py                   ← Physical system definitions
│   └── stability.py                 ← Error and stability analysis
├── results/
│   ├── pendulum_phase_portrait.png
│   ├── sir_model.png
│   └── error_comparison.png
└── docs/
    └── index.html                   ← Project detail page
```

---

## Methods Implemented

| Method | Order | Notes |
|--------|-------|-------|
| Euler | O(h) | Baseline — simple but error-prone |
| Midpoint (RK2) | O(h²) | 2× function evaluations per step |
| Classic RK4 | O(h⁴) | Industry-standard balance of speed and accuracy |

---

## Physical Systems Modeled

| System | Equation | Key Insight |
|--------|----------|-------------|
| Nonlinear Pendulum | θ'' + (g/L)sin(θ) = 0 | Small-angle approx. fails at >30° |
| Damped Harmonic Oscillator | mx'' + bx' + kx = 0 | Phase portraits reveal damping regimes |
| SIR Epidemic Model | dI/dt = βSI − γI | R₀ = β/γ determines outbreak fate |
| Logistic Growth | dP/dt = rP(1 − P/K) | Used to validate against analytical solution |

---

## Key Math

```
# RK4 — weighted average of four slopes
k₁ = f(tₙ, yₙ)
k₂ = f(tₙ + h/2, yₙ + h·k₁/2)
k₃ = f(tₙ + h/2, yₙ + h·k₂/2)
k₄ = f(tₙ + h,   yₙ + h·k₃)

y_{n+1} = yₙ + (h/6)(k₁ + 2k₂ + 2k₃ + k₄)
```

---

## Quickstart

```bash
git clone https://github.com/coyjohnson25/numerical-differential-equations.git
cd numerical-differential-equations
pip install -r requirements.txt
jupyter notebook notebooks/numerical_odes.ipynb
```

---

## Results

- RK4 ~100× more accurate than Euler at h = 0.1
- Pendulum at 70° initial angle: small-angle approximation overpredicts period by 18%
- Logistic growth global error: RK4 = 1.2×10⁻⁵ vs Euler = 8.7×10⁻³

---

## Tech Stack

`Python` `MATLAB` `NumPy` `Matplotlib` `Jupyter`

---

## Author

**Coy Johnson** — [coyjohnson25@gmail.com](mailto:coyjohnson25@gmail.com)  
M.S. Mathematics Candidate | Applied Mathematician# machine-learning-from-scratch
