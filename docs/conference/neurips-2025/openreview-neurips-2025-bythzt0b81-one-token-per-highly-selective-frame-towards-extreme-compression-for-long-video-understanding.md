---
title: "One Token per Highly Selective Frame: Towards Extreme Compression for Long Video Understanding"
title_zh: 逐帧单令牌：面向长视频理解的极致压缩
authors: "Zheyu Aqa Zhang, Ziqi Pang, Shixing Chen, Xiang Hao, Vimal Bhat, Yu-Xiong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=bythzT0b81"
tags: ["query:tf-vl-ag"]
score: 8.0
evidence: 极致令牌压缩实现高效长视频理解
tldr: 针对长视频理解中视觉语言模型因帧数多导致上下文限制和信息丢失的问题，提出可学习的渐进式令牌压缩方法，将每帧压缩至一个令牌，大幅降低计算开销并保留时序信息。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 571, \"height\": 358}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 571, \"height\": 358}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bythzt0b81/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 1176, \"height\": 740}]"
motivation: 长视频中大量帧使视觉语言模型面临上下文长度瓶颈，现有启发式压缩引起信息损失。
method: 提出LP-Comp，可学习的渐进式令牌级压缩，将每帧压缩为一个令牌。
result: 该方法在多长视频理解任务上超越了启发式压缩方法，兼顾效率与信息完整性。
conclusion: 可学习压缩是实现极高效长视频理解的关键。
---

## Abstract
Long video understanding is inherently challenging for vision-language models (VLMs) because of the extensive number of frames. With each video frame typically expanding into tens or hundreds of tokens, the limited context length of large language models (LLMs) forces the VLMs to perceive the frames sparsely and lose temporal information. To address this, we explore extreme video token compression towards *one token per frame* at the final LLM layer. Our key insight is that heuristic-based compression, widely adopted by previous methods, is prone to information loss, and this necessitates supervising LLM layers into *learnable* and *progressive* modules for *token-level compression* (LP-Comp). Such compression enables our VLM to digest 2x-4x more frames with improved performance. To further increase the token efficiency, we investigate *frame-level compression*, which selects the frames most relevant to the queries via the internal attention scores of the LLM layers, named *question-conditioned compression* (QC-Comp). As a notable distinction from previous studies, we mitigate the position bias of LLM attention in long contexts, *i.e.*, the over-concentration on the beginning and end of a sequence, by splitting long videos into short segments and employing local attention. Collectively, our combined *token-level* and *frame-level* leads to an e**x**treme compression model for long video understanding, named **XComp**, achieving a significantly larger compression ratio and enabling denser frame sampling. Our XComp is finetuned from VideoChat-Flash with a data-efficient *supervised compression tuning* stage that only requires 2.5\% of the supervised fine-tuning data, yet boosts the accuracy from 42.9\% to 46.2\% on LVBench and enhances multiple other long video benchmarks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究问题**：在长视频理解任务中，视觉语言模型面临一个根本性瓶颈：视频帧数量巨大，且每帧被编码为成百上千个令牌，这极易超出大语言模型的上下文长度和计算预算，导致模型只能稀疏采样，从而丢失关键的时序信息。
*   **核心思想**：探索极致的视觉令牌压缩，目标是在大语言模型的最终层将**每帧视频压缩为仅仅一个令牌**，从而实现前所未有的高密度帧采样，提升长视频理解性能。
*   **关键洞察**：以往的方法多采用启发式策略（如选择性丢弃、池化）进行压缩，这在极高压缩比下容易造成不可逆的信息损失。所以，让大语言模型层通过训练来主动、渐进地学习压缩能力，是达成这一目标的关键。

### 2. 论文提出的方法论
XComp 框架从两个层面实现长视频的极致压缩：

*   **令牌级压缩：可学习的渐进式压缩 (LP-Comp)**
    *   **核心思想**：与训练时便让大语言模型层学会将视频信息压缩到更少的令牌中，而非依赖推理时的启发式规则。
    *   **渐进式压缩 (Progressive Compression)**：不在一层内完成所有压缩，而是通过一个平滑的余弦调度，让大语言模型的每一层都减少少量令牌，最终在最后一层达到每帧1个令牌的极致压缩比。其令牌数量变化公式为：N(ℓ)=⌈N(1)−12 cos(ℓLπ)+N(1)+12⌉。
    *   **后缀保留策略 (Suffix Preservation)**：在每层压缩时，总是保留帧序列末尾的令牌，而丢弃前面的令牌。这种设计的目的是为了兼容解码器型大语言模型的因果注意力机制，让后续令牌能够吸收前面令牌的信息。
    *   **监督压缩调优**：采用一个数据高效的训练阶段，仅使用少量数据让大语言模型学会压缩行为。

*   **帧级压缩：问题条件的压缩 (QC-Comp)**
    *   **核心思想**：利用大语言模型内部的注意力机制，选出与用户问题最相关的帧，丢弃不相关的帧，进一步提升令牌效率。
    *   **缓解位置偏差**：为解决大语言模型在处理长序列时的“中间丢失”问题（即过度关注开头和结尾的令牌），提出**分段局部注意力**策略。将长视频切分为多个短片段，在每个片段内部独立计算问题与视频帧的注意力分数，并以此作为帧的相关性得分，筛选出高相关性的帧。

*   **整合**：模型在训练时习得LP-Comp能力，在推理时应用QC-Comp策略，最终实现“为高度筛选后的帧分配一个令牌”的极致压缩目标。

### 3. 实验设计
*   **基准模型与微调**：XComp 基于 VideoChat-Flash-2B 模型进行监督压缩调优，仅使用了其 2.5% 的监督微调数据。同时，该方法也被应用于 LLaVA-Next-Video 以验证泛化性。
*   **基准数据集**：
    *   **长视频问答**：LongVideoBench（平均时长 473s）、MLVU（平均时长 651s）、VideoMME (Long)（平均时长 2386s）、LVBench（平均时长 4101s）。
    *   **其他任务**：Multi-Hop Needle-in-a-Haystack（多跳大海捞针）、CLEVRER（推理）、VDC（视频密集描述）、MME-VideoOCR（文本感知）。
*   **对比方法**：
    *   **专有模型**：GPT-4V、GPT-4o、Gemini-1.5-Pro。
    *   **3~9B 规模的开源模型**：Qwen2.5VL-3B、mPLUG-Owl3、VideoChat-Flash-7B、Eagle2.5-8B、Kangaroo、TimeMarker、InternVL3-9B。
    *   **同级别模型 (2B)**：InternVL3-2B、VideoChat-Flash-2B（直接基线）。

### 4. 资源与算力
*   **硬件配置**：训练使用了 8 块 NVIDIA H100 GPU。
*   **训练时长**：整个监督压缩调优过程耗时约 24 小时。

### 5. 实验数量与充分性
*   **实验数量**：论文进行了超过 10 项不同的评估/消融实验。
*   **实验充分性**：
    *   **多基准评估**：在 4 个主流的、时长各异的长视频理解基准上进行测试，结果全面。
    *   **细致消融**：对 LP-Comp（可学习 vs. 训练无关、渐进 vs. 分步、后缀保留 vs. 均匀保留）和 QC-Comp（全局注意力 vs. 分段局部注意力）的各个关键设计选择均设置了消融实验，论证严谨。
    *   **基线对比**：对比了多个级别的模型，并特别排除了“微调本身带来性能提升”的干扰因素（通过 `VideoChat-Flash-2B+FT` 实验）。
    *   **泛化性验证**：在另一个主流模型 LLaVA-Next-Video 上同样验证了方法的有效性。
    *   **公平性**：实验设计客观公平，比较标准清晰，所有消融实验都基于一致的基础。

### 6. 论文的主要结论与发现
*   **性能显著提升**：XComp 在所有 2B 级别模型中表现最优，并在多个基准上超越了部分 7B 级别的模型。相较于基线模型 VideoChat-Flash-2B，LVBench 准确率从 42.9% 提升至 46.2%。
*   **高压缩比与高帧率**：LP-Comp 在实现 16 倍令牌压缩比的同时，不仅没有损失性能，反而让模型能处理更多帧并持续提升性能，而基线模型在处理过多帧时性能会下降。
*   **可学习压缩至关重要**：通过实验证明，在极高压缩比下，基于注意力的启发式压缩策略会失效，必须通过训练让大语言模型层学会压缩信息。
*   **设计选择有效**：渐进式压缩优于分步压缩，后缀保留策略优于均匀保留，分段局部注意力优于全局注意力，证明了各组件的合理性。

### 7. 优点
*   **方法创新性强**：首次探索用大语言模型层本身进行可学习的、渐进式的、达到每帧一令牌的极致压缩，为长视频处理提供了新范式。
*   **极致的效率与效能**：实现高压缩比的同时，不仅提升了计算效率，还能通过处理更密集的帧来提升任务精度，实现了效率与效能的统一。
*   **数据效率高**：仅需 2.5% 的训练数据即可实现有效的压缩能力学习，成本低廉。
*   **分析深刻**：揭示并成功缓解了长序列中的“中间丢失”位置偏差问题，解决了一个关键但易被忽视的挑战。
*   **设计原则清晰**：提出的“可学习”、“渐进式”和“后缀保留”等设计原则具有很强的可解释性。

### 8. 不足与局限
*   **模型规模验证有限**：实验主要在 ~2B 规模的模型上进行，其在更大规模模型（如 7B, 13B 或更大）上的有效性和稳定性有待进一步验证。
*   **数据集覆盖度**：尽管评估基准较全，但监督压缩调优阶段仅使用了 VideoChat-Flash 数据集的 2.5%，这部分数据的分布可能影响了模型的最终能力，且在文本感知（OCR）等任务上表现出轻微退化。
*   **帧级压缩在训练中的优化**：QC-Comp 目前仅作为推理时的策略，未能与 LP-Comp 联合训练，这可能不是最优解。论文也指出未来的工作方向是将其纳入训练。
*   **应用限制**：作为一种压缩方法，对信息损失的完全规避尚不能保证，在需要超精细视觉细节的任务上可能存在风险。
*   **计偏差风险**：论文未详尽分析训练数据中潜在的偏见及其对模型输出公平性的影响。

（完）
