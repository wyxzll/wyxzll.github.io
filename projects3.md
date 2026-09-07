---
layout: single
title: "E-RAMP：多模态融合的端到端鲁棒泊车规划与控制"
permalink: /projects3/
author_profile: true
---

## 项目简介

面向复杂、非结构化环境中的长时序泊车任务，构建融合多模态感知、模仿学习与残差强化学习的端到端泊车框架 **E-RAMP**。利用传统规划算法与模型预测控制器生成专家数据，通过模仿学习建立基础策略，再以残差强化学习进行闭环动作修正，提高泊车过程的稳定性与鲁棒性。

- **项目时间**：2025.03 - 2025.10（所属“基于学习的无人车轨迹规划控制”项目）。
- **项目支持**：深圳市基础布局研究项目、国家自然科学联合基金项目。
- **技术栈**：Python、PyTorch、C++、Bazel、CARLA、数值优化、模型预测控制（MPC）、模仿学习、残差强化学习。

## 研究背景

传统泊车规划方法依赖精确建模，在快速、长时序任务中面临求解效率问题。端到端方法虽然能够学习复杂的场景特征，但仍受到泊车专家数据不足、多模态特征融合不充分及闭环控制误差累积的限制。纯模仿学习策略在偏离专家数据分布后，也容易出现连续决策失误。

本项目围绕专家数据构建、视觉引导的多模态融合与残差动作修正，形成从数据采集到闭环训练与评估的完整流程。

## 方法设计

### 专家数据生成与基础策略学习

在 CARLA 中利用传统泊车规划算法生成参考轨迹，通过横纵解耦的 MPC 控制器跟踪轨迹，并同步记录传感器观测与控制数据，构建大规模泊车专家数据集。

基于专家数据开展端到端模仿学习，学习场景相关特征编码与基础控制策略，为后续残差强化学习提供初始行为能力。

### 视觉引导的多模态感知融合

结合 Camera 的语义信息与 LiDAR 的几何信息，设计视觉引导的深层特征融合模块。通过通道级交叉注意力（Channel-wise Cross-Attention，CCA）建立不同模态间的特征关联，改善几何与语义信息的对齐，增强复杂泊车环境的场景表征能力。

### 残差强化学习与闭环动作修正

在模仿学习基础策略上引入 Residual RL，学习对基础动作的补偿。残差策略根据闭环交互反馈修正控制行为，缓解长时序任务中的误差累积，提升障碍物规避、倒车入库与最终车位对齐阶段的稳定性。

## 闭环仿真验证

在 CARLA 大型停车场中构建闭环评估与强化学习训练环境：随机初始化自车位置和朝向，设置交互车辆及静态障碍物，要求车辆探索环境、寻找可行车位并完成泊车。

演示中的残差动作体现了三个阶段的修正作用：

- **提前避障**：在接近大型车辆障碍物时，调整基础策略的转向动作。
- **倒车入库**：修正倒车阶段的转向控制，提高入库稳定性。
- **末端对齐**：在泊车结束前进行动作微调，改善车位对齐精度。

项目通过专家数据驱动的基础策略与闭环残差修正相结合，改善复杂、长时序泊车任务中的控制表现与策略鲁棒性。

## 演示与结果

### E-RAMP 整体框架

![E-RAMP 整体框架图]({{ '/_pages/projects/e2e/pipeline.png' | relative_url }})

### 专家轨迹采集与跟踪演示

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/_pages/projects/e2e/carla_results.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

### 多传感器数据采集演示

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/images/projects/e2e/carla_6in1.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

### 停车场闭环评估环境

![停车场闭环评估环境]({{ '/_pages/projects/e2e/environment.png' | relative_url }})

### 基础策略与残差动作对比

![基础策略与残差动作对比]({{ '/_pages/projects/e2e/comparasion.png' | relative_url }})

### 闭环评估与强化学习结果

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/_pages/projects/e2e/result.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

## 相关论文

Xiang Li, **Yuxiang Wang**, Xiaoqing Yang et al. “E-RAMP: Robust End-to-End Parking with Multi-Modal Fusion and Residual Action Correction.”
