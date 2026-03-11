---
title: "Aerodynamic Design: Shahed-238 Successor Drone"
permalink: /projects/shahed-successor/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ae740_1.png
    image_path: /assets/images/projects/ae740_1.png
    alt: "Initial and optimized airfoil coordinates"
    title: "Multipoint airfoil optimization — initial NACA0012 vs. optimized section"
  - url: /assets/images/projects/ae740_2.png
    image_path: /assets/images/projects/ae740_2.png
    alt: "Optimized planform shape — Case 2"
    title: "Optimal planform shape for Case 2 (twist + taper + root chord, multipoint)"
---

*AEROSP 740 — Aerodynamic Design · University of Michigan · May 2024* <br>
*Advisor: Prof. J.R.R.A. Martins*

[📄 Full Report](/assets/reports/Mehta_AE740_FinalProject.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---
{% include gallery %}

## Overview

Full aerodynamic design of a successor to the **Shahed-238 kamikaze drone**, targeting higher speeds across all flight phases and reduced overall drag to maximize range. The design process was split into two stages: multipoint **airfoil optimization** using MACH-Aero, followed by **planform optimization** using OpenAeroStruct.

---

## Baseline: Shahed-238

| Specification | Value |
|---|---|
| Range | 200 km |
| Cruise Altitude | 9,000 m |
| Length | 3.5 m |
| Span | 2.5 m |
| Cruise Speed | 550 km/h (M = 0.5) |
| MTOW | 250 kg |

---

## Target Specifications (Successor)

| Specification | Value |
|---|---|
| Range | 400 km |
| Cruise Altitude | 9,000 m |
| Length | 3.5 m |
| Span | 2.5 m |
| Cruise Speed | 650 km/h (M = 0.6) |
| MTOW | 350 kg |

---

## Flight Point Definition

Three flight conditions were defined using the Breguet range equation to establish final and mid-cruise weights, with C_L requirements back-calculated via the lift equation at each phase:

| Parameter | Cruise | Takeoff | Terminal |
|---|---|---|---|
| Altitude | 9,000 m | 100 m | 100 m |
| Mach | 0.6 | 0.3 | 0.55 |
| Velocity | 182.3 m/s | 102.0 m/s | 186.9 m/s |
| Density | 0.47 kg/m³ | 1.21 kg/m³ | 1.21 kg/m³ |
| Mass | 285 kg | 350 kg | 225 kg |
| Required C_L | 0.08 | 0.12 | 0.02 |

---

## Stage 1: Multipoint Airfoil Optimization (MACH-Aero)

The airfoil was optimized to minimize combined drag across all three flight conditions simultaneously, subject to lift constraints at each point. Starting from a **NACA0012**:

**Minimize:** C_d(cruise) + C_d(takeoff) + C_d(terminal)

**Subject to:** C_l = 0.08 (cruise), 0.12 (takeoff), 0.02 (terminal); section area ≥ 50% initial; t/c ≥ 10%

The optimizer converged in ~30 iterations, achieving a **19.1% reduction in combined drag**. The optimized section is considerably thinner than the NACA0012. At each flight condition, the pressure distribution shows the optimizer driving toward the minimum lift consistent with each constraint — reducing the upper/lower surface pressure differential to exactly what the C_L requirement demands.

---

## Stage 2: Planform Optimization (OpenAeroStruct)

Starting from an initial planform matching Shahed-238 geometry (span 2.5 m, root chord 3.5 m, tip chord 0.25 m, sweep 26°), three cases were run with progressively more design freedom:

| Case | Design Variables | Flight Points | Combined C_D | Cruise C_D |
|---|---|---|---|---|
| I | Twist | Multipoint | 0.069 | 0.02188 |
| II | Twist + Taper + Root chord | Multipoint | 0.067 | 0.02185 |
| III | Twist + Taper + Root chord + Span + Sweep | Single-point (cruise) | — | 0.0228 |

**Case II produced the best overall result**, minimizing both multipoint combined drag and cruise drag. Optimal taper ratio: **0.159**. Case III (full design freedom, cruise-only) converged to taper 0.30, sweep 30°, span 2 m — but at higher combined drag than Case II, making it unsuitable as the final design.

---

## Tools

MACH-Aero · OpenAeroStruct · Python

