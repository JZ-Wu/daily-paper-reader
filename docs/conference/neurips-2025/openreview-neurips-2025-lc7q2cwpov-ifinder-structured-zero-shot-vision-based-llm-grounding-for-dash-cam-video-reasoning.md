---
title: "iFinder: Structured Zero-Shot Vision-Based LLM Grounding for Dash-Cam Video Reasoning"
title_zh: iFinder：面向行车记录仪视频推理的结构化零样本视觉LLM定位框架
authors: "Manyi Yao, Bingbing Zhuang, Sparsh Garg, Amit Roy-Chowdhury, Christian R. Shelton, Manmohan Chandraker, Abhishek Aich"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=lC7q2cwpov"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 零样本无需训练的LLM视频定位
tldr: 针对行车记录仪视频分析中纯视觉空间推理与因果推理困难，提出iFinder，一种训练无关的模块化框架，将视频转化为结构化层次数据以增强LLM的理解，实现零样本grounding。该方法在空间推理和可解释性上优于现有视频视觉语言模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 643, \"height\": 401}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 705, \"height\": 711}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-004.webp\", \"caption\": \"\", \"page\": 4, \"index\": 4, \"width\": 2476, \"height\": 1344}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-005.webp\", \"caption\": \"\", \"page\": 6, \"index\": 5, \"width\": 949, \"height\": 574}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-006.webp\", \"caption\": \"\", \"page\": 6, \"index\": 6, \"width\": 957, \"height\": 573}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-007.webp\", \"caption\": \"\", \"page\": 9, \"index\": 7, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-008.webp\", \"caption\": \"\", \"page\": 9, \"index\": 8, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-009.webp\", \"caption\": \"\", \"page\": 9, \"index\": 9, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-010.webp\", \"caption\": \"\", \"page\": 9, \"index\": 10, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-011.webp\", \"caption\": \"\", \"page\": 30, \"index\": 11, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-012.webp\", \"caption\": \"\", \"page\": 30, \"index\": 12, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-013.webp\", \"caption\": \"\", \"page\": 30, \"index\": 13, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-014.webp\", \"caption\": \"\", \"page\": 30, \"index\": 14, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-015.webp\", \"caption\": \"\", \"page\": 30, \"index\": 15, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-016.webp\", \"caption\": \"\", \"page\": 34, \"index\": 16, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-017.webp\", \"caption\": \"\", \"page\": 34, \"index\": 17, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-018.webp\", \"caption\": \"\", \"page\": 35, \"index\": 18, \"width\": 2048, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-lc7q2cwpov/fig-019.webp\", \"caption\": \"\", \"page\": 35, \"index\": 19, \"width\": 2048, \"height\": 1280}]"
motivation: 行车记录仪视频仅靠视觉模态，现有视频视觉语言模型难以完成空间推理与因果推理，且通用LLM缺乏该领域归纳偏置。
method: iFinder采用模块化训练无关流程，先将视频转换为层次化结构化数据，再交由LLM进行推理。
result: 在行车记录仪视频分析中，相比现有VLM，空间推理与可解释性显著提升。
conclusion: 训练无关的结构化视频定位框架可有效将通用LLM适配于特定领域视频分析。
---

## Abstract
Grounding large language models (LLMs) in domain-specific tasks like post-hoc dash-cam driving video analysis is challenging due to their general-purpose training and lack of structured inductive biases. As vision is often the sole modality available for such analysis (i.e., no LiDAR, GPS, etc.), existing video-based vision-language models (V-VLMs) struggle with spatial reasoning, causal inference, and explainability of events in the input video. To this end, we introduce iFinder, a structured semantic grounding framework that decouples perception from reasoning by translating dash-cam videos into a hierarchical, interpretable data structure for LLMs. iFinder operates as a modular, training-free pipeline that employs pretrained vision models to extract critical cues—object pose, lane positions, and object trajectories—which are hierarchically organized into frame- and video-level structures. Combined with a three-block prompting strategy, it enables step-wise, grounded reasoning for the LLM to refine a peer V-VLM's outputs and provide accurate reasoning.
Evaluations on four public dash-cam video benchmarks show that iFinder's proposed grounding with domain-specific cues—especially object orientation and global context—significantly outperforms end-to-end V-VLMs on four zero-shot driving benchmarks, with up to 39% gains in accident reasoning accuracy. By grounding LLMs with driving domain-specific representations, iFinder offers a zero-shot, interpretable, and reliable alternative to end-to-end V-VLMs for post-hoc driving video understanding.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：针对行车记录仪（dash‑cam）视频的事后分析，如何在**仅有视觉输入（无激光雷达、GPS等）**的条件下，实现准确的**空间推理、因果推理与可解释的问答**。
- **现有挑战**：
  - 通用大语言模型（LLM）缺少驾驶领域的结构化归纳偏置，难以直接理解原始视频。
  - 端到端的视频‑视觉语言模型（V‑VLM）在细粒度场景理解、空间与因果推理上常产生错误或模糊的回答。
- **整体含义**：提出一种**将感知与推理解耦**的框架，通过预训练视觉模型从视频中提取驾驶领域关键信息并组织为**结构化、可解释的数据**，再交由通用LLM进行事实性、可验证的推理，从而提升零样本行车记录仪视频理解的准确性和可解释性。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **感知‑推理分离**：用现有视觉模型把行车视频转化为结构化层次表示，再让LLM基于这些符号化证据进行推理。
- **零样本、训练无关**：整个流水线无需任何微调，仅使用预训练视觉模型与通用LLM。
- **双阶段推理**：先由“同伴”V‑VLM给出初步答案，再让LLM在结构化信息的辅助下精炼与修正该答案。

### 关键技术细节（流水线步骤）
1. **镜头畸变校正**：估计相机内参及畸变系数，对每一帧进行去畸变处理。
2. **场景理解**：用图像VLM获取天气、光照、道路结构等；用视频VLM生成事件描述。
3. **自车状态估计**：通过相机位姿估计推断自车的“运动/停止”和“直行/左转/右转”。
4. **2D目标检测与追踪**：检测车辆、行人等，并通过多目标跟踪器赋予唯一ID。
5. **目标车道定位**：在检测到的车道线基础上，将目标（含自车）分配到具体车道。
6. **目标距离估计**：利用单目深度估计与分割掩码，计算目标相对自车的平均距离。
7. **目标属性提取**：用图像VLM提取目标颜色等属性。
8. **3D检测与目标朝向**：从3D检测中获得目标的偏航角，并将其传播至2D检测结果。

### 数据结构与提示策略
- **层次化数据结构**：以JSON格式输出视频级信息（环境、自车状态、事件描述、同伴VLM回答）和帧级信息（目标ID、类别、边界框、距离、车道、朝向、颜色等）。
- **三块提示策略**：
  - **关键解释**：向LLM解释所有结构化字段的含义。
  - **步骤指导**：将推理拆分为多个子目标，引导逐步分析。
  - **同伴指导**：告知LLM同伴VLM的回答可能不准确，鼓励独立基于数据推理。

## 3. 实验设计

### 数据集与场景
- **MM‑AU（多模态事故视频理解）**：1953个测试视频，多选题形式，问题“事故原因是什么？”。
- **SUTD‑TrafficQA**：4111个真实驾驶视频，6075个多选题，覆盖基础理解、事件预测、反向推理、反事实推理、内省及归因六类认知任务。
- **LingoQA**：100个视频，500个开放式问答，需生成自然语言回答。
- **Nexar**：从训练集中抽取100个视频（50个有事故/50个无事故），用于事故出现预测。

### 对比方法
- 通用V‑VLM：VideoLLaMA2（及其提示微调版）、VideoChat2、Video‑LLaVA。
- 驾驶专用模型：DriveMM、WiseAD。
- 所有方法均在严格零样本设置下评测，无任何微调。

## 4. 资源与算力

- **硬件**：所有实验在**单张NVIDIA A6000 GPU（48 GB显存）**上完成。
- **时间开销**：论文在附录中提供了每个模块处理单个LingoQA视频的平均墙钟时间，例如帧去畸变66.7秒、3D检测14.8秒、距离估计40.3秒等；整个流水线为一系列独立前向推理，无训练过程。
- **非实时**：论文明确说明其目标是事后分析，不追求实时部署。

## 5. 实验数量与充分性

- **主要定量实验**：
  - 四组数据集上的对比实验（表1‑4），包括多选题准确率、类别细粒度得分、开放问答指标、事故预测准确率等。
  - 消融研究：逐一移除视觉组件（自车状态、车道、距离、去畸变、属性、朝向、场景理解），以及提示组件（同伴指令、步骤指令、关键解释），分析对MM‑AU准确率的影响（表5）。
  - 天气/光照条件细分：在MM‑AU下展示不同天气（雾、雨、雪、晴）和光照（白天/夜晚）的性能（表6、表7）。
  - 误差传播分析：通过调整目标检测置信度阈值模拟漏检，观察准确率随保留目标比例的变化（表8）。
  - 定性示例：在摘要和附录中提供了与多个基线模型对比的可视化案例。
- **公平性与客观性**：
  - 所有方法均零样本对比，不涉及额外微调。
  - 默认同伴V‑VLM为VideoLLaMA2，保证了比较基线的一致性。
  - 误差传播实验展示了系统对感知模块错误的鲁棒性。
  - 实验覆盖多个驾驶场景、多种推理类型及环境条件，较为全面。

## 6. 论文的主要结论与发现

- **结构化表示显著提升LLM的驾驶视频推理能力**：在多个基准上，iFinder以零样本方式大幅超过通用及驾驶专用V‑VLM，尤其在事故推理数据集MM‑AU上，相较最强通用模型提升10.5%，相较驾驶专用模型提升39%。
- **目标朝向与全局环境信息最为关键**：消融表明，移除朝向信息导致准确率下降约4.5%，移除场景理解下降约5.6%，其重要程度甚至超过距离或车道位置（影响约2.7%）。
- **提示设计三要素缺一不可**：关键解释、步骤指导与同伴提示均对最终性能有重要贡献，缺少任一模块都会导致明显下降。
- **系统对感知误差有较好容错性**：即使保持极少部分检测目标，推理准确率仍能超过最强基线。
- **iFinder在不同天气与光照下均表现出较强的鲁棒性**，在恶劣条件下性能衰退远小于对比方法。

## 7. 优点：方法或实验设计上的亮点

- **训练无关的模块化设计**：所有组件均为现成的预训练模型，无需任何微调，易于迁移和升级。
- **解耦感知与推理**：通过中间结构化表示使LLM能够进行符号化、可追溯的推理，提升了可解释性与事实可靠性。
- **强大的零样本性能**：在多个数据集和任务类型下均取得最优，证明结构化领域线索对LLM推理至关重要。
- **充分的实验分析与可复现性**：提供了详细的消融、误差传播、跨条件分析以及完整的提示词和参数设置，便于复现。
- **定性展示有效**：通过具体案例展示了iFinder如何利用追踪ID、距离、朝向等数据纠正同伴V‑VLM的错误，使推理过程透明可验证。

## 8. 不足与局限

- **社会规范与意图推理缺失**：当前框架未能捕捉行驶意图、让行行为等抽象或规范性要素，这些在真实交通理解中常至关重要。
- **高度依赖感知模块的准确性**：尽管有一定容错性，但整体性能仍受限于各视觉模型的精度，尤其对遮挡、小目标或极端天气的鲁棒性有待加强。
- **非实时应用**：流水线耗时较长，不适用于在线自动驾驶系统，仅定位于离线分析。
- **同伴模型依赖性**：框架需借助同伴V‑VLM的输出，若同伴过于混乱可能导致LLM被误导；论文虽可选出较强的同伴，但最终答案仍可能受其制约。
- **数据集覆盖**：测评所用数据集虽然多样，但事故类样本比例可能不均衡；Nexar实验样本仅100个，偶然性风险存在。
- **未知条件下的泛化**：缺少对更复杂路况（如无标记道路、异形车道）或新传感器配置的测试，存在泛化性风险。

（完）
