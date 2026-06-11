---
title: Towards General Continuous Memory for Vision-Language Models
title_zh: 面向视觉语言模型的通用连续记忆
authors: "Wenyi WU, Zixuan Song, Kun Zhou, Yifei Shao, Zhiting Hu, Biwei Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=YaQnKRtTdh"
tags: ["query:tf-vl-ag"]
score: 4.0
evidence: 视觉语言模型的连续记忆以支持多模态推理
tldr: 视觉语言模型在复杂推理中面临长上下文和性能下降问题。本文提出连续记忆机制，用一组紧凑的稠密嵌入高效表示多模态知识，以辅助复杂推理。该方法提升了模型在多模态任务上的表现，为高效视觉语言理解提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 734, \"height\": 302}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 2929, \"height\": 809}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaqnkrttdh/fig-003.webp\", \"caption\": \"\", \"page\": 19, \"index\": 3, \"width\": 3356, \"height\": 2465}]"
motivation: 现有方法拼接长序列多模态信息导致上下文过长和性能下降。
method: 提出连续记忆，用紧凑稠密嵌入表示多模态知识，供VLM读取。
result: 在复杂推理任务上提升性能，同时保持上下文效率。
conclusion: 为高效多模态推理提供了通用的记忆方案，可集成于各类VLM。
---

## Abstract
Language models (LMs) and their extension, vision-language models (VLMs), have achieved remarkable performance across various tasks. However, they still struggle with complex reasoning tasks that require multimodal or multilingual real world knowledge. To support such capabilities, an external memory system that can efficiently provide relevant multimodal information is essential. Existing approaches generally concatenate image and text tokens into a long sequence as memory, which, however, may drastically increase context length and even degrade performance. In contrast, we propose using continuous memory-a compact set of dense embeddings-to more effectively and efficiently represent multimodal and multilingual knowledge. Our key insight is that a VLM can serve as its own continuous memory encoder. We empirically show that this design improves performance on complex multimodal reasoning tasks. Building on this, we introduce a data-efficient and parameter-efficient method to fine-tune the VLM into a memory encoder, requiring only 1.2\% of the model’s parameters and a small corpus of 15.6K self-synthesized samples. Our approach CoMEM utilizes VLM's original capabilities to encode arbitrary multimodal and multilingual knowledge into just 8 continuous embeddings. Since the inference-time VLM remains frozen, our memory module is plug-and-play and can be flexibly integrated as needed. Extensive experiments across eight multimodal reasoning benchmarks demonstrate the effectiveness of our approach. Code and data is publicly released here https://github.com/WenyiWU0111/CoMEM.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：现有视觉语言模型（VLMs）在处理需要多模态（图像+文本）或多语言真实世界知识的复杂推理任务时，仍然表现不足。传统的检索增强生成（RAG）方法将检索到的图像和文本 token 直接拼接成长序列作为外部记忆，但这样会**急剧增加上下文长度**，反而可能导致 VLMs 性能下降。
- **整体含义**：本文提出一种**通用连续记忆机制**，用一组紧凑的稠密嵌入（continuous embeddings）来高效表示多模态和多语言知识，以支持 VLMs 的复杂推理，且不增加过多的上下文负担。

### 2. 论文提出的方法论
- **核心思想**：让 **VLM 自身充当连续记忆编码器**，将任意的多模态知识压缩为少量连续向量，并直接插入下游 VLMs 的推理过程中。
- **关键技术细节**：
  - **初步验证**：直接提取 VLM 最后一层的隐藏状态作为记忆，或利用注意力分数选择前 25% 的关键嵌入，无需额外训练即可改善 RAG 退化问题。
  - **正式方法（CoMEM）**：
    - **记忆编码器**：由 VLM（冻结后 LoRA 微调） + 轻量 **Q-Former** 组成。Q-Former 使用可学习的查询向量（8 个），通过交叉注意力将 VLMs 编码的表示压缩为 8 个连续嵌入。
    - **即插即用**：推理时，将压缩后的连续记忆向量序列拼接到 VLM 的输入嵌入前，VLM 本身参数保持不变。
  - **高效训练策略**：
    - **数据**：利用 VLM 自身从 InfoSeek、OK-VQA、EVQA 的训练集合成 13.8k 正确应答样本，并经多语言翻译扩充至 15.6k 样本（覆盖 10 种语言）。
    - **参数**：仅微调 VLM 中的 LoRA 矩阵（秩 16）和共享参数的 Q-Former，总共仅占模型参数的 **1.2%**。
    - **最终效果**：任意多模态知识被压缩为仅 8 个连续嵌入（平均压缩率超 80 倍）。

### 3. 实验设计
- **数据集与基准**：
  - **英语多模态推理**：InfoSeek、OVEN、MRAG-Bench、OK-VQA、A-OKVQA、ViQuAE（共 6 个）。
  - **多语言多模态推理**：CVQA 和经翻译的多语言 InfoSeek（中文、俄语、西班牙语、葡萄牙语、保加利亚语）。
  - **基础 VLM 基线**：LLaVA‑v1.5/v1.6、LLaMA3、InternLM‑XComposer2.5vl、mPLUG‑Owl3、Qwen2‑VL‑Instruct、Qwen2.5‑VL‑Instruct。
  - **RAG 基线**：直接拼接检索到的图文对的 vanilla RAG，以及 FastV（token 剪枝）。
  - **高级 RAG / 记忆基线**：Wiki‑LLaVA、RORA‑VLM、EchoSight、ReflectiVA。
- **对比方法**：共对比约 18 种设定，包括无检索、普通 RAG、压缩、训练型 RAG 等。
- **额外分析**：长上下文理解（top‑k 从 3 到 50）、向纯 LLM 迁移的效果、压缩嵌入数（4/8/16/24）、训练数据量和参数量的缩放实验、推理延迟与 token 成本。

### 4. 资源与算力
- **训练算力**：整个训练可以在**单张 NVIDIA H100 GPU** 上完成，耗时约 **20 小时**。
- **推理延迟**：所有延迟测试同样在 H100 上执行，CoMEM 的推理速度与 baseline VLM 相近，远优于 RAG。

### 5. 实验数量与充分性
- **实验数量**：涵盖 **8 个主要 benchmark**，6 个英语 + 2 个多语言；**18+ 条基准线**；**3 项深入专项研究**（长上下文、迁移学习、消融）；**2 项效率分析**（训练效率 vs 数据量/参数量、推理延迟与 token 成本）。
- **充分性**：实验设计完整，在多个模型架构、多种任务和语言上验证，包含公平的对比与消融。训练数据规模、参数效率、推理成本等均有详细分析，支持方法的有效性和普适性。

### 6. 论文的主要结论与发现
- **性能提升显著**：CoMEM 在 Qwen2‑VL 上平均提升 **+8.0%**，在 Qwen2.5‑VL 上提升 **+7.7%**（英语多模态推理），多语言基准也有 **+5.1%** 和 **+4.3%** 的提升。
- **长上下文稳定**：随着检索知识对数增加（最高 50 对），RAG 性能下降，而 CoMEM 始终保持稳定并优于基线。
- **知识可迁移**：VLM 生成的连续记忆可以直接增强纯文本 LLM（Qwen2.5‑Instruct），使其在不含视觉模块的情况下显著提升视觉推理任务。
- **高效压缩**：只需 8 个嵌入即可保留关键知识，且训练仅需少量自合成数据和极少参数。

### 7. 优点
- **即插即用，无需改动推理模型**：记忆模块可灵活地附加到原始 VLM 上。
- **极高压缩率和效率**：实现 80 倍以上压缩，仅增加极少 token；训练仅需 15.6k 样本和 1.2% 参数。
- **通用性强**：支持多模态（图文）和多语言知识，且在不同 VLMs 和基准上表现稳健。
- **训练与实验设计巧妙**：利用 VLM 自合成训练数据，避免昂贵人工标注，且消融实验充分证明了压缩尺寸、数据量和参数量的最佳配置。

### 8. 不足与局限
- **评估数据偏静态**：所有基准均为静态、合成数据，未在动态或含噪的真实场景（如网络数据、实时视频）下测试。
- **多模型协同未探索**：目前仅部署于单模型，未验证连续记忆在多个 VLM/LLM 智能体之间的共享和知识传递能力。
- **任务范围有限**：当前主要聚焦于知识密集型的 VQA 任务，虽然对图像描述和推理任务有初步泛化验证，但更广泛的复杂规划、决策任务尚未覆盖。

（完）
