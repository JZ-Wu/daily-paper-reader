---
title: Unleashing the Potential of Multimodal LLMs for Zero-Shot Spatio-Temporal Video Grounding
title_zh: 释放多模态大语言模型在零样本时空视频定位中的潜能
authors: "Zaiquan Yang, Yuhao LIU, Gerhard Petrus Hancke, Rynson W. H. Lau"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=F9SSJLg55j"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 使用多模态大语言模型的零样本时空视频定位，无需训练
tldr: 时空视频定位通常需要大量标注数据训练。本文发现多模态大语言模型能够动态分配定位令牌执行零样本定位，但常因未充分利用文本查询线索而性能欠佳。据此提出包含分解时空高亮和时间增强的零样本框架，无需任务特定训练。在多个数据集上取得高竞争力结果，为无需训练的视频定位开辟了新路径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-001.webp\", \"caption\": \"\", \"page\": 4, \"index\": 1, \"width\": 1943, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 1945, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 1944, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-004.webp\", \"caption\": \"\", \"page\": 4, \"index\": 4, \"width\": 1943, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-005.webp\", \"caption\": \"\", \"page\": 7, \"index\": 5, \"width\": 2684, \"height\": 1472}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-006.webp\", \"caption\": \"\", \"page\": 7, \"index\": 6, \"width\": 2401, \"height\": 1309}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-007.webp\", \"caption\": \"\", \"page\": 7, \"index\": 7, \"width\": 2303, \"height\": 1256}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-008.webp\", \"caption\": \"\", \"page\": 9, \"index\": 8, \"width\": 3042, \"height\": 1668}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-009.webp\", \"caption\": \"\", \"page\": 9, \"index\": 9, \"width\": 2526, \"height\": 1614}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-010.webp\", \"caption\": \"\", \"page\": 9, \"index\": 10, \"width\": 2611, \"height\": 1582}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-011.webp\", \"caption\": \"\", \"page\": 9, \"index\": 11, \"width\": 2558, \"height\": 1574}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-012.webp\", \"caption\": \"\", \"page\": 25, \"index\": 12, \"width\": 1459, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-013.webp\", \"caption\": \"\", \"page\": 25, \"index\": 13, \"width\": 1459, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-014.webp\", \"caption\": \"\", \"page\": 25, \"index\": 14, \"width\": 1459, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-015.webp\", \"caption\": \"\", \"page\": 25, \"index\": 15, \"width\": 1458, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-016.webp\", \"caption\": \"\", \"page\": 25, \"index\": 16, \"width\": 1459, \"height\": 858}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-017.webp\", \"caption\": \"\", \"page\": 25, \"index\": 17, \"width\": 1459, \"height\": 858}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-018.webp\", \"caption\": \"\", \"page\": 25, \"index\": 18, \"width\": 1459, \"height\": 858}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-019.webp\", \"caption\": \"\", \"page\": 25, \"index\": 19, \"width\": 1458, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-020.webp\", \"caption\": \"\", \"page\": 25, \"index\": 20, \"width\": 1458, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-021.webp\", \"caption\": \"\", \"page\": 25, \"index\": 21, \"width\": 1943, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-022.webp\", \"caption\": \"\", \"page\": 25, \"index\": 22, \"width\": 1943, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-023.webp\", \"caption\": \"\", \"page\": 25, \"index\": 23, \"width\": 1944, \"height\": 1143}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-024.webp\", \"caption\": \"\", \"page\": 25, \"index\": 24, \"width\": 1944, \"height\": 1143}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-025.webp\", \"caption\": \"\", \"page\": 25, \"index\": 25, \"width\": 1944, \"height\": 1143}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-026.webp\", \"caption\": \"\", \"page\": 25, \"index\": 26, \"width\": 1945, \"height\": 1145}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-027.webp\", \"caption\": \"\", \"page\": 32, \"index\": 27, \"width\": 6972, \"height\": 4562}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-f9ssjlg55j/fig-028.webp\", \"caption\": \"\", \"page\": 32, \"index\": 28, \"width\": 2303, \"height\": 1256}]"
motivation: 传统方法依赖监督训练，多模态大模型零样本定位潜力未被充分探索。
method: 利用MLLM定位令牌现象，设计分解时空高亮与时间增强框架。
result: 零样本定位性能媲美有监督方法，显著降低标注成本。
conclusion: 为零样本视频定位提供了有效方案，展示了大模型的强泛化能力。
---

## Abstract
Spatio-temporal video grounding (STVG) aims at localizing the spatio-temporal tube of a video, as specified by the input text query.
In this paper, we utilize multimodal large language models (MLLMs) to explore a zero-shot solution in STVG.
We reveal two key insights about MLLMs: 
(1) MLLMs tend to dynamically assign special tokens, referred to as \textit{grounding tokens}, for grounding the text query; and
(2) MLLMs often suffer from suboptimal grounding due to the inability to fully integrate the cues in the text query (\textit{e.g.}, attributes, actions) for inference. Based on these insights, we propose a MLLM-based zero-shot framework for STVG, which includes novel decomposed spatio-temporal highlighting (DSTH) and temporal-augmented assembling (TAS) strategies to unleash the reasoning ability of MLLMs.
The DSTH strategy first decouples the original query into attribute and action sub-queries for inquiring the existence of the target both spatially and temporally.
It then uses a novel logit-guided re-attention (LRA) module to learn latent variables as spatial and temporal prompts, by regularizing token predictions for each sub-query.
These prompts highlight attribute and action cues, respectively, directing the model's attention to reliable spatial and temporal related visual regions.
In addition, as the spatial grounding by the attribute sub-query should be temporally consistent,
we introduce the TAS strategy to assemble the predictions using the original video frames and the temporal-augmented frames as inputs to help improve temporal consistency.
We evaluate our method on various MLLMs, and show that it outperforms SOTA methods on three common STVG benchmarks.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以 Markdown 形式，对提供的论文进行结构化、深入、客观的总结。

### 论文核心问题与整体含义
本文聚焦于**零样本时空视频定位**任务。该任务要求模型在没有相应标注数据训练的情况下，根据一段文本查询，在视频中定位出目标对象的时空管道（即目标在哪些帧出现，以及在每一帧中的具体位置）。

*   **研究动机与背景**：
    *   **现有方法的局限**：传统的STVG方法依赖大量的全监督数据（昂贵的帧级标注），而弱监督或零样本方法（如基于CLIP的E3M）由于其模型固有的全局对齐特性，在细粒度定位任务上表现不佳。
    *   **MLLM的潜力与问题**：多模态大语言模型拥有强大的跨模态理解能力。作者发现MLLM在处理查询时，会**动态分配某些特殊令牌（称为“定位令牌”）来隐式地关注目标区域**，这为零样本定位提供了可能。然而，MLLM在处理复杂查询时，常常**无法充分整合文本中的所有线索（如属性、动作），导致空间或时间定位错误**。
*   **核心目标与整体含义**：本文旨在深入挖掘并释放现有多模态大语言模型在零样本STVG任务上的潜力，通过提出新颖的测试时优化策略，解决MLLM忽略关键文本线索的问题，从而无需任何针对性训练即可实现高精度的时空定位。

### 方法论
本文的核心思想是**通过分解文本查询并有针对性地优化MLLM的注意力，来增强其对空间和时间线索的辨别能力**，并辅以**时间一致性增强**。整个框架为免训练的零样本方案。

1.  **定位令牌的识别**
    *   **核心观察**：MLLM输入序列中，紧跟用户指令的特殊令牌（例如 `<_A>`, `<IST>` 等）具有卓越的定位能力，且**视觉激活值越高的特殊令牌，其定位性能越好**。
    *   **方法**：基于此发现，作者直接选取在特定层和注意力头中具有最高视觉激活值的特殊令牌作为“定位令牌”，并将其对应的文本-视觉注意力图作为定位目标的基础。

2.  **分解时空高亮策略**
    *   **核心思想**：为解决MLLM忽略文本线索的问题，将原始查询解耦为**空间（属性）子查询**和**时间（动作）子查询**，分别用于引导空间和时间定位。
    *   **目标相关线索生成**：利用大语言模型的上下文学习能力，将原始查询分解为描述属性的短语（如“一个穿红色衣服的女人”）和描述动作的短语（如“一个女人走了几步然后转身”）。
    *   **Logit引导的重关注模块**：
        *   **子查询构造**：将分解出的属性/动作短语转化为问询式（例如，“Is there a woman in red clothes in this video?”），输入MLLM。
        *   **可学习提示优化**：在与视觉令牌相加的位置，分别初始化一个**空间可学习变量（空间提示）**和一个**时间可学习变量（时间提示）**。
        *   **正则化目标**：LRA模块的核心在于通过**对比预测“yes”和“no”令牌的logit值**来优化上述变量。具体来说，目标是最大化模型对子查询回答“yes”的概率相对于回答“no”的概率。目标函数为 `Ls = 1 - exp(logit(yes) - logit(no))`。
        *   **推理**：通过这种方式，模型被迫更仔细地关注与子查询相关的视觉信息以产生肯定回答，从而使得优化后的提示能够高亮对应的属性或动作线索。

3.  **时间增强装配策略**
    *   **核心思想**：由于属性描述是静态的，基于属性子查询进行的空间定位应当具备时间一致性（即反转视频帧顺序不应影响空间定位结果）。然而实验发现，直接反转帧会破坏MLLM定位的稳定性。
    *   **方法**：在测试时，同时向MLLM输入**原始帧+空间提示**和**反转帧+空间提示**，分别进行LRA优化。在推理阶段，**融合两种输入得到的注意力图**作为最终的空间预测，从而提高空间定位的鲁棒性和时间一致性。

### 实验设计
*   **数据集与基准**：实验在三个主流的STVG基准数据集上进行评估：**HC-STVG-v1**、**HC-STVG-v2** 和 **VidSTG**。评估指标遵循标准协议，采用 **m_vIoU**（平均视频交并比）和 **vIoU@R**（在不同阈值R下的交并比准确率）。
*   **对比方法**：论文将提出的方法与全部三种设定下的SOTA方法进行了全面比较：
    *   **全监督方法**：TubeDETR, STCAT, CSDVL, CG-STVG等。
    *   **弱监督方法**：WINNER, VEM, CoSPaL, STPro等。
    *   **零样本方法**：ReCLIP, RedCircle, E3M等。
*   **提出的基线**：使用了四种先进的视频MLLM作为基础模型以验证方法的通用性：**LLaVA-Next-Video-7B**, **Qwen2-VL-7B**, **ShareGPT4Video-8B**, 和 **LLaVA-OneVision-7B**。

### 资源与算力
论文明确指出，所有实验均在**单块拥有80G显存的NVIDIA A100 GPU**上进行，基于PyTorch框架实现。考虑到使用了7B/8B级别的MLLM，这个算力配置是现代的，但对实验规模有一定限制。论文未提及总实验时长。

### 实验数量与充分性
实验设计较为充分和客观：

1.  **多基准测试**：在3个公开STVG基准上进行了测试，覆盖了不同的数据规模和查询类型。
2.  **广泛的基线对比**：与全监督、弱监督和零样本三大类共11种SOTA方法进行了横向比较，对比维度全面。
3.  **多模型验证**：在4种不同的视频MLLM上进行了效果验证，证明了方法的**通用性**和**模型无关性**。
4.  **详尽的消融研究**：
    *   对方法的各个组件（定位令牌识别、空间提示、时间提示、TAS）进行了消融，验证了每个模块的有效性。
    *   对比了不同的测试时优化策略（LRA vs. 熵最小化）。
    *   分析了关键超参数（如输入帧数、预测帧数、优化迭代次数和学习率）的影响。
5.  **扩展性分析**：还在InternVL3和Qwen2.5-VL等其他系列模型上验证了方法的可扩展性。
这些实验从多个维度验证了方法的有效性、鲁棒性和通用性，设计是客观和公平的。

### 主要结论与发现
*   MLLM中的特殊令牌具备强大的、动态分配的零样本定位能力，其视觉激活强度与定位精度正相关。
*   提出的**DSTH策略**通过将查询分解并利用**LRA模块对比“yes/no”来优化空间/时间提示**，能有效引导模型关注被忽略的属性和动作线索，显著提升定位精度。
*   提出的**TAS策略**能有效缓解视频帧反转带来的时间不一致问题，进一步提升空间定位的鲁棒性。
*   整个框架在**无需任何训练（零样本）** 的条件下，全面超越了所有现有的零样本方法，甚至超越了部分弱监督方法，并可与全监督方法媲美。

### 优点
*   **创新的洞察**：首次系统地揭示并量化了MLLM中特殊令牌的定位能力，为利用大模型感知能力开辟了新视角。
*   **免训练方案**：整个方法完全基于测试时优化和推理，无需任何微调或标注数据，部署成本低，实用性极强。
*   **精巧的测试时优化**：提出的LRA模块通过对比“yes”/“no”的logit来间接优化视觉注意力，是一种新颖且有效的提示学习方法。
*   **方法的通用性**：不依赖于特定的MLLM架构，在多个主流视频大模型上均表现出显著的性能提升，具有良好的可迁移性。

### 不足与局限
*   **计算效率**：虽然免训练，但测试时需要对每个样本进行迭代优化，引入额外的计算开销，可能不适合实时应用。
*   **长视频处理受限**：由于MLLM的计算消耗，目前只能处理有限数量的视频帧（如20帧），限制了其对长视频的理解能力。
*   **对底层模型的依赖**：性能受限于所使用的MLLM、检测器和跟踪器的能力。使用的LLM质量（如GPT-4o）也会影响查询分解的效果。
*   **实验偏差风险**：仅在公开的学术基准上测试，其对于真实世界中噪声更大、场景更复杂的视频数据的泛化能力尚需验证。
*   **可解释性**：方法基于启发式观察，对“yes/no”对比为何能有效引导注意力，内部机制的黑箱性较强，缺乏更深层次的理论证明。

（完）
