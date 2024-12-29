---
title: 'Guided Online Distillation: Promoting Safe Reinforcement Learning by Offline Demonstration'

authors:
  - admin
  - Jinning Li
  - Banghua Zhu
  - Jiantao Jiao
  - Masayoshi Tomizuka
  - Chen Tang
  - Wei Zhan

author_notes:
  - 'Co-first Author'
  - 'First Author'
  - 'Contributor'
  - 'Contributor'
  - 'Senior Author'
  - 'Contributor'
  - 'Corresponding Author'

date: '2024-01-15T00:00:00Z'
doi: '10.1109/ICRA.2024.7447-7454'

publishDate: '2024-01-15T00:00:00Z'

publication_types: ['paper-conference']

publication: In *2024 IEEE International Conference on Robotics and Automation (ICRA)*
publication_short: In *ICRA 2024*

abstract: Safe Reinforcement Learning (RL) aims to find policies that achieve high rewards while satisfying cost constraints. Existing approaches often struggle with overly conservative exploration, particularly in safety-critical domains like autonomous driving. We propose Guided Online Distillation (GOLD), an innovative offline-to-online safe RL framework that distills large-capacity offline policies into lightweight, computationally efficient policy networks through guided online safe RL training.

summary: A novel framework for promoting safe reinforcement learning by distilling offline expert demonstrations into lightweight, safe policy networks.

tags:
  - Safe Reinforcement Learning
  - Autonomous Driving
  - Policy Distillation
  - Machine Learning

featured: true

url_pdf: 'https://arxiv.org/pdf/2309.09408.pdf'
# url_code: 'https://github.com//guided-online-distillation'
url_project: 'https://sites.google.com/view/guided-online-distillation'

image:
  caption: 'GOLD Framework for Safe RL'
  focal_point: 'Center'
  preview_only: false

projects:
  - safe-reinforcement-learning
  - autonomous-systems

slides: ""
---

---
title: 'Guided Online Distillation: Promoting Safe Reinforcement Learning by Offline Demonstration'

## Mathematical Formulation

### Policy Distillation Objective

The core optimization problem is formulated as:

$$ \min_{\pi_{\theta}} \mathbb{E}_{s \sim d_{\text{expert}}} \left[ L_{\text{distill}}(\pi_{\theta}(s), \pi_{\text{expert}}(s)) + \lambda L_{\text{safety}}(\pi_{\theta}) \right] $$

Where:
- $\pi_{\theta}$: Online policy network
- $\pi_{\text{expert}}$: Offline expert policy
- $L_{\text{distill}}$: Policy distillation loss
- $L_{\text{safety}}$: Safety constraint loss
- $\lambda$: Regularization coefficient

### Safe Exploration Constraint

The safety constraint is defined as:

$$ P(\text{safe trajectory}) \geq 1 - \epsilon $$

## Technical Approach

### Key Components
- Two-stage policy extraction
- Offline expert policy distillation
- Online fine-tuning with safety constraints

### Performance Metrics
- Reduced collision rate from 30% to <3%
- 15% improvement in driving task success rates

## Research Significance

Addresses critical reinforcement learning challenges:
- Mitigates conservative exploration
- Enables lightweight policy networks
- Improves safety in autonomous systems

## Implementation Highlights
- Developed versatile driving simulation platform
- Implemented online distillation procedure
- Extracted lightweight policies from transformer models

{{% callout note %}}
Developed at UC Berkeley's MSC Lab under Prof. Masayoshi Tomizuka
{{% /callout %}}
