---
title: "SpikingVTG: A Spiking Detection Transformer for Video Temporal Grounding"
title_zh: SpikingVTG：用于视频时序定位的脉冲检测Transformer
authors: "Malyaban Bal, Brian Matejek, Susmit Jha, Adam D. Cobb"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SkhF3cuyev"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 提出基于脉冲神经网络的视频时序定位模型，直接针对需求1的任务。
tldr: 现有视频时序定位依赖密集矩阵乘法，计算昂贵。本文首次将脉冲神经网络引入VTG，提出SpikingVTG，利用事件驱动累积计算降低开销。通过显著性反馈门控机制动态分配多模态特征的权重。实验表明，该模型在保持有竞争力精度的同时，大幅提升了推理效率，为低能耗视频理解开辟新路径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-skhf3cuyev/fig-001.webp\", \"caption\": \"\", \"page\": 3, \"index\": 1, \"width\": 3999, \"height\": 210}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-skhf3cuyev/fig-002.webp\", \"caption\": \"\", \"page\": 3, \"index\": 2, \"width\": 3999, \"height\": 281}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-skhf3cuyev/fig-003.webp\", \"caption\": \"\", \"page\": 3, \"index\": 3, \"width\": 800, \"height\": 369}]"
motivation: 传统VTG计算密集，SNN的脉冲驱动计算范式尚未在该任务探索。
method: 提出多模态脉冲检测Transformer，并设计显著性反馈门控动态调控特征权重。
result: 在保持高精度的同时，推理所需能耗和计算量显著下降。
conclusion: 脉冲神经网络为视频时序定位提供了高效且具生物合理性的替代方案。
---

## Abstract
Video Temporal Grounding (VTG) aims to retrieve precise temporal segments in a video conditioned on natural language queries. Unlike conventional neural frameworks that rely heavily on computationally expensive dense matrix multiplications, Spiking Neural Networks (SNNs)—previously underexplored in this domain—offer a unique opportunity to tackle VTG tasks through bio-plausible spike-based communication and an event-driven accumulation-based computational paradigm. We introduce SpikingVTG, a multi-modal spiking detection transformer, designed to harness the computational simplicity and sparsity of SNNs for VTG tasks. Leveraging the temporal dynamics of SNNs, our model introduces a Saliency Feedback Gating (SFG) mechanism that assigns dynamic saliency scores to video clips and applies multiplicative gating to highlight relevant clips while suppressing less informative ones. SFG enhances performance and reduces computational overhead by minimizing neural activity. We analyze the layer-wise convergence dynamics of SFG-enabled model and apply implicit differentiation at equilibrium to enable efficient, BPTT-free training. To improve generalization and maximize performance, we enable knowledge transfer by optimizing a Cos-L2 representation matching loss that aligns the layer-wise representation and attention maps of a non-spiking teacher with those of our student SpikingVTG. Additionally, we present Normalization-Free (NF)-SpikingVTG, which eliminates non-local operations like softmax and layer normalization, and an extremely quantized 1-bit (NF)-SpikingVTG variant for potential deployment on edge devices. Our models achieve competitive results on QVHighlights, Charades-STA, TACoS, and YouTube Highlights, establishing a strong baseline for multi-modal spiking VTG solutions.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- 视频时序定位（Video Temporal Grounding, VTG）旨在根据自然语言查询，在视频中检索出与之对应的精确时间段。该任务通常涉及 **时刻检索** 和 **精彩片段检测**。
- 现有主流方案（如 Moment-DETR、UniVTG 等）构建于普通 Transformer 之上，严重依赖密集的浮点矩阵乘法，计算量和能耗巨大，难以部署到资源受限的边缘设备。
- 脉冲神经网络（SNN）利用二进制脉冲进行事件驱动的累积计算，天然具备稀疏性和高能效，但此前从未被系统性用于 VTG 任务。
- **核心问题**：如何设计一个完全基于 SNN 的多模态检测 Transformer，使其在 VTG 任务上达到与传统非脉冲模型相当的性能，同时显著降低计算与能量开销？

## 2. 论文提出的方法论

### 2.1 总体架构
- **SpikingVTG** 由三个主要部分构成：
  1. **脉冲 Transformer 核心**（Spiking Transformer Core）：使用 LIF（泄漏整合发放）神经元和脉冲注意力机制进行跨模态时序建模。
  2. **显著性反馈门控（Saliency Feedback Gating, SFG）**：利用 SNN 时间动态，在每一时间步根据 Spike 发放率（ASR）动态评估每个视频片段的显著性，并实施乘法门控，增强关键片段、抑制无关片段，从而降低整体神经活动。
  3. **脉冲解码器**（Spiking Decoder）：由1D卷积＋IF神经元堆叠而成，输出片段的边界偏移、前景概率和显著性分数。

### 2.2 关键技术与训练
- **SFG 机制**：通过平均发放率（ASR）与查询的全局句嵌入计算余弦相似度，得到每个视频片段的动态显著性分数，经 min‑max 归一化后对输入视频特征进行加权，再与查询特征拼接送入下一时间步的 Transformer 核心。该机制不仅提升性能，还能减少输入层和注意力层的脉冲活动。
- **层间收敛动力学与无 BPTT 训练**：理论推导和实验表明，带有 SFG 的 SpikingVTG 在时间上会收敛到平衡点。于是可利用**隐区分**（implicit differentiation）在平衡点处直接计算梯度，无需存储整个时间序列的计算图（即无需 BPTT），极大节省训练内存。
- **Cos‑L2 表示匹配（CLRM）知识迁移**：为了让学生模型继承教师模型（如 UniVTG）在大规模数据上预训练获得的泛化能力，提出将教师的层间隐藏状态和注意力图与学生对应的收敛后 ASR 及平均注意力分数对齐，损失函数由**方向损失（余弦相似度平方）**和**尺度损失（L2 距离）**组合而成。该过程只需在下游任务上进行，避免了昂贵的预训练。
- **无归一化与 1‑比特量化变体**：进一步去掉 Softmax 和层归一化，用 ReLU + 缩放替代传统的脉冲注意力（NF‑SpikingVTG）；并将权重二值化为 {−1, +1}，使用整数积累运算（1‑bit NF‑SpikingVTG），实现极低能耗和内存占用。

## 3. 实验设计

- **数据集**：
  - QVHighlights：同时支持时刻检索和精彩片段检测，约 10k 视频，平均时长 150 秒。
  - Charades‑STA：16,128 段室内视频，平均 30 秒。
  - TACoS：127 段长视频（平均 4.78 分钟）。
  - YouTube Highlights：433 段视频，涵盖 6 个领域，以领域名作为文本查询。
- **基准线（对比方法）**：均为非脉冲模型，包括 M‑DETR、UMT、UniVTG、QD‑DETR、CG‑DETR、TR‑DETR、BAM‑DETR、UVCOM、LLMEPET，以及结合了部分脉冲组件的 SpikeMba 等。
- **评估指标**：
  - 时刻检索：Recall@1 (IoU=0.3, 0.5, 0.7)、mAP、mIoU。
  - 精彩片段检测：mAP、HIT@1。
- **主要对比结果**：
  - SpikingVTG 在 QVHighlights 上达到 `R@0.5: 65.29, mAP: 64.31, HIT@1: 65.82`，与最强的非脉冲模型（如 UniVTG+PT）差距很小；在 Charades‑STA 和 TACoS 上亦获得有竞争力的结果，且明显超越同为脉冲相关的 SpikeMba。
  - 1‑bit NF‑SpikingVTG 在稍降精度的情况下，能量效率提升约 20 倍（与同规模非脉冲模型相比），且可通过调整时间步数实现精度‑能耗的动态权衡。

## 4. 资源与算力

- **硬件**：使用的 GPU 为 **NVIDIA RTX A6000 (48 GB 显存)**。
- **训练开销**：
  - CLRM 知识迁移阶段：batch size 32 时内存需求 **20 GB**；若使用 BPTT 训练相同设置，时间步数超过 10 时内存需 **100 GB 以上**，几乎不可行。
  - 仅用真实标签微调：内存**约 8 GB**。
  - 在 QVHighlights 上训练 50 个 epoch 约耗时 **5 小时**。
- **推理开销**：
  - 整个 QVHighlights 测试集，时间步数 \(T_c=2\) 时耗时约 **25 秒**，\(T_c=20\) 时约 **4 分钟**。
- 能量分析基于 45nm CMOS 工艺、32 位精度：FP‑MAC 4.6 pJ，FP‑ACC 0.9 pJ，INT‑ACC 0.1 pJ，并据此计算了各模型变体的单次推理能量。

## 5. 实验数量与充分性

- **多数据集验证**：在 4 个不同规模、不同领域的 VTG 数据集上进行了评估，覆盖时刻检索和精彩片段检测两大任务。
- **消融实验**：系统比较了基础 SpikingVTG（无 SFG）、带 SFG 的 SpikingVTG、NF‑SpikingVTG、1‑bit NF‑SpikingVTG，以及替换激活函数（GELU→ReLU）等变体，分析了各组件对性能、神经活动稀疏度和能耗的影响。
- **能量‑精度权衡分析**：展示了 1‑bit 模型在不同时间步数下的 HIT@1 与能量效率的变化曲线，验证了可调节的资源适应能力。
- **对比方法丰富**：涵盖了近年的 SOTA 非脉冲方法和半脉冲方法，对比公平。
- 总体而言，实验维度多样，覆盖了性能、效率、硬件友好性等多个维度，**实验较为充分且客观**。

## 6. 论文的主要结论与发现

- **SNN 可有效胜任 VTG 任务**：SpikingVTG 首次为多模态 VTG 提供了基于脉冲的强基线，性能接近甚至部分指标超过非脉冲 SOTA，同时显著降低计算需求和能量消耗。
- **SFG 机制是核心增效剂**：通过动态门控，显著增强了关键片段的关注度，抑制了无关部分，在提升性能的同时进一步稀疏化模型活动。
- **无 BPTT 训练和平街隐区分有效**：利用收敛平衡点的隐式微分训练，内存效率远超 BPTT，使得脉冲 Transformer 的大规模训练可行。
- **知识迁移可弥合预训练差距**：CLRM 损失使脉冲模型能够从预训练好的非脉冲教师中高效迁移泛化能力，避免了在大型视频数据集上从头训练脉冲模型的高昂代价。
- **硬件友好型设计可行**：去除 Softmax 和层归一化、二值化权重的 NF 及 1‑bit 变体在保持较强性能的同时，使模型适合部署在神经形态芯片或边缘设备上，且支持灵活的能耗‑精度折衷。

## 7. 优点

- **首创性**：第一次将完全脉冲的检测 Transformer 引入视频时序定位，填补了该方向的空白。
- **范式创新**：将 SNN 的时间处理特性与反馈门控巧妙结合，SFG 的设计既有生物可解释性，又有实际性能增益。
- **训练技术先进**：利用隐式微分和 CLRM 知识迁移，绕开了脉冲模型训练的两大瓶颈——BPTT 的高内存和预训练的巨量资源需求。
- **全面的硬件适配**：提供从 32 位浮点累积到 1‑比特整数的多级优化方案，清晰展示了从理论到边缘部署的路径。
- **能量‑精度可控**：使模型能根据设备剩余电量动态调整推理时间步数，这一特性非常契合低功耗场景。
- **实验扎实**：多数据集、多任务、多指标、多变体，消融和效率分析充分。

## 8. 不足与局限

- **性能差距尚未完全消除**：虽然接近 SOTA，但在某些指标上仍稍逊于充分预训练的非脉冲模型（如 UniVTG+PT），作者也在结论中承认仍有提升空间。
- **实验规模和设定**：
  - 所对比的教师模型性能并非在所有数据集上都达到绝对顶尖，未来的更强教师可能会带来提升，但文中未做深入探讨。
  - 仅在四个公开 VTG 数据集上验证，未在更长视频或更复杂场景（如 Ego4D 原始数据）上进行测试。
- **硬件部署尚在仿真层面**：能量计算是基于操作次数和标准工艺参数的理论估算，未在真实的神经形态芯片（如 Loihi）上实测，实际部署时的并行效率、散热、噪声等问题尚未考虑。
- **训练复杂度**：虽然 CLRM 和无 BPTT 降低了训练成本，但知识迁移阶段仍需要加载大型教师模型，且超参数（如 λcos, λl2）可能需要针对不同任务进行调整。
- **极端量化的影响**：1‑bit 模型性能略有下降，且文中未深入分析量化导致的表征退化对哪些类型的查询或视频片段影响更大。

（完）
