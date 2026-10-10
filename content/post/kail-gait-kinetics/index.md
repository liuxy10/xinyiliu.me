---
title: "Matching the Motion Isn't Matching the Physics: Gait Kinetics from Imitation Learning"
summary: "Motion-only imitation learning can track human gait kinematics well and still get ground reaction forces, center of pressure and joint moments wrong. Adding GRF and CoP to the reward fixes much of it."
date: 2026-10-10
authors:
  - admin
tags:
  - Imitation Learning
  - Gait Biomechanics
  - Reinforcement Learning
  - Wearable Robotics
image:
  caption: ""
  focal_point: "Center"
  preview_only: false
---

**TL;DR.** If you train a policy to imitate human walking from motion data alone, the simulated skeleton can look right while the forces behind it are not. Our preprint, [*Imitation Learning from Human Motion Alone Does Not Guarantee Biomechanically Plausible Gait Kinetics*](https://arxiv.org/abs/2603.12408), is on arXiv now and has been **submitted to IEEE Robotics and Automation Letters (RA-L)**.

## Why this matters

Motion imitation learning (IL) is now common in robotics and in human gait modeling. It is also starting to be used for biomechanics questions, such as estimating joint moments for wearable-robot design. That use assumes that a policy which reproduces the motion also reproduces the kinetics. We wanted to test that assumption directly.

## What we compared

- **MOIL (motion-only IL):** the reward only asks the simulated human to match the reference kinematics.
- **KAIL (kinetics-aware IL):** the same reward, plus terms for **ground reaction force (GRF)** and **center of pressure (CoP)**.
- **Ablation:** the GRF term and the CoP term added separately, to see what each contributes.

Both are trained with RL in a MuJoCo musculoskeletal model. The data come from a non-disabled participant walking at **0.9, 1.2 and 1.5 m/s**, and the simulated GRF, CoP and joint moments are compared against inverse-dynamics references.

The kinetics terms are simple exponential tracking rewards:

$$ R_{\mathrm{grf}} = \exp\left( -k_{\mathrm{grf}} \|\Delta f_{\mathrm{grf}}\|^2 \right), \qquad R_{\mathrm{cop}} = \exp\left( -k_{\mathrm{cop}} \|\Delta x_{\mathrm{cop}}\|^2 \right) $$

## What the videos show

In the videos below, **gray is the reference**, **black is MOIL**, and **blue is KAIL**. The traces are drawn progressively over time. Each walking speed has its own pair of videos.

### Ground reaction force and center of pressure

- **Vertical GRF:** MOIL unloads and reloads the foot at the wrong times. KAIL follows the timing of the reference.
- **AP GRF:** MOIL's braking and push-off peaks are out of phase with the reference. KAIL is closer in phase, though it is still noisy.
- **CoP:** the reference moves smoothly from heel to toe during stance. MOIL jumps almost immediately to the front of the foot. KAIL also starts ahead of the reference, but then moves forward along the foot rather than jumping.

**1.2 m/s**

<video controls muted loop playsinline width="100%">
  <source src="grf_cop_12.mp4" type="video/mp4">
  <a href="grf_cop_12.mp4">Download the GRF/CoP video (1.2 m/s)</a>
</video>

**1.5 m/s**

<video controls muted loop playsinline width="100%">
  <source src="grf_cop_15.mp4" type="video/mp4">
  <a href="grf_cop_15.mp4">Download the GRF/CoP video (1.5 m/s)</a>
</video>

At 1.5 m/s the gap is visible in the vertical GRF and the CoP. MOIL unloads early and its CoP jumps to the toe, while KAIL tracks the reference more closely.

### Joint moments

- MOIL produces large hip and knee moment spikes that the inverse-dynamics reference does not have.
- KAIL tracks the ankle push-off peak closely. Its hip and knee moments are closer to the reference but not perfect.

**0.9 m/s**

<video controls muted loop playsinline width="100%">
  <source src="moment_09.mp4" type="video/mp4">
  <a href="moment_09.mp4">Download the joint-moment video (0.9 m/s)</a>
</video>

At 0.9 m/s MOIL's hip and knee moments swing to about -2 N·m/kg, where the reference stays near zero. The hip in KAIL still oscillates.

**1.2 m/s**

<video controls muted loop playsinline width="100%">
  <source src="moment_12.mp4" type="video/mp4">
  <a href="moment_12.mp4">Download the joint-moment video (1.2 m/s)</a>
</video>

**1.5 m/s**

<video controls muted loop playsinline width="100%">
  <source src="moment_15.mp4" type="video/mp4">
  <a href="moment_15.mp4">Download the joint-moment video (1.5 m/s)</a>
</video>

At 1.5 m/s MOIL's hip, knee and ankle moments all show sharp spikes near the end of stance. KAIL stays much closer to the reference.

## What we found

- **Kinematic tracking was comparable** for MOIL and KAIL, so joint angles alone would not have told them apart.
- **MOIL had substantially larger errors** in GRF, CoP and joint moments relative to the inverse-dynamics references.
- **KAIL produced kinetics more consistent with biomechanical values.**

The point is not that motion imitation is useless. It is that matching the motion does not guarantee human-like kinetics. If a motion-only policy is used to interpret gait biomechanics, or to inform wearable-robot design, the result can be wrong even though the animation looks right.

## Limitations

This is one non-disabled participant at three walking speeds, so the results should be read as evidence for the limitation of MOIL, not as a general model of gait. The preprint has the full details and statistics.

## Links

- Preprint: [arXiv:2603.12408](https://arxiv.org/abs/2603.12408) (cs.RO), submitted to IEEE RA-L
- [PDF](https://arxiv.org/pdf/2603.12408.pdf)
- [Project video](https://www.youtube.com/watch?v=hMmCPn6QCsE)

Co-authors: Jangwhan Ahn, Edgar Lobaton, Jennie Si and Helen (He) Huang.
