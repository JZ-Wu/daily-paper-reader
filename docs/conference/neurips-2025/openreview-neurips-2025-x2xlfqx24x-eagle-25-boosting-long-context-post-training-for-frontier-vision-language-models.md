---
title: "Eagle 2.5: Boosting Long-Context Post-Training for Frontier Vision-Language Models"
title_zh: Eagle 2.5：提升前沿视觉语言模型的长上下文后训练
authors: "Guo Chen, Zhiqi Li, Shihao Wang, Jindong Jiang, Yicheng Liu, Lidong Lu, De-An Huang, Wonmin Byeon, Matthieu Le, Max Ehrlich, Tong Lu, Limin Wang, Bryan Catanzaro, Jan Kautz, Andrew Tao, Zhiding Yu, Guilin Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=X2xLfqX24x"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 长上下文视觉语言模型应用于视频理解并优化训练效率
tldr: 现有视觉语言模型处理长视频面临上下文长度和效率挑战。本文提出Eagle2.5，通过自动降采样和图像区域保留等技术优化长上下文训练，并构建Eagle-Video-110K数据集。模型在长视频理解任务上大幅超越先前方法，为长视频多模态学习提供了高效框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2xlfqx24x/fig-001.webp\", \"caption\": \"\", \"page\": 3, \"index\": 1, \"width\": 512, \"height\": 302}]"
motivation: 长视频理解中，长上下文训练存在效率瓶颈和细节丢失问题。
method: 引入自动降采样和图像区域保留等优化手段，构建长视频数据集。
result: 在多项长视频理解基准上显著提升，验证了训练策略的有效性。
conclusion: 为长视频多模态模型训练提供了高效管道，简化了长视频理解应用。
---

## Abstract
We introduce Eagle2.5, a frontier vision-language model (VLM) for long-context multimodal learning. Our work addresses the challenges in long video comprehension and high-resolution image understanding, introducing a generalist framework for both tasks. The proposed training framework incorporates Automatic Degrade Sampling and Image Area Preservation, two techniques that preserve contextual integrity and visual details. The framework also includes numerous efficiency optimizations in the pipeline for long-context data training. Finally, we propose Eagle-Video-110K, a novel dataset that integrates both story-level and clip-level annotations, facilitating long-video understanding. Eagle2.5 demonstrates substantial improvements on long-context multimodal benchmarks, providing a robust solution to the limitations of existing VLMs. Notably, our best model Eagle2.5-8B achieves 72.4\% on Video-MME with 512 input frames, matching the results of top-tier commercial model such as GPT-4o and large-scale open-source models like Qwen2.5-VL-72B and InternVL2.5-78B.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题背景**：现有视觉语言模型（VLM）多聚焦于短上下文任务，对长视频理解、高分辨率图像等多模态长序列处理仍面临严重性能瓶颈与训练低效问题。
- **核心挑战**：
  - 长上下文 VLM 在数据集构建、架构设计、训练策略和计算/存储开销等方面缺乏有效方案。
  - 已有扩展上下文的尝试（如专用压缩模块）往往引入额外开销或容量限制，且性能提升不一致，难以随输入帧数增加而稳定受益。
- **研究目标**：提出一种通用型长上下文多模态模型，通过优化训练策略与数据配方，使模型不仅能够处理任意长序列，更能随输入长度增加获得持续的性能增益，并在较小参数规模下匹敌大规模商用模型。

### 2. 论文提出的方法论
- **整体框架**：Eagle 2.5 基于 LLaVA 架构，使用 SigLIP 作为视觉编码器，MLP 投影层对齐至 Qwen2.5 系列大语言模型，采用图像分块策略处理任意分辨率图像。
- **信息优先采样策略**：
  - **图像区域保留（IAP）**：优化分块配置，通过最大化面积保留（≥60%）和长宽比对齐的双目标函数，避免传统方法过度下采样或形变，从而保留更多视觉细节。
  - **自动退化采样（ADS）**：一种全上下文为中心的动态令牌分配方案。优先保留完整文本，然后在剩余的视觉令牌预算内，通过两阶段优化（先调整时间采样率，再调整每图最大分块数）最大化视觉信息密度，避免文本截断或信息丢失。
- **渐进式混合后训练**：
  - 从混合长度训练出发，逐步扩展最大序列长度（Lmax: 32K → 64K → 128K），利用长度平衡打包，保证模型在各长度下性能均衡。
  - 渐进过程能够平滑学习难度，有效保留短序列能力，并逐步增强长上下文建模。
- **数据配方与 Eagle-Video-110K 数据集**：
  - **开放数据整合**：遵循“多样性优先，再质量”原则，收集大量人类标注及合成视频/文档数据（如表1所示）。
  - **多样性驱动的视频收集**：基于 CLIP 特征相似度筛选，从多个源中选取与已有数据高度不重复的新视频片段。
  - **双重标注体系**：
    - **自顶向下故事级**：利用人工标注的章节分段，生成章节级密集描述并合成覆盖整体叙事的长问答对。
    - **自底向上片段级**：对短片段用 GPT‑4o 生成多种类问答对，并通过“时间锚点”和“文本上下文锚点”将其转化为完整视频的问答，避免局部信息冲突。

### 3. 实验设计
- **视频基准**：MVBench、Perception_test、EgoSchema、MLVU、LVBench、Video‑MME、CG‑Bench、HourVideo、Charade‑STA 等多个长/短视频理解数据集。
- **图像基准**：DocVQA、ChartQA、InfoVQA、TextVQA、OCRBench、MMstar、RWQA、AI2D、MMMU、MMBench、MMVet、HallB、MathVista 等覆盖文档、图表、通用感知、推理、幻觉及数学能力的测试集。
- **对比方法**：封闭源模型（GPT‑4o, Claude‑3.5‑Sonnet, Gemini‑1.5/2.5‑Pro）和开源/公开模型（InternVL2.5‑8B/78B, Qwen2.5‑VL‑7B/72B, LLaVA‑Video‑7B/72B, MiniCPM‑V2.6 等）。
- **实验设置**：默认采样 2 FPS，关闭分块，最小 8 帧，Video‑MME 最大 512 帧；部分高分辨率测试（如 Perception_test）开启分块。

### 4. 资源与算力
- **算力需求**：训练使用了 **128 块 H100 GPU** 集群。
- **说明**：论文在局限性部分指出高计算资源需求可能限制可复现性，但未提供训练时长或单次实验 GPU 小时等细节。

### 5. 实验数量与充分性
- **主实验**：视频基准（表2）与图像基准（表3）全面对比，覆盖十余项评测，与多个同量级及更大规模模型比较。
- **消融实验**：
  - 长上下文数据对图像基准的影响（表4，不同 Lmax 阶段）。
  - 图像预训练对视频基准的影响（表5，有无 Image 数据）。
  - 信息优先采样（IAP 和 ADS）的单独移除效果（表6）。
  - 渐进训练 vs. 直接长上下文训练、Eagle‑Video‑110K 数据集的影响（表7，图6）。
- **充分性**：消融设计清晰，覆盖训练策略、数据组成和关键模块，验证了各组件的独立贡献；对比公平，均使用统一的评测协议；实验数量充足，支撑主要结论。

### 6. 论文的主要结论与发现
- Eagle 2.5‑8B 在多项长视频理解基准上显著超越同规模模型，并在 Video‑MME（512 帧）上达到 72.4%，**匹配 GPT‑4o、Qwen2.5‑VL‑72B 等超大模型**。
- **信息优先采样（IAP+ADS）+ 渐进训练** 使得模型能够随着输入帧数增加而稳定提升性能（图1），而非仅“容纳更长输入”。
- 新数据集 Eagle‑Video‑110K 通过双重标注有效增强了对超长视频的故事级理解和细粒度时空定位能力。
- 长上下文数据训练未损害短上下文图像性能，甚至略有收益。

### 7. 优点
- **训练策略创新**：IAP 保留高分辨率图像细节，ADS 以文本完整为前提动态优化视觉令牌，渐进式训练实现“易到难”的平滑扩展，策略简洁且实用。
- **数据工程完善**：多样性驱动的视频收集与双重标注体系（故事级+片段级锚点转换）为长视频理解提供了高质量、多粒度的训练信号。
- **性能与效率平衡**：8B 参数模型达到 72B 级别效果，体现了优秀的长上下文扩展效率。
- **实验全面**：多基准、多模型对比，消融实验设计严谨，分析深入，有效验证各设计选择。

### 8. 不足与局限
- **计算资源门槛高**：需要 128 块 H100 GPU，普通学术环境难以复现。
- **代码与数据未开源**（截至论文提交），限制了直接复现和进一步研究。
- **统计稳健性不足**：未报告误差棒、置信区间等，缺少多次运行的变异性分析。
- **社会影响讨论缺失**：未涉及模型偏见、安全性和滥用风险的分析。
- **领域覆盖**：主要聚焦于自然视频和通用图文，尚未对医疗、遥感等垂直领域长上下文任务进行评估。

（完）
