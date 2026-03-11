---
title: "12-Ply CFRP Laminate — Design, Manufacture & Test"
permalink: /projects/cfrp-laminate/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/ae516_1.png
    image_path: /assets/images/projects/ae516_1.png
    alt: "4-point bend testing"
    title: "4-point bend testing"
  - url: /assets/images/projects/ae516_2.png
    image_path: /assets/images/projects/ae516_2.png
    alt: "4-point bend test specimens"
    title: "Water-jet cut specimens for ASTM D7264 testing"
---

*AE 516 — Composite Structures · University of Michigan · December 2023*

[📄 Full Report](/assets/reports/AE516_Project.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---

{% include gallery %}

## Overview

End-to-end composite laminate project covering algorithmic design using Classical Lamination Theory (CLT), physical manufacture in the Aerospace Materials Laboratory at the University of Michigan, and experimental validation via 4-point bend testing per ASTM D7264.

## Problem Statement

Design a 12-ply IM7-8552 unidirectional prepreg laminate meeting a target flexural modulus of **93 GPa**, optimized for tensile stiffness, tensile strength (Tsai-Hill), and minimum manufacturing material waste.

## Material

**Hexcel IM7-8552 Unidirectional Prepreg**

| Property | Value |
|---|---|
| Longitudinal Modulus (E₁) | 158.5 GPa |
| Transverse Modulus (E₂) | 8.96 GPa |
| Shear Modulus (G₁₂) | 4.69 GPa |
| Poisson's Ratio (ν₁₂) | 0.316 |
| Longitudinal Tensile Strength (S_L) | 2500 MPa |
| Transverse Tensile Strength (S_T) | 64.05 MPa |
| Shear Strength (S_LT) | 91.14 MPa |

## Design Methodology

**Classical Lamination Theory** was used to compute the A, B, D stiffness matrices for all candidate layups. The flexural modulus was derived from the D* matrix, and tensile modulus from the A* matrix.

A **selection algorithm** screened all ply-orientation combinations (−90° to +90°, 15° increments) within a 0.1% tolerance of the 93 GPa target, then ranked by:
1. Tensile strength via progressive Tsai-Hill failure simulation
2. Manufacturing waste (trigonometric model for off-axis cutting loss)

**Final layup:** [90°/0°/0°/0°/30°/0°/0°/30°/0°/0°/0°/90°]

| Property | Predicted |
|---|---|
| Flexural Modulus (E_fx) | 93.34 GPa |
| Tensile Modulus (E_x) | 115.89 GPa |
| Tensile Strength (S_L) | 1667.27 MPa |
| Material Wastage | 38.97 in² |

## Manufacturing

- Plies cut from IM7-8552 prepreg sheet (3" × 6"): 8 × 0°, 2 × 90°, 2 × 30°
- Layup prepared with peel-ply, breather fabric, and vacuum bagging
- **Autoclave cure:** 180°C, 2–3 hours, 3–4 bar external pressure
- Post-cure: diamond-saw trim, water-jet cutting to 5 test specimens (ASTM D7264 geometry, 1:40 thickness-to-span ratio), sanding to remove tabs

## Experimental Results

4-point bend testing per **ASTM D7264 Procedure B** (Span: 81.86 mm, Half-span: 40.93 mm, Rate: 1 mm/min):

| Specimen | E_fx (GPa) |
|---|---|
| 1 | 93.899 |
| 2 | 100.483 |
| 3 | 98.777 |
| 4 | 97.669 |
| 5 | 98.158 |
| **Mean** | **97.797** |

**Error vs. CLT prediction: 4.90%** — within acceptable range for manufacturing and experimental variability.

## Tools

MATLAB · Autoclave · Instron (4-point bend) · Water-Jet · ASTM D7264

