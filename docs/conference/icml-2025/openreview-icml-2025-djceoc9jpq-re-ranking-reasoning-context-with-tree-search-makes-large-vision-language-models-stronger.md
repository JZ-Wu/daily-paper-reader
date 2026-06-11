---
title: Re-ranking Reasoning Context with Tree Search Makes Large Vision-Language Models Stronger
title_zh: 用树搜索重排序推理上下文增强大型视觉语言模型
authors: "Qi Yang, Chenghao Zhang, Lubin Fan, Kun Ding, Jieping Ye, Shiming Xiang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DJcEoC9JpQ"
tags: ["query:tf-vl-ag"]
score: 4.0
evidence: 多模态 RAG 结合树搜索重排序增强 LVLM 推理，与代理式推理增强相关
tldr: 针对多模态检索增强生成中知识稀缺和回答不稳定问题，提出 RCTS 框架，通过自洽评估充实推理知识库，并利用蒙特卡洛树搜索重排序检索结果，提升视觉问答准确性，展示了树搜索增强推理的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 827, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1617, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1567, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1568, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1577, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1783, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1803, \"height\": 74, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 70, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 72, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 1487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1737, \"height\": 2017, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1748, \"height\": 1851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1746, \"height\": 2153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1703, \"height\": 2195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djceoc9jpq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1738, \"height\": 2176, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 887, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1703, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djceoc9jpq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 809, \"height\": 203, \"label\": \"Table\"}]"
motivation: 多模态 RAG 面临推理示例稀缺和检索知识不稳定问题。
method: 构建推理上下文充实知识库，引入蒙特卡洛树搜索对检索结果重排序。
result: RCTS 在多模态 VQA 任务上性能提升。
conclusion: 树搜索重排序是增强 LVLM 推理能力的有效手段。
---

## Abstract
Recent advancements in Large Vision Language Models (LVLMs) have significantly improved performance in Visual Question Answering (VQA) tasks through multimodal Retrieval-Augmented Generation (RAG). However, existing methods still face challenges, such as the scarcity of knowledge with reasoning examples and erratic responses from retrieved knowledge. To address these issues, in this study, we propose a multimodal RAG framework, termed RCTS, which enhances LVLMs by constructing a Reasoning Context-enriched knowledge base and a Tree Search re-ranking method. Specifically, we introduce a self-consistent evaluation mechanism to enrich the knowledge base with intrinsic reasoning patterns.  We further propose a Monte Carlo Tree Search with Heuristic Rewards (MCTS-HR) to prioritize the most relevant examples.  This ensures that LVLMs can leverage high-quality contextual reasoning for better and more consistent responses. Extensive experiments demonstrate that our framework achieves state-of-the-art performance on multiple VQA datasets, significantly outperforming In-Context Learning (ICL) and Vanilla-RAG methods. It highlights the effectiveness of our knowledge base and re-ranking method in improving LVLMs.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

### 1. 研究动机与核心问题
- **核心问题**：当前的多模态检索增强生成（RAG）方法在提升大型视觉语言模型（LVLMs）的视觉问答（VQA）能力时面临两大挑战：
    - **知识稀缺**：知识库中的样本多为简单的问答对，缺乏详细的推理过程，无法为模型提供高质量的“解题思路”。
    - **回应不稳定**：检索到的示例并非总是对当前问题有帮助，有时甚至会误导模型，导致回答不一致或错误。
- **整体含义**：论文旨在通过构建一个包含丰富推理上下文的知识库，并利用树搜索对检索到的示例进行高效重排序，使LVLMs能从“略知一二”提升到“深入理解”，从而生成更准确、更可靠的答案。

### 2. 方法论：RCTS框架
该框架包含三个核心组件：构建带推理上下文的知识库、混合嵌入检索、以及基于树搜索的重排序。

- **推理上下文生成与自洽评估**
    - **目标**：为知识库中的每个问答对自动生成详细的步骤化推理过程，以增强上下文信息。
    - **流程**：
        1.  **生成候选推理**：给定知识库中的问答对（Q, A），让LVLM生成多个（Nc）候选推理上下文。
        2.  **自洽验证**：将每个候选推理与问题（Q）拼接，重新输入LVLM得到预测答案（Np次）。通过对比预测答案和真实答案（A）的匹配程度（得分），选出得分最高的候选推理作为该问答对的最终推理上下文。

- **混合嵌入知识检索**
    - **方法**：同时利用文本和视觉信息进行检索。
    - **技术细节**：分别使用文本编码器和图像编码器提取用户查询（问题+图片）和知识库条目的特征，并将它们拼接成混合嵌入。通过计算用户查询嵌入与所有知识库条目嵌入之间的相似度得分（使用迟交互机制），检索出Top-N个最相关的样本。

- **基于树搜索的重排序（MCTS-HR）**
    - **核心思想**：将检索样本的顺序选择建模为一个序列决策问题，并使用蒙特卡洛树搜索（MCTS）寻找最优组合。
    - **关键元素**：
        - **动作构建**：将检索到的Top-N个样本作为动作空间，根据与用户查询的相似度概率进行采样。
        - **启发式奖励函数**：结合两种奖励来评估一个K-shot（选择K个样本作为上下文）回答路径的好坏。
            1.  **自洽奖励**：用模型生成的K-shot回答中的推理部分（C），结合原问题再次生成多个新答案，计算其与原预测答案的一致性。
            2.  **互洽奖励**：用当前K-shot回答作为上下文，反过来回答动作空间中其他样本的问题，计算其回答准确率。
            3.  **最终奖励**：将自洽奖励和互洽奖励加权求和。
        - **搜索与回溯**：通过选择、扩展、模拟和反向传播这四个阶段迭代更新树节点价值，最终选出获得最高奖励的一系列样本，作为最优上下文排序。

### 3. 实验设计
- **数据集与基准**：
    - **推理类 VQA**：ScienceQA, MMMU, MathV。
    - **非推理类 VQA**：VizWiz, VSR-MC。
    - **基准模型**：Qwen2-VL (2B, 7B), InternVL-2 (8B)。
- **对比方法**：
    - **Zero-Shot**：不提供任何示例。
    - **In-Context Learning (ICL)**：随机从知识库中检索示例作为上下文。
    - **Vanilla-RAG**：基于嵌入相似度检索最靠前的示例作为上下文。
    - **RCTS (Ours)**：本文提出的完整方法。

### 4. 资源与算力
- **模型量化**：对于7B及以上的LVLMs，文中提到使用AWQ技术进行4-bit量化，以便在单张**NVIDIA 4090 (24GB) GPU**上运行。
- **其他模型**：检索器使用了冻结的BERT-base和ViT-L模型。
- **未明确说明**：论文未提及模型训练过程、训练时长或总GPU卡时消耗，该方法本身是免训练的。

### 5. 实验充分性
- **实验数量与设置**：
    - **主实验**：覆盖3个不同类型和规模的LVLMs，在3个推理和2个非推理数据集上进行了主要性能对比，结果非常全面。
    - **消融实验**：
        - 验证了**关键组件**（推理上下文、MCTS重排序）各自及组合后的效果。
        - 分析了**奖励函数**中自洽与互洽奖励的贡献及权重（α）的影响。
        - 探讨了MCTS中**迭代次数**（Rollouts）对性能和计算开销的权衡。
    - **分析性实验**：
        - 评估了自动生成的**推理上下文的可靠性**。
        - 提供了**定性案例**分析，对比了RCTS与Vanilla-RAG的上下文排序及最终答案质量。
- **公平性**：实验对比了公平的基线方法，且在相同设置下进行，具有较高的客观性。消融实验系统地证明了每个模块的有效性。

### 6. 主要结论与发现
- RCTS框架在所有基准测试中均取得了SOTA性能，显著优于Zero-Shot、ICL和Vanilla-RAG方法。
- 与Vanilla-RAG相比，在Qwen2-VL (7B)和InternVL-2 (8B)等模型上，平均性能提升超过3%。
- 引入**推理上下文**和**基于MCTS的重排序**是两个互补且有效的策略，两者结合能带来最大的性能增益。
- 该方法在数学、图表、自然图像等多种VQA任务中均表现出鲁棒性，证明了其通用性。

### 7. 优点
- **创新的树搜索应用**：首次将MCTS引入多模态RAG的示例重排序任务中，将顺序选择转化为序列决策问题，方法新颖。
- **多层次启发式奖励**：设计了结合自洽和互洽的奖励机制，不仅评估答案的稳定性，还评估其知识迁移能力，减少了单一模型评分的偏差。
- **自动化知识增强**：提出自洽评估方法，为知识库自动生成高质量的推理链，解决了推理示例稀缺的问题，提升了上下文信息的密度。
- **免训练即插即用**：该方法无需对LVLM进行微调，可直接应用于不同架构的模型，通用性强。
- **实验全面详实**：在多个模型、多种类型的VQA数据集上进行了充分的对比和消融实验，结论可信度高。

### 8. 不足与局限
- **对知识库依赖性强**：论文明确指出，性能提升的前提是知识库中存在对解决问题有益的样本。若知识库覆盖不足，方法可能失效（附录中的失败案例也印证了这点）。
- **计算开销较大**：生成推理上下文和MCTS多次模拟生成回答的过程会带来额外的计算和时间成本，论文中虽讨论了迭代次数与性能的权衡，但未提供具体的延迟或吞吐量数据。
- **多轮生成设置的复杂性**：论文中许多环节（如自洽评估、互洽奖励计算）需要设置多轮生成参数（Nc， Ns， Nm），这些超参数在不同任务上可能需要调整，增加了应用复杂度。

（完）
