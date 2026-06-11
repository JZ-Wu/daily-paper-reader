---
title: "CausalVTG: Towards Robust Video Temporal Grounding via Causal Inference"
title_zh: CausalVTG：通过因果推断实现稳健视频时间定位
authors: "Qiyi Wang, Senda Chen, Ying Shen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oeWgBOowL6"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 因果推断实现稳健视频时间定位
tldr: 针对视频时域定位任务中的数据集偏差和查询段缺失假设不合理问题，提出CausalVTG，使用因果推断分离真实语义关联与虚假共现模式，实现更鲁棒的定位。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 4400, \"height\": 353}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 4400, \"height\": 353}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 4400, \"height\": 353}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-004.webp\", \"caption\": \"\", \"page\": 2, \"index\": 4, \"width\": 4400, \"height\": 231}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-005.webp\", \"caption\": \"\", \"page\": 5, \"index\": 5, \"width\": 887, \"height\": 231}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-006.webp\", \"caption\": \"\", \"page\": 17, \"index\": 6, \"width\": 4400, \"height\": 971}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-007.webp\", \"caption\": \"\", \"page\": 17, \"index\": 7, \"width\": 4400, \"height\": 971}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-008.webp\", \"caption\": \"\", \"page\": 17, \"index\": 8, \"width\": 4400, \"height\": 970}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-009.webp\", \"caption\": \"\", \"page\": 17, \"index\": 9, \"width\": 4400, \"height\": 970}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-010.webp\", \"caption\": \"\", \"page\": 17, \"index\": 10, \"width\": 4400, \"height\": 1020}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-011.webp\", \"caption\": \"\", \"page\": 18, \"index\": 11, \"width\": 4400, \"height\": 970}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oewgboowl6/fig-012.webp\", \"caption\": \"\", \"page\": 18, \"index\": 12, \"width\": 4400, \"height\": 970}]"
motivation: 现有视频时域定位方法易受数据集偏差影响，且假设查询段必然存在，不贴合实际。
method: CausalVTG利用因果干预和反事实推理消除混淆效应，提升语义理解与鲁棒定位。
result: 在多个VTG基准上超越传统方法，尤其在与训练数据分布不同的场景下。
conclusion: 因果方法可有效提升视频时域定位的鲁棒性和泛化性。
---

## Abstract
Video Temporal Grounding (VTG) aims to localize relevant segments in untrimmed videos based on natural language queries and has seen notable progress in recent years.
However, most existing methods suffer from two critical limitations. 
First, they are prone to learning superficial co-occurrence patterns—such as associating specific objects or phrases with certain events—induced by dataset biases, which ultimately degrades their semantic understanding abilities.
Second, they typically assume that relevant segments always exist in the video, an assumption misaligned with real-world scenarios where queried content may be absent.
Fortunately, causal inference offers a natural solution to the above-mentioned issues by disentangling dataset-induced biases and enabling counterfactual reasoning about query relevance. 
To this end, we propose CausalVTG, a novel framework that explicitly integrates causal reasoning into VTG. 
Specifically, we introduce a causality-aware disentangled encoder (CADE) based on front-door adjustment to mitigate confounding biases in visual and textual modalities. To better capture temporal granularity, we design a multi-scale temporal perception module (MSTP) that reconstructs query-conditioned video features at multiple resolutions. 
Additionally, a counterfactual contrastive learning objective is employed to help the model discern whether a query is truly grounded in a video.
Extensive experiments on five widely-used benchmarks demonstrate that CausalVTG outperforms state-of-the-art methods, achieving higher localization precision under stricter IoU thresholds and more accurately identifying whether a query is truly grounded in the video. 
These results demonstrate both the effectiveness and generalizability of proposed CausalVTG.
The code is available at https://github.com/MxLearner/CausalVTG.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- **研究动机**：视频时间定位旨在根据自然语言查询在未裁剪视频中定位相关片段。现有方法普遍存在两个关键缺陷：
  - **表面共现模式的干扰**：模型容易学习由数据集偏差引起的虚假关联（如特定物体或短语与某些事件的浅层搭配），导致语义理解能力下降。
  - **不切实际的假设**：默认查询对应的片段总是存在于视频中，无法处理现实场景中查询内容缺失的情况（即查询“未落地”）。
- **整体含义**：作者认为，因果推断是解决上述问题的自然途径，因为它能够解开数据集引入的混淆因素，并利用反事实推理判断查询与视频之间是否存在真实语义关联。因此，本文提出将因果推理显式融入视频时间定位，以提升模型的鲁棒性和泛化能力。

## 提出的方法论
### 核心思想
- 通过构建视频时间定位的结构因果模型，将视觉和文本模态中的风格变化（如装饰模式、措辞差异）视为混淆因子，采用前门调整阻断虚假依赖，迫使模型关注真实的语义因果关系。
- 同时引入反事实对比学习，使模型能够判断查询是否真实存在于视频中。

### 关键技术模块
- **因果感知解耦编码器**：
  - 基于前门调整，利用自注意力机制分别生成视频和查询的潜在中介表示 `m`。
  - 通过干预分布 `P(Y|do(X))` 估计，消除混淆因子 `Z` 的影响，公式近似为 `F(x', m) = EX'[h(x')] + EM[g(m)]`。
  - 在实现上，使用 K‑means 聚类采样输入特征，并利用注意力机制加权聚合，得到因果解耦的视觉和文本表征。
- **多尺度时间感知模块**：
  - **查询引导的精炼**：通过三线性注意力计算视频‑查询相似度，再使用上下文‑查询和查询‑上下文注意力增强视频片段特征，有效突出语义相关部分并抑制噪声。
  - **多尺度时间特征金字塔**：对精炼后的视频特征，采用不同步长（如1,2,4,8）的时序卷积下采样，构建多分辨率特征序列，同时捕捉细粒度动作与长程事件动态。
- **预测头设计**：
  - **高光检测**：对精炼视频特征与自适应池化的查询向量计算余弦相似度，生成片段显著性得分，用采样噪声对比估计损失训练。
  - **时刻检索**：在多尺度特征上，分别使用并行的1D卷积头预测时间段边界偏移和前景置信度，分别采用L1损失和焦点损失监督。
  - **查询相关性预测**：通过拼接池化后的视频和查询特征，经由前馈网络输出相关性分数 r，并采用动态二元交叉熵损失训练。该任务配合反事实对比学习，强制模型区分正、负样本对，使模型在查询不落地时能够拒绝输出。
- **训练与推理**：总损失为上述四个损失的加权和；推理时，对预测时间段执行非极大值抑制，并根据相关性分数决定是否输出结果。

## 实验设计
### 数据集与基准
- **数据集**：
  - **QVHighlights**：联合支持时刻检索与高光检测的基准，提供私有测试分区。
  - **Charades‑STA** 和 **ActivityNet‑Captions**：专注于时刻检索，具有精确时间标注。
  - **Charades‑RF** 和 **ActivityNet‑RF**：在原始数据集基础上引入不接地查询，用于评估查询相关性判断能力。
- **评价指标**：
  - 时刻检索：mAP（IoU=0.5,0.75），平均mAP（0.5至0.95），Recall@1（IoU=0.3,0.5,0.7）及mIoU。
  - 高光检测：mAP 和 HIT@1。
  - 查询相关性：平衡准确率 Acc。
### 对比方法
- 在 QVHighlights 上与 Moment‑DETR、UMT、QD‑DETR、CG‑DETR、R2‑Tuning 等十余种方法比较。
- 在 Charades‑STA/ActivityNet 上与 VSLNet、SeqPAN、UniVTG、RaTSG 等比较。
- 在 RF 数据集上与带“++”版本（添加简单相关性判别器）的基线及 RaTSG 比较。

## 资源与算力
- **训练环境**：单张 NVIDIA RTX 4070 SUPER GPU（12GB 显存，32GB 系统内存）。
- **训练时长**：QVHighlights 上约 50 分钟，所有模型均训练 50 个 epoch。
- **实现框架**：PyTorch，视觉‑语言骨干为 InternVideo2‑CLIP。
- 论文附录还提供了在 A800 显卡上的计算成本对比，但主实验均在 4070 SUPER 上完成。

## 实验数量与充分性
- **对比实验**：覆盖 5 个主流数据集，与超过 15 种现有 SOTA 方法进行全面比较，涵盖了有/无相关性判断的设置。
- **消融研究**：在 QVHighlights 验证集上逐步添加 CADE、查询引导精炼、MSTP、查询相关性模块四个组件，共 11 种配置，详细验证了各模块的单独和联合贡献。
- **敏感性分析**：探究 K‑means 聚类数 K 的影响（16 到 2048，共 8 种取值，每种多个随机种子）以及多尺度步长配置（5 种设置），证明了方法的稳健性。
- **计算效率对比**：比较了 GPU 内存、参数量、训练时间和推理时间。
- **可视化**：提供了成功案例和失败案例的定性分析。
- 总体而言，实验设计全面、客观、公平，消融和敏感性分析充分支撑了论文主张。

## 主要结论与发现
- CausalVTG 在所有五个基准的严格 IoU 阈值下均取得领先的定位精度，尤其在 R1@0.7 和 mAP@0.75 上有显著提升。
- 在引入不接地查询的 RF 数据集中，CausalVTG 的查询相关性准确率和定位指标均大幅超越基线方法，验证了因果建模在识别真实接地条件与拒绝虚假匹配方面的有效性。
- 消融实验证实，因果解耦编码器和多尺度时间感知模块贡献最大，各组件互补，联合使用性能最优。
- 因果推断框架为视频时间定位提供了更强的鲁棒性和可解释性，能有效对抗数据偏差和语言风格变化。

## 优点
- **创新性因果建模**：首次为 VTG 构建结构因果模型并应用前门调整，具有明确的理论动机。
- **模块化设计**：四个模块职责清晰，组合灵活，消融充分。
- **强大的鲁棒性**：能拒绝不接地查询，对查询措辞的微小变化不敏感，超越强基线 R2‑Tuning。
- **实验扎实**：覆盖 5 个数据集，大量对比与消融，并提供代码和敏感性分析，可复现性高。
- **成本合理**：在普通消费级 GPU 上亦可训练，实用性较强。

## 不足与局限
- **模态单一**：目前仅利用视觉和文本信息，对涉及语音或音频关键线索的查询（如说话内容、特定音效）场景可能失效，缺乏多模态（音频、深度）扩展。
- **细粒度感知不足**：在需要分辨细微视觉属性（如衣物颜色、细小物体差异）的任务中仍表现不佳，失败案例指出了这一瓶颈。
- **计算效率中等**：虽然训练不重，但推理时间比 Moment‑DETR、QD‑DETR 等简单模型略长（53 秒 vs 31/37 秒）。
- **未提供误差条**：主实验表格未报告标准差或统计显著性，仅部分敏感性实验给出了均值和标准差。
- **应用范围限制**：仅在标准基准上验证，真实世界中更复杂的背景变化、长视频、多事件交叉等场景有待进一步探索。

（完）
