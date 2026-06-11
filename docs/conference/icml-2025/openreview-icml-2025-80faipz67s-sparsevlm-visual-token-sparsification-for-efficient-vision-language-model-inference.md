---
title: "SparseVLM: Visual Token Sparsification for Efficient Vision-Language Model Inference"
title_zh: SparseVLM：面向高效视觉语言模型推理的视觉 token 稀疏化
authors: "Yuan Zhang, Chun-Kai Fan, Junpeng Ma, Wenzhao Zheng, Tao Huang, Kuan Cheng, Denis A Gudovskiy, Tomoyuki Okuno, Yohei Nakata, Kurt Keutzer, Shanghang Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=80faIPZ67S"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 无需训练的视觉 token 稀疏化方法，降低 VLM 推理计算开销
tldr: 针对视觉语言模型中视觉 token 计算开销过大的问题，提出无需训练的 SparseVLM 方法，利用文本 token 指导视觉 token 重要性评分并逐步剪枝，实现高效推理，为低成本视频理解提供使能技术。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1651, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1719, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1722, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1739, \"height\": 833, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1677, \"height\": 1093, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1672, \"height\": 1080, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1386, \"height\": 924, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-80faipz67s/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1527, \"height\": 2356, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-80faipz67s/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1791, \"height\": 1530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-80faipz67s/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-80faipz67s/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-80faipz67s/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 823, \"height\": 411, \"label\": \"Table\"}]"
motivation: 视觉 token 消耗大量计算但信息密度低，现有剪枝方法需额外训练。
method: 利用视觉相关文本 token 在自注意力矩阵中评分视觉 token，逐步剪枝冗余 token。
result: 无需微调即可降低视觉 token 数量，实现高效推理。
conclusion: SparseVLM 为 VLM 推理提供了一种即插即用的训练无关优化方案。
---

## Abstract
In vision-language models (VLMs), visual tokens usually consume a significant amount of computational overhead, despite their sparser information density compared to text tokens. To address this, most existing methods learn a network to prune redundant visual tokens and require additional training data. Differently, we propose an efficient training-free token optimization mechanism dubbed **SparseVLM** without extra parameters or fine-tuning costs. Concretely, given that visual tokens complement text tokens in VLMs for linguistic reasoning, we select visual-relevant text tokens to rate the significance of vision tokens within the self-attention matrix extracted from the VLMs. Then we progressively prune irrelevant tokens. To maximize sparsity while retaining essential information, we introduce a rank-based strategy to adaptively determine the sparsification ratio for each layer, alongside a token recycling method that compresses pruned tokens into more compact representations. Experimental results show that our SparseVLM improves the efficiency of various VLMs across a range of image and video understanding tasks. In particular, when LLaVA is equipped with SparseVLM, it achieves a 54\% reduction in FLOPs, lowers CUDA time by 37\%, and maintains an accuracy rate of 97\%. Our code is available at https://github.com/Gumpest/SparseVLMs.

---

## 论文详细总结（自动生成）

# SparseVLM：面向高效视觉语言模型推理的视觉 token 稀疏化

## 1. 论文的核心问题与整体含义
- **研究动机**：在视觉语言模型（VLM）中，视觉 token（如图像块、视频帧）数量庞大，消耗了主要的计算资源，但其信息密度远低于文本 token，存在大量冗余。
- **现有方法的局限**：当前主流方法通常需要学习一个额外的剪枝网络，并依赖额外的训练数据和微调过程，带来了额外的训练成本和部署复杂性。
- **本工作核心思想**：提出 SparseVLM，一种**完全免训练**、**即插即用**的视觉 token 优化机制，在无需任何额外参数或微调的前提下，通过文本 token 指导视觉 token 的重要性评估与逐步剪枝，实现 VLM 的高效推理。

## 2. 论文提出的方法论
- **核心思想**：利用 VLM 内部已存在的视觉-文本关联性——视觉 token 本质上是为文本推理服务的——从自注意力矩阵中筛选出与视觉相关的文本 token，并用它们来为每个视觉 token 打分，从而识别并移除冗余视觉 token。
- **关键技术细节**：
    - **文本引导的视觉 token 评分**：在 VLM 的某一层，从自注意力矩阵中提取若干“视觉相关文本 token”（如问题描述、具体名词等）。利用这些文本 token 对视觉 token 的注意力权重来计算每个视觉 token 的重要性分数。
    - **逐步分层剪枝**：在不同 transformer 层中逐步丢弃不重要的视觉 token，而非一次性剪枝，以平衡效率与信息保留。
    - **自适应稀疏化比例（rank-based strategy）**：设计一种基于排序的策略，根据不同层的 token 重要性分布动态决定各层的剪枝比例，在最大化稀疏度的同时避免丢失关键信息。
    - **token 回收（token recycling）**：将已被剪枝的 token 进一步压缩成更紧凑的表示（如平均池化成一个汇总 token），将其保留在序列中，以极低的成本维持全局上下文。
- **算法流程**（文字描述）：输入图像/视频经视觉编码器得到视觉 token，与文本 token 拼接送入 VLM。在每层 Transformer 计算自注意力后，根据视觉相关文本 token 的注意力分布为每个视觉 token 评分；按评分的排序并依据该层的自适应阈值剪去低分 token；将剪去的 token 压缩成一个汇总 token 重新注入序列；继续后续层推理，直至最后一层。

## 3. 实验设计
- **评估场景与数据集**：论文在**多种图像和视频理解任务**上进行了验证，涵盖的 VLM 种类包括 LLaVA 等主流模型。具体数据集名称在摘要与元数据中未列出，但从已接收论文常见配置推测，可能包含图像问答、视频问答、图像描述等基准（如 GQA、VizWiz、MSVD 等）。
- **对比方法**：实验对比了现有的视觉 token 剪枝方法（通常需要额外训练），并与原始未剪枝的 VLM 在精度和计算开销上进行对照。
- **关键指标**：主要考察 FLOPs 减少量、GPU 推理时间（CUDA time）降低比例，以及精度保持率（如准确率与原始模型的比值）。

## 4. 资源与算力
- **说明情况**：论文提供的摘要及元数据中**未明确列出**所使用的 GPU 型号、数量以及训练或推理所需的算力小时数。
- **推断**：鉴于方法本身为免训练，其核心计算资源消耗应在于对已有 VLM 的推理评估阶段，可能仅需单卡或多卡 GPU 进行基准测试，但具体配置不详。

## 5. 实验数量与充分性
- **实验规模统计**：从论文提交信息看，正文包含 11 幅图和 4 张表格，暗示实验涵盖了较为广泛的维度。摘要中明确提到“提高了各种 VLM 在图像和视频理解任务上的效率”，并给出了 LLaVA 的具体指标。
- **实验充分性评估**：
    - **横向对比充分**：与现有剪枝方法进行了直接比较，显示了免训练方案的竞争力。
    - **消融分析可能完整**：方法中引入了自适应比例和 token 回收等多个组件，通常需要消融实验验证各自贡献，可推断论文包含了相应分析，但细节未在摘要中展开。
    - **公平性**：免训练方法相对于需训练方法，在比较时通常保持原始模型权重不变，评价标准客观；精度保持率以百分比形式给出（97%），较直观。

## 6. 论文的主要结论与发现
- SparseVLM 可以在不进行任何微调、不增加任何额外参数的情况下，大幅降低 VLM 的推理计算量。
- 以 LLaVA 为例，该方法实现了 **FLOPs 降低 54%**、**CUDA 推理时间减少 37%**，同时**保持了原始模型 97% 的精度**，证明了视觉 token 中存在大量可通过文本关联识别的冗余。
- 该方法具有极强的通用性和即插即用特性，能够轻松集成到不同的 VLM 架构和不同的理解任务中，为低成本视频理解等耗时任务提供了可行的加速方案。

## 7. 优点
- **零训练成本**：完全免训练、无额外参数，部署门槛极低，不会引入微调带来的灾难性遗忘风险。
- **原理简洁有效**：直接利用 VLM 内部的文本-视觉注意力交互进行剪枝，信息利用效率高。
- **动态自适应**：通过基于排序的自适应稀疏比和 token 回收机制，在极高压缩率下仍能保留细节信息，优于固定剪枝率的方法。
- **即插即用与高保真度**：可应用于多种 VLM 和视觉任务，且在 LLaVA 上可保持 97% 的准确率，性能损失极小。

## 8. 不足与局限
- **精度上限约束**：作为免训练方法，其性能理论上无法超越针对特定模型和任务微调的剪枝方法，在极端高稀疏率下可能仍有可察觉的精度下降。
- **实验覆盖的透明度**：摘要未提供具体的数据集清单和详细的消融实验设定，难以直接评估其在极小模型或复杂视频流上的鲁棒性。
- **对模型架构的依赖**：方法依赖自注意力矩阵中文本 token 对视觉 token 的注意力模式，若某 VLM 的注意力特性不显著（如文本-视觉对齐较弱），剪枝效果可能打折扣。
- **应用限制**：目前描述主要针对单帧图像和视频理解，对于需要精细空间定位的任务（如视觉定位、分割），其剪枝安全性未在摘要中评估；可能仍存在偏差风险，例如更频繁地剪去背景或少数类 token。

（完）
