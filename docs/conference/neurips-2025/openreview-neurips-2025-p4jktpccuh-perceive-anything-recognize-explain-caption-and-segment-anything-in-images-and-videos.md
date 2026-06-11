---
title: "Perceive Anything: Recognize, Explain, Caption, and Segment Anything in Images and Videos"
title_zh: Perceive Anything：在图像和视频中识别、解释、描述并分割任何物体
authors: "Weifeng Lin, Xinyu Wei, Ruichuan An, Tianhe Ren, Tingwei Chen, Renrui Zhang, Ziyu Guo, Wentao Zhang, Lei Zhang, Hongsheng Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=p4jKtPCcUh"
tags: ["query:tf-vl-ag"]
score: 4.0
evidence: 利用SAM2+LLM实现视频中的区域级视觉理解
tldr: PAM通过语义感知器将SAM 2的视觉特征转换为多模态令牌供LLM理解，实现视频中目标的分割与类别、解释、描述等多粒度语义输出统一。该框架在多种理解任务上表现优异，为视频内容全面感知提供了简单高效的基础工具，可潜在支持代理式系统的底层感知。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 433, \"height\": 770}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-002.webp\", \"caption\": \"\", \"page\": 1, \"index\": 2, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-003.webp\", \"caption\": \"\", \"page\": 1, \"index\": 3, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-004.webp\", \"caption\": \"\", \"page\": 1, \"index\": 4, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-005.webp\", \"caption\": \"\", \"page\": 1, \"index\": 5, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-006.webp\", \"caption\": \"\", \"page\": 1, \"index\": 6, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-007.webp\", \"caption\": \"\", \"page\": 1, \"index\": 7, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-008.webp\", \"caption\": \"\", \"page\": 1, \"index\": 8, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-009.webp\", \"caption\": \"\", \"page\": 1, \"index\": 9, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-010.webp\", \"caption\": \"\", \"page\": 1, \"index\": 10, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-011.webp\", \"caption\": \"\", \"page\": 1, \"index\": 11, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-012.webp\", \"caption\": \"\", \"page\": 1, \"index\": 12, \"width\": 433, \"height\": 770}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-013.webp\", \"caption\": \"\", \"page\": 1, \"index\": 13, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-014.webp\", \"caption\": \"\", \"page\": 1, \"index\": 14, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-015.webp\", \"caption\": \"\", \"page\": 1, \"index\": 15, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-016.webp\", \"caption\": \"\", \"page\": 1, \"index\": 16, \"width\": 513, \"height\": 770}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-017.webp\", \"caption\": \"\", \"page\": 1, \"index\": 17, \"width\": 1588, \"height\": 355}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-018.webp\", \"caption\": \"\", \"page\": 1, \"index\": 18, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-019.webp\", \"caption\": \"\", \"page\": 1, \"index\": 19, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-020.webp\", \"caption\": \"\", \"page\": 1, \"index\": 20, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-021.webp\", \"caption\": \"\", \"page\": 1, \"index\": 21, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-022.webp\", \"caption\": \"\", \"page\": 1, \"index\": 22, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-023.webp\", \"caption\": \"\", \"page\": 4, \"index\": 23, \"width\": 859, \"height\": 583}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-024.webp\", \"caption\": \"\", \"page\": 4, \"index\": 24, \"width\": 858, \"height\": 581}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-025.webp\", \"caption\": \"\", \"page\": 4, \"index\": 25, \"width\": 799, \"height\": 523}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-026.webp\", \"caption\": \"\", \"page\": 4, \"index\": 26, \"width\": 1225, \"height\": 814}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-027.webp\", \"caption\": \"\", \"page\": 4, \"index\": 27, \"width\": 801, \"height\": 524}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-028.webp\", \"caption\": \"\", \"page\": 4, \"index\": 28, \"width\": 860, \"height\": 583}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-029.webp\", \"caption\": \"\", \"page\": 4, \"index\": 29, \"width\": 802, \"height\": 524}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-030.webp\", \"caption\": \"\", \"page\": 4, \"index\": 30, \"width\": 859, \"height\": 582}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-031.webp\", \"caption\": \"\", \"page\": 4, \"index\": 31, \"width\": 1294, \"height\": 846}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-032.webp\", \"caption\": \"\", \"page\": 4, \"index\": 32, \"width\": 800, \"height\": 523}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-033.webp\", \"caption\": \"\", \"page\": 6, \"index\": 33, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-034.webp\", \"caption\": \"\", \"page\": 6, \"index\": 34, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-035.webp\", \"caption\": \"\", \"page\": 6, \"index\": 35, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-036.webp\", \"caption\": \"\", \"page\": 6, \"index\": 36, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-037.webp\", \"caption\": \"\", \"page\": 6, \"index\": 37, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-038.webp\", \"caption\": \"\", \"page\": 6, \"index\": 38, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-039.webp\", \"caption\": \"\", \"page\": 6, \"index\": 39, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-040.webp\", \"caption\": \"\", \"page\": 6, \"index\": 40, \"width\": 1280, \"height\": 846}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-041.webp\", \"caption\": \"\", \"page\": 6, \"index\": 41, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-042.webp\", \"caption\": \"\", \"page\": 6, \"index\": 42, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-043.webp\", \"caption\": \"\", \"page\": 6, \"index\": 43, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-044.webp\", \"caption\": \"\", \"page\": 6, \"index\": 44, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-045.webp\", \"caption\": \"\", \"page\": 6, \"index\": 45, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-046.webp\", \"caption\": \"\", \"page\": 6, \"index\": 46, \"width\": 360, \"height\": 640}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-047.webp\", \"caption\": \"\", \"page\": 8, \"index\": 47, \"width\": 775, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-048.webp\", \"caption\": \"\", \"page\": 8, \"index\": 48, \"width\": 775, \"height\": 514}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-049.webp\", \"caption\": \"\", \"page\": 9, \"index\": 49, \"width\": 531, \"height\": 544}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-050.webp\", \"caption\": \"\", \"page\": 9, \"index\": 50, \"width\": 595, \"height\": 532}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-051.webp\", \"caption\": \"\", \"page\": 9, \"index\": 51, \"width\": 615, \"height\": 513}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-052.webp\", \"caption\": \"\", \"page\": 9, \"index\": 52, \"width\": 546, \"height\": 523}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-053.webp\", \"caption\": \"\", \"page\": 9, \"index\": 53, \"width\": 988, \"height\": 766}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-054.webp\", \"caption\": \"\", \"page\": 9, \"index\": 54, \"width\": 866, \"height\": 665}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-055.webp\", \"caption\": \"\", \"page\": 9, \"index\": 55, \"width\": 775, \"height\": 724}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-056.webp\", \"caption\": \"\", \"page\": 9, \"index\": 56, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-057.webp\", \"caption\": \"\", \"page\": 9, \"index\": 57, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-058.webp\", \"caption\": \"\", \"page\": 9, \"index\": 58, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-059.webp\", \"caption\": \"\", \"page\": 9, \"index\": 59, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-060.webp\", \"caption\": \"\", \"page\": 9, \"index\": 60, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-061.webp\", \"caption\": \"\", \"page\": 9, \"index\": 61, \"width\": 558, \"height\": 587}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-062.webp\", \"caption\": \"\", \"page\": 9, \"index\": 62, \"width\": 506, \"height\": 497}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-063.webp\", \"caption\": \"\", \"page\": 9, \"index\": 63, \"width\": 1033, \"height\": 821}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-064.webp\", \"caption\": \"\", \"page\": 9, \"index\": 64, \"width\": 872, \"height\": 748}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-065.webp\", \"caption\": \"\", \"page\": 24, \"index\": 65, \"width\": 775, \"height\": 515}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-066.webp\", \"caption\": \"\", \"page\": 24, \"index\": 66, \"width\": 775, \"height\": 409}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-067.webp\", \"caption\": \"\", \"page\": 24, \"index\": 67, \"width\": 775, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-068.webp\", \"caption\": \"\", \"page\": 25, \"index\": 68, \"width\": 775, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-069.webp\", \"caption\": \"\", \"page\": 25, \"index\": 69, \"width\": 775, \"height\": 517}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-070.webp\", \"caption\": \"\", \"page\": 25, \"index\": 70, \"width\": 775, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-071.webp\", \"caption\": \"\", \"page\": 25, \"index\": 71, \"width\": 770, \"height\": 770}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-072.webp\", \"caption\": \"\", \"page\": 25, \"index\": 72, \"width\": 775, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-073.webp\", \"caption\": \"\", \"page\": 25, \"index\": 73, \"width\": 775, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-074.webp\", \"caption\": \"\", \"page\": 26, \"index\": 74, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-075.webp\", \"caption\": \"\", \"page\": 26, \"index\": 75, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-076.webp\", \"caption\": \"\", \"page\": 26, \"index\": 76, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-077.webp\", \"caption\": \"\", \"page\": 26, \"index\": 77, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-078.webp\", \"caption\": \"\", \"page\": 26, \"index\": 78, \"width\": 775, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-p4jktpccuh/fig-079.webp\", \"caption\": \"\", \"page\": 26, \"index\": 79, \"width\": 775, \"height\": 435}]"
motivation: 现有模型难以同时进行视频目标分割与细粒度语义描述，缺乏统一框架。
method: 集成SAM 2和LLM，通过语义感知器将视觉特征转化为多模态令牌，实现联合理解。
result: 在多种粒度视觉理解任务上取得领先性能，兼顾分割与语义输出。
conclusion: PAM为视频区域级理解提供了高效通用模型，可赋能下游代理任务。
---

## Abstract
We present Perceive Anything Model (PAM), a conceptually straightforward and efficient framework for comprehensive region-level visual understanding in images and videos. Our approach extends the powerful segmentation model SAM 2 by integrating Large Language Models (LLMs), enabling simultaneous object segmentation with the generation of diverse, region-specific semantic outputs, including categories, label definition, functional explanations, and detailed captions. A key component, Semantic Perceiver, is introduced to efficiently transform SAM 2's rich visual features, which inherently carry general vision, localization, and semantic priors into multi-modal tokens for LLM comprehension. To support robust multi-granularity understanding, we also develop a dedicated data refinement and augmentation pipeline, yielding a high-quality dataset of 1.5M image and 0.6M video region-semantic annotations, including novel region-level streaming video caption data. PAM is designed for lightweightness and efficiency, while also demonstrates strong performance across a diverse range of region understanding tasks. It runs 1.2$-$2.4$\times$ faster and consumes less GPU memory than prior approaches, offering a practical solution for real-world applications. We believe that our effective approach will serve as a strong baseline for future research in region-level visual understanding.

---

## 论文详细总结（自动生成）

## 1. 核心问题与背景
视觉基础模型（如 SAM 2）在交互式分割上表现优异，但缺乏对区域的深层语义理解，无法解释区域“是什么”及“在场景中起什么作用”。现有区域级视觉语言模型（VLMs）大多存在三大局限：
- 仅输出类别或简短描述，语义粒度单一；
- 通常只针对图像或视频单一模态，缺乏通用性；
- 依赖外部分割模型，计算开销大、性能受制于掩码质量。

PAM 旨在以轻量高效的方式，在同一框架中实现 **目标的精准分割** 与 **多粒度语义输出（类别、定义、功能解释、详细字幕及流式视频描述）**，从而为真实应用提供一种统一的区域级感知解决方案。

## 2. 方法论
PAM 由 SAM 2（视觉编码、提示编码、记忆模块与掩码解码器）和一个基于 LLM 的语义解码器组成，核心创新点如下：

### 2.1 语义感知器（Semantic Perceiver）与视觉令牌生成
- 复制 SAM 2 的特征融合模块（S2‑FFM）结构，使用轻量两层 Transformer（自注意力、交叉注意力、MLP）。
- 输入：S2‑FFM 输出的增强掩码令牌（含 IoU、提示信息）和更新后的图像嵌入。
- 引入 16 个可学习的语义令牌（semantic tokens），与掩码令牌拼接后通过感知器交互。
- 输出：64×2 个视觉令牌（单帧图像）和 Ns×N 个语义令牌，再经过投影层送入 LLM。

### 2.2 投影器与语义解码器
- 视觉令牌经像素混洗（pixel shuffle）下采样：图像采用 2×2，视频非提示帧采用 4×4，以压缩令牌数量。
- 使用两个独立 MLP 分别投影视觉令牌与语义令牌，送入冻结或微调的 Qwen2.5‑1.5B/3B LLM，生成所需的多粒度文本。

### 2.3 并行掩码与语义输出
- 掩码解码器与语义解码器并行工作，同时输出分割掩码和语义内容，避免串行依赖，提高推理效率。

### 2.4 流式视频编解码
- 利用 SAM 2 的逐帧记忆机制，对每个视频片段的最后一帧额外施加 2×2 像素混洗，使其作为下一片段的起始帧，并携带历史视觉信息。
- 在提示中注入上一片段的文字描述，实现时序连续、实体一致的流式区域字幕。

### 2.5 训练策略
三阶段课程学习：
- **Stage 1**：图像预训练对齐（分类 + 字幕），训练语义感知器与投影器。
- **Stage 1.5**：引入视频区域字幕，继续训练感知器与投影器，使模型适应时空信息。
- **Stage 2**：多模态监督微调，联合训练语义感知器、投影器与 LLM，使用经过精细化增强的高质量数据集。

## 3. 实验设计
### 3.1 数据集与基准
- **区域识别与解释**：LVIS（目标级）、PACO（部件级）、COCO‑Text、Total‑Text。
- **区域字幕**：Visual Genome、RefCOCOg、Ref‑L4、Ferret‑Bench、MDVP‑Bench。
- **视频区域字幕**：Elysium、BensMOT、HC‑STVG、VideoRefer‑Bench‑D。
- **流式视频区域字幕**：ActivityNet 校验集的手工筛选子集（400 个视频，满足事件连续且主体一致），并为流式评估提出新指标 G‑STDC（GPT‑4o 评判的描述时空连续性，0‑5 分）。

### 3.2 对比方法
涵盖图像和视频区域理解的近期 SOTA：Shikra‑7B、GPT4RoI‑7B、Osprey‑7B、Ferret‑13B、VP‑LLAVA‑8B、VP‑SPHINX‑13B、DAM‑8B、GLaMM‑7B、Omni‑RGPT‑7B、RegionGPT‑7B、Elysium‑7B、Merlin‑7B、Artemis‑7B、VideoRefer‑7B、GIT、Vid2Seq、Streaming Vid2Seq 等。

## 4. 资源与算力
- **硬件**：8 张 NVIDIA A100 80GB GPU。
- **训练规模**：全局批次大小 Stage 1/1.5 为 1024，Stage 2 为 256；优化器 AdamW；学习率 1e‑4（Stage 1）→ 4e‑5（Stage 1.5）→ 1e‑5（Stage 2）；各阶段训练 1 个 epoch。
- **未明确说明**：单次训练的具体时长（小时/天）未在文中给出，但可推断大致的计算量适中。

## 5. 实验数量与充分性
共涉及：
- 4 个图像区域识别基准，7+ 个区域字幕基准；
- 4 个视频区域字幕基准，1 个流式视频字幕基准；
- 效率分析（推理时间、GPU 内存）；
- 3 组消融实验（语义令牌数量、训练阶段顺序、中间特征选择）。

实验覆盖图像、视频、流式三种模态，对比了当时多数主流模型，且采用零样本测试（未在目标数据集微调），说明评估相对公平。消融设计也验证了关键组件的作用，整体较为充分。

## 6. 主要结论与发现
- PAM 在 LVIS、PACO、大部分字幕基准（VG、RefCOCOg、Ferret‑Bench 等）以及 Elysium、BensMOT 视频字幕任务上达到或超过 SOTA，且参数量更小。
- 在流式视频区域字幕任务上，PAM‑3B 获得了最佳 G‑STDC 分数，展示了强时序连续性和实体一致性。
- PAM 推理速度比先前方法快 1.2‑2.4 倍，GPU 内存占用也更低，兼顾性能与效率。
- 数据增强流水线生成的多粒度、双语、流式注释是高表现的关键支撑。

## 7. 优点
- **统一框架**：分割与多粒度语义输出并行，端到端，不依赖外部分割器。
- **高效特征利用**：直接复用 SAM 2 的中间特征作为视觉编码，避免重复特征提取。
- **轻量扩展**：仅新增少量参数的语义感知器和投影器，训练主要冻结 SAM 2，计算成本低。
- **数据驱动创新**：首次构建区域级流式视频字幕数据集，并提出相应的评估指标 G‑STDC。
- **实用性**：支持中英双语输出，推理速度快，适合实际部署。

## 8. 不足与局限
- **任务范围受限**：目前仅支持预定义的四种区域理解任务，不支持通用 VQA 等多功能对话。
- **实时流式仍有瓶颈**：视觉令牌数量过多，阻碍真正的实时在线流式字幕。
- **长视频性能**：默认仅采样 16 帧，对长视频只能给出粗粒度描述，需借助流式分段描述弥补。
- **部分失败案例**：模型可能错误定位（如数错切片顺序）、误读文本（OCR 错误），或在目标物体太小时描述场景中最显著的物体。流式输出有时受历史描述影响而产生重复。
- **数据偏差风险**：训练数据由 GPT‑4o 等模型生成，可能偏好描述显著区域而非用户指定的细微区域，存在标注不准确的隐患。
- **实验对比局限**：在部分基准（如 VideoRefer‑Bench‑D）上性能稍逊于某些专用模型，说明仍有提升空间。

（完）
