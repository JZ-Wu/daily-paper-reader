---
title: "MMInference: Accelerating Pre-filling for Long-Context Visual Language Models via Modality-Aware Permutation Sparse Attention"
title_zh: MMInference：通过模态感知置换稀疏注意力加速长上下文视觉语言模型预填充
authors: "Yucheng Li, Huiqiang Jiang, Chengruidong Zhang, Qianhui Wu, Xufang Luo, Surin Ahn, Amir H. Abdi, Dongsheng Li, Jianfeng Gao, Yuqing Yang, Lili Qiu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=me6PfbATWM"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 针对长上下文 VLM 的动态稀疏注意力，通过模态感知模式加速预填充，可用于高效视频推理
tldr: 为解决长上下文视觉语言模型预填充阶段的二次复杂度问题，提出 MMInference 动态稀疏注意力方法，利用视频时空局部性导致的网格稀疏模式和跨模态不同分布，加速长视频推理，提升视频理解效率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 657, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1711, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1729, \"height\": 1269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1347, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1653, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 859, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 821, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1083, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1349, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1375, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1373, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 895, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 799, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 901, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 893, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 889, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 895, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 895, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1154, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 894, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 880, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1042, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1686, \"height\": 1799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-me6pfbatwm/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1690, \"height\": 887, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1756, \"height\": 986, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 747, \"height\": 853, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1597, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1323, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 906, \"height\": 1180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-me6pfbatwm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1711, \"height\": 1232, \"label\": \"Table\"}]"
motivation: 长上下文 VLM 预填充阶段注意力二次复杂度阻碍实际部署。
method: 分析视频输入网格稀疏模式与模态差异，设计模态感知置换稀疏注意力。
result: 动态稀疏注意力有效加速长上下文多模态预填充。
conclusion: MMInference 为长视频 VLM 推理提供了高效加速方案。
---

## Abstract
The integration of long-context capabilities with visual understanding unlocks unprecedented potential for Vision Language Models (VLMs). However, the quadratic attention complexity during the pre-filling phase remains a significant obstacle to real-world deployment. To overcome this limitation, we introduce MMInference (Multimodality Million tokens Inference), a dynamic sparse attention method that accelerates the prefilling stage for long-context multi-modal inputs. First, our analysis reveals that the temporal and spatial locality of video input leads to a unique sparse pattern, the Grid pattern. Simultaneously, VLMs exhibit markedly different sparse distributions across different modalities. We introduce a permutation-based method to leverage the unique Grid pattern and handle modality boundary issues. By offline search the optimal sparse patterns for each head, MMInference constructs the sparse distribution dynamically based on the input. We also provide optimized GPU kernels for efficient sparse computations. Notably, MMInference integrates seamlessly into existing VLM pipelines without any model modifications or fine-tuning. Experiments on multi-modal benchmarks-including Video QA, Captioning, VisionNIAH, and Mixed-Modality NIAH-with state-of-the-art long-context VLMs (LongVila, LlavaVideo, VideoChat-Flash, Qwen2.5-VL) show that MMInference accelerates the pre-filling stage by up to 8.3x at 1M tokens while maintaining accuracy. Our code is available at https://ama.ms/MMInference.

---

## 论文详细总结（自动生成）

好的，这是对论文《MMInference: Accelerating Pre-filling for Long-Context Visual Language Models via Modality-Aware Permutation Sparse Attention》的详细中文总结。

### 1. 论文的核心问题与整体含义
*   **研究背景与动机**：视觉语言模型（VLMs）通过集成超长上下文能力，在处理长视频、混合图文输入等任务中展现出巨大潜力。然而，其核心的自注意力机制计算复杂度随输入长度呈平方级增长，导致在“预填充”阶段产生极高的时间延迟（可达数分钟），严重阻碍了模型的实时部署与应用。
*   **核心问题**：如何在不修改模型结构、不牺牲模型性能的前提下，大幅加速长上下文VLM在预填充阶段的推理速度。

### 2. 论文提出的方法论：MMInference
论文提出了一个名为 **MMInference** 的动态稀疏注意力框架，它通过离线搜索最优稀疏模式，并在推理时在线动态构建稀疏索引，从而跳过大部分冗余的注意力计算。其核心思想在于发现并利用VLM注意力机制中独特的、与模态相关的稀疏模式。

*   **关键发现与核心技术细节**：
    1.  **网格模式（Grid Pattern）发现**：视频输入的时空局部性导致某些注意力头呈现出规整的“网格”状稀疏模式，即注意力权重集中在等间距的垂直与水平线上。这是超越纯文本大模型稀疏模式的独特发现。
    2.  **模态边界分离**：混合模态（图文交错）的输入会形成清晰的“模态边界”，导致注意力在跨模态区域（如文本到图像）与模态内区域的行为截然不同，呈现不连续性。
    3.  **基于置换的稀疏注意力**：
        *   **网格头处理**：通过一种**行列置换**方法，将原本离散的网格稀疏索引在内存中聚集为连续块，使其能够被硬件高效的块稀疏矩阵计算单元（如Tensor Cores）高效处理。
        *   **混合模态头处理**：针对`Q-Boundary`（查询维度有边界）和`2D-Boundary`（查询、键维度均有边界）两种跨模态模式，提出**模态感知置换**。该方法将属于同一模态的查询（Q）、键（K）、值（V）向量物理地“聚合”在一起，使得模态内稀疏模式可以在各自区域内独立、连续地应用，从而消除边界带来的计算碎片化问题。
    4.  **模态感知稀疏模式搜索算法**：离线阶段，在给定的计算量预算下，对每一层、每一个注意力头，分别在**模态内**和**跨模态**搜索空间内，通过评估注意力召回率来寻找最优稀疏模式（A-shape, Vertical-Slash, Grid等）及其超参数（如网格步长）。

*   **算法流程简述**：
    1.  **离线搜索**：使用少量校准数据，为模型的每个注意力头确定其属于哪种稀疏模式（网格、垂直斜线、A形等）以及是否需处理模态边界（Q-/2D-Boundary），并记录最优配置。
    2.  **在线动态预估**：实际推理时，利用每个模态末尾的少量查询向量（最后64个）与所有键向量快速计算一个近似的注意力矩阵。
    3.  **动态索引构建与置换**：根据离线确定的本头模式，在近似注意力矩阵上以极低开销（O(n)）在线搜索出具体的稀疏索引（如网格的步长和相位），然后对Q、K、V执行相应的置换操作。
    4.  **高效计算**：调用论文提供的优化GPU内核，对置换后的连续块执行块稀疏的FlashAttention计算。

### 3. 实验设计
*   **使用的数据集与评测基准**：
    *   **长视频理解**：VideoDC（视频描述）、ActNet-QA、EgoSchema、Next-QA、PerceptionTest、VideoMME（视频问答）。输入从110帧到256帧不等。
    *   **长视频检索**：Video Needle-in-a-Haystack (V-NIAH)。
    *   **混合模态检索**：论文新提出的Mixed-Modality Needle-in-a-Haystack (MM-NIAH)，用于评估模型在图文交错输入下的检索能力。
*   **对比的方法**：与多种训练无关的稀疏或压缩方法进行了对比，包括：
    *   静态稀疏模式：A-shape、Tri-shape、Sparse Transformer的Fixed和Strided模式。
    *   动态稀疏方法：MInference。
    *   视觉令牌压缩方法：VisionZip。
    *   基准线：完整的FlashAttention-2。

### 4. 资源与算力
*   **硬件**：论文明确提到，所有延迟实验均在**单张NVIDIA A100 GPU**上完成，使用bfloat16精度进行推理。
*   **搜索开销**：模态感知的稀疏模式搜索（离线一次性进行）在单张A100上耗时约**15分钟**。
*   **模型**：实验基于开源的7B参数规模VLM。

### 5. 实验数量与充分性
*   **实验规模**：实验覆盖全面，可归为以下几个层次：
    1.  **基线对比实验**：在4个领先的长上下文VLM（Llava-Video、LongVila、VideoChat-Flash、Qwen2.5-VL）上，于6个长视频理解基准上，与6种不同方法进行了全面的性能对比。
    2.  **长上下文检索压力测试**：在V-NIAH和MM-NIAH两个任务上，对多种稀疏方法进行了上下文长度从300帧拉伸至6000帧（约110万tokens）的极限性能测试。
    3.  **效率测试**：对比了端到端延迟和单注意力核在不同上下文长度下的延迟，提供了详细的加速比。
    4.  **分析与消融实验**：包括稀疏模式随模态转换的可视化、稀疏索引跨模态泛化能力的分析、以及所提方法与令牌压缩技术（VideoChat-Flash）的兼容性测试。
*   **公平性**：实验设置详细，对比时尽量控制了FLOPs变量，例如调整A-shape等窗口大小以对齐计算量。评测指标使用各基准的官方标准，确保了比较的客观与公平。

### 6. 论文的主要结论与发现
*   MMInference能够在**不损失模型精度**的情况下，显著加速长上下文VLMs的预填充阶段。在视频理解任务上，其性能与完整注意力机制几乎持平。
*   在延迟方面，处理百万级令牌的输入时，MMInference相比FlashAttention可实现最高**8.3倍**的端到端加速。
*   VLMs的注意力头呈现出比纯文本LLM更丰富的稀疏模式，尤其是视频输入引发的**网格模式**，以及**模态边界**导致的稀疏分布不连续性。有效利用这些模式是实现高效加速的关键。

### 7. 优点
*   **系统-算法协同设计**：不是简单的“补丁”式稀疏，而是从算法模式发现到硬件高效内核的一体化垂直优化，尤其是置换策略，巧妙地将稀疏加载转换为硬件友好的密集计算。
*   **即插即用**：无需任何模型训练或微调，可无缝集成到现有VLM推理流程中。
*   **处理混合模态的独创性**：首次深入分析并有效解决了混合多模态输入场景下的模态边界问题，这在实际应用（如多轮图文对话）中至关重要。
*   **发现新知识**：揭示了VLM特有的“网格”注意力模式，为理解和优化多模态模型提供了新的视角。

### 8. 不足与局限
*   **实验模型规模**：实验仅在7B参数级别的模型上进行，未验证该方法在更大规模（如13B、34B或更大）VLM上的有效性和加速比。
*   **泛化性局限**：所识别的模式主要基于特定的视频编码方式（基于帧的、规则采样），对于未来可能出现的非规则结构的多模态输入，模式可能发生变化，需要重新探索。
*   **评价基准偏向**：虽然基准覆盖广，但主要集中于视频理解和检索。对于多模态对话、具身智能等更复杂的交互式多模态场景，效果有待进一步检验。

（完）
