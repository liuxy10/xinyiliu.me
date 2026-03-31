---
title: "Beyond Motion Imitation: Is Human Motion Data Alone Sufficient to Explain Gait Control and Biomechanics?"
authors:
  - admin
  - Jangwhan Ahn
  - Edgar Lobaton
  - Jennie Si
  - He Huang

author_notes:
  - 'First Author'

date: '2026-03-12T00:00:00Z'
doi: '10.48550/arXiv.2603.12408'

publishDate: '2026-03-12T00:00:00Z'

publication_types: ['paper-preprint']

publication: arXiv preprint arXiv:2603.12408
publication_short: arXiv:2603.12408

abstract: With the growing interest in motion imitation learning (IL) for human biomechanics and wearable robotics, this study investigates how additional foot-ground interaction measures, used as reward terms, affect human gait kinematics and kinetics estimation within a reinforcement learning-based IL framework. Results indicate that accurate reproduction of forward kinematics alone does not ensure biomechanically plausible joint kinetics. Adding foot-ground contacts and contact forces to the IL reward terms enables the prediction of joint moments in forward walking simulation, which are significantly closer to those computed by inverse dynamics. [arxiv](https://arxiv.org/abs/2603.12408)

summary: Motion-only imitation learning fails to produce biomechanically plausible gait kinetics; kinetics-aware rewards using GRF and CoP are essential for physical consistency in RL-based gait simulation.

tags:
  - Imitation Learning
  - Gait Biomechanics
  - Reinforcement Learning
  - Wearable Robotics
  - Ground Reaction Forces

featured: true

url_pdf: 'https://arxiv.org/pdf/2603.12408.pdf'
url_project: 'https://www.youtube.com/watch?v=hMmCPn6QCsE'

image:
  caption: 'Comparison of (a) a biomechanics inverse dynamics pipeline and (b) a motion-only imitation learnin(IL) pipeline integrating a reinforcement learning agent with forward dynamics'
  focal_point: 'Center'
  preview_only: false

projects:
  - gait-biomechanics
  - imitation-learning
  - reinforcement-learning

slides: ""
---


## Mathematical Formulation
### Imitation Learning Objective
The policy maximizes expected cumulative reward:

$$ J(\theta) = \mathbb{E}_{\pi_\theta} \left[ \sum_{t=0}^T \gamma^t r(s_t, a_t, q^{\exp}_t, f^{\exp}_{\mathrm{grf},t}, x^{\exp}_{\mathrm{cop},t}) \right] $$

Where $ r(\cdot) $ includes kinematics $ R_k $ and dynamics $ R_{\mathrm{dyn}} $ terms.
### Reward Components
Kinematics reward:

$$ R_k = w_p R_p + w_{ee} R_{ee} + w_{rp} R_{rp} + w_{rv} R_{rv} + w_{vf} R_{vf} $$

Dynamics reward:

$$ R_{\mathrm{dyn}} = w_{\mathrm{grf}} R_{\mathrm{grf}} + w_{\mathrm{cop}} R_{\mathrm{cop}} $$

With GRF term $ R_{\mathrm{grf}} = \exp\left( -k_{\mathrm{grf}} \|\Delta f_{\mathrm{grf}}\|^2 \right) $ and CoP term $ R_{\mathrm{cop}} = \exp\left( -k_{\mathrm{cop}} \|\Delta x_{\mathrm{cop}}\|^2 \right) $.
## Technical Approach
### Key Components
- RL-based IL with PPO and residual force control in MuJoCo.
- Ablation on kinetics rewards: baseline (kinematics-only, MOIL), +GRF, +CoP, full KAIL.
- Forward dynamics simulation of musculoskeletal model matching Visual3D inverse dynamics.
### Performance Metrics
- Joint angle RMSE <7° across conditions.
- GRF correlation improves significantly with kinetics rewards (p<0.001).
- Joint moment RMSE reduced, correlations increased (p<0.0001) in KAIL vs. MOIL.
The figure shows simulated human gait skeletons adapting walking speeds via imitation learning, illustrating kinematic fidelity in MuJoCo environments similar to the study's setup.
## Research Significance
Motion imitation alone prioritizes kinematic matching but yields implausible GRFs and joint moments due to unphysiological foot-ground interactions. KAIL with GRF/CoP rewards ensures biomechanical plausibility, critical for biomechanics analysis, clinical diagnostics, and wearable robot design.
## Implementation Highlights
- Data from motion capture and force-plate treadmill on healthy subject walking at 1.2 m/s.
- MuJoCo model with floating-base, impedance control, trained 900 PPO iterations.
- Evaluation via GRF butterfly diagrams, CPCC, joint moment RMSE/correlations vs. inverse dynamics.

