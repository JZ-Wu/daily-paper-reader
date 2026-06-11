---
title: "Vad-R1: Towards Video Anomaly Reasoning via Perception-to-Cognition Chain-of-Thought"
title_zh: Vad-R1：通过感知到认知链式思维实现视频异常推理
authors: "Chao Huang, Benfeng Wang, Wei Wang, Jie Wen, Chengliang Liu, Li Shen, Xiaochun Cao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6eLlczxbrp"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 基于多模态大模型的视频异常推理，通过感知到认知的思维链
tldr: 现有MLLM视频异常检测仅浅层描述，该文提出视频异常推理新任务Vad-R1，采用端到端MLLM框架，设计感知到认知链式思维（P2C-CoT）模拟人类识别异常过程，引导深度推理。方法在视频异常分析中实现深层理解和显式思维，提升了多模态推理的可解释性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 396, \"height\": 368}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 526, \"height\": 528}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-003.webp\", \"caption\": \"\", \"page\": 25, \"index\": 3, \"width\": 940, \"height\": 470}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-004.webp\", \"caption\": \"\", \"page\": 25, \"index\": 4, \"width\": 940, \"height\": 470}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-005.webp\", \"caption\": \"\", \"page\": 31, \"index\": 5, \"width\": 3160, \"height\": 1660}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-006.webp\", \"caption\": \"\", \"page\": 31, \"index\": 6, \"width\": 3160, \"height\": 1660}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-007.webp\", \"caption\": \"\", \"page\": 31, \"index\": 7, \"width\": 3160, \"height\": 1660}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6ellczxbrp/fig-008.webp\", \"caption\": \"\", \"page\": 31, \"index\": 8, \"width\": 3160, \"height\": 1660}]"
motivation: 当前多模态大模型视频异常检测缺乏深层推理，停留在浅层描述。
method: 提出端到端MLLM框架Vad-R1，使用感知到认知链式思维指导推理。
result: 实现视频异常的深度分析和显式推理，可能提升检测准确率。
conclusion: 链式思维引导的显式推理增强了视频异常理解的可解释性。
---

## Abstract
Recent advancements in reasoning capability of Multimodal Large Language Models (MLLMs) demonstrate its effectiveness in tackling complex visual tasks. However, existing MLLM-based Video Anomaly Detection (VAD) methods remain limited to shallow anomaly descriptions without deep reasoning. In this paper, we propose a new task named Video Anomaly Reasoning (VAR), which aims to enable deep analysis and understanding of anomalies in the video by requiring MLLMs to think explicitly before answering. To this end, we propose Vad-R1, an end-to-end MLLM-based framework for VAR. Specifically, we design a Perception-to-Cognition Chain-of-Thought (P2C-CoT) that simulates the human process of recognizing anomalies, guiding the MLLMs to reason about anomalies step-by-step. Based on the structured P2C-CoT, we construct Vad-Reasoning, a dedicated dataset for VAR. Furthermore, we propose an improved reinforcement learning algorithm AVA-GRPO, which explicitly incentivizes the anomaly reasoning capability of MLLMs through a self-verification mechanism with limited annotations. Experimental results demonstrate that Vad-R1 achieves superior performance, outperforming both open-source and proprietary models on VAD and VAR tasks.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，我将基于提供的论文内容，以Markdown形式对该论文进行结构化、深入、客观的总结。

---

### **论文核心问题与整体含义**

*   **研究背景**：视频异常检测（VAD）是计算机视觉的重要任务，但传统方法仅停留在检测层面，缺乏对异常事件的理解和解释。近期，多模态大语言模型（MLLMs）虽被引入VAD，但其应用仍局限于生成浅层描述或简单问答，未能进行深入的推理和分析。
*   **核心问题**：当前基于MLLMs的视频异常检测方法缺乏深层推理能力，无法模拟人类从感知到认知的复杂思维过程来理解和分析视频中的异常事件。
*   **整体含义**：为解决上述问题，本文提出了一项名为**视频异常推理（Video Anomaly Reasoning, VAR）** 的新任务，旨在赋予MLLMs对视频中的异常事件进行结构化、分步骤、深层推理的能力，从简单的检测扩展到真正的认知理解。

### **论文提出的方法论**

本文的核心贡献是提出了一个端到端的MLLM框架 **Vad-R1** 及配套的数据集和训练算法，具体如下：

*   **核心思想：感知到认知链式思维（P2C-CoT）**
    *   模仿人类识别异常的过程，设计了一个结构化的推理链，分为“感知”和“认知”两个阶段，共四个步骤。
        *   **感知阶段**：
            1.  **全局感知**：观察整体视频环境、场景和物体。
            2.  **局部感知**：聚焦于偏离常态的可疑事件，识别“发生了什么”、“何时发生”、“在哪里发生”。
        *   **认知阶段**：
            3.  **浅层认知**：识别事件为何被视为异常，并关联视觉线索。
            4.  **深层认知**：推理深层次原因、违反的社会规范以及可能导致的后果。
        *   **答案**：最终提供一个包含异常类别（Which）、描述（What）、时空定位（When/Where）、原因（Why）和影响（How）的简洁摘要。

*   **关键技术细节：数据集与训练算法**
    *   **Vad-Reasoning数据集**：基于P2C-CoT构建，包含两个子集：
        *   `Vad-Reasoning-SFT`：包含1755个带有高质量、逐步推理过程标注的视频，用于监督微调。
        *   `Vad-Reasoning-RL`：包含6448个仅有视频级弱标签（正常/异常）的视频，用于强化学习。
    *   **AVA-GRPO算法**：一种改进的强化学习算法，在GRPO（Group Relative Policy Optimization）基础上，引入了**异常验证奖励（Anomaly Verification Reward）** 机制，无需详细标注即可激励模型的推理能力。
        *   **算法流程（文字说明）**：
            1.  模型针对输入视频生成一组候选答案。
            2.  根据格式和准确性等标准计算奖励。
            3.  **自验证机制**：模型首先预测视频的异常状态（正常/异常）。
                *   如果预测为“异常”，则将模型认为的异常片段从视频中剪除，得到仅含正常片段的修剪视频。随后，让模型观察此修剪视频。若模型将其预测为“正常”，则赋予正奖励，因为这证明被剪除的片段确实关键。
                *   如果预测为“正常”，则随机剪除视频的开头或结尾片段。随后，让模型观察此修剪视频。若模型此时将其预测为“异常”，则给予负奖励，因为这暗示模型最初仅凭视频的局部帧（时间片面的信息）做出了判断，而非全局理解。
            4.  结合该自验证奖励进行策略优化，鼓励模型进行全局、一致的推理，而非依赖“时间黑客（temporal hacking）”等捷径。
    *   **训练流程**：分两阶段训练。
        *   **阶段一（SFT）**：在`Vad-Reasoning-SFT`数据集上进行监督微调，赋予模型基础的异常推理能力。
        *   **阶段二（RL）**：在`Vad-Reasoning-RL`数据集上，利用AVA-GRPO算法进行强化学习，进一步激励和泛化模型的推理能力。

### **实验设计**

*   **使用数据集/场景**：
    *   **Vad-Reasoning测试集**：包含438个视频，覆盖真实犯罪、暴力事件、交通、校园、城市等多种场景。
    *   **VANE基准**：一个用于评估MLLMs视频异常理解能力的多选问答基准，包含325个视频片段（含真实监控和AI生成视频）。
*   **对比方法**：实验对比了广泛的方法，包括：
    *   **开源通用视频MLLMs**：如InternVideo2.5, InternVL3, VideoChat-Flash, VideoLLaMA3, LLaVA-NeXT-Video, Qwen2.5-VL等。
    *   **开源视频推理MLLMs**：如Open-R1-Video, Video-R1, VideoChat-R1等。
    *   **基于MLLM的VAD方法**：如Holmes-VAD, Holmes-VAU, HAWK等。
    *   **闭源商业MLLMs**：如GPT-4o, Claude3.5-Haiku, Gemini2.5系列, o4-mini, QVQ-Max等。

### **资源与算力**

*   **硬件配置**：所有实验均在 **4块 NVIDIA A100 (80GB) GPU** 上进行。
*   **训练时长**：
    *   **监督微调（SFT）阶段**：训练4个epochs，耗时约**6小时**。
    *   **强化学习（RL）阶段**：训练1个epoch，耗时约**26小时**。

### **实验数量与充分性**

论文中的实验设计较为充分、客观且公平，主要体现在：
1.  **主实验**：在两个主要任务（异常推理和检测）和多个指标（文本质量、LLM评判、分类精度、时间定位等）上，与超过15个主流的开源和闭源模型进行了系统比较。
2.  **消融实验**：设计了三组关键消融实验来验证核心设计的有效性：
    *   **推理策略有效性实验**：对比了“直接回答”、“随机推理”和“结构化推理（P2C-CoT）”三种策略对检测性能的影响。
    *   **训练策略有效性实验**：对比了仅SFT、仅RL（AVA-GRPO）以及“SFT+RL”组合策略的效果，验证了两阶段训练的必要性。
    *   **奖励函数消融实验**：在16帧和32帧两种输入条件下，对比了原始GRPO、GRPO+长度奖励、GRPO+异常验证奖励以及完整的AVA-GRPO四种奖励策略，验证了自验证机制和复合奖励的贡献。
3.  **泛化性实验**：在独立的VANE基准上进行测试，验证了模型在未见过的数据和问题格式上的迁移能力。
4.  **定性分析**：通过案例展示了Vad-R1相比其他模型的推理准确性和细节优势，如正确识别出“障碍物”而非“移动的物体”，并指出了其他模型的幻觉或漏判问题。

### **论文的主要结论与发现**

1.  **VAR任务的有效性**：提出的视频异常推理（VAR）任务将VAD从浅层识别提升到了深层认知理解，是可行且有价值的。
2.  **P2C-CoT的优越性**：结构化的“感知到认知链式思维（P2C-CoT）”能有效引导模型进行分步推理，相比直接回答或随机推理，能显著提升异常检测和推理的性能。
3.  **两阶段训练范式的成功**：“监督微调（SFT）+ 强化学习（RL）”的冷启动训练策略是有效的。SFT赋予了基础推理能力，而RL（尤其是AVA-GRPO）则进一步强化和泛化了这一能力，仅靠RL效果不佳。
4.  **AVA-GRPO算法的贡献**：提出的AVA-GRPO算法，通过其自验证机制，能在仅有视频级弱标签的情况下，有效激励和改善模型的推理质量，减少了模型对“时间黑客”等捷径的依赖。
5.  **性能领先**：Vad-R1在异常检测和推理任务上均取得了卓越性能，超越了众多开源和强大的商业闭源模型。

### **优点**

*   **问题定义新颖**：提出的“视频异常推理（VAR）”任务具有前瞻性，将研究重点从检测推向理解与认知。
*   **方法论扎实**：设计了精巧的P2C-CoT结构来模拟人类认知过程，逻辑清晰，可解释性强。
*   **训练机制创新**：提出的AVA-GRPO算法巧妙地利用自验证方式解决了弱标签下高质量推理的评估难题，是一个核心亮点。
*   **实验全面且说服力强**：实验设计覆盖多数据集、多指标、多基线，并通过深入的消融研究证实了各个组件的有效性，结论可靠。

### **不足与局限**

*   **推理速度**：论文明确指出，多步推理过程引入了额外的计算开销，导致**推理速度较慢**，限制了其在实时性要求高的场景中的应用。
*   **数据集依赖与偏差**：虽然构建了大规模数据集，但其来源仍主要是现有监控视频数据集和网络视频，可能无法全面覆盖所有真实世界的异常类型，存在**场景和类别偏差**的风险。
*   **标注成本**：尽管RL阶段使用了弱标签，但SFT阶段仍需高质量的链式思维标注。自动标注流程虽有LLM辅助验证，但生成数据的质量上限和可能引入的偏误未被深入探讨。
*   **模型上限**：Vad-R1的能力很大程度上被其基座模型（Qwen2.5-VL-7B）的限制所约束，对极其复杂或需要超长上下文理解的异常可能仍力有不逮。

（完）
