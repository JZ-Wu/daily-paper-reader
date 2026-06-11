---
title: "video-SALMONN-o1: Reasoning-enhanced Audio-visual Large Language Model"
title_zh: video-SALMONN-o1：面向通用视频理解的推理增强音视觉大语言模型
authors: "Guangzhi Sun, Yudong Yang, Jimin Zhuang, Changli Tang, Yixuan Li, Wei Li, Zejun MA, Chao Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=y62fhuA69I"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 提出首个开源推理增强的音视觉LLM，用于通用视频理解
tldr: 针对现有推理增强方法局限于数学和图形输入，忽视通用视频理解的问题，提出首个开源推理增强音视觉LLM video-SALMONN-o1，通过构建推理密集型数据集和过程直接偏好优化（pDPO）实现步骤级奖励，在通用视频理解任务上展现了强大的推理能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1505, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 774, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1218, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1227, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1229, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 581, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1224, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1413, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1409, \"height\": 310, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1226, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1238, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1230, \"height\": 186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1233, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1415, \"height\": 212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1414, \"height\": 211, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-y62fhua69i/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1402, \"height\": 462, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 818, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1607, \"height\": 430, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1368, \"height\": 322, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1530, \"height\": 625, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1335, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1351, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-y62fhua69i/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1607, \"height\": 193, \"label\": \"Table\"}]"
motivation: 现有推理增强主要针对数学和图形，忽视通用视频理解任务。
method: 构建推理密集型音视频问答数据集，并提出过程直接偏好优化（pDPO）进行步骤级对比奖励。
result: 在通用视频理解任务上取得优异表现，并开源了首个推理增强音视觉LLM。
conclusion: video-SALMONN-o1为视频理解领域的推理增强提供了新基准和有效方法。
---

## Abstract
While recent advancements in reasoning optimization have significantly enhanced the capabilities of large language models (LLMs), existing efforts to improve reasoning have been limited to solving mathematical problems and focusing on visual graphical inputs, neglecting broader applications in general video understanding. This paper proposes video-SALMONN-o1, the first open-source reasoning-enhanced audio-visual LLM designed for general video understanding tasks. To enhance its reasoning abilities, we develop a reasoning-intensive dataset featuring challenging audio-visual questions with step-by-step solutions. We also propose process direct preference optimization (pDPO), which leverages contrastive step selection to achieve efficient step-level reward modelling tailored for multimodal inputs. Additionally, we introduce RivaBench, the first reasoning-intensive video understanding benchmark, featuring over 4,000 high-quality, expert-curated question-answer pairs across scenarios such as standup comedy, academic presentations, and synthetic video detection. video-SALMONN-o1 achieves 3-8% accuracy improvements over the LLaVA-OneVision baseline across different video reasoning benchmarks. Besides, pDPO achieves 6-8% improvements compared to the supervised fine-tuning model on RivaBench. Enhanced reasoning enables video-SALMONN-o1 zero-shot synthetic video detection capabilities.

---

## 论文详细总结（自动生成）

好的，以下是根据论文内容生成的详细中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景与动机**：当前，通过优化推理过程来提升大语言模型（LLM）能力的研究取得了显著进展，但这些工作大多局限于解决数学问题或分析图像输入，忽视了推理能力在通用视频理解这一更广泛领域中的关键作用。
*   **核心问题**：论文旨在解决如何为音视觉（audio-visual）LLM增强推理能力，使其不仅能“看”和“听”，更能进行复杂的多步逻辑思考，从而胜任一般性的视频理解任务（如理解学术报告、脱口秀的幽默梗、识别AI合成视频等）。
*   **整体含义**：提出**video-SALMONN-o1**，是世界上首个开源的、专为通用视频理解任务打造的、具备增强推理能力的音视觉LLM，弥补了现有研究在非数学、通用视频推理领域的空白。

### 2. 论文提出的方法论

*   **核心思想**：通过构建包含推理步骤的训练数据，并设计一种更适合多模态视频输入的步骤级偏好对齐算法，来分阶段地增强模型的推理能力。
*   **关键技术细节**
    *   **模型结构**：采用一个视觉LLM作为基础，添加音频编码器分支。视频和音频分别由各自编码器处理后，通过一个**交错同步（Interleaved Synchronization）** 模块在时间维度上对齐并融合，输入给LLM主干。
    *   **推理密集型SFT数据构建**：使用Gemini-1.5-pro模型观看视频后，生成具有挑战性的问答对及逐步的解答方案，并通过GPT-4o进行质量校验，构建了一个包含约3万条数据的推理密集型监督微调（SFT）子集。
    *   **过程直接偏好优化 (pDPO)**
        *   **目的**：解决在通用视频理解任务中，标准过程奖励模型（PRM）难以直接预测绝对分数的问题。
        *   **思想**：采用成对偏好建模，让模型学习在两个推理步骤中选择“更好”的一个，而不是学习给出绝对评分。
        *   **公式与流程**：
            1.  **对比性步骤选择**：通过向视频输入施加微小的扰动，计算每个推理步骤的**KL散度**，筛选出对输入变化最敏感的、最可能出错的`T`个关键步骤。
            2.  **步骤级偏好对构建**：为选中的关键步骤`sk`采样一个替代步骤`s'k`，接着对两个步骤都进行“**rollout**”（即从该步骤出发，多次采样生成完整的解决方案路a径），并通过比较最终答案的正确率来近似估计每个步骤的期望正确性`p_sk`。这将形成`(sk > s'k)`的偏好对。
            3.  **pDPO损失函数**：基于布拉德利-特里模型定义`sk`优于`s'k`的概率，并使用DPO损失函数，最大化偏好步骤的优势，从而实现对模型的步骤级精细调优。

### 3. 实验设计

*   **提出的基准 (Benchmark)**
    *   **RivaBench**：首个专注于推理的视频理解基准，包含超过4000个由专家（如医生）精心标注的问答对，涵盖三个新场景：
        *   **学术报告 (Academic)**：理解讲座、会议报告中的复杂概念。
        *   **脱口秀 (StandUp)**：推理幽默段子“梗”在何处，需要结合语言、表情和动作。
        *   **合成视频检测 (SynthDec)**：判别视频是真实还是AI生成，需要寻找不符合物理规律或物体扭曲的线索。
*   **使用的数据集与对比方法**
    *   **评估数据集**: 除RivaBench外，还在 **Video-MME** 和 **NExT-QA** 两个具有挑战性的通用视频问答基准上进行了评测。
    *   **对比基线**：
        *   **商业模型**：GPT-4o 和 Gemini-1.5-pro。
        *   **开源模型**：LLaVA-OneVision (纯视觉基线), video-SALMONN, Video-LLaMA 2 等音视觉LLM。
        *   **自身消融**：对比了SFT模型、未进行推理训练的模型，以及使用不同奖励模型（ORM, PRM）与本方法pDPO的效果。

### 4. 资源与算力

*   **SFT阶段**：使用 **16块NVIDIA A100 GPU**，训练了 **48小时**。
*   **pDPO阶段**：使用 **8块NVIDIA A100 GPU**，训练了 **24小时**。
*   **模型底座**：视觉编码器为SigLIP，音频编码器为Whisper-Large-v3，LLM骨干为7B参数的Qwen 2，并使用LoRA进行高效训练。

### 5. 实验数量与充分性

*   **实验组数**：进行了一系列充分的实验，包括：
    *   **主实验**：在Video-MME、NExT-QA及RivaBench的三个子集上，与多个开源和商业模型进行全面对比。
    *   **SFT数据消融实验**：对比了使用/不使用推理密集型数据、推理/直接回答对性能的影响。
    *   **奖励模型消融实验**：对比了ORM（结果奖励模型）、PRM（过程奖励模型）、多数投票与本方法pDPO的性能差异。
    *   **pDPO变体消融实验**：研究了仅用完整路径对、结合全部步骤对、以及结合对比性步骤选择对（Top T步）的性能变化。
*   **充分性与客观性**：实验设计较为充分，从多个维度验证了方法的有效性，对比基线全面，消融研究逻辑清晰，具有较强的客观性和说服力。

### 6. 论文的主要结论与发现

*   **性能大幅提升**：video-SALMONN-o1在多个视频推理基准上相对于强基线LLaVA-OneVision，实现了3-8%的绝对准确率提升。
*   **pDPO方法有效**：pDPO训练相比于SFT模型，在RivaBench上带来了6-8%的显著提升，且效果优于传统的ORM和PRM，证明步骤级偏好优化在视频推理中的优越性。
*   **数据策略关键**：构建的推理密集型SFT数据对激活推理能力至关重要，但仅靠它是次优的；将推理路径融合到所有数据中，并配合直接输出答案的训练，才能获得最佳SFT性能。
*   **涌现新能力**：通过增强推理，模型获得了零样本（zero-shot）合成视频检测能力，这是其他开源模型不具备的，体现推理能力迁移的潜力。
*   **对比性步骤选择的价值**：通过对比性步骤选择，聚焦于对视频内容敏感的易错步骤进行优化，比不加区分地优化所有步骤或仅优化完整路径更有效。

### 7. 优点

*   **创新性强**：是首个将推理过程优化引入通用视频理解领域的开源工作，填补了研究空白。
*   **方法论贡献**：提出的**pDPO**是一种巧妙的方法，它利用对比性步骤选择，以较低的计算成本实现了面向多模态输入的步骤级偏好优化，避免了直接预测分数的不稳定性。
*   **基准构建有意义**：提出的**RivaBench**基准新颖且富有挑战性，将视频推理从传统的感知和因果推理提升到需要更深层理解的幽默解析、学术图表关联和AI内容鉴别，具有很高的应用价值。
*   **理论与实践结合**：通过大量消融实验，清晰揭示了SFT数据、推理路径训练和偏好优化之间的相互作用，为后续研究提供了宝贵的经验指导。
*   **可解释性强**：推理步骤的输出使模型的决策过程透明化，便于定位错误原因（如视觉幻视），增强了模型的可信赖性。

### 8. 不足与局限

*   **零样本能力有限**：尽管在合成视频检测上表现出涌现能力，但其绝对性能（F1分数）仍然较低，远未达到实用化水平。
*   **基准覆盖面**：RivaBench虽新，但仅涵盖三类场景，可能不足以全面评估模型在所有类型视频下的推理泛化能力。
*   **计算资源需求**：推理密集型数据的生成和pDPO训练中的多次rollout采样，需要大量的额外计算开销，增加了复现和扩展的门槛。
*   **推理效率**：虽然声称推理时间无额外开销，但pDPO训练本身耗时耗卡。模型在推理时进行逐步思考，会生成更长的序列，相比直接回答模型，其推理延迟会更高。
*   **依赖大模型标注**：SFT数据和偏好对的生成高度依赖Gemini和GPT-4o等闭源商业大模型，可能存在固有偏差，且数据质量无法被完全保证。

（完）
