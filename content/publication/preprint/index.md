---
title: "SplaTraj: Camera Trajectory Generation with Semantic Gaussian Splatting"
authors:
- admin
- Tianyi Zhang
- Matthew Johnson-Roberson
- Weiming Zhi
date: "2024-10-08T00:00:00Z"
doi: "10.48550/arXiv.2410.06014"

publication_types: ["article"]
publication: "*arXiv preprint*"

abstract: We propose SplaTraj, a novel framework for generating camera trajectories using semantic Gaussian splatting. The method transforms image sequence generation into a continuous-time trajectory optimization problem by querying photorealistic representations with language embeddings.

summary: Semantically-aware camera trajectory generation using Gaussian splatting and language-guided optimization

tags:
- Robotics
- Computer Vision
- Semantic Gaussian Splatting

featured: true
---

## Technical Overview

### Key Contributions
- Novel semantic Gaussian splatting for camera trajectory generation
- Language-guided trajectory optimization
- Continuous-time trajectory generation

### Mathematical Formulation

Camera trajectory optimization is formulated as:

\[ \min_{\tau} J(\tau) = \int_0^T \left( L_{\text{smoothness}}(\tau) + L_{\text{semantic}}(\tau, \mathbf{E}) \right) dt \]

Where:
- \( \tau \) represents camera trajectory
- \( L_{\text{smoothness}} \) ensures trajectory smoothness
- \( L_{\text{semantic}} \) captures semantic constraints
- \( \mathbf{E} \) represents language embeddings

### Semantic Representation

The semantic Gaussian splatting uses a volumetric representation:

\[ G(x) = \sum_{i=1}^{N} \alpha_i \exp\left(-\frac{(x - \mu_i)^T \Sigma_i^{-1} (x - \mu_i)}{2}\right) \]

Where:
- \( G(x) \) is the semantic density
- \( \alpha_i \) are opacity values
- \( \mu_i \) are Gaussian means
- \( \Sigma_i \) are covariance matrices

## Experimental Results

- Successfully generated semantically-aware camera trajectories
- Demonstrated ability to follow language-specified spatial instructions
- Achieved photogenic view generation across various environments

{{% callout note %}}
Developed at Carnegie Mellon University's Drop Lab
{{% /callout %}}
