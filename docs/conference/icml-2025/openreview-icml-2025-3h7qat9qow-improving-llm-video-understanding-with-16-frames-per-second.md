---
title: Improving LLM Video Understanding with 16 Frames Per Second
title_zh: 以每秒16帧提升大语言模型视频理解能力
authors: "Yixuan Li, Changli Tang, Jimin Zhuang, Yudong Yang, Guangzhi Sun, Wei Li, Zejun MA, Chao Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3H7qAT9Qow"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 首个面向高帧率视频理解的多模态大模型，将帧率提升至 16 FPS 并压缩 token 以捕捉动态特征
tldr: 针对当前视频大模型仅依赖低帧率静态特征的问题，提出 F-16 模型，通过 16 FPS 高帧率和每秒片段内视觉 token 压缩，高效捕获动态视觉特征，在多个视频理解基准上显著提升性能，为高帧率视频 LLM 开辟新路径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1735, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 647, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1371, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1369, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3h7qat9qow/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1369, \"height\": 2283, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1765, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1764, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 739, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 772, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1677, \"height\": 1141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1241, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1272, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1243, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3h7qat9qow/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1642, \"height\": 1116, \"label\": \"Table\"}]"
motivation: 现有方法依赖≤2 FPS 静态特征，丢失关键视觉信息。
method: 设计 F-16 模型，将帧率提高至 16 FPS 并压缩每秒片段内的视觉 token。
result: 高帧率显著增强视频理解性能，在多个基准上有效。
conclusion: 高帧率配合 token 压缩是提升视频 LLM 理解能力的简单有效方案。
---

## Abstract
Human vision is dynamic and continuous. However, in video understanding with multimodal large language models (LLMs), existing methods primarily rely on static features extracted from images sampled at a fixed low frame rate of frame-per-second (FPS) $\leqslant$2, leading to critical visual information loss. In this paper, we introduce F-16, the first multimodal LLM designed for high-frame-rate video understanding. By increasing the frame rate to 16 FPS and compressing visual tokens within each 1-second clip, F-16 efficiently captures dynamic visual features while preserving key semantic information.
Experimental results demonstrate that higher frame rates considerably enhance video understanding across multiple benchmarks, providing a new approach to improving video LLMs beyond scaling model size or training data. F-16 achieves state-of-the-art performance among 7-billion-parameter video LLMs on both general and fine-grained video understanding benchmarks, such as Video-MME and TemporalBench. Furthermore, F-16 excels in complex spatiotemporal tasks, including high-speed sports analysis (*e.g.*, basketball, football, gymnastics, and diving), outperforming SOTA proprietary visual models like GPT-4o and Gemini-1.5-pro.
Additionally, we introduce a novel decoding method for F-16 that enables highly efficient low-frame-rate inference without requiring model retraining. We will release the source code, model checkpoints, and data at [https://github.com/bytedance/F-16](https://github.com/bytedance/F-16).

---

## 论文详细总结（自动生成）

好的，请看以下对论文《Improving LLM Video Understanding with 16 Frames Per Second》的结构化深入总结。

### 1. 论文的核心问题与整体含义

*   **核心问题：** 当前多模态大语言模型在视频理解中普遍采用低帧率（通常 ≤ 2 FPS）静态图像采样的方式。这种方法假设1秒内的视频片段等同于几张独立图片，虽能捕捉场景主题，但严重丢失了快速变化的动态视觉线索（如细微动作、高速运动），导致模型在需要精细时空理解的任务上表现不佳，甚至可能产生幻觉。
*   **研究动机：** 人类视觉是动态且连续的。为了弥补现有视频LLM与人类视觉之间的鸿沟，需要让模型能够处理更高帧率的视频，捕获更丰富、连贯的动态信息。
*   **整体含义：** 本文旨在证明，通过将视频帧率提升至接近真实世界感知的16 FPS，并设计相应的特征压缩机制，能够显著增强 LLM 对视频的理解能力，为提升视频LLM性能开辟了一条超越简单扩大模型或数据规模的新路径。

### 2. 论文提出的方法论

**核心思想：** 提出名为F-16的模型，在输入端以高帧率（16 FPS）采样视频帧，并设计一个特殊的“高帧率对齐器”来压缩每秒内连续帧的视觉 token，在保留关键语义信息的同时，显式地提取和编码帧间的动态变化信息。

**关键技术细节与流程：**

1.  **高帧率采样：** 以16 FPS对视频进行密集采样，支持最长110秒视频，即最多处理1760帧。
2.  **高帧率对齐器：**
    *   **输入分组：** 将每秒内的 \(w = 16\) 个连续帧作为一个处理窗口。
    *   **特征拼接：** 将窗口内 \(w\) 帧由图像编码器提取的特征（维度 \(p \times d\)）在特征维度上拼接，形成一个 \(p \times wd\) 的组合特征。
    *   **3层MLP压缩：** 设计一个包含两个线性层和一个GELU激活函数的3层MLP结构。第一层 \(P(\cdot)\) 将特征维度从 \(wd\) 映射到 \(wh\)，第二层 \(Q(\cdot)\) 再从 \(wh\) 映射到最终的LLM输入维度 \(h\)。这个MLP在学习帧间差异、提取运动特征的同时，完成了特征维度的压缩。
    *   **空间池化：** 在MLP之后应用 \(2 \times 2\) 的最大池化层，进一步将token数量减少约4倍，降低计算负担。
3.  **模型初始化：** 为从预训练的图像LLM平滑迁移知识，设计了巧妙的初始化策略。将高帧率对齐器的大权重矩阵分解为块状结构，初始化时使用单帧对齐器的权重 \(W_A, W_B\) 进行填充，使得模型初始状态下的输出等价于对各独立帧特征的**平均**。非对角线位置用随机噪声初始化。
4.  **可变帧率解码：** 提出一种无需重新训练的测试时解码方法。若希望以 \(k\) 倍低帧率推理，只需将每个采样帧的特征重复 \(k\) 次，以匹配高帧率对齐器的输入维度。实验证明这种“帧重复”策略优于直接裁剪对齐器参数的“裁剪”策略，能在几乎不损失性能的情况下大幅提升推理速度。

### 3. 实验设计

*   **通用视频理解基准：**
    *   **数据集：** Video-MME、NeXT-QA、TemporalBench、MotionBench、VideoVista、MLVU、LongVideoBench。
    *   **对比方法：** GPT-4o、Gemini-1.5-Pro（商用模型）以及 LLaVA-Video-7B、NVILA-7B、Qwen2-VL-7B 等同参数规模的先进开源视频LLM。
*   **高速体育视频理解任务：**
    *   **数据集：** 专门构建了包含体操（FineGym）、跳水（Diving48）、足球（SoccerNet）和篮球（自建NBA数据集）的评测集，用于考验模型对快速动作的精细理解能力。
    *   **任务：** 动作描述、动作计数（如传球次数）、结果判断（如投篮是否命中）。
    *   **对比方法：** GPT-4o、Gemini-1.5-Pro，以及基于 FPS=1 训练的 F-16 版本作为消融对比。

### 4. 资源与算力

*   **通用视频训练：** 使用 **128 块 H100 GPU**，在通用视频数据上训练 **1 个 epoch**，学习率为 \(2 \times 10^{-5}\)。
*   **体育视频微调：** 使用 **64 块 H100 GPU**，对体育视频数据进行 **5 个 epoch** 的 LoRA 微调，学习率为 \(2 \times 10^{-5}\)。

### 5. 实验数量与充分性

论文进行了较为全面的实验，以验证方法的有效性和先进性。

*   **多基准评测：** 在7个主流视频QA和时空理解基准上进行了性能对比，涵盖了通用理解、长时理解和精细时空理解，评估维度充分。
*   **专项任务评测：** 专门构建了4类高速体育视频任务，验证了高帧率在特定场景下的绝对优势，对比目标包括强大的商用模型。
*   **消融与分析方法：**
    *   **池化策略消融：** 对比了在模态对齐器之前和之后进行池化的效果，证明了保留细粒度时序细节的重要性（后置池化 > 前置池化）。
    *   **上下文窗口可视化分析：** 通过计算连续帧特征相似度，可视化展示了关键动态信息是如何被池化操作抑制的，为模型设计提供了依据。
    *   **可变帧率测试消融：** 对比了“帧重复”与“参数裁剪”两种低帧率解码方法，并测试了不同测试帧率下的性能-速度曲线。
    *   **对齐器结构探索：** 将MLP对齐器与CNN、自注意力等结构进行了对比实验，验证了当前设计的优越性。
*   **公平性：** 为了公平对比，F-16的训练数据与主要对比模型LLaVA-Video-7B保持一致，确保了性能提升归因于方法本身而非数据增加。与商用模型的对比也使用了统一的帧数输入（120帧）。

### 6. 论文的主要结论与发现

1.  **高帧率是提升视频理解的有效途径：** F-16在7B参数规模下，在多个通用和精细时空理解基准上达到SOTA，证明了16 FPS的高帧率输入能显著减少信息丢失，增强模型对动态场景的理解。
2.  **优秀的时空推理能力：** 在 TemporalBench 和 MotionBench 这类专门评估时间与运动理解的基准上，F-16 相比同类模型有巨大提升，甚至超越了 GPT-4o 和 Gemini-1.5-Pro。
3.  **专用领域的巨大潜力：** 在高速体育视频分析等需要专业知识的复杂时空任务中，经过微调的F-16显著优于未能识别特定动作的商用大模型，展现了高帧率方案在下游应用中的价值。
4.  **高效推理的可行性：** 提出的可变帧率解码方法有效解决了高帧率模型推理慢的痛点，能够在几乎不损失性能的前提下灵活适应低帧率场景，大幅降低计算成本。

### 7. 优点

*   **原创性强：** 首次在视频LLM中系统性探索了高达16 FPS的高帧率建模，并提出了一套完整的解决方案。
*   **设计巧妙：** 高帧率对齐器的设计（3层MLP + 空间池化）在特征维度和空间维度上均实现了有效压缩，平衡了信息保真度与计算效率。基于块矩阵分解的初始化策略实现了预训练知识的平滑迁移。
*   **实际应用导向：** 可变帧率解码方法解决了高帧率模型落地时的推理效率瓶颈，具有很高的实用价值。
*   **验证全面扎实：** 实验设计覆盖面广，从通用评测到专项任务、从性能对比到机制分析，论证链条完整且说服力强。

### 8. 不足与局限

*   **长视频理解挑战：** 论文也指出，在处理长视频时，由于帧在时间上更稀疏，导致处理窗口内帧间变化更大，对齐器压缩编码的难度增加，F-16在部分长视频基准上的性能并未超越基于相同数据训练的低帧率SOTA模型。
*   **计算开销：** 虽然提出了可变帧率解码，但训练和全帧率推理时的计算量（所有帧均需通过图像编码器）显著高于传统低帧率模型，对硬件要求更高。
*   **通用性验证：** 模型基于特定的基座模型（LLaVA-OV， Qwen2-7B）构建，其方法迁移到其他LLM架构或视频编码器上的效果有待进一步验证。
*   **数据依赖：** 体育专项领域的优越性能依赖于高质量的微调数据，其泛化到其他未见的复杂动态场景的能力仍是未知数。

（完）
