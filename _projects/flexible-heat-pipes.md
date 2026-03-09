---
title: "Flexible Heat Pipes for ISRO Spacecraft"
permalink: /research/flexible-heat-pipes/
layout: single
author_profile: true

gallery:
  - url: /assets/images/research/fhp_design.jpg
    image_path: /assets/images/research/fhp_design.jpg
    alt: "Flexible heat pipe design"
    title: "Ammonia-based flexible heat pipe with axial grooves"
  - url: /assets/images/research/fhp_stress.jpg
    image_path: /assets/images/research/fhp_stress.jpg
    alt: "Groove fin structural simulation"
    title: "Von Mises stress in axial groove fins under ammonia saturation pressure"
---

*Summer Research Intern · Space Applications Centre (SAC), ISRO, Ahmedabad*
*Guided by Dr. S. Suresh, NIT Tiruchirappalli · May 2022 – Jul 2022*

[← Back to Research](/research/){: .btn .btn--inverse}

---

## Overview

Design engineering of ammonia-based flexible heat pipes for spacecraft thermal management, conducted in collaboration with ISRO's Space Applications Centre (SAC), Ahmedabad. Heat pipes are passive, sealed thermal transport devices that move heat from electronics and engines to radiators without any power input — their effective thermal conductivity far exceeds conventional conductors of equivalent size and mass.

The focus was on **axially grooved flexible heat pipes** with ammonia as the working fluid — capable of routing around geometric constraints within spacecraft structures where rigid heat pipes are impractical.

## Objectives

- Design the cross-section and groove geometry of an ammonia-based axial grooved flexible heat pipe for spacecraft use
- Analytically model thermodynamic performance (capillary pressure, pressure drops, maximum heat transport)
- Validate structural integrity of groove fins under internal ammonia saturation pressure

## Methodology

**Thermodynamic modeling:** Capillary pressure and pressure drop analysis using the Young–Laplace equation for the liquid–vapor interface in axial grooves. Groove parameters (width, depth, half-angle) were iterated to maximize capillary pumping relative to viscous pressure drop.

**Working fluid selection:** Ammonia selected for its high latent heat, low viscosity, and suitability for spacecraft operating temperature ranges. Saturation pressure modeled as a function of temperature.

**Structural mechanics:** Lame's equation applied to model the flexible heat pipe envelope (pressure vessel) under internal ammonia saturation pressure:
- Tangential stress: **4.106 MPa**
- Radial stress: **18.88 MPa**
- Von Mises simulation of axial groove fin deformation

**Design outputs:**
- Optimized groove cross-section geometry for target heat transport capacity
- Structural validation of pipe wall and groove fins under operating pressure
- Parametric study of groove geometry effects on maximum heat transport

## Tools

MATLAB · SolidWorks · Analytical thermal/structural modeling

{% include gallery %}
