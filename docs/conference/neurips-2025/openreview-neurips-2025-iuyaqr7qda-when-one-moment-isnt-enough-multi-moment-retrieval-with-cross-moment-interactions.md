---
title: "When One Moment Isn't Enough: Multi-Moment Retrieval with Cross-Moment Interactions"
title_zh: 当单一时刻不够时：跨时刻交互的多时刻检索
authors: "Zhuo Cao, Heming Du, Bingqing Zhang, Xin Yu, Xue Li, Sen Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=IUYAqr7qDA"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 解决多时刻检索，属于需求1的视频时序定位变体。
tldr: 现实查询往往对应多个视频片段，现有单时刻检索方法不足。本文引入QV-M^2多时刻数据集和新评估指标，并提出FlashMMR框架，通过跨时刻交互和多时刻后验证细化边界。实验表明，利用多时刻关系显著提升了复杂查询的检索准确性，对真实世界应用更具实用性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuyaqr7qda/fig-001.webp\", \"caption\": \"\", \"page\": 5, \"index\": 1, \"width\": 2952, \"height\": 1756}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuyaqr7qda/fig-002.webp\", \"caption\": \"\", \"page\": 6, \"index\": 2, \"width\": 605, \"height\": 1028}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuyaqr7qda/fig-003.webp\", \"caption\": \"\", \"page\": 6, \"index\": 3, \"width\": 748, \"height\": 785}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuyaqr7qda/fig-004.webp\", \"caption\": \"\", \"page\": 6, \"index\": 4, \"width\": 727, \"height\": 785}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-iuyaqr7qda/fig-005.webp\", \"caption\": \"\", \"page\": 6, \"index\": 5, \"width\": 1611, \"height\": 640}]"
motivation: 单时刻检索无法处理真实查询对应多个相关片段的常见场景。
method: 构建QV-M^2数据集，提出FlashMMR框架，包含多时刻后验证和跨时刻交互模块。
result: 在多时刻检索指标上明显优于现有方法，证明了跨时刻信息的有效性。
conclusion: 多时刻检索更贴近实际需求，跨时刻建模是实现高精度检索的关键。
---

## Abstract
Existing Moment retrieval (MR) methods focus on Single-Moment Retrieval (SMR). However, one query can correspond to multiple relevant moments in real-world applications. This makes the existing datasets and methods insufficient for video temporal grounding. 
By revisiting the gap between current MR tasks and real-world applications, we introduce a high-quality datasets called QVHighlights Multi-Moment Dataset (QV-M$^2$), along with new evaluation metrics tailored for multi-moment retrieval (MMR). QV-M$^2$ consists of 2,212 annotations covering 6,384 video segments. Building on existing efforts in MMR, we propose a framework called FlashMMR. Specifically, we propose a Multi-moment Post-verification module to refine the moment boundaries. We introduce constrained temporal adjustment and subsequently leverage a verification module to re-evaluate the candidate segments. Through this sophisticated filtering pipeline, low-confidence proposals are pruned, and robust multi-moment alignment is achieved.
We retrain and evaluate 6 existing MR methods on QV-M$^2$ and QVHighlights under both SMR and MMR settings. Results show that QV-M$^2$ serves as an effective benchmark for training and evaluating MMR models, while FlashMMR provides a strong baseline. Specifically, on QV-M$^2$, it achieves improvements over prior SOTA method by 3.00% on G-mAP, 2.70% on mAP@3+tgt, and 2.56% on mR@3. The proposed benchmark and method establish a foundation for advancing research in more realistic and challenging video temporal grounding scenarios. Code is released at https://github.com/Zhuo-Cao/QV-M2.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究动机**：现有的视频时刻检索（Moment Retrieval, MR）方法几乎全部假设一个自然语言查询只对应视频中的**单个**相关片段（Single‑Moment Retrieval, SMR）。然而，真实场景中一个查询往往匹配**多个不相交的时刻**（例如“切菜”在一段烹饪视频中出现多次；篮球比赛中的“成功三分球”可能发生多次）。现有的 SMR 模型会忽略其他正确片段，仅输出最相关的一个片段，这严重限制了视频理解在实际中的应用。
- **整体含义**：论文指出，视频时序定位需要从 SMR 向**多时刻检索（Multi‑Moment Retrieval, MMR）**转型，但当前缺乏高质量的 MMR 专用数据集、评价指标以及能有效捕捉多时刻依赖的模型。为此，论文系统性地填补了这一空白，推动视频‑语言研究走向更真实、更具挑战性的场景。

## 2. 方法论

论文的核心贡献包括三个部分：**QV‑M² 数据集**、**MMR 评估指标**以及 **FlashMMR 模型**。

- **QV‑M² 数据集**
  - 基于广泛使用的 QVHighlights 数据集，保留其原始视频，从头重新进行高质量人工标注。
  - 标注规范：要求为每个查询标注多个时刻；覆盖**上下文相关查询**和**逆向查询**（标注某事件未发生的片段）。
  - 质量控制：每标注 100 个视频后随机抽取 5 % 由第二位标注者检查，若时间边界重叠度低于 90 %，则由第三位标注者重新标注。
  - 最终数据集包含 **2 212 条查询**，对应 **6 384 个标注时刻**，平均每条查询对应 2.9 个时刻（远超先前数据集）。

- **MMR 评估指标**
  - **Generalized mAP (G‑mAP)**：对多个 IoU 阈值（如 0.5~0.9）下的平均精度再取平均；同时按查询的目标时刻数量（1 个、2 个、≥3 个）分别报告 mAP。
  - **mIoU@k**：针对具有至少 k 个真实时刻的查询，计算 top‑k 预测与真实时刻的最大 IoU 的平均值。
  - **mR@k**：针对至少 k 个真实时刻的查询，计算 top‑k 预测中满足 IoU 阈值的真实时刻召回率的平均值。
  - 这些指标在 k=1 时可以退化为标准 SMR 指标，保证了与先前工作的可比性。

- **FlashMMR 模型**
  - **总体架构**：在 FlashVTG 等多尺度时刻检测框架的基础上，增加一个**多时刻后验证（Multi‑Moment Post‑Verification）模块**，专门用于处理多时刻场景。
  - **特征提取与融合**：使用冻结的 SlowFast 和 CLIP 提取视频和文本特征；通过自适应交叉注意力（ACA）融合视频、文本以及可学习的 dummy token，生成融合特征 \( \mathbf{F} \)。
  - **多尺度时序处理**：对融合特征进行多尺度 1D 卷积下采样，构建时序特征金字塔；在每个尺度上预测边界和置信度，并通过跨尺度融合得到初步的时刻预测。
  - **后验证模块**：
    1. **边界后处理**：利用最小/最大窗口长度、裁剪、取整等结构化约束，对初始预测进行修正，得到 \(\tilde{\mathbf{B}}\)。
    2. **语义一致性验证**：从融合特征中抽取每个预测窗口内的特征片段，送入一个循环模块（GRU）重新评估其置信度，得到精炼分数 \(p_i\)。
    3. 训练时使用**预测‑真实 IoU** 作为监督信号（MSE 损失），并引入**表示损失**鼓励时间上相邻的片段保持高语义一致性。
  - 经过后验证模块，低置信度预测被抑制，多个与查询语义一致的片段得到增强。

## 3. 实验设计

- **数据集与场景**
  - **QVHighlights**：原版 SMR 数据集，用于对比 MMR 和 SMR 下的性能。
  - **QV‑M²**：新构建的 MMR 数据集，分为训练/验证/测试分割，用于评测 MMR 能力。
  - 实验覆盖 **SMR 和 MMR 两种设定**，以及 **跨数据集评估**（在 QVHighlights 上训练 → 在 QV‑M² 上测试，反之亦然），以检验数据集迁移效果。

- **基准方法对比**
  - 对 6 种已有开放源代码的 MR 方法进行重训练和评估：M‑DETR、EATR、UVCOM、QD‑DETR、TR‑DETR、CG‑DETR，以及最新的 FlashVTG。
  - 提出的 FlashMMR 在所有设定下与上述方法进行比较。

- **消融实验**
  - 在 QV‑M² 和 QVHighlights 两个数据集上，分别测试有无后验证模块（PV）的性能变化，以验证该模块对 MMR 的贡献。

## 4. 资源与算力

- 论文明确说明所有实验在 **单块 NVIDIA RTX 4090 GPU** 上完成。
- 未提供单次训练的具体时长、显存占用等细节，但指出整体计算开销与现有方法（如 FlashVTG）相当，仅因后验证模块略有增加。

## 5. 实验数量与充分性

- **主要实验表格**包含：
  - 跨数据集性能对比（Table 2）：7 种方法 ×3 种训练/测试设定（QV‑M² Train、Val 等），共计 **21 行对比**。
  - QV‑M² 测试集上的全指标对比（Table 3）：所有方法在 G‑mAP、mAP@k、mIoU@k、mR@k 等 **10 个指标**上的结果。
  - QVHighlights 验证集上的相同指标对比（Table 4）。
  - 消融实验（Table 5）：FlashMMR 在有无 PV 模块下在两个数据集上的性能，覆盖主要 MMR 指标。
- **实验公平性**：所有对比方法均使用相同的视频/文本特征提取器（SlowFast + CLIP）和相同训练配置进行重训练；评价指标在 SMR 与 MMR 间具有兼容性；超参数公开。
- 总体实验数量适中，但关键对比（跨设定、跨数据集、消融）覆盖全面，能够充分支撑论文的主要结论。

## 6. 主要结论与发现

- **QV‑M² 数据集有效提升了模型的多时刻定位能力**：所有方法在使用 QV‑M² 训练后，SMR 和 MMR 指标均优于仅用 QVHighlights 训练的结果。
- **现有 SMR 模型在 MMR 场景下性能大幅下降**，表明它们缺乏处理多时刻依赖的能力。
- **FlashMMR 建立了强大的 MMR 基线**：在 QV‑M² 测试集上，相比于此前最优的 FlashVTG，G‑mAP 提升 **3.00 %**，mAP@3+tgt 提升 **2.70 %**，mR@3 提升 **2.56 %**。
- **后验证模块是关键**：消融实验显示该模块在两个数据集上均带来一致的增益，尤其在多目标指标上表现突出，验证了“跨时刻交互与语义一致性重评估”对于多时刻检索的重要性。

## 7. 优点

- **问题定义清晰且贴合实际**：直接将单时刻假设纠正为多时刻检索，点出真实应用痛点。
- **数据集构建严谨**：全人工标注 + 多重质量控制，平均时刻数、词汇多样性等统计均优于已有数据集。
- **评估体系兼容且细致**：新指标既能评估 MMR，也可退化为标准 SMR 指标，按目标数量分组报告，能精细分析模型行为。
- **方法设计简洁有效**：在成熟 SMR 框架上仅增加一个后验证模块，通过 GRU 和表示损失捕捉多时刻间的关系，即插即用且效果显著。
- **实验充分且公平**：重训练所有对比方法，跨数据集评估，并提供代码和数据，保证可复现性。

## 8. 不足与局限

- **后验证模块仍较简单**：论文也指出，当前仅采用 GRU 和 MSE 损失，未来可引入强化学习、对比学习等更强机制来进一步区分时段。
- **数据集规模有限**：QV‑M² 仅有约 2 200 条查询，随着模型复杂度提高，可能成为瓶颈；场景局限于生活 vlog 和新闻，多样性一般。
- **计算资源细节缺失**：未给出训练时长、内存占用等信息，难以评估实际部署成本。
- **未进行统计显著性检验**：对比均基于单次运行结果，缺少误差棒或显著性报告。
- **可能存在的偏差风险**：数据来源为 YouTube vlog/新闻，地域、文化偏见尚未分析；人工标注的主观性虽通过质量控制减弱，但无法完全消除。

（完）
