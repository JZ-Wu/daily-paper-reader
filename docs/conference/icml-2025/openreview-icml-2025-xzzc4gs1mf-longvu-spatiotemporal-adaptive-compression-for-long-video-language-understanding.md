---
title: "LongVU: Spatiotemporal Adaptive Compression for Long Video-Language Understanding"
title_zh: LongVU：面向长视频语言理解的时空自适应压缩
authors: "Xiaoqian Shen, Yunyang Xiong, Changsheng Zhao, Lemeng Wu, Jun Chen, Chenchen Zhu, Zechun Liu, Fanyi Xiao, Balakrishnan Varadarajan, Florian Bordes, Zhuang Liu, Hu Xu, Hyunwoo J. Kim, Bilge Soran, Raghuraman Krishnamoorthi, Mohamed Elhoseiny, Vikas Chandra"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=XzZC4gs1mf"
tags: ["query:tf-vl-ag"]
score: 8.0
evidence: 提出LongVU时空自适应压缩机制，减少视频令牌以实现高效的MLLM长视频理解
tldr: 为解决多模态大模型处理长视频时上下文长度限制的问题，提出LongVU时空自适应压缩方法，利用跨模态查询和帧间依赖分别减少时间和空间冗余，在保持视频细节的同时大幅降低令牌数量，实现了高效的长视频理解。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1730, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 847, \"height\": 1227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1726, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1667, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xzzc4gs1mf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1702, \"height\": 946, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1686, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1601, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1567, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1044, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1462, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1605, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1300, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1700, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1685, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1080, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1258, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1260, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1259, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1258, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1260, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xzzc4gs1mf/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1256, \"height\": 208, \"label\": \"Table\"}]"
motivation: 多模态LLM处理长视频受限于上下文长度，需要降低视频令牌数量。
method: 提出LongVU，基于DINOv2去除相似冗余帧，并利用文本引导的跨模态查询选择性减少帧特征。
result: 在长视频理解任务中，以更少的令牌保持了视觉细节，高效提升了处理能力。
conclusion: LongVU为长视频的多模态理解提供了高效的压缩方案，拓展了LLM的视频处理范围。
---

## Abstract
Multimodal Large Language Models (MLLMs) have shown promising progress in understanding and analyzing video content. However, processing long videos remains a significant challenge constrained by LLM's context size. To address this limitation, we propose \textbf{LongVU}, a spatiotemporal adaptive compression mechanism that reduces the number of video tokens while preserving visual details of long videos. Our idea is based on leveraging cross-modal query and inter-frame dependencies to adaptively reduce temporal and spatial redundancy in videos. Specifically, we leverage DINOv2 features to remove redundant frames that exhibit high similarity. Then we utilize text-guided cross-modal query for selective frame feature reduction. Further, we perform spatial token reduction across frames based on their temporal dependencies. Our adaptive compression strategy effectively processes a large number of frames with little visual information loss within given context length. Our LongVU consistently surpass existing methods across a variety of video understanding benchmarks, especially on hour-long video understanding tasks such as VideoMME and MLVU. Given a light-weight LLM, our LongVU also scales effectively into a smaller size with state-of-the-art video understanding performance.

---

## 论文详细总结（自动生成）

好的，请查收基于您提供的论文内容生成的中文详细总结。

### 论文核心问题与整体含义

*   **核心问题**：多模态大语言模型在理解和分析视频内容方面展现出了潜力，但处理长视频（如小时级视频）仍是一个重大挑战。这主要是因为LLM的上下文长度有限，无法容纳从长视频中提取的大量视觉令牌。
*   **研究动机**：现有方法通常采用均匀采样或密集采样来处理视频，但这两种方式都存在明显缺陷。均匀采样会遗漏关键帧，而密集采样则容易超出上下文窗口限制，导致令牌被截断，丢失信息。因此，研究旨在解决如何在有限的上下文长度内，有效处理长视频并尽可能保留关键视觉细节这一难题。

### 论文提出的方法论

*   **核心思想**：提出了一种名为 **LongVU** 的时空自适应压缩机制，通过利用跨模态查询和帧间依赖性，自适应地减少视频中的时间冗余和空间冗余，从而在有限的上下文窗口内处理大量帧。
*   **关键技术细节与流程**：
    1.  **帧特征提取与时序减少**：
        *   利用自监督模型 **DINOv2** 提取每帧特征，因为它能比视觉-语言对比模型（如 SigLIP）更有效地捕捉细微的帧间差异和低级视觉特征。
        *   在滑动窗口内计算 DINOv2 特征的平均相似度，**去除高度相似的冗余帧**，实现第一步时间压缩。
    2.  **基于跨模态查询的选择性特征减少**：
        *   若剩余帧的令牌总数仍超过上下文限制，则引入**文本查询**进行交互。
        *   计算每个保留帧特征与文本查询嵌入之间的跨模态注意力得分，选择得分最高的 \( N_h \) 个关键帧保留其完整的空间分辨率（高令牌数）。
        *   对其余帧进行**空间池化**，将其压缩为低分辨率的令牌表示，以平衡细节保留与上下文长度限制。
    3.  **基于时序依赖的空间令牌压缩**：
        *   如果低分辨率令牌序列依然过长，将帧序列划分为滑动窗口（窗口大小为 \( K \)）。
        *   在每个窗口内，以第一帧为锚点，计算后续帧与第一帧在**相同空间位置**上令牌的余弦相似度。
        *   **剪枝**掉相似度高于阈值 \( \theta \) 的空间令牌（通常在静态背景中），从而进一步压缩令牌数量。

### 实验设计

*   **数据集与场景**：
    *   **训练**：分为两个阶段。图像-语言预训练使用 LLaVA-OneVision 的单图像数据集；视频-语言微调使用多个公开数据集，如 VideoChat2-IT、MovieChat、ShareGPT4Video 等。
    *   **评测基准**：在多个视频理解基准上进行评估，包括 **EgoSchema**、**MVBench**、**VideoMME**（特别关注其30-60分钟的长视频子集）和 **MLVU**（3分钟到2小时的长视频）。
*   **对比方法**：与多个开源和闭源模型进行了广泛对比。
    *   **闭源模型**：GPT-4V, GPT-4o。
    *   **开源视频MLLMs**：Video-LLaVA, LLaMA-VID, Chat-UniVi, ShareGPT4Video, LLaVA-NeXT-Video, VideoLLaMA2, LongVA, VideoChat2, LLaVA-OneVision等。
    *   **轻量级模型对比**：使用 Llama3.2-3B 的 LongVU 与 InternVL2、Phi-3.5-vision-instruct 等小模型进行了对比。

### 资源与算力

*   **算力资源**：论文明确声明，模型训练使用了 **64 块 NVIDIA H100 GPU**。
*   **训练时长**：文中未明确提及训练总时长，仅说明了训练轮数（图像预训练和视频微调均为1个epoch）及批次大小等配置。

### 实验数量与充分性

*   **实验数量**：进行了大量实验，足以支撑其结论。
    *   **主流基准测试**：在4个主要长视频理解基准上进行了全面评估，并与超过10种基线模型进行对比。
    *   **消融研究**：设计了详尽的消融实验来验证各组件的有效性，包括：
        *   每帧令牌数、上下文长度的选择。
        *   时序减少（TR）、跨模态查询（Query）、空间令牌压缩（STC）各组件的贡献。
        *   在MLVU的7个子任务上进行分项性能分析。
        *   空间令牌压缩的不同策略（锚点帧选择）。
        *   对不同阈值（DINO阈值、STC阈值）、滑动窗口大小（\( J \), \( K \)）、上下文长度等超参数的敏感性分析。
        *   添加帧级位置编码的影响。
*   **充分性与公平性**：实验设计**严谨、充分且公平**。对比基准广泛，包含了同期最先进的开源模型。消融实验清晰量化了所提每个组件的价值。在轻量级模型上的扩展实验也证明了方法的泛化能力。此外，还通过“视频大海捞针”实验从定性角度展示了长上下文信息检索能力。

### 论文的主要结论与发现

*   LongVU 提出的时空自适应压缩策略能在**大幅减少视频令牌数量的同时，有效保留视觉细节**。
*   LongVU 在多个长视频理解基准上，性能显著超越所有对比的开源模型，并缩小了与闭源模型的差距。尤其在 **VideoMME 的长视频子集**上，相比强基线 LLaVA-OneVision 有显著提升（约 **12.8%**）。
*   该框架**具有良好的可扩展性**，即使使用轻量级的LLM（Llama3.2-3B），也能取得极具竞争力的性能，证明了其在资源受限场景下的应用潜力。
*   **DINOv2 特征在消除帧级时间冗余方面比 SigLIP 特征更有效**；基于文本查询的选择性压缩和基于帧间依赖的空间压缩，对于提升长视频理解性能至关重要。

### 优点

*   **问题导向清晰**：直接针对LLM上下文窗口限制这一核心瓶颈，提出了系统性的解决方案。
*   **方法论创新且有效**：新颖地结合了 DINOv2 用于时序冗余检测和跨模态查询用于指导空间选择性压缩，三步压缩策略环环相扣，设计精巧。
*   **性能提升显著**：在多个重要基准上取得了领先结果，尤其是在实际应用价值高的超长视频任务上表现出色。
*   **实验详实透彻**：消融实验设计非常全面，不仅验证了每个模块的有效性，还对关键超参数进行了细致分析，论证充分，说服力强。

### 不足与局限

*   **视频SFT导致图像能力下降**：论文指出了在视频微调后，模型的图像理解性能会下降。虽然通过混合图像数据再次微调能恢复，但这本身是一个局限，文中方案未完全解决模态间的知识遗忘问题。
*   **时序定位能力弱**：该方法将视频帧压缩为统一的令牌序列，但未有效编码帧的绝对时间位置。模型在需要精确定位事件起止时间的**时序定位**任务上表现不佳。
*   **训练数据限制**：主要使用的视频训练数据集（VideoChat2-IT）中的长视频资源有限（多数在3分钟内），这可能限制了模型从更长视频中学习的能力，是性能进一步提升的潜在瓶颈。
*   **缺乏与训练无关压缩方法的对比**：文中虽与诸多方法对比，但未讨论和比较另一类流行的、无需训练的令牌压缩技术。
*   **训练效率未明确**：虽然推理时间有分析，但未提供所提方法在训练阶段产生的额外计算开销和总训练时长的分析。

（完）
