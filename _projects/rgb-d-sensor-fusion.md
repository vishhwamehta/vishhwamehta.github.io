---
title: "RGB-D Sensor Fusion Fixture"
permalink: /projects/rgb-d-sensor-fusion/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/fixture-cs.jpg
    image_path: /assets/images/projects/fixture-cs.jpg
    alt: "RGB-D fixture CAD cross-section"
    title: "Fusion360 cross-section showing sensor mounting cavities and kinematic features"
  - url: /assets/images/projects/fixture-assembled.jpg
    image_path: /assets/images/projects/fixture-assembled.jpg
    alt: "Fabricated RGB-D fixture prototype"
    title: "FDM-printed housing with RGB camera and depth sensor installed"
---

*Lead Design Engineer / CTO · NextGen Diastasi LLP · 2026*

[← Back to Projects](/projects/){: .btn .btn--inverse}

---

{% include gallery %}

## Overview

Cost-effective RGB-D sensor fixture for robotic perception applications, developed for an aerospace startup client. The goal was to achieve 70–80% of commercial RGB-D sensor performance at less than 40% of the cost by integrating a low-cost RGB camera module with an off-the-shelf depth sensor in a precision-designed housing.

**Outcome:** ±8mm depth accuracy at 1m range with <2 pixel RGB-D alignment error.

## Design Requirements

- Maintain ±0.5° angular tolerance and ±0.3mm positional tolerance between RGB and depth sensor optical axes
- Working range: 0.5–3m
- Modular — allow sensor swaps without realignment
- Manufacturable via FDM with post-processing; cost target <40% of commercial equivalent

## Design Process

**Sensor selection:** RGB camera module and ToF/structured light depth sensor selected and characterised for the 0.5–3m working range, balancing FOV, resolution, and interfacing requirements.

**Fixture design:** Rigid two-cavity housing designed in Fusion 360, with independent mounting pockets for the RGB and depth sensors. Kinematic features (three-point contact and datum surfaces) ensure repeatable sensor seating and maintain the optical axis relationship across assembly and disassembly cycles.

**Tolerancing:** ±0.5° angular and ±0.3mm positional tolerances specified and enforced through precision-machined mounting interfaces post-FDM print. Critical mating surfaces cleaned up by filing and light sanding to bring within tolerance.

**Cable management:** Integrated routing channels and cable tie-off points designed into the housing interior to prevent cable-induced sensor displacement.

**Fabrication:** FDM printed in PETG. Mounting interfaces post-processed to achieve required tolerances. Kinematic features validated against tolerance stack-up analysis before assembly.

**Validation:** Depth accuracy and RGB-D pixel alignment measured at 0.5m, 1m, and 2m standoff distances against a calibration checkerboard. Final performance: ±8mm depth accuracy at 1m, <2 pixel RGB-D alignment error.

## Tools

Fusion 360 · FDM (PETG) · Tolerance stack-up analysis · OpenCV (calibration)
