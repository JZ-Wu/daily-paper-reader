---
title: Uncertainty-quantified Rollout Policy Adaptation for Unlabelled Cross-domain Video Temporal Grounding
title_zh: 面向无标签跨域视频时序定位的不确定性量化 rollout 策略自适应
authors: "Jian Hu, Zixu Cheng, Shaogang Gong, Isabel Guan, Jianye HAO, Jun Wang, Kun Shao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=RfNiN2rENM"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 利用VLM的无标签跨域视频时序定位不确定性量化策略自适应
tldr: 针对视频时序定位在无标签域中微调成本高、延迟大的问题，提出不确定性量化的 rollout 策略自适应方法，利用视觉语言模型在无需标签的情况下实现细粒度时序定位。在多个跨域数据集上验证了其高效与准确，为低成本、零训练的视频理解代理提供了关键技术支持。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 1587, \"height\": 980}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 722, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 1182, \"height\": 558}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-004.webp\", \"caption\": \"\", \"page\": 9, \"index\": 4, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-005.webp\", \"caption\": \"\", \"page\": 9, \"index\": 5, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-006.webp\", \"caption\": \"\", \"page\": 9, \"index\": 6, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-007.webp\", \"caption\": \"\", \"page\": 9, \"index\": 7, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-008.webp\", \"caption\": \"\", \"page\": 9, \"index\": 8, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-009.webp\", \"caption\": \"\", \"page\": 9, \"index\": 9, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-010.webp\", \"caption\": \"\", \"page\": 9, \"index\": 10, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-011.webp\", \"caption\": \"\", \"page\": 9, \"index\": 11, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-012.webp\", \"caption\": \"\", \"page\": 9, \"index\": 12, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-013.webp\", \"caption\": \"\", \"page\": 9, \"index\": 13, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-014.webp\", \"caption\": \"\", \"page\": 9, \"index\": 14, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-015.webp\", \"caption\": \"\", \"page\": 9, \"index\": 15, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-016.webp\", \"caption\": \"\", \"page\": 9, \"index\": 16, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-017.webp\", \"caption\": \"\", \"page\": 9, \"index\": 17, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-018.webp\", \"caption\": \"\", \"page\": 9, \"index\": 18, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-019.webp\", \"caption\": \"\", \"page\": 9, \"index\": 19, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-020.webp\", \"caption\": \"\", \"page\": 14, \"index\": 20, \"width\": 3600, \"height\": 2100}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-021.webp\", \"caption\": \"\", \"page\": 14, \"index\": 21, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-022.webp\", \"caption\": \"\", \"page\": 14, \"index\": 22, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-023.webp\", \"caption\": \"\", \"page\": 14, \"index\": 23, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-024.webp\", \"caption\": \"\", \"page\": 14, \"index\": 24, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-025.webp\", \"caption\": \"\", \"page\": 14, \"index\": 25, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-026.webp\", \"caption\": \"\", \"page\": 14, \"index\": 26, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-027.webp\", \"caption\": \"\", \"page\": 14, \"index\": 27, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-028.webp\", \"caption\": \"\", \"page\": 14, \"index\": 28, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-029.webp\", \"caption\": \"\", \"page\": 14, \"index\": 29, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-030.webp\", \"caption\": \"\", \"page\": 14, \"index\": 30, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-031.webp\", \"caption\": \"\", \"page\": 14, \"index\": 31, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-032.webp\", \"caption\": \"\", \"page\": 14, \"index\": 32, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-033.webp\", \"caption\": \"\", \"page\": 14, \"index\": 33, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-034.webp\", \"caption\": \"\", \"page\": 14, \"index\": 34, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-035.webp\", \"caption\": \"\", \"page\": 14, \"index\": 35, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-036.webp\", \"caption\": \"\", \"page\": 14, \"index\": 36, \"width\": 960, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-037.webp\", \"caption\": \"\", \"page\": 14, \"index\": 37, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-038.webp\", \"caption\": \"\", \"page\": 14, \"index\": 38, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-039.webp\", \"caption\": \"\", \"page\": 14, \"index\": 39, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-040.webp\", \"caption\": \"\", \"page\": 14, \"index\": 40, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-041.webp\", \"caption\": \"\", \"page\": 14, \"index\": 41, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-042.webp\", \"caption\": \"\", \"page\": 14, \"index\": 42, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-043.webp\", \"caption\": \"\", \"page\": 14, \"index\": 43, \"width\": 854, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rfnin2renm/fig-044.webp\", \"caption\": \"\", \"page\": 14, \"index\": 44, \"width\": 854, \"height\": 480}]"
motivation: GRPO虽能实现精细时序定位但依赖标签，且全量自适应开销大，不适用于无标签域。
method: 提出不确定性量化的 rollout 策略自适应，在无标签域以低计算代价实现视频时序定位。
result: 在多个数据集上取得与有监督方法相当的定位精度，且推理效率显著提升。
conclusion: 该方法为无标签、低成本的视频时序定位提供了有效解决方案，推动VLMs的实际部署。
---

## Abstract
Video Temporal Grounding (TG) aims to temporally locate video segments matching a natural language description (a query) in a long video. While Vision-Language Models (VLMs) are effective at holistic semantic matching, they often struggle with fine-grained temporal
localisation. Recently, Group Relative Policy Optimisation (GRPO) reformulates the inference process as a reinforcement learning task, enabling fine-grained grounding and achieving strong in-domain performance. However, GRPO relies on labelled data, making it unsuitable in unlabelled domains. Moreover, because videos are large and expensive to store and process, performing full-scale adaptation introduces prohibitive latency and computational overhead, making it impractical for real-time deployment. To overcome both problems, we introduce a Data-Efficient Unlabelled Cross-domain Temporal Grounding method, from which a model is first trained on a labelled source domain, then adapted to a target domain using only a small number of {\em unlabelled videos from the target domain}. This approach eliminates the need for target annotation and keeps both computational and storage overhead low enough to run in real time. Specifically, we introduce \textbf{U}ncertainty-quantified \textbf{R}ollout \textbf{P}olicy \textbf{A}daptation (\textbf{URPA}) for cross-domain knowledge transfer in learning video temporal grounding without target labels. URPA generates multiple candidate predictions using GRPO rollouts, averages them to form a pseudo label, and estimates confidence from the variance across these rollouts. This confidence then weights the training rewards, guiding the model to focus on reliable supervision. Experiments on three datasets across six cross-domain settings show that URPA generalises well using only a few unlabelled target videos. Codes are given in supplemental materials.

---

## 论文详细总结（自动生成）

## 1. 研究动机与核心问题
视频时序定位（Temporal Grounding, TG）旨在根据自然语言查询，在长视频中定位对应的起止时刻。视觉‑语言大模型（VLMs）虽能进行整体语义匹配，但在细粒度时间定位上表现不佳。近期工作 GRPO 将推理过程建模为强化学习，能实现较精细的定位，且域内性能出色，但该方法**依赖标注数据**，无法在无标签目标域使用；同时，**对大量视频进行全量自适应会带来高延迟和高计算开销**，难以实时部署。

因此，本文的核心问题可概括为：**如何在无标签目标域，仅利用极少的目标域视频，实现低开销、实时的跨域视频时序定位**。为解决该问题，作者提出了数据高效的跨域时序定位新范式，即在有标签源域训练模型后，仅用少量无标签目标域视频进行测试期适应，从而消除对目标域标注的依赖，并将计算和存储成本降到足以实时运行的水平。

## 2. 方法论：不确定性量化的 Rollout 策略自适应（URPA）
整体框架分两阶段。

### 2.1 源域模型训练
- **骨干模型**：基于 VLM（Qwen2.5‑7B），通过 GRPO 进行有监督微调，使模型具备结构化的时序推理能力。
- **格式奖励**（`R_format`）：要求模型按 `<think>…</think>` 和 `<answer>…</answer>` 格式输出，匹配格式则奖励 1，否则 0。
- **准确性奖励**：为缓解标注边界的主观偏差，对真实标签区间作松弛处理（前后各扩展固定比例 α 的时长），得到松弛标签 \(\tilde{I}^{\text{gt}}_s\)。再计算预测区间与松弛标签的时序交并比（`R_tIoU`）。最终奖励为二者加权和：`R_s = 0.5 × R_format + 0.5 × R_tIoU`。

### 2.2 目标域适应
- **伪标签生成**：对每个目标域视频，通过 GRPO 策略采样 \(G\) 条不同的 rollout 响应，对预测的起止时间戳取平均，得到伪标签 \(\hat{\tau}^{\text{start}}_t, \hat{\tau}^{\text{end}}_t\)。
- **不确定性估计**：将 rollout 输出视为近似贝叶斯预测分布的采样，计算起止时间戳的标准差之和作为不确定性 \(u\)，再经指数衰减函数转换为置信度 \(c = \exp(-\gamma u)\)。
- **置信度加权奖励**：在计算时序奖励时，用置信度缩放 \(R_tIoU\)，格式奖励不缩放：`R_s = 0.5 × R_format + 0.5 × R_tIoU × c`。高置信度（低方差）的伪标签将在梯度更新中获得更大权重，从而引导模型聚焦于可靠的监督信号。
- **理论支撑**：定理 4.1 证明，在 rollout 采样数量 \(G\to\infty\) 且 GRPO 训练使 KL 散度 \(\varepsilon\to0\) 的条件下，rollout 的标准差一致收敛于贝叶斯预测标准差（即认知不确定性的度量）。这为利用 rollout 方差估计不确定性提供了理论保证。

## 3. 实验设计
### 3.1 数据集与跨域设置
使用三个标准视频时序定位数据集，构建六个跨域场景（以下为单向转移）：  
- **ActivityNet Captions** (约 20000 视频，10 万描述)  
- **TACoS** (127 个烹饪视频)  
- **Charades‑STA** (12408 训练、3720 测试对)  
每个实验选择一个作为有标签源域，其余一个作为无标签目标域。

### 3.2 对比基准
对比方法分为三大类：
1. **全量无监督域适应方法**：CBP、SCDM、CMIN、CSMGAN、2DTAN、DRN、MMN、UDA‑TSL（均在完整目标域视频上训练/适应）。
2. **域泛化方法**：原版 Qwen2.5‑7B（零样本）、仅源域训练的 GRPO 模型、仅源域训练的 URPA 模型（无任何目标域数据）。
3. **本文的**数据高效无监督适应：URPA 在 100‑shot 和 200‑shot 目标域视频上测试期适应。

### 3.3 评估指标
报告不同 tIoU 阈值下的召回率：R@0.3、R@0.5、R@0.7，以及部分实验中的 mIoU。

### 3.4 消融与参数分析
- 对不确定度和软标签进行消融，观察移除某一模块后的性能变化。
- 分析超参数 \(\gamma\)（置信度衰减系数）和 rollout 数量 \(G\) 的影响。
- 提供定性可视化，展示适应前后预测边界的变化以及成功/失败案例。

## 4. 资源与算力
- **硬件**：32 块 NVIDIA V100 GPU。
- **实现框架**：PyTorch。
- **训练细节**：最大提示长度为 4096，最大响应长度为 2048，rollout 数 \(G=8\)，批大小为 16，训练 1 个 epoch。  
论文未明确给出单次实验的总训练时长或 GPU‑小时数。

## 5. 实验数量与充分性
总共进行了 **6 个跨域方向**上的主实验，每个方向汇报两种 shot 数（100、200）下的 R@0.5、R@0.7 等指标；在 Charades→ActivityNet 方向额外做了详细的消融实验（4 个变体）和两组参数分析（γ 和 G 各多个取值）；还提供了定性分析。对比的基线方法涵盖传统全量 UDA 方法（8 种）和域泛化方法（3 种），整体对比维度丰富。实验设计既验证了数据高效适应的有效性，也通过消融证明了不确定性量化和软标签的关键作用，实验较充分、客观且公平。

## 6. 主要结论与发现
- **数据高效自适应可行**：仅用 100 或 200 个无标签目标域视频，URPA 即可显著提升源域训练的模型性能，在多个转移任务上**接近甚至超过**全目标域数据的无监督域适应方法。
- **不确定性量化至关重要**：用 rollout 方差加权奖励，可有效利用高置信度伪标签，抑制噪声；消融实验证实移除不确定性加权后性能大幅下降。
- **理论一致性**：rollout 标准差可渐近估计贝叶斯预测标准差，为认知不确定性提供可靠度量。
- **对超参数鲁棒**：在一定范围内，γ 和 rollout 数 G 的变化对性能影响不大，G=8 已足够。

## 7. 优点
- **问题设置实用**：提出利用极少无标签目标视频进行测试期适应，大幅降低标注和计算成本，适合实时部署。
- **方法创新**：首次将 GRPO 的多轮 rollout 用于同时生成伪标签和估计不确定性，通过置信度加权奖励实现了无需标签的强化学习适应。
- **理论支撑**：给出了 rollout 方差与贝叶斯预测标准差的收敛性证明，解释不确定性度量的合理性。
- **实验全面**：覆盖多种数据集、跨域方向，与大量基线对比，消融和参数分析充分，并附有定性案例。

## 8. 不足与局限
- **伪标签噪声风险**：当伪标签噪声较大时，模型可能过拟合到错误监督信号，适应性能随样本数增加可能先升后降（论文自身也观察到这一现象）。
- **目标域需少量视频**：方法假设部署时能获得 K（~100‑200）个目标域视频，若连少量视频也无法获取则无法适用。
- **适应仍需反向传播**：虽避免了全量训练，但仍需梯度更新，并非完全“免训练”，在极低延时场景可能仍有开销。
- **跨域实验局限**：实验主要在三类活动/烹饪数据集间转移，未覆盖更大规模的域差异或视频风格巨变的情形，泛化边界有待进一步验证。
- **计算资源需求**：使用 32 块 V100 GPU，部分研究人员可能难以复现；论文未说明训练时间，资源消耗的具体量化不够清晰。

（完）
