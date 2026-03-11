---
title: "Tsai-Wu Failure Model for Composite Aerostructural Optimization"
permalink: /research/research-tsai-wu/
layout: single
author_profile: true

gallery:
  - url: /assets/images/research/oas_wingbox.jpg
    image_path: /assets/images/research/oas_wingbox.jpg
    alt: "OpenAeroStruct wingbox"
    title: "OpenAeroStruct wingbox layout with VLM mesh (Chauhan & Martins, 2018)"
  - url: /assets/images/research/oas_results.jpg
    image_path: /assets/images/research/oas_results.jpg
    alt: "Optimized thickness distribution"
    title: "Optimized skin/spar thickness distribution — Benchmark Case 2"
---

*Independent Research · MDO Lab, University of Michigan*
*Advisor: Prof. Joaquim R.R.A. Martins · Jan 2024 – May 2024*

[📄 Full Report](/assets/reports/Mehta_AE590_Report.pdf){: .btn .btn--primary}
[← Back to Research](/research/){: .btn .btn--inverse}

---

## Overview

Development of a Tsai-Wu based composite failure criterion integrated into [OpenAeroStruct](https://github.com/mdolab/OpenAeroStruct) — the MDO Lab's open-source low-fidelity aerostructural optimization framework. OpenAeroStruct couples a Vortex Lattice Method (VLM) aerodynamic solver with a spatial beam FEM for structural analysis. Its existing failure model used von Mises stress — an isotropic criterion that is physically incorrect for fiber-reinforced composites, which exhibit strongly direction-dependent failure behavior.

## Motivation

With composites increasingly dominant in aerospace primary structures, an accurate, differentiable failure constraint was essential for composite aerostructural MDO. TACS (Toolkit for the Analysis of Composite Structures) provides high-fidelity composite FEA, but its computational cost precludes use in early-stage design optimization. The goal was to bring physically correct composite failure prediction into OpenAeroStruct's low-fidelity loop.

## Composite Wingbox Model

The wingbox skin and spar panels were modeled as CFRP composites with quasi-isotropic layups:

| Element | Orientations | Ply Fractions |
|---|---|---|
| Skin | [0°/90°/45°/−45°] | 44.4% / 22.2% / 22.2% / 11.2% |
| Spar | [0°/90°/45°/−45°] | 10% / 35% / 35% / 20% |

**Material (CFRP ply properties):**

| Property | Value |
|---|---|
| E₁₁ | 117.7 GPa |
| E₂₂ | 9.7 GPa |
| G₁₂ | 4.8 GPa |
| T₁ (tensile) | 1648 MPa |
| C₁ (compressive) | 1034 MPa |
| T₂ | 64 MPa · C₂: 228 MPa |
| S₁₂ | 71 MPa |

## Implementation

**Stress computation:** Ply-level stresses derived from beam element strains at 4 critical stress points per wingbox element using CLT transformation matrices [T] and [Q̄].

**Tsai-Wu Strength Ratio (SR):**

SR = ½(a + √(a² + 4b)) where a = F₁σ₁ + F₂σ₂ and b = F₁₁σ₁² + F₂₂σ₂² + F₆₆τ₁₂²

**Factor of Safety:** Incorporated via SR ≤ 1/FOS, scaling the failure envelope without distorting its anisotropic geometry.

**KS aggregation:** 16 SR values per element (4 plies × 4 critical points) aggregated using the Kreisselmeier–Steinhauser function for smooth, differentiable constraint enforcement in gradient-based optimization.

**Gradient framework:** Analytic partial derivatives exposed to OpenMDAO's adjoint-based gradient computation, enabling efficient MDO with composite failure constraints.

## Benchmark Validation

Validated against the Gray & Martins (2024) aeroelastic optimization benchmark (Boeing 717 wing configuration):

| Case | Objective | This Work | Reference (high-fidelity) |
|---|---|---|---|
| Case I | Minimize wingbox mass | 558.7 kg | 706 kg |
| Case II | Minimize fuel burn | **8346.9 kg** | **8311 kg** ✓ |

Case II fuel burn matches the high-fidelity benchmark to within **0.4%**, validating the composite aerostructural model for low-fidelity MDO. The Case I underprediction is attributed to the isotropic approximation of elastic moduli — identified as future work.

## Tools

Python · OpenAeroStruct · OpenMDAO · TACS · NumPy

{% include gallery %}
