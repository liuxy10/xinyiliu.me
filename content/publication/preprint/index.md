```yaml
---
title: "SplaTraj: Camera Trajectory Generation with Semantic Gaussian Splatting"
authors:
- admin
- Tianyi Zhang
- Matthew Johnson-Roberson
- Weiming Zhi
date: "2024-10-08T00:00:00Z"
doi: "10.48550/arXiv.2410.06014"

publishDate: "2024-10-08T00:00:00Z"

publication_types: ["article"]

publication: "*arXiv preprint*"
publication_short: "arXiv"

abstract: Many recent developments for robots to represent environments have focused on photorealistic reconstructions. This paper contributes a novel framework, SplaTraj, which formulates the generation of images within photorealistic environment representations as a continuous-time trajectory optimization problem. The approach enables generating camera trajectories that match user-specified language instructions by querying photorealistic representations with language embeddings to isolate and project specified spatial regions dynamically.

summary: A novel framework for generating semantically-aware camera trajectories using Gaussian splatting and language-guided trajectory optimization.

tags:
- Robotics
- Computer Vision
- Semantic Gaussian Splatting
- Camera Trajectory Generation

featured: true

url_pdf: "https://arxiv.org/pdf/2410.06014.pdf"
url_code: "https://github.com/your-github-repo/SplaTraj"
url_project: ""
url_slides: ""
url_video: ""

image:
  caption: 'Semantic Camera Trajectory Generation'
  focal_point: "Center"
  preview_only: false

projects:
- semantic-robotics
- computer-vision

slides: ""
---

## Research Highlights

- Developed SplaTraj, a novel framework for generating semantically-aware camera trajectories
- Introduced a method for querying photorealistic representations using language embeddings
- Formulated camera trajectory generation as a continuous-time trajectory optimization problem
- Successfully generated Radial Basis Function-based camera trajectories matching user-specified language instructions

{{% callout note %}}
This work was developed during research at Carnegie Mellon University's Drop Lab under the supervision of Dr. Matthew Johnson-Roberson.
{{% /callout %}}

## Technical Approach

The SplaTraj framework addresses the challenge of generating meaningful camera trajectories by:
1. Creating a dense semantic representation using Gaussian splatting
2. Implementing a language-guided trajectory optimization method
3. Dynamically projecting specified spatial regions
4. Generating photogenic camera movements that respect semantic constraints
```

