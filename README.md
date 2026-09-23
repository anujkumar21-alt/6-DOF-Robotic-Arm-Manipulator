# 6R Serial Robotic Manipulator — Kinematic Assembly in CATIA V5

A 6-DOF articulated serial industrial robotic manipulator modeled and assembled using **CATIA V5 (Assembly Design & Part Design)**. The project models an industrial articulated arm featuring an anchor foundation, rotating waist, upper/lower linkages, an articulated wrist, and an integrated dual-claw mechanical end-effector.

---

## 📌 Project Overview

* **Software:** CATIA V5 (Part Design, Assembly Design)
* **Architecture:** 6-Revolute (6R) Serial Articulated Topology
* **End-Effector:** Synchronized mechanical dual-claw gripper mechanism
* **Design Objectives:** Kinematic clearance verification, spatial reachability, and zero-interference joint mate definition.

---

## ⚙️ CAD Hierarchy & Part Breakdown

The assembly tree (`Robotic arm assembly.CATProduct`) is structured hierarchically to mirror real-world industrial serial links:

| Component | File Name | Role & Kinematics |
|---|---|---|
| **Base / Pedestal** | `Part1.CATPart` | Heavy cast foundation anchor; secures the manipulator to the factory floor. |
| **Turntable / Waist** | `link_1.CATPart` | Revolute joint 1 (Azimuth rotation / Base yaw). |
| **Shoulder / Boom** | `link_2.CATPart` | Revolute joint 2 (Shoulder pitch elevation). |
| **Forearm / Elbow** | `Part4.CATPart` | Revolute joint 3 (Elbow pitch articulation). |
| **Wrist Mechanism** | `gripper_support.CATPart` | Revolute joints 4 & 5 (Pitch and roll wrist positioning). |
| **End-Effector Body** | `gripper.CATPart` | Housing and actuator chassis for mechanical gripper. |
| **Claw Fingers** | `claw.CATPart` | Dual-jaw parallel/pivot mechanical grasping claws. |

---

## 🔧 Assembly Constraints & Kinematics

Mechanical joints and kinematic degrees of freedom were established inside CATIA V5's **Assembly Design** workbench using precise engineering constraints:

* **Coaxial / Coincidence Constraints:** Applied across pivot bore centerlines and cylindrical pins to establish revolute rotational axes.
* **Surface Contact & Offset Constraints:** Set precise axial clearances and planar mating surfaces between linkage clevises and bearing seats.
* **Angular Limits & Orientation Constraints:** Defined joint stop limits to simulate actual servo and hydraulic actuator limits, preventing self-intersection across the workspace envelope.
* **Gripper Synchronization:** Constrained twin claw linkages symmetrically relative to the gripper centerline for centered grasping.

---

## 📁 Repository Structure

```text
├── CAD_Models/
│   ├── Parts/
│   │   ├── Part1.CATPart
│   │   ├── link_1.CATPart
│   │   ├── link_2.CATPart
│   │   ├── Part4.CATPart
│   │   ├── gripper.CATPart
│   │   ├── gripper_support.CATPart
│   │   └── claw.CATPart
│   └── Assembly/
│       └── Robotic arm assembly.CATProduct
├── Renders/
│   └── Robotic_Arm_Assembly_Overview.png
└── README.md
