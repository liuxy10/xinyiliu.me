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

Camera trajectory optimization is formulated as a constrained optimization problem:

$$ \min_{\tau} J(\tau) = \int_0^T \left( L_{\text{smoothness}}(\tau) + L_{\text{semantic}}(\tau, \mathbf{E}) \right) dt $$

Key components:
- $ \tau $: Camera trajectory
- $ L_{\text{smoothness}} $: Trajectory smoothness penalty
- $ L_{\text{semantic}} $: Semantic constraint loss
- $ \mathbf{E} $: Language embedding vector

### Semantic Representation

Semantic Gaussian splatting uses a probabilistic volumetric representation:

$$ G(x) = \sum_{i=1}^{N} \alpha_i \exp\left(-\frac{(x - \mu_i)^2}{2\sigma_i^2}\right) $$

Where:
- $ G(x) $ represents semantic density
- $ \alpha_i $ are opacity coefficients
- $ \mu_i $ are Gaussian cluster centers
- $ \sigma_i $ are cluster spread parameters

The mathematical formulation draws inspiration from semantic querying techniques developed in previous research on photorealistic environment representations, particularly leveraging language embeddings for dynamic spatial projection.


## Experimental Results

- Successfully generated semantically-aware camera trajectories
- Demonstrated ability to follow language-specified spatial instructions
- Achieved photogenic view generation across various environments

{{% callout note %}}
Developed at Carnegie Mellon University's Drop Lab
{{% /callout %}}
