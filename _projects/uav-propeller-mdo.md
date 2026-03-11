---
title: "Stealth UAV Propeller Blade Optimization"
permalink: /projects/uav-propeller-mdo/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ae588_1.png
    image_path: /assets/images/projects/ae588_1.png
    alt: "Optimum Twist Distribution along the blade during different mission phases"
    title: "Optimum Twist Distribution along the blade during different mission phases"
  - url: /assets/images/projects/ae588_2.png
    image_path: /assets/images/projects/ae588_2.png
    alt: "Optimum Twist Distribution along the blade for different constraint values of the Thrust Coefficient"
    title: "Optimum Twist Distribution along the blade for different constraint values of the Thrust Coefficient"
---

*AEROSP 588 — Multidisciplinary Design Optimization · University of Michigan · December 2023*
*Team: Naman Makkar, Vishwa Mehta*

[📄 Full Report](/assets/reports/AEROSP588_Project.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---

## Overview

Multidisciplinary optimization of the **twist distribution** across the span of a propeller blade for a fixed-wing military UAV (single rear-mounted pusher propeller). The optimization simultaneously maximized propulsive efficiency (η) and minimized radiated noise (SPL) to enable long-range stealth missions.

## Problem Statement

A fixed-wing military UAV operates across three distinct mission phases — takeoff, cruise, and dash — each with different thrust and speed requirements. The propeller must perform efficiently across all phases while keeping acoustic signature below detection thresholds. These objectives are in direct conflict: high efficiency typically requires higher tip speeds, which increase noise.

## Methodology

**Aerodynamic modeling:** Blade Element Momentum (BEM) theory, coupled with XFOIL-generated airfoil polars, to compute thrust, torque, and efficiency at each spanwise station.

**Acoustic modeling:** Ffowcs Williams–Hawkings (FW-H) based SPL estimation from blade loading and thickness noise sources.

**Optimizer:** SLSQP (Sequential Least Squares Quadratic Programming) with:
- Design variables: twist angle at each spanwise control point
- Objectives: maximize η, minimize SPL
- Constraints: minimum thrust per mission phase, structural twist limits

**Multi-phase formulation:** Weighted composite objective across takeoff, cruise, and dash conditions — preventing over-optimization for a single phase.

## Results

| Metric | Value |
|---|---|
| Propulsive Efficiency (η) | **0.885** |
| Sound Pressure Level (SPL) | **33.7 dB** |
| Mission phases covered | Takeoff · Cruise · Dash |

Both efficiency and acoustic targets satisfied simultaneously.

## Tools

Python · SLSQP · XFOIL · Blade Element Momentum Theory · FW-H Acoustics

{% include gallery %}
