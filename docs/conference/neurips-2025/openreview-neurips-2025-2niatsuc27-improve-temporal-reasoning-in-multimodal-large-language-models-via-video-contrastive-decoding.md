---
title: Improve Temporal Reasoning in Multimodal Large Language Models via Video Contrastive Decoding
title_zh: 通过视频对比解码改进多模态大语言模型的时间推理
authors: "Daiqing Qi, Dongliang Guo, Hanzhang Yuan, Handong Zhao, Mengxuan Hu, Lehan Yang, Sheng Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2nIAtsUC27"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 通过对比解码增强视频LLM的时间推理
tldr: 针对现有视频大语言模型在处理连续动作等时间推理上的不足，提出视频对比解码方法，通过抑制语言和图像先验偏差增强模型的时间理解能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2niatsuc27/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 650, \"height\": 439}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2niatsuc27/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 592, \"height\": 328}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2niatsuc27/fig-003.webp\", \"caption\": \"\", \"page\": 4, \"index\": 3, \"width\": 3000, \"height\": 1050}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2niatsuc27/fig-004.webp\", \"caption\": \"\", \"page\": 9, \"index\": 4, \"width\": 3600, \"height\": 1200}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2niatsuc27/fig-005.webp\", \"caption\": \"\", \"page\": 9, \"index\": 5, \"width\": 2400, \"height\": 1200}]"
motivation: 视频LLM在通用理解上表现良好，但在如动作理解和物体变换等需要时间连贯性的任务上表现不佳。
method: 提出视频对比解码，从语言和图像先验角度解释失败原因，并通过解码策略缓解偏差。
result: 实验验证该方法提升了视频LLM在多类时间推理任务上的性能。
conclusion: 对比解码是一种有效的时间推理增强策略，无需额外训练。
---

## Abstract
A major distinction between video and image understanding is that the former requires reasoning over time.
Existing Video Large Language Models (VLLMs) demonstrate promising performance in general video understanding, such as brief captioning or object recognition within individual frames. However, they often struggle with temporal reasoning such as understanding continuous actions or tracking object transformations over time—which typically demands the integration of multiple frames in a temporally coherent manner.
We first explore and explain such failures in Video LLMs from the perspective of \textit{language and ``image'' priors.}
While existing research has attempted to enhance the temporal understanding of VLLMs through various training strategies, the demand for expensive computational resources and training data often presents significant barriers.
To this end, we further propose a simple yet novel idea for improving temporal reasoning in videos at no additional training cost.
Specifically, to better capture the temporal structure across multiple frames—the key to effective temporal reasoning—we distort the temporal consistency in key frames \textit{during the decoding phase}. Such corruption induces time-insensitive wrong responses from the model, which are then contrastively avoided when generating the final correct output. In this way, the model is encouraged to perform more temporally coherent reasoning.
Our method yields consistent improvements across both temporal-specific and general video understanding benchmarks, demonstrating its effectiveness and generalizability.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文内容，以下是结构化的详细中文总结。

### 1. 论文的核心问题与整体含义
*   **核心问题**：现有的视频大语言模型在通用视频理解上表现不错，但在**时间推理**方面存在显著缺陷，例如难以理解连续动作或追踪物体随时间的变化。
*   **整体含义（研究动机）**：
    *   论文首先探究了造成时间推理失败的原因，从全新的**“语言先验”和“图像先验”** 角度进行了解释。即，模型有时会过度依赖文本中的常识性知识，或被静态帧的视觉内容误导，从而忽略了视频中的时序动态信息。
    *   现有研究主要通过修改模型架构和改进训练数据等**资源密集型**方式来提升时序理解，成本高昂。本研究旨在探索一种**无需额外训练、即插即用**的方法，通过在解码阶段进行操作来提升视频LLM的时间推理能力。

### 2. 论文提出的方法论
*   **核心思想**：采用**对比解码**框架。核心思路是故意破坏视频输入中的时间一致性，诱导模型生成对时间不敏感的“错误答案”，然后在最终解码时，通过对比，明确地避开这些错误模式，从而生成时间上更连贯的正确答案。
*   **关键技术细节**：
    *   **视频时序扭曲**：设计了一个“时序扭曲单元”，自适应地对原始视频进行扭曲，生成一个“坏”的输入`V'`。扭曲需要满足三个标准：(1) 移除时间信息；(2) 保留可能误导模型的静态视觉先验；(3) 能够根据视频内容自适应调整。
    *   **扭曲流程**：
        1.  **关键帧选择**：利用LLM中间层的注意力图，通过动量累积计算每一帧的重要性，选出最关键（含有丰富时序信息）的`Top-w`帧。
        2.  **关键帧融合**：对选出的关键帧，用它们的**平均池化**结果进行替换，并加入少量高斯噪声。这移除了帧间变化的时序线索，但保留了粗粒度的图像上下文，用于诱导出错。
        3.  **剩余帧令牌级扭曲**：对剩余的次重要帧，根据令牌重要性分数，**屏蔽**掉其中最关键的`Top-w`个图像令牌区域。
        4.  **移动内容破坏**：对剩余帧，通过滑动窗口比较各个图像块在不同帧之间的相似度，找出并融合（平均池化）那些动态变化的区域，从而抹除时序变化信息。
    *   **解码公式**：最终的概率分布`p_vtd`通过以下公式计算，其中`α`是控制差异放大程度的超参数。
        `p_vtd(y | V, V', x) = softmax [(1 + α) logit(y | V, x) - α logit(y | V', x)]`
        简单说，就是奖励原始视频下的高概率答案，惩罚被扭曲视频下的高概率（错误）答案。

### 3. 实验设计
*   **数据集与基准测试**：
    *   **时间推理基准**：`TempCompass`（评估事件顺序、属性变化等）、`EventHallusion`（评估对连续动作的理解）。
    *   **通用视频理解基准**：`VideoMME`（评估长视频综合理解）、`MLVU`（多任务长视频理解）。
*   **对比方法**：
    *   **骨干模型**：`Video-LLaVA` 和 `LLaVA-Video-7B-Qwen2`。在其上应用本方法，与原始模型结果（Vanilla）对比。
    *   **其他对比解码策略**：`VCD`（视觉对比解码）、`SID`（自省解码）、`TCD`（时间对比解码，随机丢帧）。
    *   **其他先进视频LLM**：如`VILA`系列、`InternVL`、`LongVA`等。

### 4. 资源与算力
*   文中“实验配置”部分提到，所有的推理均在**NVIDIA A6000 GPU 和 A100 GPU**上运行。但未提及具体的使用数量和推理总时长。

### 5. 实验数量与充分性
*   **实验数量**：
    *   在**4个主要数据集**（TempCompass, EventHallusion, VideoMME, MLVU）上进行了评估。
    *   与多种方法进行了对比，包括2个骨干模型的原始版本、3种其他的对比解码策略以及数个先进的视频大模型。
    *   在LLaVA-Video-7B-Qwen2模型上进行了详细的**消融研究**，分析了时序扭曲单元中每个模块的贡献，并讨论了多个关键超参数（如帧扭曲比率、令牌扭曲比率等）对性能的影响。
*   **充分性**：实验设计较为充分，覆盖了专门的时间推理和通用视频理解任务，证明了方法的有效性和泛化能力。与多种基线方法的对比，以及详细的消融和超参数分析，使得结论客观、公平。

### 6. 论文的主要结论与发现
*   **失败原因**：视频LLM在时间推理上的失败可归因于**语言先验和“图像”先验**的干扰。
*   **方法有效性**：提出的无需训练的视频对比解码方法，通过自适应时序扭曲和对比解码，能够显著提升模型的时间推理能力。
*   **性能提升**：该方法在多个时间推理和通用视频理解基准测试上，为骨干模型带来了**一致性且显著的性能提升**，尤其在时间相关的子任务上。例如，在TempCompass上，LLaVA-Video-7B-Qwen2的整体性能从65.0提升至67.5。
*   **时空权衡**：研究发现提升时间感知可能会对静态空间细节的理解产生**轻微的负面影响**，存在一定的权衡关系。

### 7. 优点
*   **无需额外训练**：该方法是一种在解码端操作的即插即用技术，不产生额外的训练成本，计算开销小，具有很高的实用价值。
*   **视角新颖**：首次从“语言先验”和“图像先验”的角度分析和解释了视频LLM时间推理失败的原因，为后续研究提供了新思路。
*   **方法设计精巧**：提出的时序扭曲单元设计巧妙，能自适应地、细粒度地破坏视频中的时间信息，同时保留用于诱导模型出错的混淆性上下文。
*   **效果显著且稳健**：不仅在时间推理专用基准上效果显著，还在通用视频理解任务上取得提升，证明了其泛化能力。

### 8. 不足与局限
*   **对注意力图的依赖**：时序扭曲单元依赖LLM中间层的注意力图来评估视觉令牌的重要性，而注意力图可能无法总是精确反映令牌的真实重要性，可能影响扭曲的质量。
*   **模态局限性**：当前研究仅针对视频的视觉表征进行扭曲。对于现实中常带有字幕的视频，如何进行跨模态（视频和字幕）的扭曲以进一步改进，尚待探索。
*   **时空权衡**：研究观察到，方法在提升时间感知能力的同时，可能会略微损害对空间细节的理解任务，揭示了能力之间的潜在冲突，但未提供深层次的解决方案。
*   **计算效率**：基于对比解码的方法需要两次前向传播（原始视频和扭曲视频），生成速度会比普通解码慢。文中虽提出了一种优化方案，但存在高峰期显存增大的问题。

（完）
