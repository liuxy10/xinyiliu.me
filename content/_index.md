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
      text: "Robotics Research Engineer specializing in autonomous systems, computer vision, and machine learning. Focused on developing innovative robotic technologies including semantic camera trajectory generation, safe reinforcement learning, and trip-recovery planning for prosthetic systems.
      
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

  - block: markdown
    content:
      title: Languages
      text: |-
        - English (Proficient)
        - Chinese (Native)
        - Cantonese (Intermediate)
        - French (Intermediate)
---
