---
title: "VideoRFT: Incentivizing Video Reasoning Capability in MLLMs via Reinforced Fine-Tuning"
title_zh: VideoRFT：通过强化微调激励多模态大语言模型的视频推理能力
authors: "Qi Wang, Yanrui Yu, Ye Yuan, Rui Mao, Tianfei Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3pORFyKzh1"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 强化微调提升MLLM视频推理
tldr: 为应对视频数据复杂逻辑和时间结构的推理挑战，提出VideoRFT，将强化微调范式扩展到多模态模型，通过思维链监督微调和强化学习阶段提升模型视频推理与泛化能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3porfykzh1/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 5544, \"height\": 3697}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3porfykzh1/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 5544, \"height\": 3697}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3porfykzh1/fig-003.webp\", \"caption\": \"\", \"page\": 8, \"index\": 3, \"width\": 2379, \"height\": 259}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3porfykzh1/fig-004.webp\", \"caption\": \"\", \"page\": 20, \"index\": 4, \"width\": 2378, \"height\": 217}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3porfykzh1/fig-005.webp\", \"caption\": \"\", \"page\": 21, \"index\": 5, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3porfykzh1/fig-006.webp\", \"caption\": \"\", \"page\": 24, \"index\": 6, \"width\": 512, \"height\": 512}]"
motivation: 现有MLLM在视频推理上仍面临复杂逻辑、时序和因果关系的挑战。
method: VideoRFT采用两阶段强化微调：先思维链监督微调，再强化学习优化泛化。
result: 在视频推理基准上取得优于监督微调基线的性能提升。
conclusion: 强化微调可有效激发多模态模型的视频推理能力。
---

## Abstract
Reinforcement fine-tuning (RFT) has shown great promise in achieving humanlevel reasoning capabilities of Large Language Models (LLMs), and has recently been extended to MLLMs. Nevertheless, reasoning about videos, which is a fundamental aspect of human intelligence, remains a persistent challenge due to the complex logic, temporal and causal structures inherent in video data. To fill this gap, we propose VideoRFT, a novel approach that extends the RFT paradigm to cultivate human-like video reasoning capabilities in MLLMs. VideoRFT follows the standard two-stage scheme in RFT: supervised fine-tuning (SFT) with chain-of-thought (CoT) annotations, followed by reinforcement learning (RL) to improve generalization. A central challenge to achieve this in the video domain lies in the scarcity of large-scale, high-quality video CoT datasets. We address this by building a multi-expert-driven, cognition-inspired CoT curation pipeline. First, we devise a cognition-inspired prompting strategy to elicit a reasoning LLM to generate preliminary CoTs based solely on rich, structured, and literal representations of video content. Subsequently, these CoTs are revised by a MLLM conditioned on the actual video, ensuring visual consistency and reducing visual hallucinations. This pipeline results in two new datasets, i.e.VideoRFT-CoT-102K for SFT and VideoRFT-RL-310K for RL. To further strengthen the RL phase, we introduce a novel semantic-consistency reward that explicitly promotes the alignment between textual reasoning and visual evidence. This reward encourages the model to produce coherent, context-aware reasoning outputs grounded in visual input. Extensive experiments show that VideoRFT achieves state-of-the-art performance on six video reasoning benchmarks.

---

## 论文详细总结（自动生成）

### 论文概述

本文《VideoRFT: Incentivizing Video Reasoning Capability in MLLMs via Reinforced Fine-Tuning》针对多模态大语言模型在复杂视频推理任务上的挑战，提出了一种名为 VideoRFT 的新框架。该框架通过强化微调范式，模拟人类的认知推理过程，显著提升了模型在视频理解基准上的性能。

---

### 1. 核心问题与整体含义

*   **研究背景与动机**：
    *   视频理解是人工智能的核心目标之一，要求模型不仅具备感知能力，还需理解事件的时间、因果逻辑。
    *   当前的多模态大语言模型大多是“答案驱动型”的，缺乏显式的、可解释的逐步推理过程。
    *   虽然强化微调在纯文本大语言模型和多模态大语言模型的图像推理上取得了成功，但将其应用于视频领域面临一个核心瓶颈：**缺乏大规模、高质量的视频思维链数据集**。现有的视频思维链数据或依赖简单模板，或缺乏视觉基础，容易产生幻觉，限制了模型的推理深度。

---

### 2. 方法论

VideoRFT 采用标准的强化微调两阶段方案，并结合一项关键的创新数据构建流程与奖励机制。

*   **核心思想**：通过一个认知启发的、多专家协作的流程，自动构建高质量的视频思维链数据，并将其用于监督微调和强化学习，从而激励模型产生类人的视频推理能力。

*   **关键技术细节与流程**：
    *   **阶段一：高质量视频思维链数据集构建**。这是论文的关键贡献，包含三个子步骤：
        1.  **结构化视频表示**：使用 MLLM为每个视频生成包含高层摘要和逐帧元数据的结构化文本描述。
        2.  **认知启发式思维链生成**：让一个纯文本推理大语言模型**仅基于**上一步的结构化文本描述和问题，通过一系列模拟人类认知的提示生成初步思维链。这些提示分别对应：模拟观察、任务理解、选择性关注、视觉推理和反思性回答。
        3.  **跨模态思维链精炼**：为解决纯文本推理产生的与视觉事实不符的“幻觉”，再次引入原始视频，让另一个 MLLM审视初步思维链与视频内容的一致性，并基于视觉证据进行修正。
    *   最终生成 **VideoRFT-CoT-102K** 和 **VideoRFT-RL-310K** 两个数据集，分别用于监督微调和强化学习。

    *   **阶段二：视频强化微调**：
        1.  **监督微调**：使用 VideoRFT-CoT-102K 数据集对基座模型进行预热训练。
        2.  **基于组相对策略优化 (GRPO)的强化学习**：使用 VideoRFT-RL-310K 数据集进行强化学习，以提升模型的泛化能力。该阶段设计了三种奖励函数：
            *   **格式奖励**：确保模型输出包含 `...` 和 `...` 等结构化标签。
            *   **准确性奖励**：根据任务类型（如多选题、数值题、开放题）评估最终答案的正确性。
            *   **语义一致性奖励**：**本文的核心算法创新**。该奖励旨在强制模型的文本推理与视觉输入对齐。其关键洞察是：模型的推理过程可分解为“问题解析”、“视频描述”和“抽象推理”三部分。语义一致性奖励通过计算“视频描述”部分的文本嵌入与视频帧视觉嵌入的余弦相似度，来衡量其视觉基础性。该奖励仅在准确性奖励非零时激活，以避免奖励看似合理但事实错误的推理。

---

### 3. 实验设计

*   **基准测试**：在六个权威视频理解和推理基准上评估，覆盖不同能力维度：
    *   **视频推理**：VSI-Bench， VideoMMMU， MMVU
    *   **视频理解**：MVBench， TempCompass， VideoMME
*   **对比方法**：与广泛的基线模型进行对比，包括：
    *   **专有模型**：GPT-4o。
    *   **开源最先进多模态大语言模型**：Qwen2.5-VL-7B， LLaVA-OneVision-7B， VILA-1.5-8B， LongVA-7B 等。
    *   **同期工作**：Video-R1， TinyLLaVA-Video-R1， VideoChat-R1 等同样探索视频强化微调的模型。

---

### 4. 资源与算力

*   训练使用了 **8 块 NVIDIA A800 GPU**，每块 80GB 显存。
*   整个训练过程包括 **1 个 epoch 的监督微调**和 **1K 步的强化学习**。
*   为提升效率，训练时视频输入限制为 16 帧，推理时则提高到 32 帧。

---

### 5. 实验数量与充分性

*   **主要实验**：在 6 个数据集上与超过 10 种不同的开源、闭源及同期模型进行了全面的性能对比，实验规模充分。
*   **消融实验**：系统性设计了诊断性实验，以验证各组件的有效性：
    *   **训练数据消融**：去除“跨模态思维链精炼”步骤。
    *   **训练范式消融**：单独使用“仅监督微调”或“仅强化学习”。
    *   **奖励函数消融**：对比仅使用格式+准确性奖励、直接添加语义一致性奖励、以及最终带有门控机制的完整奖励方案。
*   **可扩展性分析**：训练了 3B 参数版本并与同规模的同期模型对比，验证了方法在不同算力规模下的有效性。
*   **超参数分析**：研究语义一致性奖励中的缩放因子对性能的影响。
*   **分析评价**：实验设计客观、公平。通过在统一基座模型上进行多组消融实验，清晰地分离并验证了数据构建、训练范式和奖励机制各自对最终性能的贡献。

---

### 6. 主要结论与发现

*   VideoRFT 在所有六个基准测试上均**显著超越其基座模型 Qwen2.5-VL-7B**。
*   在视频推理基准上，VideoRFT 取得了**最先进的性能**，超过了所有对比的开源模型，并在部分基准上超越了 GPT-4o。
*   **“跨模态思维链精炼”**和**“语义一致性奖励”**是提升性能的关键，能有效减少幻觉，提高视觉推理的准确性。
*   模型在强化学习过程中涌现出**“顿悟时刻”**，表现为在生成最终答案前会自发地进行“等等，让我再检查一遍”这样的自我反思和验证行为。

---

### 7. 优点

*   **方法创新性**：首次将认知启发式的流程与多智能体协作引入视频思维链数据的构建，系统地解决了数据匮乏和幻觉问题。
*   **奖励设计巧妙**：提出的“语义一致性奖励”精准地针对多模态推理中的视觉基础问题，且通过门控机制避免了错误奖励，设计思想精巧且有效。
*   **工程可扩展性好**：整个思维链数据构建流程是自动化的，可扩展至大规模数据。
*   **可解释性强**：模型的“顿悟时刻”和结构化的推理过程增强了模型行为和决策的透明度。

---

### 8. 不足与局限

*   **数据构建成本**：思维链生成流水线依赖多个高性能的专家模型，这本身带来了较高的推理成本和潜在的延迟。
*   **对生成式模型的依赖**：构建的思维链数据质量高度依赖于上游推理大语言模型和多模态大语言模型的能力，可能继承这些模型的偏见。
*   **实验覆盖广度**：尽管在六个基准上取得了最先进结果，但对更复杂、更长的视频场景的泛化能力未做深入探讨。
*   **局限场景**：论文提到，在快速运动或严重遮挡等复杂视觉条件下，模型的有效性可能会受到影响，当前方法未能根本解决这些挑战。
*   **社会影响风险**：强大的视频理解能力可能被滥用于监控或生成误导性信息，论文虽然提到了这一点但未提出具体缓解措施。

---
（完）
