---
title: "Empower Words: DualGround for Structured Phrase and Sentence-Level Temporal Grounding"
title_zh: 词语赋能：DualGround用于结构化短语和句子级时序定位
authors: "Minseok Kang, Minhyeok Lee, Minjung Kim, Donghyeong Kim, Sangyoun Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=p5PFCVsXWf"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 直接涉及需求1中指定的视频时序定位任务。
tldr: "现有视频时序定位模型过度依赖[EOS]全局语义，忽略了词汇级信号。本文提出DualGround，通过强制短语和句子级结构化定位，使模型有效利用词级信息。在标准基准上，该方法提升了时刻检索和高亮检测的准确率，证明了细粒度对齐对视频理解的重要价值。"
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 1064, \"height\": 313}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 1212, \"height\": 452}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 1021, \"height\": 644}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-004.webp\", \"caption\": \"\", \"page\": 4, \"index\": 4, \"width\": 1021, \"height\": 644}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-005.webp\", \"caption\": \"\", \"page\": 4, \"index\": 5, \"width\": 698, \"height\": 839}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-006.webp\", \"caption\": \"\", \"page\": 4, \"index\": 6, \"width\": 846, \"height\": 839}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-007.webp\", \"caption\": \"\", \"page\": 9, \"index\": 7, \"width\": 1689, \"height\": 823}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-008.webp\", \"caption\": \"\", \"page\": 27, \"index\": 8, \"width\": 353, \"height\": 1137}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-009.webp\", \"caption\": \"\", \"page\": 27, \"index\": 9, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-010.webp\", \"caption\": \"\", \"page\": 27, \"index\": 10, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-011.webp\", \"caption\": \"\", \"page\": 27, \"index\": 11, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-012.webp\", \"caption\": \"\", \"page\": 27, \"index\": 12, \"width\": 2800, \"height\": 333}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-013.webp\", \"caption\": \"\", \"page\": 27, \"index\": 13, \"width\": 1598, \"height\": 255}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-014.webp\", \"caption\": \"\", \"page\": 27, \"index\": 14, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-015.webp\", \"caption\": \"\", \"page\": 27, \"index\": 15, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-016.webp\", \"caption\": \"\", \"page\": 27, \"index\": 16, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-017.webp\", \"caption\": \"\", \"page\": 27, \"index\": 17, \"width\": 2800, \"height\": 333}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-018.webp\", \"caption\": \"\", \"page\": 27, \"index\": 18, \"width\": 1591, \"height\": 260}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-019.webp\", \"caption\": \"\", \"page\": 27, \"index\": 19, \"width\": 351, \"height\": 1105}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-020.webp\", \"caption\": \"\", \"page\": 27, \"index\": 20, \"width\": 1608, \"height\": 276}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-021.webp\", \"caption\": \"\", \"page\": 27, \"index\": 21, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-022.webp\", \"caption\": \"\", \"page\": 27, \"index\": 22, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-023.webp\", \"caption\": \"\", \"page\": 27, \"index\": 23, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-024.webp\", \"caption\": \"\", \"page\": 27, \"index\": 24, \"width\": 2800, \"height\": 333}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-025.webp\", \"caption\": \"\", \"page\": 27, \"index\": 25, \"width\": 369, \"height\": 1130}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-026.webp\", \"caption\": \"\", \"page\": 28, \"index\": 26, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-027.webp\", \"caption\": \"\", \"page\": 28, \"index\": 27, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-028.webp\", \"caption\": \"\", \"page\": 28, \"index\": 28, \"width\": 2800, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-029.webp\", \"caption\": \"\", \"page\": 28, \"index\": 29, \"width\": 2800, \"height\": 333}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-030.webp\", \"caption\": \"\", \"page\": 28, \"index\": 30, \"width\": 1606, \"height\": 267}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p5pfcvsxwf/fig-031.webp\", \"caption\": \"\", \"page\": 28, \"index\": 31, \"width\": 361, \"height\": 1136}]"
motivation: 解决VTG模型忽视词汇级语义、仅依赖全局EOS表示的局限。
method: 提出DualGround，一种强制短语和句子级结构化定位的方法，利用词级注意力。
result: 在时刻检索和高亮检测上显著提升，优于现有统一建模方法。
conclusion: 词汇级信号对精确时序定位至关重要，结构化定位可有效利用文本细粒度语义。
---

## Abstract
Video Temporal Grounding (VTG) aims to localize temporal segments in long, untrimmed videos that align with a given natural language query. This task typically comprises two subtasks: \textit{Moment Retrieval (MR)} and \textit{Highlight Detection (HD)}. While recent advances have been progressed by powerful pretrained vision-language models such as CLIP and InternVideo2, existing approaches commonly treat all text tokens uniformly during cross-modal attention, disregarding their distinct semantic roles. To validate the limitations of this approach, we conduct controlled experiments demonstrating that VTG models overly rely on [EOS]-driven global semantics while failing to effectively utilize word-level signals, which limits their ability to achieve fine-grained temporal alignment. Motivated by this limitation, we propose DualGround, a dual-branch architecture that explicitly separates global and local semantics by routing the [EOS] token through a sentence-level path and clustering word tokens into phrase-level units for localized grounding. Our method introduces (1) token-role-aware cross modal interaction strategies that align video features with sentence-level and phrase-level semantics in a structurally disentangled manner, and (2) a joint modeling framework that not only improves global sentence-level alignment but also enhances fine-grained temporal grounding by leveraging structured phrase-aware context. This design allows the model to capture both coarse and localized semantics, enabling more expressive and context-aware video grounding. DualGround achieves state-of-the-art performance on both Moment Retrieval and Highlight Detection tasks across QVHighlights and Charades-STA benchmarks, demonstrating the effectiveness of disentangled semantic modeling in video-language alignment.

---

## 论文详细总结（自动生成）

## 1. 论文核心问题与整体含义（研究动机和背景）

- **研究背景**  
  - 视频时序定位（Video Temporal Grounding, VTG）旨在根据自然语言查询，在长视频中定位相关片段，通常包含**时刻检索（Moment Retrieval, MR）** 和**高亮检测（Highlight Detection, HD）** 两个子任务。  
  - 主流方法使用预训练视觉‑语言模型（如CLIP、InternVideo2）提取视频和文本特征，但其跨模态注意力机制中**将所有文本标记（token）一视同仁**，未考虑标记间语义角色的差异。

- **核心问题**  
  - 实验发现，现有VTG模型**严重依赖`[EOS]`标记所携带的全局句子语义**，而未能有效利用词级（word‑level）信号（如图1b中模型对单词标记的注意力极弱）。  
  - 这种偏置导致模型难以捕捉视觉上关键但局部的语义（如“红色夹克”），**限制了细粒度时序对齐能力**。  
  - 论文通过受控实验（仅用单词/仅用`[EOS]`/完整序列）及大规模相关性分析，定量验证了该现象在多种模型中的普遍性。

- **整体含义与目标**  
  - 提出**DualGround**，显式分离全局与局部语义，使模型既能利用全局意图，又不丢失细粒度的短语/词级线索，从而提升视频‑文本对齐的精度与鲁棒性。

## 2. 方法论：核心思想、关键技术细节与算法流程

### 2.1 总体架构：双分支分离式建模
- 模型由**句子级路径（Sentence‑level Path）** 和**短语级路径（Phrase‑level Path）** 组成，分别处理全局`[EOS]`表征和词级短语集群，最终通过**解码路径**融合两个分支的特征完成MR与HD。

### 2.2 句子级路径
- **仅使用`[EOS]`标记** e_{[EOS]} 作为句子级表示。
- 引入**自适应交叉注意力（ACA）** 和**可学习虚拟标记（Dummy Tokens）**，以弥补单标记无法形成对比性注意力分布的缺陷。  
  - 虚拟标记 `D` 经轻量Transformer编码后与 `e_{[EOS]}` 拼接作为键值，查询来自视频片段特征。  
  - 语义不相关的视频片段注意力被虚拟标记“吸收”，相关片段则更多关注 `[EOS]`，从而得到稳健的句子引导视频表征 `V_s`。  
  - 公式上，第i个片段的注意力权重 α_i 仅对最后（`[EOS]`对应）位置计算softmax（见式(1)）。

### 2.3 短语级路径
- **短语生成**  
  - 采用**循环短语生成器（RPG）** 逐步生成 N 个短语。在第 n 步，引导向量 g^{(n)} 由全局 `e_{[EOS]}` 与前一个短语表征通过MLP生成，再用其对词标记进行软注意力加权，得到初始短语 `p_i^{(n)}`。  
  - 引入位置嵌入以鼓励相邻词的聚合。
  
- **短语精炼与全局令牌重建**  
  - 初始短语通过**Slot Attention**进一步精炼：每个短语作为槽（slot）对词序列进行注意力，经槽内softmax和输入归一化实现语义解耦，得到精炼短语集合 `P`。  
  - 附加一个可学习的 `P_{[EOS]}`，与 `P` 经自注意力块后，用于汇聚短语语义并保持全局一致性。

- **短语‑片段上下文建模**  
  - 对每个短语 p^{(n)} 和每个视频片段 v_t，通过哈达玛积（Hadamard product）计算交互特征 `C_{n,t} = f_{ctx}(f_p(p^{(n)}) ⊙ f_v(v_t))`，形成 `N×T×d` 的张量 `C`。  
  - 随后在片段维度应用时序自注意力以保持时间一致性。

- **短语引导聚合**  
  - 利用 `P_{[EOS]}` 与各短语的相似度作为重要性权重，加权聚合 `C`，得到最终短语引导的视频表征 `V_p`（式(4)）。

### 2.4 解码路径（预测）
- 融合 `V_s` 和 `V_p`（默认采用元素相加）得到 `F = V_s + V_p`，再通过多层1D卷积构建时间特征金字塔。  
- **多尺度预测**：在多个时间分辨率上预测片段边界（用L1回归）和置信度（Focal Loss），拼接后预测最终的时刻坐标与分数。  
- **高亮检测**：在基础分辨率上利用哈达玛积的显着性头得到片段级显著分数。

### 2.5 训练目标
- **总损失**：`L_total = λ_mr L_mr + λ_hd L_hd + λ_phrase (L_DQA + L_EOS)`  
  - `L_mr`：时刻检索分类损失（Focal）和回归损失（L1）。  
  - `L_hd`：包含片段显著分数的排序损失与对比损失，以及句子级注意力权重的相应损失（带权重 λ_attn）。  
  - **短语级监督**：  
    - `L_DQA`（Distinct Query Attention Loss）：强制不同短语对词的注意力向量相互正交（式(5)），促进语义多样性。  
    - `L_EOS`（EOS重建损失）：用InfoNCE拉近 `P_{[EOS]}` 与原始 `e_{[EOS]}` 的余弦相似度（式(6)），保持短语路径的全局语义一致性。

## 3. 实验设计

### 3.1 数据集与评估指标
- **QVHighlights**：10,148个YouTube视频，同时包含MR和HD标注。指标：Recall@1（IoU=0.5, 0.7）、mAP、mAP@0.5、mAP@0.75、VG‑mAP、VG‑HIT@1。  
- **Charades‑STA**：室内活动，16,128个查询‑时刻对，用于MR。指标：Recall@1（0.5, 0.7）和mIoU。  
- **TVSum**：50个视频，利用标题进行HD。指标：top‑5 mAP（平均mAP）和HIT@1。

### 3.2 对比方法
- 基于**CLIP+SlowFast**和**InternVideo2（IV2）** 两种特征主干的对比：
  - CG‑DETR， TR‑DETR， UVCOM， R2‑Tuning， FlashVTG， UniVTG（仅Charades）等。
- 特别关注在不同令牌输入条件（仅单词、仅[EOS]、完整序列）下模型表现，以揭示[EOS]偏差。

### 3.3 消融分析
- 在QVHighlights验证集上，消融短语生成模块（RPG）、Slot Attention、DQA Loss、EOS重建 Loss 的有无（共7种设置）。  
- 短语分段数 N 的敏感性分析（N=2~6）。  
- 不同特征融合策略（Add、Hadamard、Gate、Concat‑MLP）的比较。  
- 按查询长度分组的性能分析（0‑10词、10‑15词、15‑20词、>20词）。  
- 不同主干（CLIP vs IV2）下各令牌条件的对比。

## 4. 资源与算力

- 硬件环境：AMD Ryzen 3960X 24核CPU + **单张** NVIDIA RTX 3090 GPU。  
- 训练配置（附录A.4详表）：  
  - QVHighlights：batch size=64，训练150 epoch，学习率 1e‑4（IV2下相同）。  
  - Charades‑STA：batch size=128，训练50 epoch，学习率 2.5e‑4。  
  - TVSum：batch size=4，训练600 epoch，学习率 1e‑3。  
- **未明确报告**整体训练时长或总GPU小时数，但给出了层数、维度等所有必要超参数以保证可复现。

## 5. 实验数量与充分性

- **多数据集、多主干**：在QVHighlights、Charades‑STA、TVSum三个基准上，使用CLIP+SlowFast和InternVideo2两种特征提取方案，覆盖10余种SOTA方法的系统对比。
- **多项消融研究**：包括组件有效性、短语数量、融合策略、查询长度敏感度、令牌条件对比等，总计数十组子实验，从多个角度验证设计合理性。
- **定性分析**：提供注意力可视化、短语‑词对齐热力图、预测片段对比图，直观展示模型优势。
- **公平性**：所有对比方法均采用相同特征和无微调设置，结果报告均为标准指标，实验设置透明，无数据泄露或特殊后处理倾斜。

总体而言，实验设计**充分且客观**，既有与SOTA的全面比较，又有内部消融以支撑核心主张。

## 6. 主要结论与发现

- **现有模型普遍依赖[EOS]全局语义**，词级信号利用不足，导致细粒度定位欠佳；DualGround通过**结构化解耦**有效缓解了该问题。  
- **双分支设计**（句子级路径+短语级路径）能同时捕获全局意图和局部上下文，在MR和HD任务上均取得**新的SOTA**，尤其在更严格的IoU阈值（R1@0.7）下提升显著。  
- **短语级模型**（RPG+Slot Attention）将语义相关的词聚合成短语单元，再与视频片段精细交互，显著提高了长查询、复杂场景下的鲁棒性。  
- 短语多样性正则（DQA）和EOS重建损失对维持短语解耦及全局语义一致性至关重要。

## 7. 方法优点与亮点

- **问题洞察深刻**：首次通过系统实验和相关性分析定量揭示了VTG模型对`[EOS]`的过度依赖，为社区提供了明确的方向性发现。  
- **架构设计新颖**：  
  - 自适应交叉注意力（ACA）让单标记的`[EOS]`也能形成有效的注意力分布，简洁而高效。  
  - 短语生成与精炼流程（RPG + Slot Attention）**兼顾上下文连贯性与语义纯净性**，是一项精巧的表示学习设计。  
- **解耦式双路径融合**：将全局与局部信息流显式分离，避免相互干扰，且通过简单加权或加法即可集成，易于实现。  
- **实验说服力强**：大量消融、多主干、多数据集验证，配合定量分析和可视化，无过度宣称，结论坚实。

## 8. 不足与局限

- **固定短语数量**：每句话需预设短语数 N，且最优值随数据集和查询长度变化（QVHighlights最优4，Charades最优3），缺乏自适应动态分割能力。  
- **未利用多模态信号**：虽然模型验证了文本语义的解耦有效，但未整合音频等辅助信息，在音视频联合场景中可能性能受限。  
- **计算开销未详述**：论文未提供训练时间或推理延迟数据，实际部署效率无从评估。  
- **统计显著性缺失**：性能提升未汇报标准误差或显著性检验，仅依赖单次运行的指标，影响结论的统计置信度。  
- **场景覆盖有限**：仅在三个英文数据集上评估，对跨语言、长尾查询或动态开放域视频的泛化性尚未验证；且未讨论数据偏差或隐私伦理等更广泛的影响。

（完）
