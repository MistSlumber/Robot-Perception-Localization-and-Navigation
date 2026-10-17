<div align="center">



<img src="./assets/cover.png" alt="Robot Perception, Localization and Navigation" width="650"/>



\# Autonomous Robotics: From Fundamentals to Real-World Systems



\*\*课外视野拓展 · 课后技术研究记录\*\*



\[!\[Course](https://img.shields.io/badge/Course-Robot%20Perception%20%26%20Navigation-0078D7?style=flat-square)](#)

\[!\[Instructor](https://img.shields.io/badge/Instructor-Sen%20Wang-orange?style=flat-square)](#)

\[!\[Toolchain](https://img.shields.io/badge/Toolchain-ROS%20%7C%20Gazebo%20%7C%20Docker-2EA043?style=flat-square)](https://www.ros.org/)

\[!\[Status](https://img.shields.io/badge/Status-Active%20Learning-blueviolet?style=flat-square)](#)



</div>



\---



\## ?? 导言



> 本仓库记录了 \*\*Robot Perception, Localization and Navigation\*\* 课程的课外拓展、知识梳理与课后实践探索。

> 

> 本课程由 Sen Wang 讲授，旨在建立机器人学（Robotics）的系统性认知。这不是一份枯燥的理论报告，而是一份\*\*技术探索地图\*\*，帮助我们理解机器人如何感知世界、如何定位自身，以及如何安全地规划并执行动作。



\---



\## ??? 核心架构：移动机器人的三大组件 (Sense-Think-Act)



现代智能机器人构建在三大核心组件构成的闭环之上。没有这三者，机器人就只是一堆盲目的金属。



```mermaid

flowchart LR

&#x20;   subgraph SENSE \[??? Sense: 感知环境]

&#x20;       direction TB

&#x20;       S1\[Camera / LiDAR / Ultrasonic]

&#x20;       S2\[GPS / IMU / Encoders]

&#x20;   end



&#x20;   subgraph THINK \[?? Think: 认知与决策]

&#x20;       direction TB

&#x20;       T1\[Localization \& Mapping]

&#x20;       T2\[Path Planning \& Cognition]

&#x20;   end



&#x20;   subgraph ACT \[?? Act: 执行动作]

&#x20;       direction TB

&#x20;       A1\[Brushless Motors / Servos]

&#x20;       A2\[Manipulation \& Locomotion]

&#x20;   end



&#x20;   SENSE -->|传感器数据| THINK

&#x20;   THINK -->|控制指令| ACT

&#x20;   ACT -.->|物理反馈| SENSE

