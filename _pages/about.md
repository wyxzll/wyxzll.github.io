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

实习经历
======

### 文远知行 | Rbotics-PNC-算法岗

2026.05 - 2026.08

**端到端模型与 QP 采样规划器结合方案（L4 Guarded AI Planner）**

参与 GAP 混合规划架构中的 Critical Bounds 多维评估指标建设：以端到端 AI 规划器处理常规场景，以 QP 采样规划器作为安全兜底，对比 AI Top1 轨迹与代价函数最优轨迹，在异常情况下触发自适应降级。

- **静态阻滞评估（Static Stuck）**：融合 Static Graph 拓扑搜索与 Static Tube 几何通道分析，量化静态障碍物及高精地图元素对规划轨迹的阻滞程度，覆盖路径障碍物侵占、任务边界及路沿合规性检测，并针对掉头、红灯驻车、窄路会车、ETC/Pickup 等场景设计启发式规则。
- **横向变道代价（Lat Effort）**：从变道难度、变道幅度与环境增强三个维度建模，引入环境、方向、分歧、几何四层密度自适应放大器及跨 Plan 归一化机制，支持变道、汇入、分歧及出口匝道、BRT、施工区等复杂场景的代价调节。
- **持续低速评估（Continue Below Limit Speed）**：针对开放道路上的不合理持续低速行驶，设计“阈值 + 权重”双重动态调节机制，根据车速与限速比值实时计算权重；结合七维场景豁免策略与滞回决策器，避免正常减速误判并实现跨帧防抖。

### 美团 | 无人车业务部 · 决策规划组 · 算法策略岗

2025.10 - 2026.02

**停车场车云一体化算法与工具交互方案**

针对停车场中单车独立规划导致的多车路径冲突，设计云端协同调度方案，统一管理车辆路径分配与通行顺序。

- **云端路线预分配**：基于车辆起终点及场景数据，通过 RS 曲线、人工绘制轨迹和人驾轨迹聚类生成候选动线，为车辆预分配行驶路线。
- **多车冲突消解**：综合车辆任务类型及各动线在冲突点的预计占用时段，动态计算通行优先级；为各动线构建局部障碍物地图，结合 Hybrid A* 与 RS 曲线生成可行驶轨迹。
- **调度可视化**：开发可视化工具，展示动线分配、冲突消解及多车通行效果，辅助方案验证与问题定位。

**无图行车决策规划方案**

针对缺少高精度地图的园区场景，独立设计并实现专用无图规划器，支撑无人车自主行驶，并与园区外有图路线平滑衔接。

- **参考线生成与优化**：基于导航路由，通过动态规划（DP）搜索生成初始道路参考线；结合平滑度、可行驶区域贴合度、障碍物避让及绕行方向一致性约束进行迭代优化，处理路由精度低、偏离可行驶区域及穿越障碍物等问题。
- **有图/无图区域衔接**：设计有图与无图区域实时判断算法，通过两区域路由平滑融合，实现规划路线的无缝切换。


主要科研成果
------
- **Yuxiang Wang**, Xiang Li, Xiaoqing Yang et al."REALM:Reinforcement Fine-Tuning with Latent World Model-Based Online Evaluation for Multimodal Planning,"in 2026 IEEE/RSJ International Conference on Intelligent Robots and Systems.
- **Yuxiang Wang**, Xiang Li, Xiaoqing Yang et al., et al. “PRIME: Enhancing End-to-End Planning via Pareto-Guided Multimodal Intent Learning and Rule-Based Rollouts,” in 2027 IEEE International Conference on Robotics and Automation(ICRA 2027).
- Xiang Li, **Yuxiang Wang**, Xiaoqing Yang et al."E-RAMP: Robust End-to-End Parking with Multi-Modal Fusion and Residual Action Correction,"in 2026 IEEE/RSJ International Conference on Intelligent Robots and Systems.



