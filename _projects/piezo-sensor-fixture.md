---
title: "Piezoelectric Sensor Assembly Fixture"
permalink: /projects/piezo-sensor-fixture/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/piezo_mk1.png
    image_path: /assets/images/projects/piezo_mk1.png
    alt: "Mark 1 fixture tray"
    title: "Mark 1 — 6×6 fixture tray with concentric O-ring seats and retainer plate"
  - url: /assets/images/projects/piezo_mk2.png
    image_path: /assets/images/projects/piezo_mk2.png
    alt: "Mark 2 fixture with inserts"
    title: "Mark 2 — universal tray with interchangeable inserts and tolerance rings for mixed-diameter sensors"
---

*Design Intern · Azeriri · Jun – Jul 2021* <br>
*Mentors: Nishal Ramadas, Makesh Janakraj*

[← Back to Projects](/projects/){: .btn .btn--inverse}

---

{% include gallery %}

## Overview

Piezoelectric ultrasonic sensors are three-part assemblies — a ceramic (piezo) transducer, a polymer relay piece, and a polymeric adhesive — requiring precise coaxial alignment during cure. Manual assembly is slow, inconsistent, and error-prone at production volumes. This project designed a batch assembly fixture capable of aligning and holding dozens of sensors simultaneously through the adhesive cure cycle, at a fraction of the cost of commercial alternatives.

## Mark 1

**Concept:** A two-plate system — a lower tray holding the ceramic piezo elements and an upper tray holding the polymer pieces — that are brought together to mate and compress the assemblies in batch. Scaled to a 6×6 array.

**Key design challenges and solutions:**

- *Axial misalignment from part-to-part manufacturing variation:* Solved by specifying O-rings in each seat, using their compliance to self-centre components with minor diameter variation while maintaining coaxiality during cure.
- *Component drop-out when inverting the upper tray:* Solved by adding a Retainer Plate — a cover plate with appropriately sized through-holes that retains components in their seats during inversion and mating.
- *Handling fragility during cure transit:* Solved by adding flathead and standard screws to clamp the two plates together as a single rigid body, safe to move without disturbing the adhesive bond during cure.

## Mark 2

**Problem:** A fixed-dimension tray is inflexible for a startup producing sensors of varying diameters (8mm, 10mm, 20mm). High wear and tear of the trays during assembly and maintenance and tray replacement per size being cost-prohibitive at early stage. 

**Solution:** Universal tray with **interchangeable inserts** — cylindrical sleeves with fixed OD (matching tray bore) and varying ID (matching sensor diameter). The same tray body serves all sensor sizes; only the inserts are swapped.

- Inserts are easily removable for cleaning, wear-replaceable in bulk at low cost
- Tolerance rings added to ensure coaxial seating of inserts within the tray bore despite insert manufacturing variation
- O-rings, retainer plate, and flathead screws carried forward from Mark 1

Mark 2 was designed as a 6×6 tray with 2 rows per sensor diameter (8mm / 10mm / 20mm) to validate the insert concept across all three sizes simultaneously.

## Tools

Fusion 360 · GD&T · Design for Manufacture


