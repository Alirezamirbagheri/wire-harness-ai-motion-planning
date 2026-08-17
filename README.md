# AI-Based Wire Harness Perception, Motion Planning & PLC Integration

Portfolio showcase of an industrial research project for autonomous wire-harness handling using AI perception, geometric reasoning, multi-mover motion planning and PLC-based execution.

> This public showcase intentionally excludes the original research repository, datasets, model checkpoints, machine-specific configuration and internal experiment history.

## Demo

[![Wire-harness system demo](media/wire_harness_demo_thumbnail.jpg)](media/wire_harness_demo_15s.mp4)

The demo shows the physical multi-mover system together with computer-vision and runtime/planning views.

## System pipeline

1. **Camera acquisition and preprocessing**
2. **Semantic segmentation** of background, wire harness and movers
3. **Geometry extraction** including mover poses, wire skeleton/branches and attachment relations
4. **Persistent tracking** of physical movers
5. **Global formation planning**
6. **Local collision-aware planning**
7. **PLC communication and synchronized execution**
8. **Runtime supervision / state-machine handling**

## Engineering focus

- Computer vision for thin, deformable objects
- Semantic segmentation
- Geometry extraction from segmentation masks
- Multi-object tracking and assignment
- Multi-mover motion planning
- Collision avoidance
- Beckhoff TwinCAT 3 and ADS communication
- PyTorch / TensorRT / OpenVINO inference experiments
- Industrial real-time integration

## Segmentation benchmark

A separate public-release repository compares U-Net, U-Net++, DeepLabV3+, HRNet, SegFormer, PIDNet and YOLO26s-Sem using a common evaluation and runtime protocol.

The final test showed:
- **U-Net:** best Wire Dice ≈ 0.889 and Boundary F1 ≈ 0.847
- **YOLO26s-Sem:** Wire Dice ≈ 0.886 with ≈ 24.5 ms native inference latency (≈ 40.8 FPS)

## Public-release scope

This repository is intended as a technical portfolio showcase rather than a copy of the full research workspace. Source code or additional implementation details should only be published after confirming redistribution/publication rights for the underlying research material.
