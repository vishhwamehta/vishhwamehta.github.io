---
title: "Tsai-Wu Failure Model for OpenAeroStruct"
permalink: /projects/tsai-wu-openaerostruct/
layout: single
author_profile: true

gallery:
  - url: /assets/images/research/oas_wingbox.png
    image_path: /assets/images/research/oas_wingbox.png
    alt: "OpenAeroStruct wingbox"
    title: "OpenAeroStruct wingbox layout with VLM mesh (Chauhan & Martins, 2018)"
  - url: /assets/images/research/composite_elements.png
    image_path: /assets/images/research/composite_elements.png
    alt: "Stresses on the Composite Laminate at critical points on the wingbox"
    title: "Stresses on the Composite Laminate at critical points on the wingbox"
---

*AEROSP 590 — Independent Research · University of Michigan · May 2024*
*Advisor: Prof. Joaquim R.R.A. Martins*

[📄 Full Report](/assets/reports/Mehta_AE590_Report.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---

{% include gallery %}

## Overview

Developed a custom **Tsai-Wu composite failure criterion** integrated directly into [OpenAeroStruct](https://github.com/mdolab/OpenAeroStruct) — an open-source low-fidelity aerostructural optimization tool developed by the MDO Lab at the University of Michigan. The project extended OpenAeroStruct's FEM layer to natively support anisotropic composite failure prediction within gradient-based MDO loops.

## Motivation

OpenAeroStruct couples a Vortex Lattice Method (VLM) aerodynamic solver with a spatial beam FEM for structural analysis. Its existing failure model used **von Mises stress** — an isotropic criterion unsuitable for composite materials, which exhibit strongly direction-dependent failure behavior. With composites increasingly dominant in aerospace structures, an accurate, differentiable failure constraint was needed for composite aerostructural optimization.

## Approach

The Tsai-Wu failure criterion for a composite ply is:

*F₁σ₁ + F₂σ₂ + F₁₁σ₁² + F₂₂σ₂² + F₆₆τ₁₂² + 2F₁₂σ₁σ₂ ≤ 1*

where the F-coefficients are derived from ply-level strength properties (tensile, compressive, shear). The implementation:

- Computed ply-level stresses from beam element strains using CLT
- Evaluated the Tsai-Wu index at each element's critical section
- Exposed analytic partial derivatives for use by OpenMDAO's gradient framework (enabling adjoint-based optimization)
- Validated results against **TACS** (Toolkit for the Analysis of Composite Structures), MDO Lab's high-fidelity FEA tool

## Key Outcome

First composite failure model natively integrated into OpenAeroStruct's aerostructural optimization loop, enabling fully gradient-based MDO of composite wing structures with physically correct failure constraints.

## Tools

Python · OpenAeroStruct · OpenMDAO · TACS · NumPy

