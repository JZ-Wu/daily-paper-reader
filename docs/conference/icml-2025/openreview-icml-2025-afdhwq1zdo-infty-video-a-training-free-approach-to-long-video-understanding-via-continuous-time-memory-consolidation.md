---
title: "$\\infty$-Video: A Training-Free Approach to Long Video Understanding via Continuous-Time Memory Consolidation"
title_zh: ∞-Video：基于连续时间记忆巩固的训练无关长视频理解方法
authors: "Saul Santos, António Farinhas, Daniel C McNamee, Andre Martins"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=afDHwQ1ZDO"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 训练无关的连续时间记忆巩固方法，用于VLM长视频理解
tldr: "针对现有视频语言模型因上下文长度限制和稀疏帧采样而导致长视频理解信息丢失的问题，提出∞-Video方法。该方法通过连续时间长期记忆巩固机制，在不增加额外训练的前提下，使视频Q-former能高效处理无限长视频，并动态关注最相关片段，形成'粘性'记忆。实验表明，在Video-LLaMA和VideoChat2上均取得提升，为训练无关的高效视频理解提供了新途径。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1537, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1732, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1065, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1595, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-afdhwq1zdo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1747, \"height\": 1067, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1642, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-afdhwq1zdo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1770, \"height\": 236, \"label\": \"Table\"}]"
motivation: 长视频理解存在上下文限制和信息丢失问题，现有方法需要额外训练。
method: 提出连续时间长期记忆巩固机制，增强视频Q-former，实现训练无关的动态注意力分配。
result: 在Video-LLaMA和VideoChat2上无需额外训练即提升长视频理解性能。
conclusion: 提供了一种训练无关的高效长视频理解方案，具有普适性。
---

## Abstract
Current video-language models struggle with long-video understanding due to limited context lengths and reliance on sparse frame subsampling, which often leads to information loss. In this paper, we introduce $\infty$-Video, which is able to process arbitrarily long videos through a continuous-time long-term memory (LTM) consolidation mechanism. Our framework augments video Q-formers by making them able to process unbounded video contexts efficiently and without requiring additional training. Through continuous attention, our approach dynamically allocates higher granularity to the most relevant video segments, forming "sticky" memories which evolve over time. Experiments with Video-LLaMA and VideoChat2 demonstrate improved performance in video question-answering tasks, showcasing the potential of continuous-time LTM mechanisms to enable scalable and training-free comprehension of long videos.

---

## 论文详细总结（自动生成）

好的，以下是对论文《∞-Video: A Training-Free Approach to Long Video Understanding via Continuous-Time Memory Consolidation》的结构化深度总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前的视频语言模型在处理长视频时面临两大挑战：
    *   **上下文长度限制**：模型（尤其是大型语言模型作为骨干的模型）能处理的token数量有限，无法一次摄入完整的长视频。
    *   **稀疏帧采样导致信息丢失**：为解决长度限制，常见做法是对视频帧进行稀疏且均匀的采样，但这会不可避免地丢失关键细节和长程时间依赖关系。
*   **整体含义（研究动机）**：人类记忆可通过“巩固”过程，动态整合重要事件到长期记忆中。受此启发，本文旨在开发一种**无需额外训练**的框架，使现有为短视频设计的模型能够高效处理任意长度的视频，并且能像人类注意力一样，动态地给予视频中更相关的片段以更高的处理“粒度”，从而避免关键信息丢失。

### 2. 论文提出的方法论

*   **核心思想**：通过在现成的视频Q-former（如Video-LLaMA或VideoChat2中的模块）中，引入一个基于**连续时间的长期记忆（Continuous-Time LTM）** 巩固机制，来扩展其处理无限长视频的能力。整个过程**无需训练**，只需单次遍历视频。
*   **关键技术细节与算法流程**：
    1.  **视频分块与短期记忆**：将长视频序列分割成多个时间块（chunk）。在每个块内，模型原有的离散注意力机制充当**短期记忆（STM）**，处理当前块的帧。
    2.  **连续信号表示**：为了构建连续时间记忆，先将每帧的嵌入向量进行平均池化，得到一个离散序列。然后，使用**多元岭回归**将其拟合成一个定义在单位区间 `[0, 1]` 上的连续信号 `x(t)`，其中 `t` 为时间索引。
    3.  **连续时间注意力（LTM的核心）**：
        *   用查询（Query）向量和连续信号 `x(t)` 产生的键（Key）向量计算连续查询-键相似度函数 `s(t)`。
        *   基于此相似度，构建一个**吉布斯密度函数（Gibbs PDF）** `p(t)` 替代传统的softmax，作为连续注意力分布。这比之前工作中使用的高斯分布更为强大。
        *   最终，长期记忆的上下文表示 `Z_LTM` 被计算为在该注意力密度 `p(t)` 下，连续值（Value）信号 `v(t)` 的期望值。
    4.  **记忆巩固与更新**：当处理新的视频块时，执行一个“压缩-采样-拼接-回归”的循环：
        *   **压缩**：通过一个遗忘因子 `τ` 将旧LTM信号 `x(t)` 压缩到 `[0, τ]` 区间。
        *   **采样**：在 `[0, τ]` 区间内采样 `T` 个点，得到对过去记忆的离散表征。采样方式可分为**均匀采样**和基于历史注意力密度的**“粘性”记忆采样**，后者会分配更多“内存空间”给过往视频中的高相关度区域。
        *   **拼接与回归**：将采样得到的过去表征与当前块的新表征拼接，再次通过岭回归生成更新后的连续信号，完成一次记忆巩固。
    5.  **最终输出**：每个视频块经处理会输出一个综合了STM和LTM的上下文向量：`Z = αZ_STM + (1 - α)Z_LTM`，其中 `α` 是平衡因子。所有块的表示通过运行平均进行聚合，最后送入LLM生成答案。

### 3. 实验设计

*   **使用的数据集**：
    *   **多项选择问答**：NeXT-QA（短视频）、EgoSchema（中等长度视频）、Video-MME（超长视频，最长1小时）。
    *   **开放式问答**：MovieChat-1K（长视频）。
*   **基准模型**：评测体系分为三类进行对比。
    1.  **基于私有LLM的训练无关方法**：如LLoVi、VideoAgent、VideoTree（均以GPT-4为骨干）。
    2.  **Video-LLaMA系列模型**：原版Video-LLaMA，及其训练无关变体MovieChat、MovieChat+。
    3.  **VideoChat2系列模型**：原版VideoChat2。
    此外，还对比了∞-Video自身的变体，如`∞-Video (No LTM)` (即`α=1`)、`∞-Video (Uniform)` 和 `∞-Video (Sticky)`。
*   **对比方法与评估指标**：
    *   **多项选择任务**：评估准确率。
    *   **开放式生成任务**：使用GPT-3.5来评判答案的正确性/相关度，并输出一个0-5的置信度分数，以及正确性、细节导向、上下文理解等定性指标的分数。

### 4. 资源与算力

*   **算力说明**：论文中**未明确提及**进行推理评测所用的GPU型号、数量或具体耗时。因其方法是**训练无关**的，所以不涉及模型训练阶段的算力报告，其资源消耗主要体现在推理阶段的计算和存储开销上。

### 5. 实验数量与充分性

*   **实验数量**：实验覆盖了**4个**不同类型的视频问答数据集，从短视频到超长视频，从多项选择到开放式生成。在Video-LLaMA和VideoChat2两个骨干模型上分别进行了评测，并对比了多种同类方法和自身变体。此外，论文还包括了消融实验（分析`α`和基函数数量`N`的影响）和定性分析（注意力密度可视化）。
*   **充分性与公平性**：实验设计较为**充分和公平**。
    *   **充分性**：覆盖了多维度任务和视频长度，验证了方法的普适性。
    *   **公平性**：对比对象包括了相同骨干模型的不同工作模式（有无LTM、采样方式）以及同期其他训练无关的方法，具有可比性。对于VideoChat2这个本身在NeXT-QA上已高度优化的模型，提升不明显是可预期的，这恰恰反映了实验的客观性。消融实验也为理解关键超参数的影响提供了依据。

### 6. 论文的主要结论与发现

*   本文提出的`∞-Video`框架，成功地在**不额外训练**的情况下，使预训练的短视频语言模型（如Video-LLaMA和VideoChat2）能够处理任意长度的视频。
*   **“粘性”记忆机制有效性显著**：相比均匀采样，基于历史注意力密度进行重点采样的“粘性”记忆，在绝大多数任务上带来了更显著的性能提升，尤其是在Video-LLaMA模型上。这表明动态分配更高粒度给关键帧是有效的。
*   **在长视频上优势明显**：在EgoSchema， Video-MME和MovieChat-1K等长视频基准上，配备“粘性”记忆的`∞-Video LLaMA`显著优于未使用LTM的版本和其他训练无关方法，验证了其处理长程依赖的能力。
*   **模型无关性**：该方法在Video-LLaMA和VideoChat2两种不同架构上均展现出有效性，证明其作为一种通用扩展模块的潜力。

### 7. 优点

*   **训练无关**：最大的亮点，无需昂贵的微调或预训练，即可“即插即用”地扩展已有模型的能力，降低了使用门槛和计算成本。
*   **理论新颖性**：将连续时间注意力机制创造性地应用于视频领域，并提出基于吉布斯密度的更强连续注意力形式。其“粘性”记忆概念模仿了人脑的记忆巩固机制，设计巧妙。
*   **单次遍历处理**：模型只需按时间顺序观看一次视频，即可建立起用于问答的全局记忆，符合流式处理场景。
*   **可解释性强**：通过对连续注意力密度进行可视化，可以直观地看到模型关注了视频中的哪些关键片段，为理解模型行为提供了窗口。

### 8. 不足与局限

*   **基础模型能力依赖**：作为“训练无关”的扩展方法，其性能上限受限于作为基础的短视频模型本身的能力。例如，如果基础模型在某个领域（如NeXT-QA）已经性能饱和，该方法带来的提升有限。
*   **超参数敏感性**：方法包含若干关键超参数（如LTM权重 `α`、基函数数量 `N`、遗忘因子 `τ`），论文中的消融实验表明不同参数对性能有影响，其最优设置可能需要针对不同任务进行调整。
*   **计算与内存开销**：尽管无需训练，但引入连续信号拟合、积分运算、以及维护和更新长期记忆等操作，相比原始模型的简单帧采样，必然增加了推理时的计算复杂度和内存占用，论文未对此进行定量分析。
*   **视频特征的压缩损失**：为构建连续信号，对每帧内的多个补丁（patch）嵌入进行了平均池化，这可能丢失了目标级别的细粒度空间信息。

（完）
