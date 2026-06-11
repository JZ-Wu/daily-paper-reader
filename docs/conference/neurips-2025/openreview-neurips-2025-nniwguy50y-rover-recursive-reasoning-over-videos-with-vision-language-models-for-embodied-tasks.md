---
title: "ROVER: Recursive Reasoning Over Videos with Vision-Language Models for Embodied Tasks"
title_zh: ROVER：使用视觉语言模型进行递归视频推理以用于具身任务
authors: "Philip Schroeder, Ondrej Biza, Thomas Weng, Hongyin Luo, James R. Glass"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NNiwGUY50Y"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 递归V LM推理视频轨迹用于具身任务
tldr: 为解决具身场景中长视频轨迹推理的挑战，提出ROVER框架，将长序列递归分解为对应子任务的短片段，利用VLM进行时序局部化专注推理。在具身任务实验中显著提升推理准确率，展示出递归分解策略在视频理解代理中的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 2752, \"height\": 1710}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-002.webp\", \"caption\": \"\", \"page\": 5, \"index\": 2, \"width\": 2356, \"height\": 1254}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-003.webp\", \"caption\": \"\", \"page\": 6, \"index\": 3, \"width\": 770, \"height\": 903}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-004.webp\", \"caption\": \"\", \"page\": 8, \"index\": 4, \"width\": 749, \"height\": 927}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-005.webp\", \"caption\": \"\", \"page\": 23, \"index\": 5, \"width\": 3258, \"height\": 1628}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-006.webp\", \"caption\": \"\", \"page\": 23, \"index\": 6, \"width\": 2992, \"height\": 1638}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-007.webp\", \"caption\": \"\", \"page\": 24, \"index\": 7, \"width\": 3106, \"height\": 1560}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-008.webp\", \"caption\": \"\", \"page\": 29, \"index\": 8, \"width\": 1544, \"height\": 506}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-009.webp\", \"caption\": \"\", \"page\": 29, \"index\": 9, \"width\": 1543, \"height\": 506}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-010.webp\", \"caption\": \"\", \"page\": 29, \"index\": 10, \"width\": 1542, \"height\": 506}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-011.webp\", \"caption\": \"\", \"page\": 29, \"index\": 11, \"width\": 1543, \"height\": 506}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-012.webp\", \"caption\": \"\", \"page\": 30, \"index\": 12, \"width\": 2308, \"height\": 455}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-013.webp\", \"caption\": \"\", \"page\": 35, \"index\": 13, \"width\": 3038, \"height\": 1282}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-014.webp\", \"caption\": \"\", \"page\": 35, \"index\": 14, \"width\": 2544, \"height\": 1070}]"
motivation: VLM难以在长视频序列上进行持续推理，限制其在具身任务中的应用。
method: 递归分解长视频轨迹为短子任务片段，对每个片段进行VLM推理。
result: 在具身任务上推理性能大幅提升，超越直接处理长视频的方法。
conclusion: ROVER为视频推理代理提供了一种分解-聚焦的通用策略，增强VLM的时序理解。
---

## Abstract
Vision-language models (VLMs) have exhibited impressive capabilities across diverse image understanding tasks, but still struggle in settings that require reasoning over extended sequences of camera frames from a video. This limits their utility in embodied settings, which require reasoning over long frame sequences from a continuous stream of visual input at each moment of a task attempt. To address this limitation, we propose ROVER (Reasoning Over VidEo Recursively), a framework that enables the model to recursively decompose long-horizon video trajectories into segments corresponding to shorter subtasks within the trajectory. In doing so, ROVER facilitates more focused and accurate reasoning over temporally localized frame sequences without losing global context. We evaluate ROVER, implemented using an in-context learning approach, on diverse OpenX Embodiment videos and on a new dataset derived from RoboCasa that consists of 543 videos showing both expert and perturbed non-expert trajectories across 27 manipulation tasks. ROVER outperforms strong baselines across three video reasoning tasks: task progress estimation, frame-level natural language reasoning, and video question answering. We observe that, by reducing the number of frames the model reasons over at each timestep, ROVER mitigates model hallucinations, especially during unexpected or non-optimal moments of a trajectory. In addition, by enabling the implementation of a subtask-specific sliding context window, ROVER's time complexity scales linearly with video length, an asymptotic improvement over baselines.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机与背景**：视觉语言模型（VLM）在图像理解任务中表现出色，但在需要从连续视频流（如搭载在机器人上的摄像头）中进行长时序推理的**具身场景**（Embodied Settings）中仍面临巨大挑战。
*   **核心问题**：现有方法存在两难困境：要么只对少数关键帧进行局部推理，**牺牲了全局上下文**；要么将所有视频帧拼接成一个长序列进行处理，导致**计算成本高昂且模型被冗余视觉输入淹没**，容易产生幻觉。
*   **整体含义**：论文旨在提升VLM在具身场景下的视频推理能力，实现高精度的逐帧推理，同时兼顾效率和全局任务上下文。

### 2. 论文提出的方法论
*   **核心思想**：提出**ROVER**框架，其核心是**递归地**将长时域视频轨迹**分解**为对应更短子任务的片段。这使得模型能在时间上局部化的帧序列上进行更专注、更准确的推理，而不会丢失全局上下文。
*   **关键技术细节与算法流程**：
    *   **递归函数**：ROVER实现为一个递归函数（Algorithm 1）。它接收任务上下文c和已生成的令牌序列Y，然后循环生成新令牌。
    *   **子任务切换**：当模型生成特定文本标记（如“The robot needs to: {new_subtask}”）时，表示指定了一个新的子任务。此时，函数会**递归调用自身**，启动一个子进程来处理新子任务对应的视频片段。子进程结束后，其输出会返回给父进程。
    *   **帧推进**：当模型生成“[next-frame]”标记时，将视频的下一帧图像令牌添加到序列Y中。
    *   **滑动上下文窗口**：在每个时间步，ROVER使用一个**子任务特定的滑动窗口**。窗口仅包含3帧：当前推理行的第一帧、最近的前一帧和当前新加入的帧。这使得模型推理时的复杂度与视频长度呈**线性关系**，解决了长上下文导致的幻觉问题。
    *   **上下文传递**：函数ϕ定义子任务的上下文（如新的任务描述和父进程的最后一帧），函数ψ定义子进程返回给父进程的输出（如最终帧及其描述）。

### 3. 实验设计
*   **数据集**：
    *   **自建数据集**：基于**RoboCasa**模拟器，通过对专家演示注入随机扰动，自动生成了包含27个操作任务、543个视频的数据集。视频涵盖了从近乎专家到完全随机的多种轨迹，并配有基于几何距离计算的真值任务进度标签。
    *   **真实世界数据集**：使用了**OpenX Embodiment (OXE)** 数据集中的真实机器人视频进行评估。
*   **Benchmark与评估任务**：
    1.  **帧级任务进度估计 (Task 1)**：预测视频每一帧的任务完成百分比。
    2.  **帧级自然语言推理 (Task 2)**：在每一帧生成描述，并与真值状态比对计算错误率和成功率。
    3.  **视频问答 (Task 3)**：回答关于视频中是否及何时发生特定事件的问题。
*   **对比方法**：
    *   **LIV**：基于多模态对比学习的SOTA价值模型。
    *   **GVL**：通过随机打乱视频帧序列进行推理的SOTA上下文学习方法。
    *   **TemporalConcat**：按时间顺序拼接所有帧进行推理的基线方法。
    *   **LocalConcat**：只使用最近3帧进行推理的局部基线方法。
*   **骨干VLM**：主要使用**Gemini-1.5-Pro**，并额外测试了**GPT-4o**、**Gemini-2.5-Pro-Preview**和**Qwen-2.5-VL-32B**。

### 4. 资源与算力
*   论文**未明确说明**使用Gemini-1.5-Pro等商业API模型进行实验的具体算力成本。
*   对于开源模型（如Qwen2.5-VL-32B），论文提及在**A6000 GPU**上运行了实验。但整体的训练（该工作主要为上下文学习，不涉及训练）或大规模推理的总GPU时长、数量等细节没有被完整报告。

### 5. 实验数量与充分性
*   **实验组数**：实验设计较为**充分**。
    *   **主实验**：在自建的RoboCasa数据集上，针对3个不同类型的推理任务，与4个基线方法进行了全面对比。
    *   **领域外测试**：在真实世界的OXE数据集上测试了任务进度预测，验证了方法的泛化能力。
    *   **消融实验**：分别消融了滑动窗口和递归推理模块，以分析各组件的贡献。
    *   **鲁棒性分析**：测试了不同视频长度、帧率、相机视角和骨干VLM下的性能表现。
    *   **错误分析**：手工审查了100个仿真和100个真实视频，对错误类型进行了分类统计。
*   **客观性与公平性**：对比的基线方法包含当前SOTA，评估指标（相关性、距离、错误率、QA准确率等）多样且客观。所有方法在同一数据集和评估协议下进行测试，比较公平。

### 6. 论文的主要结论与发现
*   ROVER在所有三个视频推理基准和真实世界OXE视频上**均优于**所有基线方法。
*   **核心发现**：ROVER通过递归分解和滑动窗口**减少了模型需要同时推理的帧数**，从而有效**减轻了模型的幻觉**，尤其是在处理视频中**非最优、意外**的行为时刻。
*   通过与真值任务进度的对比，ROVER具有更高的相关性（Pearson correlation），且在帧级推理中错误率更低。
*   ROVER的处理时间复杂度与视频长度**呈线性关系**，相比基线方法的二次方复杂度，在长视频上具有显著的效率优势。

### 7. 优点
*   **创新性框架**：提出了一个将“递归分解”应用于具身视频推理的新颖框架，优雅地解决了全局上下文与局部精度、计算效率之间的权衡。
*   **问题洞察深刻**：精准地识别并解决了VLM在长视频序列中因上下文过长而产生幻觉，尤其在非理想状态下推理失败的痛点。
*   **实验扎实全面**：不仅构建了带真值标签的多样化仿真数据集，还在真实世界数据上验证，并通过丰富的消融实验、鲁棒性测试和人工错误分析，深入揭示了方法有效性的内在机理。
*   **效率提升显著**：实现了推理复杂度的线性增长，为处理更长的视频流提供了可扩展的解决方案。

### 8. 不足与局限
*   **对任务分解准确性的依赖**：当递归分解失败（如生成错误或不必要的子任务）时，会导致后续推理碎片化或与任务实际进程错位，这是该方法的一个关键风险点。
*   **应用限制**：
    *   **任务结构假设**：方法假设任务可以被分解为一组已知的、以对象为中心的子任务序列，这可能不适用于所有现实世界的复杂任务。
    *   **实现方式单一**：目前仅验证了基于上下文学习的实现，尚未探索通过微调来提升帧级推理和价值估计性能的潜力。
*   **实验评估覆盖**：虽然任务多样，但所有仿真实验均局限于**RoboCasa厨房环境**，在更广泛的环境和任务类型上的通用性有待进一步验证。
*   **误差传播风险**：递归结构存在误差传播的可能性，早期子任务的推理错误可能影响后续所有父任务或子任务。

（完）
