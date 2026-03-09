---
title: "Anti-Interception Robust Trajectory Optimization for UAVs"
permalink: /projects/uav-trajectory-optimization/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ae567_1.jpg
    image_path: /assets/images/projects/ae567_1.jpg
    alt: "Robust UAV trajectory"
    title: "Robust anti-interception trajectory under wind uncertainty"
  - url: /assets/images/projects/ae567_2.jpg
    image_path: /assets/images/projects/ae567_2.jpg
    alt: "3-DOF dynamics model"
    title: "3-DOF UAV dynamics and interception geometry"
---

*AEROSP 567 — Estimation and Statistical Inference · University of Michigan*

[📄 Full Report](/assets/reports/Mehta_AE567_FinalProject.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---

## Overview

Developed a **robust trajectory optimization framework** for unmanned aerial vehicles operating in contested airspace, where both environmental disturbances (wind) and active interception threats create uncertainty in mission planning. The framework generates trajectories that are dynamically feasible, fuel-efficient, and probabilistically robust against interception.

## Problem Statement

UAV trajectory generation in adversarial environments must contend with:
- **Wind uncertainty** — stochastic disturbances affecting flight path
- **Threat location uncertainty** — imperfect knowledge of interceptor positions and engagement envelopes
- **Dynamic feasibility** — trajectories must respect the UAV's equations of motion

Classical deterministic trajectory optimization fails in these settings, as point-estimate solutions are fragile to uncertainty realizations.

## Methodology

**Aircraft dynamics:** 3-DOF point-mass model with aerodynamic force and moment equations, capturing coupled longitudinal and lateral dynamics.

**Uncertainty modeling:**
- Wind treated as a stochastic process with known statistics (mean, covariance)
- Threat locations modeled as probability distributions updated via statistical inference as new observations arrive
- Kalman-filter-based state estimation for threat tracking

**Robust optimization:**
- Trajectory parameterized as a sequence of waypoints with associated timing
- Chance constraints formulated to bound the probability of interception below a threshold
- SLSQP optimizer minimizes fuel/time objective subject to dynamic and chance constraints

**Inference integration:** Bayesian updates to threat location beliefs as the UAV collects new observational data mid-flight, enabling online replanning.

## Key Outcomes

- Robust trajectories with probabilistic interception avoidance guarantees
- Demonstrated robustness to wind and threat uncertainty realizations vs. deterministic baseline
- Online replanning capability via sequential Bayesian inference

## Tools

MATLAB · Python · 3-DOF Dynamics · Kalman Filter · SLSQP · Bayesian Inference

{% include gallery %}
