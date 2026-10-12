# 6dof-robotic-arm
A self-directed 6-degree-of-freedom robotic arm built entirely from scratch - from mechanical design in Fusion 360 through 3D printing, hardware integration, and planned autonomous operation using ROS2 and machine learning.

---

## Project Overview

This project documents the end-to-end design and build of a desktop 6-DOF robotic arm capable of autonomous pick-and-place operation. Every component was designed from first principles with no prior mechanical engineering training - including motor cavity tolerancing, bearing seat geometry, wire routing, counterbore bolt patterns, and print-ready clearances.

The arm is being built in phases: mechanical assembly first, followed by motor control, ROS2 integration, and finally a computer vision and ML autonomy stack using YOLOv8 object detection.

---

## Current Status

| Phase | Status |
|-------|--------|
| CAD Design (Fusion 360) | Complete |
| 3D Printing | In Progress |
| Motor Wiring and Arduino Control | Planned |
| ROS2 Integration | Planned |
| Computer Vision (YOLOv8) | Planned |
| Autonomous Pick and Place | Planned |

---

## Hardware Stack

### Mechanical
- **CAD Software:** Autodesk Fusion 360
- **3D Printer:** Bambu Lab P1S
- **Filament:** Bambu Lab PLA Basic
- **Bearings:** 608-2RS sealed ball bearings (8x22x7mm) — McMaster 5972K501
- **Fasteners:** M3 brass heat-set inserts (McMaster 94180A331) + M3 socket head cap screws

### Electronics and Motion
- **Motors:** 6x NEMA 17 Stepper Motor (17HS4401) - 1.5A, 42x42x38mm, 5mm shaft
- **Drivers:** 6x BIGTREETECH TMC2209 V1.3 - ultra-silent StealthChop2, UART mode
- **Microcontroller:** Arduino Mega 2560
- **Power Supply:** 12V 10A switching power supply

### Phase 2 - Autonomy (Planned)
- **Single Board Computer:** Raspberry Pi 4 (4GB RAM)
- **Camera:** Raspberry Pi Camera Module v3
- **Position Feedback:** Rotary encoders (one per joint)
- **Grasp Detection:** Force Sensitive Resistor (FSR402)

---

## Software Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Motor Control | Arduino IDE (C++) | Low-level step/direction signals to TMC2209 drivers |
| Robot OS | ROS2 Humble | Joint state management, motion planning coordination |
| Motion Planning | MoveIt2 | Inverse kinematics, collision-aware path planning |
| Computer Vision | OpenCV + YOLOv8 | Real-time object detection and localization |
| ML Inference | PyTorch | Custom object classification model |
| Simulation | Gazebo + RViz | Pre-deployment testing and visualization |
| RL Training | Stable Baselines3 | Reinforcement learning for autonomous task learning |

---

## Mechanical Design

The arm was designed entirely in Fusion 360 with functional actuation in mind rather than aesthetics. Key engineering decisions include:

- **Motor cavities** sized to NEMA 17 body dimensions (42x42x38mm) with pilot boss recess (23mm diameter, 2.5mm deep) for precise centering
- **Counterbore bolt holes** for flush M3 screw head seating with heat-set insert thread engagement
- **608-2RS bearing seats** at each joint for smooth low-friction rotation
- **Wire routing channels** through the base for clean cable management
- **0.55 scale factor** applied to fit all parts within the Bambu P1S 256x256mm build volume
- **Side-mounted motor configuration** on shoulder joint for clean shaft-to-link direct drive

### Joint Configuration

| Joint | Location | Motor | Function |
|-------|----------|-------|----------|
| J1 | Base | NEMA 17 | Full arm waist rotation |
| J2 | Shoulder | NEMA 17 | Upper arm lift |
| J3 | Elbow | NEMA 17 | Forearm bend |
| J4 | Forearm | NEMA 17 | Forearm axial rotation |
| J5 | Wrist | NEMA 17 | Wrist tilt |
| J6 | Gripper | NEMA 17 | Finger open/close |

---

## Autonomy Architecture (Phase 2)

The target autonomous operation pipeline:

```
Raspberry Pi 4 (high-level brain)
        |
        |- Camera -> YOLOv8 -> object detection + 3D localization
        |- MoveIt2 -> inverse kinematics + path planning
        |- Stable Baselines3 -> reinforcement learning policy
        |
        v
Arduino Mega (low-level)
