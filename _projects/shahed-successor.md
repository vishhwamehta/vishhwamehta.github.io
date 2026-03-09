---
title: "Aerodynamic Design: Shahed-238 Successor Drone"
permalink: /projects/shahed-successor/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ae740_1.jpg
    image_path: /assets/images/projects/ae740_1.jpg
    alt: "Shahed-238 successor aerodynamic design"
    title: "Final aerodynamic configuration"
  - url: /assets/images/projects/ae740_2.jpg
    image_path: /assets/images/projects/ae740_2.jpg
    alt: "AVL aerodynamic analysis"
    title: "AVL vortex lattice analysis — lift distribution"
---

*AEROSP 740 — Aerodynamic Design · University of Michigan · May 2024*
*Advisor: Prof. Joaquim R.R.A. Martins*

[📄 Full Report](/assets/reports/Mehta_AE740_FinalProject.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---

## Overview

Full aerodynamic design of a successor aircraft to the **Shahed-238 kamikaze drone**, targeting significantly higher cruise speeds, reduced drag, and extended operational range over the baseline configuration.

## Baseline: Shahed-238

| Specification | Value |
|---|---|
| Range | 200 km |
| Cruise Altitude | 9,000 m |
| Length | 3.5 m |
| Wingspan | 2.5 m |
| Propulsion | Jet (upgraded from Shahed-136) |

The Shahed-238 introduced jet propulsion and advanced guidance (IR/optical/radar) over the baseline Shahed-136 design. The objective of this project was to supersede its aerodynamic performance — specifically maximizing L/D, reducing cruise drag, and extending range.

## Design Approach

Starting from the known Shahed-238 geometry and performance envelope, an iterative aerodynamic design process was conducted:

1. **Baseline aerodynamic characterization** — AVL vortex lattice model of the Shahed-238 configuration to establish drag polar and lift distribution
2. **Wing redesign** — Planform, taper ratio, and sweep optimized for high-altitude cruise efficiency
3. **Tail configuration** — Evaluated conventional vs. V-tail for drag reduction and stability trade-offs
4. **Fuselage shaping** — Cross-section refinement to reduce pressure drag
5. **Drag breakdown** — Induced, profile, and wave drag components quantified via AVL + XFOIL

## Key Outcomes

- Measurable L/D improvement over baseline Shahed-238 configuration
- Extended range estimate from drag reduction
- AVL-validated lift distribution and stability derivatives for the final configuration

## Tools

AVL (Athena Vortex Lattice) · XFOIL · MATLAB

{% include gallery %}
