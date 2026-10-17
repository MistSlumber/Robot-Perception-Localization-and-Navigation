<div align="center">

<img src="./assets/cover.png" alt="Robot Perception, Localization and Navigation" width="650"/>

# Autonomous Robotics: Perception, Localization & Navigation

**个人课外研究 · 技术视野扩展 · 架构拆解**

[![Domain](https://img.shields.io/badge/Domain-Autonomous%20Systems-0078D7?style=flat-square)](#)
[![Topic](https://img.shields.io/badge/Topic-SLAM%20%7C%20Path%20Planning-2EA043?style=flat-square)](#)
[![Toolchain](https://img.shields.io/badge/Toolchain-ROS%20%7C%20Gazebo%20%7C%20Docker-orange?style=flat-square)](https://www.ros.org/)
[![Status](https://img.shields.io/badge/Status-Active%20Research-blueviolet?style=flat-square)](#)

</div>

---

## 💡 导言 (Introduction)

> 本仓库记录了个人在课外对 **Robot Perception, Localization and Navigation**（机器人感知、定位与导航）领域的自主研究与视野拓展。
> 
> 出于对自主移动机器人与自动驾驶技术的浓厚兴趣，我自发整理了该领域的核心理论架构、技术演进以及前沿应用。这不是一份枯燥的学术报告，而是一份**技术全景地图**，旨在探索机器人如何感知世界、如何定位自身，以及如何安全地规划并执行动作。

---

## 🧠 核心概念：机器人的定义与本质

基于对文献和开源项目的调研，一个真正的物理机器人（区别于纯软件智能体）必须具备以下特征：
- **物理存在**：存在于 3D 物理世界中，受物理定律约束。
- **可动部件**：由连杆 (Links) 和关节 (Joints) 组成。
- **感知与行动**：能感知内外环境，通过执行器（电机等）产生物理动作。
- **目标导向**：半自主或全自主地做出决策以完成任务。

> *开环控制 (Open-loop)*：不考虑传感器反馈，按预设程序执行（需极高确定性）。
> *闭环控制 (Closed-loop)*：利用传感器反馈实时调整决策，应对外界变化。

---

## 🗺️ 架构拆解：感知-思考-行动闭环

任何智能自主机器人都构建在三大核心组件（**Sense-Think-Act**）的循环之上。这是我在研究中理清的最重要的系统级架构：

```mermaid
graph TD
    subgraph SENSE [👁️ Sense: 感知环境]
        S1[Camera / LiDAR / Ultrasonic]
        S2[GPS / IMU / Encoders]
    end

    subgraph THINK [🧠 Think: 认知与决策]
        T1[Localization & Mapping]
        T2[Cognition & Path Planning]
    end

    subgraph ACT [⚙️ Act: 执行动作]
        A1[Brushless Motors / Servos]
        A2[Manipulation & Locomotion]
    end

    SENSE -->|环境数据与自身体态| THINK
    THINK -->|运动控制指令| ACT
    ACT -.->|物理世界反馈| SENSE

