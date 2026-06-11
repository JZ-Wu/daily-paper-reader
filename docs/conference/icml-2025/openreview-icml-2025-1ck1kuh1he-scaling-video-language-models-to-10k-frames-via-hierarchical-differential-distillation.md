---
title: Scaling Video-Language Models to 10K Frames via Hierarchical Differential Distillation
title_zh: ViLAMP：通过分层差分蒸馏将视频语言模型扩展至万帧级视频
authors: "Chuanqi Cheng, Jian Guan, Wei Wu, Rui Yan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1CK1kuH1he"
tags: ["query:tf-vl-ag"]
score: 8.0
evidence: 通过分层差分蒸馏实现高效长视频VLM处理，降低成本
tldr: 针对长视频处理中VLM计算成本高且信息压缩导致时序依赖丢失的问题，提出差分蒸馏原理，并基于此开发ViLAMP模型，通过分层差分关键帧选择和patch融合机制，以混合精度高效处理长达一小时的视频。实验证明，该方法在保持关键信息的同时显著提升效率，为低成本长视频理解提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 880, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1728, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 818, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 626, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1768, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1ck1kuh1he/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 622, \"height\": 493, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 1368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 637, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1020, \"height\": 1160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1ck1kuh1he/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 943, \"height\": 846, \"label\": \"Table\"}]"
motivation: 长视频处理计算成本高，传统令牌剪枝和特征合并易牺牲时序依赖或稀释语义。
method: 提出差分蒸馏原理，设计分层差分关键帧选择和差分patch融合的混合精度处理机制。
result: 在万帧视频上实现高效处理，保持任务相关信息的同时降低计算开销。
conclusion: 为长视频理解提供原则性高效方法，平衡信息保留与效率。
---

## Abstract
Long-form video processing fundamentally challenges vision-language models (VLMs) due to the high computational costs of handling extended temporal sequences. Existing token pruning and feature merging methods often sacrifice critical temporal dependencies or dilute semantic information. We introduce differential distillation, a principled approach that systematically preserves task-relevant information while suppressing redundancy. Based on this principle, we develop ViLAMP, a hierarchical video-language model that processes hour-long videos at "mixed precision" through two key mechanisms: (1) differential keyframe selection that maximizes query relevance while maintaining temporal distinctiveness at the frame level and (2) differential feature merging that preserves query-salient features in non-keyframes at the patch level. Hence, ViLAMP retains full information in keyframes while reducing non-keyframes to their most salient features, resembling mixed-precision training. Extensive experiments demonstrate ViLAMP's superior performance across five video understanding benchmarks, particularly on long-form content. Notably, ViLAMP can process ultra-long videos (up to 10K frames) on a single NVIDIA A100 GPU, achieving substantial computational efficiency while maintaining state-of-the-art performance. 
Code and model are available at https://github.com/steven-ccq/ViLAMP.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义
- **研究背景与动机**：随着视觉语言模型（VLMs）能力从处理单张图像扩展到长视频，面临的核心瓶颈是长视频产生的海量视觉令牌（例如，一段 1 分钟 24fps 的视频可产生超百万令牌），导致算力成本和推理延迟极高，远超主流大语言模型（LLM）的上下文窗口限制。
- **现有方法局限**：现有的令牌剪枝（Token Pruning）方法可能丢失关键的时序依赖信息，而特征合并（Feature Merging）方法则易导致语义信息稀释，无法在计算效率与信息保真度之间取得平衡。
- **核心思想与整体含义**：本文提出 **差分蒸馏（Differential Distillation）原理**，旨在系统地识别并保留与任务（查询）相关且具有时序独特性的显著信息，同时主动抑制冗余信息。基于此原理构建的模型 **ViLAMP**，通过“混合精度”的层级式压缩框架，实现了对超长视频（最高 10K 帧，约 2.7 小时）的高效、高性能理解，实质是依据信息显著性来动态分配计算资源。

### 论文提出的方法论
- **核心原理：差分蒸馏 (Differential Distillation)**
    - **问题**：如何从长视频中识别真正的显著信号？传统方法仅依赖查询相关性，但视频中存在大量时序相关和重复内容，可能选出冗余信号。
    - **初步分析发现**：
        1.  **帧级分析**：约 90% 的查询注意力权重集中在不到 5% 的帧（关键帧）上，且这些高注意力帧内部视觉相似度高（余弦相似度 > 0.8），存在显著视觉冗余。
        2.  **块级 (patch-level) 分析**：非关键帧中，约 50% 的图像块贡献了 80% 的注意力，但这些块与相邻关键帧中的对应块视觉相似度极高，表明大量算力被用于处理跨帧的冗余视觉模式。
    - **原理定义**：对任何视频组件 \( v \)，其差异信息显著性得分定义为 \( D(v) = R(v, Q) - T(v, C(v)) \)。其中 \( R(v, Q) \) 衡量与查询 \( Q \) 的相关性，\( T(v, C(v)) \) 衡量其时序上下文 \( C(v) \) 中的冗余度。得分越高，表示该信息越独特、与任务越相关，应获得更多计算资源。
- **模型架构：ViLAMP (层级式混合精度视频处理)**
    - **整体流程**：ViLAMP 通过两个层级机制实现差分蒸馏。首先，筛选出少数关键帧保留完整视觉令牌；然后，对剩余的大量非关键帧，压缩至单个令牌，但仅保留其中与查询最相关且非冗余的特征。
    - **层级一：差分关键帧选择 (Differential Keyframe Selection, DKS)**
        - **目标**：选出查询相关度高且帧间时序差异性大的关键帧。
        - **实现**：采用一种高效的贪心算法。首先，根据查询相关性对所有帧降序排序。然后，按顺序将相关性最高的帧加入关键帧集合，但要求新加入的帧与集合中已有关键帧的最大相似度低于一个阈值 \( \tau \)。该算法复杂度为 \( O(\max(NK, N\log N)) \)，\( N \) 为总帧数，\( K \) 为最大关键帧数。
    - **层级二：差分特征合并 (Differential Feature Merging, DFM)**
        - **目标**：将非关键帧压缩至单个令牌，但保留查询相关的显著特征。
        - **实现**：对于某个非关键帧及其前序最近的关键帧，计算该非关键帧内每个图像块的差分显著性得分 \( D_p \)，得分为该块的查询相关性减去其与关键帧中对应位置块的视觉相似度（作为时序冗余度）。然后，使用一个由 \( D_p \) 得分经过 softmax 函数控制的**加权池化 (Weighted Pooling)** 操作，聚合该帧所有块的嵌入，生成唯一的压缩令牌 \( t_n \)。公式为 \( t_n = \frac{\sum_{m} w_{mn} \cdot p_{mn}}{\sum_{m} w_{mn}} \)，权重 \( w_{mn} \) 由显著性得分 \( D_p \) 决定，\( \alpha \) 控制权重分布的尖锐度。
    - **多模态学习**：采用双流视觉连接器，将关键帧的完整块嵌入和非关键帧的压缩嵌入，分别通过两个独立的二层 MLP 投影到 LLM 的输入空间，并按时间顺序排列，最后通过语言建模目标进行端到端训练。

### 实验设计
- **测评基准 (Benchmarks)**：在五个视频理解基准上评测，覆盖不同时长和任务：
    - **LVBench**: 长时序决策 (`Avg. 4,101s`)。
    - **EgoSchema**: 长视频场景理解 (`180s`)。
    - **LongVideoBench**: 指称推理 (`Avg. 473s`)。
    - **MLVU**: 多任务长视频问答 (`Avg. 651s`)。
    - **Video-MME**: 综合性视频理解 (`Avg. 1,010s`)，并特别考察其子集“Long” (`>39 min`)。
    - **自建基准 VideoNIAH**: 模拟“大海捞针”范式，要求模型在长达 2K-10K 帧的“干草堆”视频中定位并理解“针”视频片段，以严格评估超长视频理解能力。
- **对比方法**：
    - **闭源商业模型**: GPT-4V, GPT-4o, Gemini-1.5-Pro。
    - **开源多图 VLM**: LLaVA-OneVision (72B, 7B), InternVL2 (76B, 8B), Oryx-1.5 (7B), Qwen2-VL (7B), NVILA (7B) 等。
    - **开源视频 VLM**: VideoLLaMA2 (72B, 7B), LLaVA-Video (7B), LLaMA-VID (7B), Video-XL (7B), LongVU (7B), LongVILA (7B) 等。

### 资源与算力
- **推理算力**：所有模型推理评估均在**单个 NVIDIA A100 GPU** 上进行。ViLAMP 能在此条件下成功处理长达 **10K 帧** 的超长视频，而多数基线模型因显存不足（Out-Of-Memory, OOM）而失败。
- **训练算力**：ViLAMP 使用 **32 块 NVIDIA A100 GPU**，训练 **1 个 epoch**，耗时约 **两周**。

### 实验数量与充分性
- **实验数量较为充分**，包含：
    1.  **主要结果对比**：1 组 5 个基准上的大规模对比实验（表 1）。
    2.  **可扩展性评估**：1 组专为超长视频设计的 VideoNIAH 基准测试（图 1、图 2），考察不同干草堆长度和针位置的性能。
    3.  **消融实验**：1 组完整的消融实验，分别验证 DKS 和 DFM 机制的有效性，并与查询引导采样、均匀采样、Q-former、均值池化等方法进行对比（表 2）。
    4.  **关键帧影响分析**：1 组分析不同关键帧数量对性能影响的实验（图 6）。
    5.  **效率分析**：1 组详细对比不同帧数下，各模型在 FLOPs、显存占用和时延（TTFT）的计算效率实验（表 5）。
    6.  **超参数敏感性分析**：1 组调整 α 和 τ 超参数的实验（表 6）。
    7.  **任务泛化性补充实验**：在视频定位（QVHighlights）和动作识别（3个基准）上的额外实验（表 3、表 4）。
- **客观性与公平性**：对比模型涵盖了多种架构（多图、视频）和参数规模（7B 至 70B+），所有基线结果均引自原论文，对比客观。消融实验在相同的数据集和训练设置下进行，保证了对比公平。

### 论文的主要结论与发现
- **有效性**：ViLAMP 在所有 5 个视频理解基准上，均超越了同等参数规模（7B 级别）的 SOTA 模型，并在长视频子集（如 Video-MME “Long”）上优势显著，甚至能媲美或超越更大规模（~70B）的开源模型及部分闭源模型（如 GPT-4o）。
- **可扩展性**：在 VideoNIAH 测试中，ViLAMP 是唯一能在单张 A100 GPU 上成功处理 10K 帧的模型，且性能随视频长度增长的下降幅度远小于基线模型（比 VideoChat-Flash 少下降 12.82%），表现出极佳的稳定性。
- **效率优势**：ViLAMP 的显存占用随输入帧数增长极缓慢，在长输入下 FLOPs 大幅减少（如 8K 帧时仅为 VideoChat-Flash 的 18.4%），推理时延也极具竞争力。
- **设计有效性**：DKS 和 DFM 两大组件均对性能有显著正向贡献，且关键帧数量存在数据集特定的饱和点，验证了设计合理性。

### 优点
- **理念新颖**：提出的“差分蒸馏”原理为长视频高效处理提供了原则性的方法论，从信息论角度同时考虑相关性和冗余度。
- **架构简洁高效**：通过“关键帧 + 压缩非关键帧”的混合精度框架，巧妙地在信息保留和计算成本间取得平衡，实现了对超长视频的端到端处理。
- **实验扎实全面**：不仅覆盖广泛的通用基准，还专门设计了高难度的 VideoNIAH 基准来测试极限能力，并对模型的计算效率进行了精细的量化分析。
- **性能与效率兼得**：在同级模型中达到最佳性能的同时，实现了对超长视频的高效处理和卓越的可扩展性，具有较强的实用价值。

### 不足与局限
- **模态限制**：研究仅关注视觉信息，未利用音轨、字幕等多模态信息，而这些在长视频中往往是重要的补充线索。
- **关键帧上限固定**：关键帧数量 \( K \) 是预先设定的，可能导致对信息量变化幅度大的视频适应性不足。
- **压缩机制依赖关键帧**：非关键帧的压缩完全依赖于前序最近的关键帧，若关键帧选择有偏差，可能造成信息丢失的连锁反应。
- **训练数据与任务覆盖**：主要在视频问答和字幕数据上训练，虽然在动作识别等任务上展现了零样本能力，但其对更复杂的视频稠密描述、事件定位等下游任务的泛化上限仍需进一步验证。

（完）
