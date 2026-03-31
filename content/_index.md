---
title: ""
date: 2024-07-01
type: landing

design:
  spacing: "5rem"

sections:
  - block: resume-biography-3
    content:
      username: admin
      text: "Hi! I'm Xinyi Liu, I joined UNC & NCSU joint BME Doctoral program in the Fall of 2024. I previously worked on algorithms that enable powered prosthetic legs to automatically avoid trips. My research interests currently focus on reinforcement learning deployed on real robotics systems.
      
      "
      button:
        text: Download CV
        url: uploads/resume.pdf
    design:
      css_class: dark
      background:
        color: black
        # image:
        #   filename: stacked-peaks.svg
        #   filters:
        #     brightness: 1.0
        #   size: cover
        #   position: center
        #   parallax: false

  # - block: markdown
  #   content:
  #     title: '🤖 Research Focus'
  #     subtitle: ''
  #     text: |-
  #       My research explores cutting-edge robotics technologies, with a particular emphasis on:
  #       - Semantic Camera Trajectory Generation
  #       - Safe Reinforcement Learning
  #       - Autonomous Systems
  #       - Computer Vision and Machine Learning Applications

  #       Current research aims to develop innovative solutions that enhance robotic perception, decision-making, and interaction capabilities.

  #   design:
  #     columns: '1'

  - block: markdown
    id: news
    content:
      title: '📢 News'
      text: |-
        - **[Spring 2026]** Invited to present our work at DexLab speaker series @ Duke and NC State Robotics Symposium. 
        - **[Fall 2024]** Joined UNC & NCSU joint BME Doctoral program as a Mansour doctoral fellow.
    design:
      columns: 1

  - block: collection
    id: papers
    content:
      title: Featured Publications
      filters:
        folders:
          - publication
        featured_only: true
    design:
      view: article-grid
      columns: 2

  - block: collection
    content:
      title: Recent Publications
      filters:
        folders:
          - publication
        exclude_featured: false
    design:
      view: citation



  - block: markdown
    content:
      title: Technical Skills
      text: |-
        **Programming Languages:** Python, C/C++, MATLAB, R, LaTeX
        **Frameworks:** PyTorch, TensorFlow, ROS/ROS2, CUDA
        **Tools:** Carla, Gym, IsaacSim, Mujoco, OpenSim

  # - block: markdown
  #   content:
  #     title: Languages
  #     text: |-
  #       - English (Proficient)
  #       - Chinese (Native)
  #       - Cantonese (Intermediate)
  #       - French (Intermediate)
---
