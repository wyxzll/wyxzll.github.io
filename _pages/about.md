---
permalink: /
title: "基本情况"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
王宇翔，哈尔滨工业大学（深圳）智能科学与工程学院在读研究生（导师：[李衍杰教授]（http://homepage.hit.edu.cn/liyanjie）），2024年获中南大学自动化专业学士学位。研究方向：自动驾驶决策规划与控制，强化学习，模仿学习，世界模型。2026年IROS在投论文两篇。

Yuxiang Wang, a graduate student at the School of Intelligent Science and Engineering, Harbin Institute of Technology (Shenzhen), supervised by Prof. [Yanjie Li](https://homepage.hit.edu.cn/liyanjie). He received his Bachelor's degree in Automation from Central South University in 2024. His research focuses on decision-making, planning, and control for autonomous driving, reinforcement learning, imitation learning, and world models. He has two papers under review for IROS 2026.

技术栈
======
- 编程技能：Python，C++11，百度Apollo框架，PyTorch，Bokeh，MATLAB。
- 理论基础：机器人学，汽车理论，强化学习，矩阵分析，最优化理论，自动控制，最优控制。
- 硬件水平：具有百度 Apollo D-Kit Lite真车调试经验。

项目经历
======
基于学习的多模式轨迹规划控制：提出了一种结合模仿学习轨迹生成、强化学习策略微调与潜在世界模型在线评估的自动驾驶规划框架。
- 该方法采用横向‑纵向分解的查询机制生成多模式轨迹。
- 除真实专家轨迹外，还为每类场景从训练数据中聚类出一组高质量轨迹作为辅助监督信号，以加速模型收敛。
- 策略优化阶段，基于横向查询将候选轨迹分组，基于nuPlan闭环仿真计算奖励，并采用组内相对策略优化（group relative policy optimization, GRPO）对轨迹进行在线微调。
- 框架包含一个潜在世界模型，能为每条候选轨迹独立推演其对应的未来环境潜在状态序列；该序列与当前场景特征一并输入至一个通过知识蒸馏从基于规则的教师模型中学习多维度评分准则的评分模型，对候选轨迹进行综合评价与筛选，输出最优轨迹。
<video width="100%" controls poster="fengmian.png">
  <source src="REALM1.mp4" type="video/mp4">
</video>
<p><small>我们的规划器在大型数据集nuPlan仿真成果展示。</small></p>

主要科研成果
------
- Yuxiang Wang, Xiang Li, Xiaoqing Yang et al."REALM:Reinforcement Fine-Tuning with Latent World Model-Based
      Online Evaluation for Multimodal Planning,"in 2026 IEEE/RSJ International Conference on Intelligent Robots and Systems.
- Xiang Li, Yuxiang Wang, Xiaoqing Yang et al."E-RAMP: Robust End-to-End Parking with Multi-Modal Fusion and
      Residual Action Correction,"in 2026 IEEE/RSJ International Conference on Intelligent Robots and Systems.


