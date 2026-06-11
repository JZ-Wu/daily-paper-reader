---
title: "$\\mathcal{V}ista\\mathcal{DPO}$: Video Hierarchical Spatial-Temporal Direct Preference Optimization for Large Video Models"
title_zh: VistaDPO：面向大视频模型的视频层次时空直接偏好优化
authors: "Haojian Huang, Haodong Chen, Shengqiong Wu, Meng Luo, Jinlan Fu, Xinya Du, Hanwang Zhang, Hao Fei"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=O2jukIZR50"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 提出VistaDPO，用于层次化视频-文本对齐的大视频模型
tldr: 针对大视频模型存在的与人类意图不一致和幻觉问题，提出VistaDPO框架，通过实例、时序、感知三层次直接偏好优化，增强视频内容与文本的细粒度对齐。实验结果表明该方法能有效提升视频理解性能，该框架无需额外标注数据，利用偏好优化策略，使模型输出与人类期望更贴合，为训练高效视频理解模型开辟了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1744, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1778, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 742, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1687, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1318, \"height\": 1051, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1767, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1396, \"height\": 173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1382, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1401, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-o2jukizr50/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1379, \"height\": 168, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 865, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1751, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-o2jukizr50/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 388, \"label\": \"Table\"}]"
motivation: 大视频模型与人类偏好的错位及视频幻觉问题。
method: 提出VistaDPO，在实例、时序、感知三层次上进行直接偏好优化对齐。
result: 通过层次化对齐，提升了视频文本匹配的准确性和可靠性。
conclusion: VistaDPO为提升大视频模型的视频理解能力提供了有效方案。
---

## Abstract
Large Video Models (LVMs) built upon Large Language Models (LLMs) have shown promise in video understanding but often suffer from misalignment with human intuition and video hallucination issues. 
To address these challenges, we introduce **VistaDPO**, a novel framework for Video Hierarchical Spatial-Temporal Direct Preference Optimization. VistaDPO enhances text-video preference alignment across three hierarchical levels: 
i) **Instance Level**, aligning overall video content with responses; 
ii) **Temporal Level**, aligning video temporal semantics with event descriptions; 
and iii) **Perceptive Level**, aligning spatial objects with language tokens. 
Given the lack of datasets for fine-grained video-language preference alignment, we construct **VistaDPO-7k**, a dataset of 7.2K QA pairs annotated with chosen and rejected responses, along with spatial-temporal grounding information such as timestamps, keyframes, and bounding boxes. Extensive experiments on benchmarks such as Video Hallucination, Video QA, and Captioning performance tasks demonstrate that VistaDPO significantly improves the performance of existing LVMs, effectively mitigating video-language misalignment and hallucination.

---

## 论文详细总结（自动生成）

好的，我将基于提供的论文内容，为您生成一份结构化的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的大型视频模型（Large Video Models, LVMs）虽然展现出强大的视频理解能力，但普遍存在两个关键问题：
    - **与人类直觉错位（Misalignment）**：模型输出的内容可能偏离用户指令或视频实际内容。
    - **视频幻觉（Video Hallucination）**：模型生成的信息在视频中并不存在，或与视频内容不符。
- **研究背景与动机**：
    - 当前LVMs的架构通常是将视频编码器与大语言模型（LLM）通过一个简单的连接器集成，但LLM强大的语言先验可能导致其过度自信地基于编码器可能产生的偏差或错误感知来生成输出。
    - 有监督微调（SFT）可以部分缓解此问题，但依赖海量高质量标注数据。
    - 直接偏好优化（DPO）作为一种有前景的替代方案，通过让模型学习偏好“选择”而非“拒绝”的回答来与人类偏好对齐，降低了对精细标注数据的依赖。
    - 现有的多模态DPO工作（如Hound-DPO）直接将其应用于视频-语言模型，但存在**两大局限**：
        1.  **未充分考虑视频的时序特性**，将其等同于静态图片处理。
        2.  **仅进行粗粒度（实例级）对齐**，忽略了视频内容与文本在细粒度层面的对应关系。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

本论文提出了 **VistaDPO**，一个新颖的视频层次时空直接偏好优化框架，旨在对LVMs进行细粒度、多层次的对齐。

- **核心思想**：在**实例级（Instance）、时序级（Temporal）、感知级（Perceptive）** 三个层次结构上，优化模型对视频内容和对应文本的偏好选择，从而实现更精确的跨模态对齐。

- **关键技术细节与三个优化层级**：
    1.  **实例级语义偏好优化 (Instance-wise Semantic Preference Optimization)**：
        - **回答级对齐 (Response-Level Alignment)**：在标准DPO基础上，不仅区分首选的（chosen）和次选的（rejected）回答，还将“次选回答”进一步细分为：
            - **相关但非首选（Relevant Non-Preferred, `y_re`）**：回答与视频相关，但包含空间或时序上的不一致性。
            - **无关回答（Irrelevant Non-Preferred, `y_ir`）**：回答内容与视频完全无关。
            - 通过对这两种不同性质的负样本进行加权联合优化，更有效地对抗幻觉。
        - **视频级对齐 (Video-Level Alignment)**：首次引入视频级别的偏好优化。模型不仅需要区分好的文本回答，还要能分辨与查询相关的完整视频（`v_vw`）和无关视频（`v_vl`），从而减轻LVMs对语言先验的过度依赖。
    2.  **时序语义偏好优化 (Temporal Semantic Preference Optimization)**：
        - **片段级对齐 (Clip-Level Alignment)**：将视频中与提示（Prompt）相关的时间片段（如某事件发生的时间段）视为首选片段（`v_cw`），将无关片段视为非首选片段（`v_cl`），通过偏好优化使模型学会定位和对齐关键的时序动态信息。
    3.  **感知空间-物体偏好优化 (Perceptive Spatial-Object Preference Optimization)**：
        - **物体级空间对齐 (Object-Level Spatial Alignment)**：在空间层面，将与提示相关的关键帧（`v_fw`）作为首选实例，而对非首选样本（`v_fl`）进行关键区域掩码（Masking）操作，迫使模型关注正确的空间内容和物体关系。
        - **令牌级对齐 (Token-Level Alignment)**：引入基于TDPO（Token-level DPO）的方法，在更细粒度的令牌级别进行优化，精确评估和对齐单个单词（如“跑” vs “走”）与视频内容的匹配度，解决短语级别的错误。

- **总体优化目标**：
    VistaDPO的最终损失函数 `L_VistaDPO` 是上述各项损失的加权求和：
    `L_VistaDPO = (L_DPO_v + L_DPO_r) + λ*L_DPO_c + μ*L_DPO_o + ρ*L_DPO_t`
    其中 `λ`, `μ`, `ρ` 为各项损失的权重系数。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
    - **训练集**：作者专门为此框架构建并开源了 **VistaDPO-7k** 数据集，包含7.2K个高质量的问答对。该数据集整合自14个主流视频数据集，并进行了精细的人工标注，包括选择/拒绝的回答，以及时间戳、关键帧、物体边界框等时空定位信息。
- **基准测试与评估场景**：
    - **视频幻觉**：VideoHallucer, EventHallusion
    - **通用视频问答**：MSVD-QA, MSR-VTT-QA, TGIF-QA, ActivityNet-QA
    - **视频描述性能**：VideoChatGPT-Bench（从正确性、细节、上下文、时序、一致性五个维度评估）
    - **综合视频理解**：MVBench
- **基线与对比方法**：
    - **主要基线**：PLLaVA (7B) 和 Video-LLaVA (7B)。
    - **直接对比方法**：主要在基线模型上应用 **Hound-DPO**（之前的视频DPO工作）作为直接对比对象。
    - **其他参考模型**：VideoChatGPT, VideoChat2, LLaMA-VID, LLaMA-Adapter, Video-LLaMA，提供了更广泛的结果参照。

### 4. 资源与算力

- **GPU型号**：论文提到使用 **H100 GPU** 进行训练。
- **算力细节**：
    - **训练轮数**：3个epochs。
    - **批次大小**：8。
    - **学习率**：5e-7。
    - 论文未明确提及训练所需的总时长或GPU卡的具体数量。

### 5. 实验数量与充分性

- **实验数量**：实验设计非常全面，包含**多个层级**。
    - **主实验结果**：在2个基线模型（PLLaVA, Video-LLaVA）上，与Hound-DPO，在**2个幻觉基准**、**4个QA基准**、**1个Captioning基准**（包含5个维度）和**1个综合基准**上进行了全面对比。
    - **消融研究**：系统性地移除了时序级(`L_DPO_c`)、物体级(`L_DPO_o`)、令牌级(`L_DPO_t`)和回答级(`L_DPO_r`)的优化项，验证了每个层次的必要性。
    - **超参数分析**：对损失权重(`λ`, `μ`, `ρ`)以及相关/无关回答的权重进行了消融实验。
    - **表示分析**：通过T-SNE可视化模型表征，验证了VistaDPO能更好地区分幻觉与非幻觉内容。
    - **对抗性测试**：针对性地设计了**时序对抗**（反转视频）、**空间对抗**（掩码关键物体）和**令牌对抗**（替换近义词）测试，评估模型的鲁棒性。
    - **负样本构建分析**：在视频、片段、物体三个级别，探索了多种负样本构建策略（如随机、黑屏、倒序、掩码、移动物体等）对性能的影响。
- **充分性、客观性与公平性**：
    - **充分性**：实验非常充分，不仅验证了最终性能，还通过多层次消融和深入分析揭示了方法有效性的内在机理。
    - **客观性与公平性**：与最强的直接竞争对手Hound-DPO在完全相同的基线模型上进行训练和评估，对比公平。使用了多个公开的、广泛采用的基准数据集，评估客观。

### 6. 论文的主要结论与发现

1.  **显著提升性能**：VistaDPO在多种视频理解任务上，包括幻觉缓解、QA和描述生成，均能显著且一致地提升现有LVMs的性能。例如，在VideoHallucer上，相较于Hound-DPO，VistaDPO在PLLaVA和Video-LLaVA模型上的“Hallucinated”指标取得了29.9%和217.2%的惊人相对提升。
2.  **有效缓解幻觉**：通过层次化时空偏好优化，VistaDPO能有效缓解视频-语言错位和幻觉问题，而现有方法（如Hound-DPO）在某些情况下甚至可能引入新的问题（如基本能力下降）。
3.  **层次化优化的必要性**：消融实验证实，实例、时序和感知三个层级（包括回答级、视频级、片段级、物体级和令牌级）的细粒度对齐都对最终性能有正向贡献，证明了框架设计的有效性。
4.  **增强模型鲁棒性**：对抗性测试结果表明，VistaDPO显著提升了模型对时序、空间和令牌层面扰动的鲁棒性。
5.  **高质量数据集的价值**：使用VistaDPO-7k数据集，即使在标准DPO策略下也能超越Hound-DPO，证明了丰富和高质量标注数据的重要性。

### 7. 优点：方法或实验设计上有哪些亮点

- **创新的层次化对齐框架**：首次在视频DPO中系统性地引入实例、时序、感知三个层次的对齐，实现了从全局到局部、从静态到动态的细粒度优化，这是区别于以往方法的核心创新。
- **精细的负样本设计**：将负样本区分为“相关但错误”和“完全无关”，并在视频、片段、物体等多层级设计针对性的非首选样本，能更有效地引导模型学习精准的跨模态对应关系。
- **全面的实验验证与分析**：实验设计极其详尽，不仅是简单的性能对比，还包含了多维度消融、表征可视化、超参数分析以及多种富有洞察力的对抗性测试，对方法的有效性和鲁棒性进行了深入的剖绘。
- **高质量数据集的构建与开源**：构建并计划开源VistaDPO-7k数据集，为后续研究提供了宝贵的资源。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **长视频处理能力有限**：论文在局限性部分明确指出，VistaDPO在处理具有复杂时序依赖关系的长视频时，性能仍有提升空间。这是视频理解领域的普适性挑战。
- **模型和数据集规模**：实验主要在7B规模的LVMs上进行，并未在更大（如13B、34B）或更多样化的模型架构上验证其可扩展性。
- **偏差风险**：尽管论文提及了负责任的AI，但与其他基于偏好对齐的方法类似，VistaDPO-7k数据集中的人工标注偏好可能会引入标注者的主观偏见。论文未对此类潜在偏差进行深入分析和评估。
- **对抗性测试的局限性**：对抗性测试多为案例展示或特定子集测试，缺少在更大规模对抗性数据集上的系统性量化评估。

（完）
