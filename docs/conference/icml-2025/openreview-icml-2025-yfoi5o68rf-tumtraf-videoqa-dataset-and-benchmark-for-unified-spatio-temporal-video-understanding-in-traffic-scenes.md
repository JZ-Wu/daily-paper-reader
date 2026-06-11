---
title: "TUMTraf VideoQA: Dataset and Benchmark for Unified Spatio-Temporal Video Understanding in Traffic Scenes"
title_zh: TUMTraf VideoQA：面向交通场景统一时空视频理解的数据集与基准
authors: "Xingcheng Zhou, Konstantinos Larintzakis, Hao Guo, Walter Zimmer, Mingyu Liu, Hu Cao, Jiajie Zhang, Venkatnarayanan Lakshminarasimhan, Leah Strand, Alois Knoll"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Yfoi5O68rf"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 数据集包含时空物体定位任务，直接与视频定位相关
tldr: "TUMTraf VideoQA是一个面向交通场景时空视频理解的数据集，包含1000个视频和85,000个问答对、2,300个物体描述和5,700个物体定位标注，统一了视频问答、指称物体描述和时空物体定位三项任务。该数据集为视频定位研究提供了基准，并引入了TraffiX-Qwen基线模型。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 423, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 413, \"height\": 195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1712, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 845, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 847, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 835, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1624, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1626, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 737, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 749, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 751, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1710, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1770, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1773, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1768, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1767, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 802, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 802, \"height\": 1001, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 803, \"height\": 1005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yfoi5o68rf/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1678, \"height\": 1978, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1782, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 873, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1779, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 893, \"height\": 677, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 892, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yfoi5o68rf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1766, \"height\": 369, \"label\": \"Table\"}]"
motivation: 复杂路边交通场景缺乏统一时空视频理解基准，尤其是物体定位任务。
method: 构建TUMTraf VideoQA数据集，包含多元标注，并引入TraffiX-Qwen基线模型，增强视觉令牌采样。
result: 提供了丰富的基准，涵盖多种真实世界条件。
conclusion: 该数据集推动了交通场景的视频定位与理解研究。
---

## Abstract
We present TUMTraf VideoQA, a novel dataset and benchmark designed for spatio-temporal video understanding in complex roadside traffic scenarios. The dataset comprises 1,000 videos, featuring 85,000 multiple-choice QA pairs, 2,300 object captioning, and 5,700 object grounding annotations, encompassing diverse real-world conditions such as adverse weather and traffic anomalies. By incorporating tuple-based spatio-temporal object expressions, TUMTraf VideoQA unifies three essential tasks—multiple-choice video question answering, referred object captioning, and spatio-temporal object grounding—within a cohesive evaluation framework. We further introduce the TraffiX-Qwen baseline model, enhanced with visual token sampling strategies, providing valuable insights into the challenges of fine-grained spatio-temporal reasoning. Extensive experiments demonstrate the dataset’s complexity, highlight the limitations of existing models, and position TUMTraf VideoQA as a robust foundation for advancing research in intelligent transportation systems. The dataset and benchmark are publicly available to facilitate further exploration.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **研究动机**：传统交通场景理解模型多针对单一任务（如目标检测、跟踪），难以应对复杂、多变的现实场景，且缺乏从路边监控视角对细粒度时空关系进行统一理解的能力。现有视觉语言数据集主要面向驾驶视角，忽略了路边视角视频中时空目标定位与推理的需求。
*   **核心问题**：如何构建一个统一的、能同时评估视频问答、指称目标描述（Referred Object Captioning）和时空目标定位（Spatio-Temporal Object Grounding）的基准，以推动智能交通系统中细粒度视频理解的研究。

### 2. 论文提出的方法论
#### 2.1 数据集构建
*   **半自动标注流水线**：包含三个阶段——视频选取、元数据整理（利用目标检测/跟踪器、大视觉语言模型及外部天气/事故记录生成相机伪3D位置、目标轨迹及外观描述，并经人工校验）以及问答对生成与过滤。
*   **生成方式**：混合使用模板（约15类模板，经LLM扩展）和LLM（GPT-4o-mini），通过迭代优化与质量检查生成高质量、多样化的问答对。
*   **时空对象表达**：采用唯一四元组 `(c, f_n, x, y)` 统一表示目标在视频中的时空位置，其中 `c` 为目标标识符，`f_n` 为归一化帧时间戳，`(x, y)` 为归一化图像中心坐标。

#### 2.2 任务与评估指标
*   **多选问答（MQA）**：涵盖五大维度（定位、计数、运动、类别、存在），每个维度按单跳（Easy）和多跳（Hard）难度划分，以 Top-1 准确率为指标。
*   **视频指称目标描述（V-ROC）**：根据给定目标的时空位置生成其外观描述，使用 BLEU-4、ROUGE-L、CIDEr、METEOR、SPICE 等 NLG 指标评估。
*   **时空目标定位（ST-OG）**：给定目标标识，预测其起始和结束帧的时空元组 `[(c, f'_n, x', y'), (c, f''_n, x'', y'')]`，采用时间误差 `E_{f_n}`（L1）、空间误差 `E_s`（L2 距离）和时空综合误差 `E_{st}`（L2 范数）评估。

#### 2.3 基线模型 TraffiX-Qwen
*   **架构**：视觉编码器 SigLIP（384×384 输入，采样101帧） + 跨模态投影层 + 视觉令牌采样器 + 大语言模型 Qwen-2（7B/0.5B）。
*   **视觉令牌采样策略**：
    *   `Spatial Pooling`：对每帧特征图做空间池化。
    *   `MultiRes Spatial-Pooling`：首帧保持高分辨率，其余帧空间池化。
    *   `MultiRes Token-Pruning`：首帧为关键帧，后续帧保留与关键帧余弦相似度最低的25%令牌。
    *   `MultiRes Temporal-Pooling`：基于问题自适应选取关键帧（`K ≤ 2`）保持高分辨率，其余帧池化。
*   **训练**：两阶段训练（4块A100）：先视频-语言对齐（训练投影层，1 epoch）；再视觉指令微调（冻结视觉编码器和投影，全参微调 LLM，1 epoch）。

### 3. 实验设计
*   **数据集 / 场景**：使用自建的 TUMTraf VideoQA（1000 个视频，85k 问答对，5.7k 定位标注，2.3k 描述标注），涵盖城市、郊区、高速等多种场景，以及晴天、雨雪、事故等复杂条件。
*   **对比方法**：
    *   **开放源模型零样本**：LLaVA-OneVision (0.5B/7B)、Qwen2-VL (2B/7B)、VideoLLaMA2 (7B-8F/16F)。
    *   **基线模型不同变体**：TraffiX-Qwen 0.5B 和 7B，结合 4 种视觉令牌采样策略。
    *   **消融实验**：探究输入帧数（无视觉、1帧、11帧、101帧）对性能的影响，以及在统一 101 帧输入下各类模型的对比。

### 4. 资源与算力
*   **GPU**：4 块 NVIDIA A100。
*   **训练时长**：
    *   TraffiX-Qwen-0.5B：28 小时（可训练参数 495.6M）。
    *   TraffiX-Qwen-7B：36 小时（可训练参数 7629.6M）。
*   **推理速度**：0.5B 模型约 1.6 秒/问题，7B 模型约 3.8 秒/问题（单卡 A100，无量化/缓存加速）。

### 5. 实验数量与充分性
*   **实验组数**：在三个主要任务上，系统评估了 3 类开放源模型（共 6 个配置）和 2 种规模的基线模型（各 4 种采样策略），构成约 25 组主要对比实验。
*   **消融与一致性分析**：额外开展了帧数影响分析（4 种配置下评估三个任务）和统一帧数对比，验证结论的稳健性。
*   **充分性与客观性**：实验设计较为全面，覆盖零样本与微调模型，对比了不同架构和参数量的方法，并分析了各项任务的难易程度。所有对比均采用相同的系统提示和评估指标，保证了相对公平。

### 6. 论文的主要结论与发现
*   **任务难度差异**：存在类问题最简单，运动/计数其次，3D 空间定位问题最难；多跳问题难度普遍高于单跳问题。
*   **现有模型局限**：开放源模型零样本表现不佳，尤其在定位任务上，即便扩大模型规模或增加输入帧数，提升亦有限。这说明当前模型普遍缺乏细粒度时空推理能力。
*   **TraffiX-Qwen 基线表现**：经过微调的基线模型在所有任务上大幅超越零样本模型，验证了该基准的可学习性。
*   **视觉令牌策略影响**：多分辨率策略能轻微提升问答和描述性能（特别是定位维度），但对时空定位任务可能产生负面影响，表明动态改变帧分辨率会损害帧间表征的一致性。
*   **帧数的作用**：增加输入帧数能提升性能，但从 11 帧到 101 帧的提升幅度明显减小，模型从密集视觉令牌中高效提取上下文的能力待加强。模型存在依赖文本先验产生“幻觉”答案的倾向。

### 7. 优点
*   **统一框架**：首次在单一基准中融合视频问答、指称目标描述和时空目标定位三项任务，且采用统一的时空元组表达，设计新颖。
*   **数据质量与多样性**：半自动标注结合人工校验，保证了标注质量。数据集覆盖日夜、多天气、多场景及事故等边缘案例，贴近真实交通监控需求。
*   **基线设计**：提供的 TraffiX-Qwen 可统一处理所有任务，并设计了多种视觉令牌采样策略，为后续研究提供了清晰的对比基础和效率优化思路。
*   **分析深入**：不仅对比了性能，还通过分难度、消融帧数和令牌策略等实验，深入剖析了模型在时空推理上的具体短板。

### 8. 不足与局限
*   **模型能力限制**：基线模型在时空定位和指称描述上的指标绝对值仍较低，3D 空间推理能力不足，距离实际部署仍有差距。
*   **数据偏差风险**：虽然覆盖较广，但数据主要来自德国慕尼黑周边，天气、交通规则和场景分布可能存在地域性偏差。
*   **多分辨率策略适用性**：发现该策略在时空定位任务上可能有害，其通用设计仍需改进，论文暂未给出完美解决方案。
*   **评估指标**：指称描述仍采用传统 NLG 指标，部分指标（如 ROUGE-L）无法准确反映语义准确性，缺乏基于 LLM 的更高级评估。
*   **任务定义简化**：时空定位任务将目标的时间范围简化为起始和终止帧，而现实中目标可能存在进出视野、遮挡等情况，任务设定相对理想化。

（完）
