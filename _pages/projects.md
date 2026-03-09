---
title: "Projects"
permalink: /projects/
layout: single
author_profile: true

gallery_ae590:
  - url: /assets/images/projects/ae590_1.jpg
    image_path: /assets/images/projects/ae590_1.jpg
    alt: "OpenAeroStruct aerostructural optimization"
    title: "Aerostructural optimization with Tsai-Wu failure constraint"
  - url: /assets/images/projects/ae590_2.jpg
    image_path: /assets/images/projects/ae590_2.jpg
    alt: "Tsai-Wu failure envelope"
    title: "Tsai-Wu composite failure envelope vs. von Mises"

gallery_ae588:
  - url: /assets/images/projects/ae588_1.jpg
    image_path: /assets/images/projects/ae588_1.jpg
    alt: "Propeller twist distribution"
    title: "Optimized twist distribution across blade span"
  - url: /assets/images/projects/ae588_2.jpg
    image_path: /assets/images/projects/ae588_2.jpg
    alt: "Efficiency vs SPL trade-off"
    title: "Pareto front: efficiency vs. acoustic signature"

gallery_ae740:
  - url: /assets/images/projects/ae740_1.jpg
    image_path: /assets/images/projects/ae740_1.jpg
    alt: "Shahed-238 successor aerodynamic design"
    title: "Final aerodynamic configuration"
  - url: /assets/images/projects/ae740_2.jpg
    image_path: /assets/images/projects/ae740_2.jpg
    alt: "AVL aerodynamic analysis"
    title: "AVL vortex lattice analysis results"

gallery_ae567:
  - url: /assets/images/projects/ae567_1.jpg
    image_path: /assets/images/projects/ae567_1.jpg
    alt: "UAV trajectory optimization"
    title: "Robust trajectory under threat uncertainty"
  - url: /assets/images/projects/ae567_2.jpg
    image_path: /assets/images/projects/ae567_2.jpg
    alt: "3-DOF UAV dynamics model"
    title: "3-DOF dynamics model and interception geometry"

gallery_ae516:
  - url: /assets/images/projects/ae516_1.jpg
    image_path: /assets/images/projects/ae516_1.jpg
    alt: "Manufactured CFRP laminate"
    title: "Autoclave-cured IM7-8552 laminate"
  - url: /assets/images/projects/ae516_2.jpg
    image_path: /assets/images/projects/ae516_2.jpg
    alt: "4-point bend test specimens"
    title: "Water-jet cut specimens for ASTM D7264 testing"

gallery_ae481:
  - url: /assets/images/projects/ae481_1.jpg
    image_path: /assets/images/projects/ae481_1.jpg
    alt: "C-5/C-17 successor three-view drawing"
    title: "Dimensioned three-view drawing — Lifting Large Design Co."
  - url: /assets/images/projects/ae481_2.jpg
    image_path: /assets/images/projects/ae481_2.jpg
    alt: "Cargo bay interior layout"
    title: "Cargo bay loading configurations and interior layout"

gallery_rob530:
  - url: /assets/images/projects/rob530_1.jpg
    image_path: /assets/images/projects/rob530_1.jpg
    alt: "ORB-SLAM3 occupancy map in low light"
    title: "2D occupancy map generated via enhanced ORB-SLAM3"
  - url: /assets/images/projects/rob530_2.jpg
    image_path: /assets/images/projects/rob530_2.jpg
    alt: "LLM path planning framework"
    title: "Hybrid LLM + SLAM navigation architecture"
---

A collection of academic research and engineering projects spanning composite aerostructures, aerodynamic optimization, robotics, and autonomous systems.

---

## Tsai-Wu Failure Model for OpenAeroStruct
*AEROSP 590 — Independent Research · University of Michigan · May 2024*
*Advisor: Prof. Joaquim R.R.A. Martins*

Developed a custom Tsai-Wu composite failure criterion integrated directly into [OpenAeroStruct](https://github.com/mdolab/OpenAeroStruct), extending its FEM layer to support anisotropic failure prediction. Existing failure modeling relied on von Mises stress — insufficient for composites. This work enabled gradient-based MDO with composite structural constraints, validated against TACS high-fidelity FEA results.

**Tools:** Python · OpenAeroStruct · OpenMDAO · TACS

[📄 View Full Report](/assets/reports/Mehta_AE590_Report.pdf){: .btn .btn--primary}

{% include gallery id="gallery_ae590" %}

---

## Stealth UAV Propeller Blade Optimization
*AEROSP 588 — Multidisciplinary Design Optimization · University of Michigan · Dec 2023*

Multidisciplinary optimization of propeller blade twist for a fixed-wing military UAV, simultaneously maximizing propulsive efficiency and minimizing acoustic signature across three mission phases (takeoff, cruise, dash). SLSQP-based multi-objective optimizer with blade element momentum theory.

**Result:** η = 0.885 · SPL = 33.7 dB

**Tools:** Python · SLSQP · XFOIL · Blade Element Momentum Theory

[📄 View Full Report](/assets/reports/AEROSP588_Project.pdf){: .btn .btn--primary}

{% include gallery id="gallery_ae588" %}

---

## Aerodynamic Design: Shahed-238 Successor Drone
*AEROSP 740 — Aerodynamic Design · University of Michigan · May 2024*
*Advisor: Prof. Joaquim R.R.A. Martins*

Aerodynamic design of a successor to the Shahed-238 kamikaze drone (200 km range, 9000 m cruise altitude), targeting higher cruise speeds, reduced drag, and extended range. Wing geometry, tail configuration, and fuselage shaping iterated via AVL vortex lattice analysis to maximize L/D across the design flight envelope.

**Tools:** AVL · XFOIL · MATLAB

[📄 View Full Report](/assets/reports/Mehta_AE740_FinalProject.pdf){: .btn .btn--primary}

{% include gallery id="gallery_ae740" %}

---

## Anti-Interception Robust Trajectory Optimization for UAVs
*AEROSP 567 — Estimation and Statistical Inference · University of Michigan*

Robust trajectory optimization framework for UAVs operating in contested airspace with interception threats and environmental uncertainties. Aircraft dynamics modeled via 3-DOF equations; statistical inference handles wind uncertainty and threat location estimation. Generates dynamically feasible, interception-robust trajectories combining optimal control with probabilistic threat modeling.

**Tools:** MATLAB · Python · 3-DOF Dynamics

[📄 View Full Report](/assets/reports/Mehta_AE567_FinalProject.pdf){: .btn .btn--primary}

{% include gallery id="gallery_ae567" %}

---

## 12-Ply CFRP Laminate — Design, Manufacture & Test
*AE 516 — Composite Structures · University of Michigan · Dec 2023*

End-to-end composite laminate project: algorithmic CLT-based design, physical autoclave manufacture, and ASTM D7264 experimental validation. Selection algorithm ranked valid 12-ply IM7-8552 layups by Tsai-Hill tensile strength and manufacturing waste. Final layup [90°/0°/0°/0°/30°/0°/0°/30°/0°/0°/0°/90°] autoclave-cured at 180°C. Experimental E_fx = **97.8 GPa** vs. predicted 93.3 GPa (4.9% error).

**Tools:** MATLAB · Autoclave · Instron (4-pt bend) · Water-Jet · ASTM D7264

[📄 View Full Report](/assets/reports/AE516_Project.pdf){: .btn .btn--primary}

{% include gallery id="gallery_ae516" %}

---

## C-5 / C-17 Successor Heavy-Lift Aircraft — CDR
*AE 481 — Aircraft Design · University of Michigan · Dec 2023*
*Team: Lifting Large Design Co. (Aayush Agarwal, Rawan Aljaber, Andrew Chen, Ian Johnson, Vishwa Mehta)*

Conceptual design of a next-generation strategic airlifter to replace the USAF C-5 and C-17 fleet, per a DoD brief with EIS 2033. Requirements: 430,000 lb payload at 2,500 nmi; 295,000 lb at 5,000 nmi; 8,000 nmi ferry; ICAO Class F. Contributions: interior layout, cargo bay loading configurations, cargo ramp design, and structural sizing.

**Tools:** SolidWorks · AVL · MATLAB · FLOPS

[📄 View Full Report](/assets/reports/AE481_CDR_Report.pdf){: .btn .btn--primary}

{% include gallery id="gallery_ae481" %}

---

## LLM-Based Path Planning in Low-Light Conditions
*ROB 530 — Mobile Robotics · University of Michigan*
*Team: Kaushek Kumar T R · Sanjana Raghavan · Vishwa Mehta*

Hybrid autonomous navigation framework for a differential-drive robot in low-light indoor environments. A custom GAN-based image enhancement pipeline preprocesses camera feeds for ORB-SLAM3 feature detection, yielding robust 2D occupancy maps. An LLM-based semantic planner interprets high-level navigation instructions and resolves ambiguous waypoints. Dynamic obstacles tracked via a semantic extraction node enable real-time replanning.

**Tools:** ROS2 · ORB-SLAM3 · PyTorch (EnlightenGAN) · LLM API · 2D LiDAR · IMU · Depth + Stereo Cameras

[📄 View Full Report](/assets/reports/ROB530_Project_Report.pdf){: .btn .btn--primary}

{% include gallery id="gallery_rob530" %}
