---
title: "Mathematical Modeling of Bent Ammonia–Aluminum Axial Grooved Heat Pipes"
permalink: /research/bent-aghp-publication/
layout: single
author_profile: true

gallery:
  - url: /assets/images/research/aghp_model.jpg
    image_path: /assets/images/research/aghp_model.jpg
    alt: "AGHP mathematical model"
    title: "Capillary pressure and pressure drop model for bent AGHP"
  - url: /assets/images/research/aghp_grooves.jpg
    image_path: /assets/images/research/aghp_grooves.jpg
    alt: "Axial groove geometry"
    title: "Axial groove geometry and liquid-vapor interface meniscus"
---

*Peer-Reviewed Publication · NIT Tiruchirappalli & ISRO Space Applications Centre*
*Authors: **Vishwa Mehta**, V.K. Singh (ISRO SAC), S. Suresh (NIT Trichy)*

[📄 View Publication](/assets/reports/FMR_Mehta_2025.pdf){: .btn .btn--primary}
[← Back to Research](/research/){: .btn .btn--inverse}

---

## Citation

> Mehta, V., Singh, V.K., & Suresh, S. (2025). Mathematical Modeling of Bent Ammonia–Aluminum Axial Grooved Heat Pipes for Spacecraft Applications. *International Journal of Fluid Mechanics Research*, 52(4), 93–116.

---

## Overview

Development and validation of a mathematical model for predicting the heat transfer characteristics of **aluminum–ammonia axial grooved heat pipes (AGHPs) with bends**. Bends are geometrically necessary in spacecraft heat pipe routing but introduce performance penalties through additional flow resistance and disruption of the liquid–vapor interface. Prior models did not fully account for the coupled effects of bend geometry on capillary-driven flow.

## Motivation

In spacecraft thermal management, heat pipes must route between components in constrained geometries, requiring bends of varying angle. A bend in an AGHP introduces:
- Additional viscous pressure drop in the liquid return path
- Redistribution of the liquid–vapor interface radius of curvature
- Modified interfacial shear stress between liquid and vapor phases

Without accurate modeling of these effects, heat pipe performance in spacecraft is over-predicted, leading to under-sized thermal management systems.

## Model Description

The model is built around the capillary pressure balance driving liquid flow through the axial grooves:

**ΔP_cap ≥ ΔP_liquid + ΔP_vapor + ΔP_gravity**

Key modeling contributions:

- **Liquid–vapor interfacial shear stress** — incorporated via the χ (interfacial shear stress factor), modifying the effective Poiseuille number for liquid flow in grooves
- **Axial variation of interface radius** — the meniscus radius is tracked axially using a differential-integral-algebraic model based on the Young–Laplace equation
- **Bend pressure drop** — additional pressure loss at bend locations modeled as a function of bend angle β and hydraulic diameter
- **Flow regime transitions** — laminar (f·Re = 64/Re) and turbulent (f = 0.316/Re^0.25) liquid flow regimes handled
- **Governing assumptions:** steady-state, fully saturated grooves, incompressible unidirectional flow, negligible bend effect on groove/vapor core dimensions

## Validation

Model predictions validated against experimental data for straight and bent aluminum–ammonia AGHP configurations. Results demonstrate accurate prediction of maximum heat transport capacity as a function of bend angle, filling fraction, and operating temperature.

## Journal

*International Journal of Fluid Mechanics Research* · Vol. 52, Issue 4, pp. 93–116 · 2025
Published by Begell House

{% include gallery %}
