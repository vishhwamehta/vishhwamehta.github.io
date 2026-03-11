---
title: "Anti-Interception Robust Trajectory Optimization for UAVs"
permalink: /projects/uav-trajectory-optimization/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ae567_1.png
    image_path: /assets/images/projects/ae567_1.png
    alt: "Robust optimal trajectory"
    title: "Robust optimal trajectory (g_robust = 0.99) vs. reference trajectory, with threat location"
  - url: /assets/images/projects/ae567_2.png
    image_path: /assets/images/projects/ae567_2.png
    alt: "EKF filtering and forecasting for missile trajectory"
    title: "EKF state-parameter filtering and open-loop forecasting of interceptor trajectory"
---

*AEROSP 567 — Statistical Inference, Estimation & Learning · University of Michigan · Mar–Apr 2024*

[📄 Full Report](/assets/reports/Mehta_AE567_FinalProject.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---
{% include gallery %}

## Overview

A two-part robust trajectory optimization framework for UAVs in contested airspace. **Part 1:** learn the states and unknown parameters of an incoming interceptor using an Extended Kalman Filter, then forecast its future position via open-loop prediction. **Part 2:** optimize the UAV's trajectory to evade the interceptor by solving a stochastic Optimal Control Problem with a Monte Carlo-based robustness constraint — iterating until the likelihood of evasion meets a 0.99 safety threshold.

The UAV is modeled as a loitering munition during its descent phase, analogous to the Shahed-136.

---

## UAV Dynamics Model

A **3-DOF point-mass model** governs the UAV, with state vector **x** = [x_c, y_c, z_c, γ, χ, V] and control inputs **u** = [α, μ, T]. The equations of motion capture coupled longitudinal and lateral dynamics through thrust, lift, drag, angle of attack, and roll angle. Control and state bounds are enforced throughout:

| Variable | Bounds |
|---|---|
| Angle of attack α | ±π/18 rad |
| Roll angle μ | ±π/18 rad |
| Thrust T | 0 – 200 N |
| Airspeed V | 0 – 150 m/s |
| Flight-path angle γ | ±π/6 rad |
| Heading angle χ | ±π/6 rad |

Dynamics are propagated using **RK4** integration within a **Multiple Shooting Method** formulation, which treats the state at each time step as a decision variable and enforces continuity constraints — avoiding the numerical conditioning issues of single shooting over a long horizon.

---

## Part 1: Interceptor State & Parameter Learning (EKF)

The interceptor is modeled as a constant-velocity kinematic projectile with unknown initial position, speed V, pitch angle θ_z, and heading angle θ_x. These 6 unknowns are **augmented into the state vector** and jointly estimated from noisy position measurements using an Extended Kalman Filter.

The augmented state vector is **X** = [x, y, z, V, θ_x, θ_z]ᵀ, propagated via forward Euler. The EKF linearizes the nonlinear propagation and measurement models using Jacobians A_k and H_k at each step.

**Simulation:** Interceptor set to reach the UAV at t = 5s. EKF observes measurements from t = 0 to t = 4s, then switches to **open-loop forecasting** — propagating the learned states forward to predict the threat location at t = 5s.

Estimated at t = 5s: x = 243.71m, y = −34.59m, z = 804.60m, V = 214.03 m/s. Position prediction was accurate; angular estimates (θ_x, θ_z) showed error, attributed to EKF linearization over trigonometric functions — a known limitation addressable with a Particle Filter.

---

## Part 2: Robust Trajectory Optimization

**Deterministic baseline:** The OCP minimizes a weighted cost on state and control deviations from a reference trajectory, subject to a spatial evasion constraint keeping the UAV outside the interceptor's blast radius. The deterministic solution successfully avoids the threat geometrically — but **failed to meet the 0.99 robustness threshold** when evaluated stochastically, since it doesn't account for model and sensor uncertainty.

**Stochastic extension:** Gaussian noise is injected into both states and controls at every time step:

> x_{k+1} = x_k + Δt · f(x_k, u_k) + ε_K

A **Monte Carlo robustness constraint** is added: at each iteration, N particles are propagated from the current optimal solution through the noisy dynamics. The fraction of particles that clear the blast radius must exceed 0.99:

> g_robust(x, u) = (1/N) Σ 1_success(particle_j) ≥ 0.99

The optimization iterates until this constraint is satisfied.

**Result:** g_robust = **0.99** achieved. The robust trajectory diverges visibly from the deterministic one, taking a wider evasive path to ensure safety under uncertainty across 200 Monte Carlo runs.

---

## Tools

Python · NumPy · SciPy · Extended Kalman Filter · Multiple Shooting · RK4 · Monte Carlo


