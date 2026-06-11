---
title: Modularized Self-Reflected Video Reasoner for Multimodal LLM with Application to Video Question Answering
title_zh: 面向多模态大语言模型的模块化自反思视频推理器及其在视频问答中的应用
authors: "Zihan Song, Xin Wang, Zi Qian, Hong Chen, Longtao Huang, Hui Xue, Wenwu Zhu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dtmTQawQN2"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 提出模块化视频推理器，包含时空定位，用于可解释的视频问答
tldr: 针对多模态大模型在视频问答中缺乏可解释性问题，提出模块化自反思视频推理器MSR-ViR，首次将模块化网络集成到多模态LLM中，通过时空定位和自反思机制提供清晰的推理过程，并在视频问答任务上验证了方法的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1596, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1546, \"height\": 942, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1595, \"height\": 1047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1482, \"height\": 2135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1498, \"height\": 2045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1592, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1590, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1599, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dtmtqawqn2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1645, \"height\": 653, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 690, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 714, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 792, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 752, \"height\": 638, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1354, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1510, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1265, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dtmtqawqn2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1326, \"height\": 236, \"label\": \"Table\"}]"
motivation: 现有基于多模态LLM的视频问答方法缺乏可解释性，无法展示推理路径和答案来源。
method: 提出MSR-ViR，集成模块化时空定位（MoST-Grounding）与自反思机制，显式生成推理步骤。
result: 在视频问答基准上获得可解释的推理路径和高准确率。
conclusion: MSR-ViR提升了视频问答的可解释性，为多模态LLM的视频理解提供了新思路。
---

## Abstract
Multimodal Large Language Models (Multimodal LLMs) have shown their strength in Video Question Answering (VideoQA). However, due to the black-box nature of end-to-end training strategies, existing approaches based on Multimodal LLMs suffer from the lack of interpretability for VideoQA: they can neither present reasoning paths nor indicate where the answers are derived from the video. To address this issue, we propose **MSR-ViR** (**M**odularized **S**elf-**R**eflected **Vi**deo **R**easoner), which for the first time integrates modular networks to Multimodal LLMs, capable of providing VideoQA with explicit reasoning paths for more interpretability. Specifically, a **MoST-Grounding** (Modularized Spatial-Temporal Grounding) network is proposed to decompose complex questions via tree-structured policies, localizing relevant temporal and spatial segments within videos through step-by-step reasoning. The proposed MoST-Grounding network provides explicit visually grounded information for Multimodal LLMs with clear reasoning paths, thus enhancing interpretability for the predicted answers. To further improve the reasoning quality, we design an **Alternate Self-reflection Training Strategy** to jointly optimize policy generation and Multimodal LLMs. Experiments on real-world datasets demonstrate the superiority of our proposed MSR-ViR framework in video understanding, reasoning transparency, and providing explicit localization evidence for answers.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：当前基于多模态大语言模型（Multimodal LLM）的视频问答（VideoQA）方法普遍采用端到端黑盒训练，缺乏**可解释性**，无法展示清晰的**推理路径**，也无法指明答案源自视频的哪一时空片段。
- **研究动机**：为突破这一瓶颈，需要赋予多模态 LLM 透明的推理能力，使模型不仅能回答复杂问题，还能提供从问题到答案的**逐步推理链条**和**视觉定位证据**。
- **整体含义**：首次将**模块化网络**与**多模态 LLM** 深度融合，构建可解释的视频问答框架，在提升问答准确率的同时，生成显式的时空推理路径与视觉依据。

### 2. 方法论
#### 2.1 总体框架：MSR‑ViR
提出 **Modularized Self‑Reflected Video Reasoner (MSR‑ViR)**，包含三个关键组件：
- **Question Parser**：基于大语言模型，通过上下文学习将复杂问题分解为树状结构的执行策略（JSON 格式）。
- **MoST‑Grounding（Modularized Spatial‑Temporal Grounding）**：模块化时空定位网络，按策略递归调用 7 个小模块，逐步定位视频中最相关的时序片段和空间区域。
- **Multimodal LLM Answerer**：接收全局视频表示、时空定位帧以及引导提示，进行答案推理。

#### 2.2 MoST‑Grounding 模块
- **时序定位器（Temporal Localizer）**：包含 `DetectAct`（基于 UniVTG 的简单动作检测）、`TemporalLocalize`（依据关系词如 after/before 扩展时间窗）、`TemporalBetween`（合并时间段）、`TemporalTruncate`（截取视频帧）。
- **空间定位器（Spatial Localizer）**：包含 `LocateObj`（基于 YOLO‑World 的开集目标检测）、`SpatialLocalize`（依据空间关系如 left/above 外推边界框）、`SpatialTruncate`（裁剪图像区域）。
- 工作流程：根据策略 p，动态实例化模块链 \( \mathcal{F}_t|p(\cdot) \) 和 \( \mathcal{F}_s|p(\cdot) \)，先对视频进行时序定位得到片段 \( v_s \)，再逐帧进行空间定位得到边界框 \( b_{v_s} \)。

#### 2.3 多模态 LLM 推理
- 输入扩展：在原始问题基础上，额外提供**均匀采样的全局视频表示** \( g_v \)（防止定位遗漏），以及**解释视觉组件含义的引导提示** \( P_t \)。
- 输出答案 \( \hat{y} \) 通过多模态 LLM 正向传播得到，训练损失为标准交叉熵。

#### 2.4 交替自反思训练策略
- **核心思想**：利用多模态 LLM 在训练中的损失大小作为反馈，通过强化学习优化 Question Parser 生成的策略，使其更合理。
- **具体实现**：
    - 固定多模态 LLM，针对同一问题生成多个策略，执行后计算损失，损失小者为正例 \( p_w \)，大者为负例 \( p_l \)。
    - 使用 **Direct Preference Optimization (DPO)** 优化策略生成器，损失为 \( \mathcal{L}_{DPO}(\pi_\theta; \pi_{ref}) = -\mathbb{E}[\log \sigma(\hat{r}_\theta(p_w, q) - \hat{r}_\theta(p_l, q))] \)。
    - 训练以 **200 步为周期**交替进行多模态 LLM 的监督微调（SFT）和 Question Parser 的强化学习（DPO），二者轮流冻结、交替优化。

#### 2.5 计算复杂度分析
- 理论证明 MSR‑ViR 的复杂度上界为 \( O(c_1 T H^2 W^2 + c_2 T^2 + C_1 H^2 W^2 + C_2 L^2 + C_3 l_p^2) \)，其中 \( c_1, c_2 \) 来自小模型，\( C_1, C_2, C_3 \) 来自大模型。
- 额外开销主要来自 Question Parser 的 \( C_3 l_p^2 \)（提示长度 \( l_p \) 固定），与视频长度/分辨率无关，因此**上界可控**。

### 3. 实验设计与对比
#### 3.1 数据集与评测基准
- **标准 VideoQA**：NExT‑QA（含时间、因果、描述等子类）、STAR‑sub（交互与序列类问题，去除不合适类型）。
- **长视频 VideoQA**：EgoSchema（全量测试与子集）、VideoMME（含短、中、长视频子集）。
- **可接地 VideoQA**：NExT‑GQA（需提供预测时间段的 IoP、IoU 及 Acc@GQA）。

#### 3.2 对比方法
涵盖多类模型：
- 小视觉语言模型：ATP, MIST, CoVGT, HiTeA, InternVideo 等。
- 多模态 LLM 直训基线：Qwen‑VL, LLaVA‑NeXT, Qwen2‑VL, LLaVA‑Video。
- 接地/检索型方法：TGB, SeViLA, GCG, LangRepo。
- 模块化方法：LLoVi, MoReVQA (部分使用超大 LLM 如 GPT‑4/Palm‑2)。
- 零样本对比：在上述直训基线上微调或直接测试的 MSR‑ViR 版本（MSR‑ViR_Q, MSR‑ViR_L, MSR‑ViR_Q2, MSR‑ViR_LV）。

### 4. 资源与算力
- **推理速度测试**：明确使用 **一块 NVIDIA A100 GPU** 测试每样本推理时间（如 MSR‑ViR_Q 7B 解析器约 3.10s/sample）。
- **训练资源配置**：论文未详细说明训练所使用的 GPU 数量、显存大小或总训练小时数；仅提及使用 LoRA 微调、梯度累积步数 16、交替训练周期 200 步、NExT‑QA/STAR 训练 5 个 epoch。**训练算力描述不充分**。

### 5. 实验数量与充分性
- **总体实验量**：覆盖 **4 个主要数据集**（NExT‑QA, STAR‑sub, EgoSchema, VideoMME）+ 1 个接地数据集 NExT‑GQA，并与 **超过 15 种** 现有方法进行对比。
- **消融研究**：对自反思训练、空间定位模块、引导提示、全局表示、仅用全局表示等组件进行消融；对策略中的推理路径进行移除实验。
- **额外分析**：推理速度对比、不同大小 Question Parser（1.5B vs 7B）的影响、替换小模型（UniVTG vs R2‑Tuning vs Moment‑DETR）的影响、不同帧采样策略的对比。
- **公平性与充分性**：所有比较均在统一训练/测试划分下进行，采用同量级 LLM（7B 附近）对比，避免因模型规模差异导致的不公平。实验设计全面，消融充分，结论可靠。

### 6. 主要结论与发现
- **性能提升**：MSR‑ViR 在多个 VideoQA 数据集上均**显著优于**同等规模的端到端多模态 LLM 以及已有的接地/模块化方法。例如，在 NExT‑QA 上 MSR‑ViR_L 达到 74.9%，在 EgoSchema 子集上达到 61.2%，在 VideoMME 上其长视频子集提升尤为明显（+3.4%）。
- **接地精度**：在 NExT‑GQA 上，MSR‑ViR 同时获得了最高的 **mIoU (23.4)** 和 **Acc@GQA (18.6)**，证明其不仅能答对问题，还能更准确地定位答案对应的时序区间。
- **消融核心发现**：交替自反思训练显著提升策略质量（去除后准确率下降约 1.5%）；空间定位模块对交互类问题重要；全局表示与引导提示均对性能有正面贡献。
- **推理路径可视化**：案例表明，自反思训练后 Question Parser 能生成更合理的树状策略，从而正确接地并推导出答案。

### 7. 优点
- **可解释性创新**：首次将模块化时空定位网络与多模态 LLM 结合，输出显式的**树状推理路径**和**视觉接地证据**，极大提升了 VideoQA 的透明性。
- **深思熟虑的训练机制**：交替自反思训练利用问答损失作为反馈，无需人工标注策略，使 Question Parser 与多模态 LLM 协同进化，策略质量持续提升。
- **理论支撑**：给出了计算复杂度的上界证明，表明额外开销合理且可控。
- **实验扎实全面**：在标准、长视频、接地多个维度与大量基线对比，消融分析细致，且验证了不同模块替换和采样策略的影响。
- **灵活可扩展**：MoST‑Grounding 的小模块可动态组合，易于扩展新的时空定位功能。

### 8. 不足与局限
- **计算效率**：尽管复杂度上界可控，但实际推理速度约为直接基线的 2 倍（如 MSR‑ViR_L 需 4.96s/sample），在实时或大规模部署中仍可能成为瓶颈。
- **依赖小模块性能**：时序定位依赖 UniVTG 等模型，若小模块在特定域（如细粒度动作）表现不佳，会限制整体可解释性和准确率的上限。
- **策略生成方式**：Question Parser 依赖固定的 prompt 模板和 in‑context learning，缺乏对开放域、多步超长推理的适应性；且仅通过 DPO 从局部损失区分优劣，可能存在偏差。
- **实验覆盖面**：尽管多个数据集，但仅限于英文 VideoQA；未在更多视频时长、更多语言或更多复杂推理类型上验证。
- **训练算力未披露**：论文未明确训练所需 GPU 数量和训练时长，难以评估实际资源消耗与可复现性。
- **模型规模单一**：主实验均围绕 7B 左右的多模态 LLM，未探索更大模型（如 13B/30B）下的表现和推理路径质量变化。

（完）
