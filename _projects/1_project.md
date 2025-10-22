---
layout: page
title: Autonomous Vehicle Simulation
description: Self-driving car simulator using Unity and deep reinforcement learning with custom physics, traffic systems, and real-time computer vision integration.
img: /assets/img/autonomous-vehicle.jpg
importance: 1
category: work
related_publications: false
---

This project implements a comprehensive self-driving car simulator using Unity ML-Agents with custom deep reinforcement learning algorithms. The system features realistic vehicle physics, dynamic traffic simulation, and integrates state-of-the-art computer vision models for lane and object detection in real-time.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="https://github.com/aveen007/autonomous-vehicle-with-unity/assets/73739296/fa9a7b1c-31a9-4608-a213-1e3d17ae0aba" title="Autonomous Vehicle Simulation Environment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Custom city environment with realistic vehicle physics simulating six distinct forces and dynamic traffic system.
</div>

## Simulation Architecture

The simulator creates two training environments with custom car physics based on six simulated forces:
- **Suspension, Acceleration, Steering** - Core vehicle dynamics
- **Brakes, Slipping, Friction** - Realistic movement constraints

Animation curves were implemented for hyperrealistic vehicle feel and precise control. The traffic system utilizes a custom waypoint tool for flexible route planning with branching at intersections to increase environmental randomness.

## Technical Implementation

### Machine Learning Pipeline
- **Unity ML-Agents Release 20** with Python Low Level API
- **Custom DQN Algorithm** for vehicle control (throttle/steering)
- **Sensor Integration**: LIDAR and Camera data fusion
- **Computer Vision**: CLRNet for lane detection and YOLOv8 for object detection
- **Learning from Demonstrations** through experience replay memory

### System Features
- Dynamic traffic spawning using object pooling and navigation mesh
- Custom side channels for real-time UI visualization
- Checkpoint system for training progression
- Multi-platform standalone builds
- Real-time performance monitoring in TensorBoard

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="https://github.com/aveen007/autonomous-vehicle-with-unity/assets/73739296/2da26b10-0a68-4f64-8cb4-1d5c9e8ab22c" title="Neural Network Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
   
</div>
<div class="caption">
    Neural network architecture for DQN implementation (left) and real-time visualization interface showing vehicle controls and sensor data (right).
</div>

## Project Outcomes

- Achieved **94% evaluation score** and ranked as top graphics project for bachelor's thesis
- Successfully coordinated **6 researchers** across computer vision, graphics, AI, and systems engineering
- Implemented **comparative analysis** between LIDAR-only and LIDAR+CLRNet enhanced models
- Developed **custom reward function** that significantly improved training efficiency
- Average vehicle speed of **30 km/h** using DQN control methods

**Project Documentation**: [View Full Project PDF](https://github.com/aveen007/autonomous-vehicle-with-unity/blob/main/Aveen%20Hussein2.pdf)

**Source Code**: Available upon request at [aveen2000hussein@gmail.com](mailto:aveen2000hussein@gmail.com)

## Technologies Used

- **Unity 3D** with ML-Agents
- **Python** with PyTorch
- **C#** for Unity scripting
- **YOLOv8** and **CLRNet** for computer vision
- **Deep Q-Network (DQN)** reinforcement learning
- **Custom Physics Engine** with six-force simulation

