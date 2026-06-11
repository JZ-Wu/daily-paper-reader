---
title: "MAGNET: A Multi-agent Framework for Finding Audio-Visual Needles by Reasoning over Multi-Video Haystacks"
title_zh: MAGNET：通过推理多视频大海捞针式多代理寻找视听关键片段
authors: "Sanjoy Chowdhury, Mohamed Elmoghany, Yohan Abeysinghe, Junjie Fei, Sayan Nag, Salman Khan, Mohamed Elhoseiny, Dinesh Manocha"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CwXyUdqFqW"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 多代理框架，用于跨视频视听检索
tldr: 针对大规模视频集合中的复杂视听推理需求，提出MAGNET多代理框架，引入AVHaystacksQA新任务，要求从多视频中定位并连接关键片段以生成最优回答。实验表明该框架在跨视频检索与推理上显著优于单视频方法，推动了代理式多视频理解的发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 1024, \"height\": 1024}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 4040, \"height\": 2205}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 2345, \"height\": 1280}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-004.webp\", \"caption\": \"\", \"page\": 9, \"index\": 4, \"width\": 994, \"height\": 726}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-005.webp\", \"caption\": \"\", \"page\": 24, \"index\": 5, \"width\": 2971, \"height\": 1466}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-006.webp\", \"caption\": \"\", \"page\": 24, \"index\": 6, \"width\": 2972, \"height\": 1466}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-007.webp\", \"caption\": \"\", \"page\": 24, \"index\": 7, \"width\": 2971, \"height\": 1466}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-008.webp\", \"caption\": \"\", \"page\": 25, \"index\": 8, \"width\": 989, \"height\": 490}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-009.webp\", \"caption\": \"\", \"page\": 26, \"index\": 9, \"width\": 993, \"height\": 737}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-010.webp\", \"caption\": \"\", \"page\": 27, \"index\": 10, \"width\": 878, \"height\": 884}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-011.webp\", \"caption\": \"\", \"page\": 28, \"index\": 11, \"width\": 913, \"height\": 662}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-012.webp\", \"caption\": \"\", \"page\": 28, \"index\": 12, \"width\": 998, \"height\": 655}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-013.webp\", \"caption\": \"\", \"page\": 29, \"index\": 13, \"width\": 994, \"height\": 508}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-014.webp\", \"caption\": \"\", \"page\": 31, \"index\": 14, \"width\": 2592, \"height\": 1008}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-015.webp\", \"caption\": \"\", \"page\": 33, \"index\": 15, \"width\": 2756, \"height\": 1737}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-016.webp\", \"caption\": \"\", \"page\": 35, \"index\": 16, \"width\": 4795, \"height\": 6000}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-017.webp\", \"caption\": \"\", \"page\": 35, \"index\": 17, \"width\": 4795, \"height\": 6000}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-018.webp\", \"caption\": \"\", \"page\": 36, \"index\": 18, \"width\": 4795, \"height\": 6000}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-019.webp\", \"caption\": \"\", \"page\": 36, \"index\": 19, \"width\": 4635, \"height\": 6000}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-020.webp\", \"caption\": \"\", \"page\": 37, \"index\": 20, \"width\": 4635, \"height\": 6000}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cwxyudqfqw/fig-021.webp\", \"caption\": \"\", \"page\": 37, \"index\": 21, \"width\": 4635, \"height\": 6000}]"
motivation: 现有视频问答基准局限于单段视频，无法应对多视频大规模检索与推理。
method: 构建多代理框架，协同定位不同视频中的关键片段并整合生成答案。
result: 在AVHaystacksQA上大幅超越基线，展现多代理系统在复杂视听推理中的优势。
conclusion: MAGNET为多视频推理提供了有效的代理方案，拓展了代理式视频理解的边界。
---

## Abstract
Large multimodal models (LMMs) have shown remarkable progress in audiovisual understanding, yet they struggle with real-world scenarios that require complex reasoning across extensive video collections. Existing benchmarks for video question answering remain limited in scope, typically involving one clip per query, which falls short of representing the challenges of large-scale, audiovisual retrieval and reasoning encountered in practical applications. To bridge this gap, we introduce a novel task named AVHaystacksQA, where the goal is to identify salient segments across different videos in response to a query and link them together to generate the most informative answer. To this end, we present AVHaystacks, an audio-visual benchmark comprising 3100 annotated QA pairs designed to assess the capabilities of LMMs in multi-video retrieval and temporal grounding task. Additionally, we propose a model-agnostic, multi-agent framework MAGNET to address this challenge, achieving up to 89% and 65% relative improvements over baseline methods on BLEU@4 and GPT evaluation scores in QA task on our proposed AVHaystacks. To enable robust evaluation of multi-video retrieval and temporal grounding for optimal response generation, we introduce two new metrics, STEM, which captures alignment errors between a ground truth and a predicted step sequence and MTGS, to facilitate balanced and interpretable evaluation of segment-level grounding performance.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究背景与动机**：当前大型多模态模型（LMMs）在单视频视听理解任务中表现优异，但真实场景中往往需要在大量视频集合中进行跨视频检索与复杂推理（例如查询个人视频档案或教育视频库）。现有视频问答基准普遍限于“一题一片”的设定，无法评估模型在多视频、大规模环境下的检索与多步推理能力。
- **核心问题**：提出名为**AVHaystacksQA**的新任务，要求模型针对一个自然语言查询，从庞大的视频语料库中定位多个视频中的关键视听片段，并将这些片段关联、合成，生成最全面、有时序依据的答案。该任务本质上是一种“多视频大海捞针”式的视听检索与推理挑战。

## 2. 方法论

为解决上述任务，论文提出了模型无关的多代理框架**MAGNET**，整体流程分为检索、帧选择与代理推理三个阶段。

- **视听预处理与检索（AV-RAG）**  
  - 使用 ImageBind 对查询文本和视频的视听特征进行编码，同时利用 Gemini 1.5 Pro 为视频生成描述，并编码为文本嵌入。  
  - 对于查询 q 和视频集 V，通过余弦相似度计算平均相似度 `Sim_avg`，融合视听特征相似度与描述文本相似度。  
  - 按相似度降序排序，选择 Top-k 最相关的视频作为候选。

- **显著帧选择器（Salient Frame Selector, SFS）**  
  - 目的：从长视频中高效定位与查询相关的稀疏但关键的时刻。  
  - 方法：先均匀采样 m 帧，提取每帧的视听联合嵌入，计算帧间余弦相似度矩阵 Γ_ab。  
  - 引入时间分离惩罚项 Δ_ab（利用反三角函数抑制时间上相邻帧的重复性），得到总亲和力矩阵 Q_ab = Γ_ab + Δ_ab。  
  - 使用动态规划算法（算法1）从 m 帧中选择 k 个帧索引，最小化相邻选定帧之间的总亲和力，从而选出既视觉多样化又在时间上分散的关键帧。

- **基于视听代理的扎根问答**  
  - 对每个候选视频，动态生成一个基于 Qwen 2.5 Omni 的视听代理，独立分析视频并输出最相关的时间段以及局部答案。  
  - 所有代理的输出（时间窗与部分回答）交由一个**元代理（Meta-Agent）**（默认采用 GPT-4o）进行汇总，综合生成具有跨视频时序依据的连贯最终答案。  
  - 该结构实现了检索与推理的紧密耦合，支持高效扩展至大规模视频集。

- **评估指标**  
  - 提出 **STEM（Step-wise Error Metric）**：通过匈牙利匹配量化预测步骤序列与真实步骤序列之间的对齐错误，涵盖缺失步骤、幻觉步骤、顺序错误以及视频 ID 和时间段的匹配偏差。  
  - 提出 **MTGS（Matched Temporal Grounding Score）**：仅针对视频 ID 匹配的片段，计算预测与真实时间区间的平均交并比，提供可解释的片段级扎根评估。

## 3. 实验设计

- **数据集与基准**  
  - 构造了 **AVHaystacks** 基准，包含 500 个视频，涵盖 27 个领域（如教程、烹饪、音乐、语言学习等），共 3100 条问答对（训练/测试约为 2k/1k）。  
  - 82% 的问题需要从至少两个不同视频中提取证据，实现了跨视频的多模态实体链接。  
  - 为支持基线实验，额外创建小规模子集 **AVHaystacks-50**。

- **对比方法**  
  - 基线模型：VideoRAG、Video-RAG、Qwen 2.5 Omni、Unified IO2、Video-SALMONN。  
  - MAGNET 框架与上述多个 AVLLM 结合，包含零样本（ZS）与微调（FT）版本，并引入闭源模型 Gemini 1.5 Pro 作为性能上界参考。  
  - 评估指标：回答质量（BLEU@4, CIDEr, 文本相似度, GPT Eval, 人工评分）、检索召回率（R@1,3,5）、时序扎根指标（MTGS, STEM）。

## 4. 资源与算力

- 论文明确给出了微调部分的计算资源：  
  - 使用 **4 块 A100 GPU** 进行训练。  
  - 共训练 **5 个 epoch**，选取最佳检查点用于评估。  
  - 采用 LoRA（秩 8，alpha 32）进行参数高效微调；优化器为 AdamW，学习率 1e-4，每设备批次大小 1，梯度累计步长 16，余弦学习率调度、预热比例 0.05。

## 5. 实验数量与充分性

- **实验覆盖较全面**  
  - 对多种开源和闭源 AVLLM 进行性能比较，涵盖零样本和微调两种设定。  
  - 在 AVHaystacks-50 和 AVHaystacks-Full 两个数据规模下均进行了测试，保证了可扩展性验证。  
  - 设置了丰富的消融研究：  
    - 模态组合（纯音频、纯视觉、视听联合）。  
    - 帧采样策略（均匀采样 vs. SFS）。  
    - 惩罚超参数 γ 的影响分析。  
    - Top-k 视频数量、元代理选择、帧采样函数形式、帧数选择、文本相似度阈值 τ_s 等。  
  - 所提出的 STEM 指标经过与人工评价（20 名评估者，Cohen’s κ=0.82）的相关性验证。
- **公平性**：基线模型均经适当适配（统一采样帧并压缩音频）以支持长视频输入；MAGNET 统一使用 ImageBind 编码和相同代理结构，对比条件一致。

## 6. 主要结论与发现

- MAGNET 框架在 AVHaystacksQA 上显著超越所有基线方法，在回答质量（BLEU@4 相对提升最高约 89%，GPT Eval 相对提升约 65%）和检索精度（R@5 提升至 79.20）上均取得大幅领先。
- 细粒度的视听扎根评估表明，引入 SFS 和多代理推理能大幅降低步骤错失、幻觉和时序偏差，同时提升 MTGS 分数。
- 多模态信息（音频+视觉）相较于单一模态带来显著增益；SFS 优于常规均匀采样；元代理的选择对最终生成质量影响明显。
- MAGNET + Qwen 2.5 Omni-FT 的性能已十分接近 Gemini 1.5 Pro 上界，展示了开源模型在框架加持下的潜力。

## 7. 优点

- **任务新颖且贴近实际**：首次提出多视频、跨片段视听检索与推理的 QA 任务，并配套了大规模、细粒度的基准。
- **方法简洁有效**：MAGNET 通过检索增强、显著性帧选择和动态多代理协作，无需改动 LMM 内部结构，即实现了模型无关的大幅提升。
- **评估体系完善**：不仅引入传统文本指标和人工评价，还设计了专门的 STEM 和 MTGS 以量化时序扎根和步骤对齐错误，且通过人工一致性验证了其有效性。
- **实验扎实**：系统性的消融分析清晰展现了不同组件（模态、采样、元代理、参数）的贡献，提供了良好的参考价值。

## 8. 不足与局限

- **框架依赖组件较多**：检索、帧选择、多代理推理等模块为 pipeline 形式，部分组件并非端到端可训练，可能限制了联合优化空间。
- **未见统计显著性检验**：实验中未报告误差条或显著性检验，结果的稳定性尚缺乏严格统计支撑。
- **应用局限性**：基准视频主要来自公开教程类 YouTube 视频，对特定领域（如监控、直播、非结构化视频）的泛化性未验证；检索依赖 ImageBind 编码，可能受预训练数据分布影响。
- **未充分讨论隐私与偏见**：虽声明遵守伦理准则，但对视频数据中可能存在的个人隐私、文化偏见等社会影响讨论不足。

（完）
