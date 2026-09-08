---
layout: single
title: "项目介绍"
permalink: /projects/
author_profile: true
---

这里介绍我的科研与工程项目，重点关注自动驾驶决策、规划与控制，以及强化学习和世界模型。

## REALM：基于潜在世界模型在线评估的强化微调

REALM 是一个面向多模态规划的自动驾驶决策与规划框架。项目将轨迹生成、强化学习策略优化和潜在世界模型结合起来，为每条候选轨迹推演未来环境状态，并进行在线评估与筛选。

### 项目简介

面向复杂交通环境中的多模态轨迹规划问题，REALM 首先利用模仿学习高效生成多条候选轨迹，再通过闭环强化学习微调提升轨迹的安全性、通行效率和舒适性。针对传统评分器难以判断周围车辆如何响应不同候选轨迹的问题，框架引入潜在世界模型，为每条候选轨迹并行推演对应的未来场景状态，并通过多目标评估器选择最终轨迹。

- **项目时间**：2025.03 - 2025.10（所属“基于学习的无人车轨迹规划控制”项目）。
- **项目支持**：深圳市基础布局研究项目、国家自然科学联合基金项目。
- **技术栈**：Python、PyTorch、C++、Bazel、nuPlan、模仿学习、强化学习（GRPO）、世界模型、后训练。

### 项目要点

- 轨迹生成采用横向—纵向解耦的查询机制，生成多模态候选轨迹，缓解模式坍缩。
- 通过按横向意图分组的 GRPO 进行在线微调，避免整组统一优化的奖励将多模态策略压缩至单一模式，并采取全局截断抑制低质量整组对优化方向的误导。
- 构建候选轨迹条件化的隐空间世界模型与多头评分评估器，并行推演每条候选轨迹的未来交互状态，综合评估安全性、舒适性与可行性，筛选出对动态参与者与场景突变响应更佳的轨迹。
- 在公开 nuPlan 大型数据集上完成验证，整体规划性能超越规则式规划器 PDM 与学习式规划器 Car planner，达到 SOTA 水平。

### 方法流程

REALM 主要包含多模态轨迹生成器、策略优化器、潜在世界模型和轨迹评估器四个部分：

- **多模态轨迹生成器**：输出不同横向意图与纵向进度组合的候选轨迹。
- **策略优化器**：利用闭环模拟奖励进行组内相对策略优化（GRPO）。
- **潜在世界模型**：根据每条固定候选轨迹推演未来环境状态。
- **轨迹评估器**：综合无碰撞、可行驶区域、碰撞时间、舒适性和行驶进度完成在线排序，选出最终轨迹。

![REALM 方法流程]({{ '/images/projects/worldmodel/pipeline.png' | relative_url }})

<video width="100%" controls poster="/images/fengmian.png">
  <source src="/REALM1.mp4" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

### 实验展示

以下视频展示了 REALM 在提前避障、紧急响应、变道超车和行人交互等场景中的规划效果，以及不同模块配置下的结果对比。

#### 提前感知风险并及时避障

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/images/projects/worldmodel/avoidance_in_time.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

#### 紧急交通场景响应

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/images/projects/worldmodel/emergency_response.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

#### 变道超车轨迹规划

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/images/projects/worldmodel/lane_change_overtake.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

#### 行人交互场景通行

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/images/projects/worldmodel/pass_pedestrian.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

#### 不同模块配置的结果对比

<video width="100%" controls preload="metadata" playsinline>
  <source src="{{ '/images/projects/worldmodel/Ablation_result.mp4' | relative_url }}" type="video/mp4">
  您的浏览器不支持 HTML5 视频播放。
</video>

### 相关论文

Yuxiang Wang, Xiang Li, Xiaoqing Yang et al. "REALM: Reinforcement Fine-Tuning with Latent World Model Based Online Evaluation for Multimodal Planning," in 2026 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS 2026).
