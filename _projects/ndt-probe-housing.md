---
title: "NDT Ultrasonic Probe Housing — Coil UT & Plate UT"
permalink: /projects/ndt-probe-housing/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ndt_coil_cad.png
    image_path: /assets/images/projects/ndt_coil_cad.png
    alt: "Coil UT probe housing CAD"
    title: "Coil UT probe — housing and backing material slab with T-R piezo alignment"
  - url: /assets/images/projects/ndt_plate_cad.png
    image_path: /assets/images/projects/ndt_plate_cad.png
    alt: "Plate UT probe housing CAD"
    title: "Plate UT probe — housing and angled backing slab for 12mm depth detection"
---

*Design Intern · Azeriri · Jun – Jul 2021* <br>
*Mentors: Nishal Ramadas, Makesh Janakraj*

[← Back to Projects](/projects/){: .btn .btn--inverse}

---
{% include gallery %}
## Overview

3D CAD design of housing and internal components for two non-destructive testing (NDT) ultrasonic probe variants: a **Coil UT probe** for detecting defects at 8mm depth in stainless steel, and a **Plate UT probe** for detecting defects at 12mm depth. Both probes use a Transmitter-Receiver (T-R) piezo configuration, requiring precise angular alignment of the ceramic elements to focus the ultrasonic beam at the target inspection depth via Snell's Law refraction geometry.

## T-R Alignment Calculation

The critical design parameter in both probes is the angle between the T-R ceramic piezo faces — set to direct the transmitted and received ultrasonic beams to converge at the target inspection depth. This was calculated from first principles:

Using **Snell's Law** at the coupling medium / stainless steel interface and the probe geometry (piezo height h, target depth, material acoustic velocities), a Python script was written to solve for the required T-R angle given user inputs of h and target angle.

- **Coil UT:** h = 6.035mm, angle = 15° → T-R offset = **12.84mm**
- **Plate UT:** h = 5.521mm, angle = 10° → T-R offset = **11.56mm**

These offsets were directly dimensioned into the backing material slab geometry in CAD.

## Coil UT Probe (8mm depth)

Housing dimensions referenced from an existing commercial product. The internal backing material slab positions the two ceramic piezos at the computed angular offset, with dedicated wiring channels for cable routing. The housing exterior features a flanged base for mounting and four bolt holes for assembly clamping.

## Plate UT Probe (12mm depth)

Similar architecture to the Coil UT probe but with a larger housing form factor appropriate for plate inspection geometry. The backing slab geometry reflects the shallower T-R angle (10° vs 15°) required for the 12mm depth target with the given piezo height.

## Tools

Fusion 360 · Python (Snell's Law T-R alignment calculator) · GD&T

