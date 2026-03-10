---
title: "Ultrasonic Sensor Tester Head"
permalink: /projects/ultrasonic-tester-head/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/tester_head_cad.jpg
    image_path: /assets/images/projects/tester_head_cad.jpg
    alt: "Tester head CAD"
    title: "Open-book tester head — front and isometric views"
  - url: /assets/images/projects/tester_assembly.jpg
    image_path: /assets/images/projects/tester_assembly.jpg
    alt: "Full tester assembly concept"
    title: "Full assembly concept: tester head on optical rail + bearing block system"
---

*Design Intern · Azeriri · Jun – Jul 2021*
*Mentors: Nishal Ramadas, Makesh Janakraj*

[← Back to Projects](/projects/){: .btn .btn--inverse}

---

## Overview

High-throughput testing of piezoelectric ultrasonic sensors requires precise, repeatable face-to-face alignment of two sensor probes for pulse-echo characterisation. Commercial alignment rigs were available but cost-prohibitive for an early-stage startup needing to test hundreds of probes per day. This project designed a custom sensor tester head and assembly system achieving the required degrees of alignment at a fraction of commercial cost.

## Design Requirements

Three degrees of freedom must be controlled to ensure valid back-to-back sensor testing:
- **Translation** — axial spacing between sensor faces
- **Rotation** — angular alignment about the sensor axis
- **Lateral alignment** — coaxiality of the two sensor faces

## Design Approach

**Translation and lateral alignment** were handled using off-the-shelf **optical rails and block bearings** (SBR20 linear rail + SBR16UU bearing blocks). The bearing blocks provide smooth, accurate translation along the rail axis, constraining lateral motion to within machined tolerances.

**Rotation** was handled by integrating rotary stages for optics, sourced off-the-shelf, into the assembly.

**Tester head design:** The probe-holding element was designed from scratch using an "open-book" geometry — two angled faces meeting at a V-shaped centre, such that a cylindrical sensor probe self-locates by gravity and contact into a defined, repeatable seating position. The base of the head is profiled to mount directly onto the bearing block.

**Detail features:**
- Two central slots for cable tie-down, keeping sensor cable slack from disturbing the probe seating during test cycles
- Top slot for optional rubber belt retention, ensuring the probe remains seated during rapid back-to-back test changeovers

## Tools

Fusion 360 · GD&T · Off-the-shelf component integration (optical rails, bearing blocks, rotary stages)

{% include gallery %}
