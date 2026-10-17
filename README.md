<div align="center">

<img src="./assets/cover.png" alt="Robot Perception, Localization and Navigation" width="650"/>

# Autonomous Robotics: Perception, Localization & Navigation

**个人课外研究 · 技术视野扩展 · 架构拆解**

[![Domain](https://img.shields.io/badge/Domain-Autonomous%20Systems-0078D7?style=flat-square)](#)
[![Topic](https://img.shields.io/badge/Topic-SLAM%20%7C%20Path%20Planning-2EA043?style=flat-square)](#)
[![Status](https://img.shields.io/badge/Status-Active%20Research-blueviolet?style=flat-square)](#)

</div>

---

## 💡 项目简介 (Introduction)

> 本仓库记录了我个人在课外对**自主移动机器人（Autonomous Mobile Robots）**领域的自主研究与技术探索。
> 
> 出于对机器人感知、定位与导航技术的兴趣，我系统性地梳理了该领域的核心理论、算法架构以及工程实践路线。这不是一份简单的资料堆砌，而是一份**结构化的技术全景地图**。

---

## 🗺️ 核心架构总览

任何智能自主机器人都构建在三大核心组件（**Sense-Think-Act**）的循环之上：

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

