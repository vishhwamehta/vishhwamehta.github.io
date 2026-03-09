---
title: "LLM-Based Path Planning in Low-Light Conditions using ORB-SLAM3"
permalink: /projects/llm-path-planning/
layout: single
author_profile: true

gallery:
  - url: /assets/images/projects/rob530_1.jpg
    image_path: /assets/images/projects/rob530_1.jpg
    alt: "ORB-SLAM3 occupancy map"
    title: "2D occupancy map generated via image-enhanced ORB-SLAM3"
  - url: /assets/images/projects/rob530_2.jpg
    image_path: /assets/images/projects/rob530_2.jpg
    alt: "LLM navigation architecture"
    title: "Hybrid LLM + SLAM navigation system architecture"
---

*ROB 530 — Mobile Robotics · University of Michigan*
*Team: Kaushek Kumar T R (EECS), Sanjana Raghavan (EECS), Vishwa Mehta (Aerospace Engineering)*

[📄 Full Report](/assets/reports/ROB530_Project_Report.pdf){: .btn .btn--primary}
[← Back to Projects](/projects/){: .btn .btn--inverse}

---

## Overview

A hybrid autonomous navigation framework for a **differential-drive robot** operating in low-light indoor environments, where traditional SLAM pipelines and classical path planners fail due to degraded visual feature detection. The system combines GAN-based image enhancement, ORB-SLAM3 mapping, and an LLM-based semantic planner into a unified navigation stack.

## Problem Statement

In near-dark indoor environments:
- **ORB feature detection degrades severely** — insufficient texture contrast for keypoint extraction
- **Classical planners lack semantic understanding** — unable to interpret high-level navigation instructions or resolve spatial ambiguity
- **Dynamic obstacles** require real-time replanning beyond static map assumptions

Existing solutions either require active illumination (impractical for covert or power-constrained robots) or rely on depth-only sensing (losing semantic richness).

## System Architecture

### 1. Image Enhancement Module
A custom **EnlightenGAN**-based image enhancement pipeline preprocesses raw camera frames before feature extraction. EnlightenGAN is a generative adversarial network trained for unpaired low-light enhancement — it adaptively boosts local features without overexposure or contextual distortion, enabling reliable ORB keypoint detection in near-zero-light conditions.

### 2. SLAM & Mapping (ORB-SLAM3)
Enhanced frames feed into **ORB-SLAM3**, which constructs a 2D occupancy map of the environment. The IMU and stereo camera provide additional constraint for robust pose estimation when visual features are sparse.

### 3. Semantic Obstacle Extraction
A **semantic segmentation node** runs continuously on depth camera data, detecting and tracking dynamic obstacles (people, moving objects) not captured in the static occupancy map. Obstacle positions are published as real-time costmap updates.

### 4. LLM-Based Path Planner
A large language model interprets high-level natural language navigation commands ("go to the room with the whiteboard") and resolves spatial ambiguity in the occupancy map using semantic scene understanding. The LLM generates waypoint sequences passed to a local motion planner (DWA) for execution.

## Sensor Suite

- 2D LiDAR
- IMU
- Depth camera
- Stereo camera

## Key Outcomes

- Reliable SLAM and navigation in near-zero-light conditions where baseline ORB-SLAM3 fails
- Successful LLM-guided semantic navigation with high-level instruction following
- Real-time dynamic obstacle avoidance integrated into planning loop

## Tools

ROS2 · ORB-SLAM3 · PyTorch (EnlightenGAN) · LLM API · OpenCV · DWA Local Planner

{% include gallery %}
