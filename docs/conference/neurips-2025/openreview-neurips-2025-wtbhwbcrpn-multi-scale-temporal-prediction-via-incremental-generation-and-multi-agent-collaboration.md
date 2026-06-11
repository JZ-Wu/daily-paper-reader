---
title: Multi-scale Temporal Prediction via Incremental Generation and Multi-agent Collaboration
title_zh: 通过增量生成和多智能体协作的多尺度时序预测
authors: "Zhitao Zeng, Guojian Yuan, Junyuan Mao, Yuxuan Wang, Xiaoshuang Jia, Yueming Jin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=wTBhWbCRpN"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 使用多智能体协作进行通用和手术场景的视频推理，直接匹配需求6。
tldr: 视觉语言模型难以预测多时间尺度和多状态等级的复杂场景未来。本文形式化多尺度时序预测任务，覆盖通用和手术场景，提出多智能体协作的增量生成框架。通过多代理分工预测不同时间跨度和状态粒度的场景演变。实验表明，模型能准确预测人类动作和手术进程的细粒度状态，为具身智能和手术辅助提供了重要技术基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 2049, \"height\": 1007}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 3784, \"height\": 1790}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-003.webp\", \"caption\": \"\", \"page\": 9, \"index\": 3, \"width\": 270, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-004.webp\", \"caption\": \"\", \"page\": 9, \"index\": 4, \"width\": 360, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-005.webp\", \"caption\": \"\", \"page\": 9, \"index\": 5, \"width\": 360, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-006.webp\", \"caption\": \"\", \"page\": 9, \"index\": 6, \"width\": 1280, \"height\": 800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-007.webp\", \"caption\": \"\", \"page\": 9, \"index\": 7, \"width\": 1280, \"height\": 800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-008.webp\", \"caption\": \"\", \"page\": 9, \"index\": 8, \"width\": 270, \"height\": 480}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-009.webp\", \"caption\": \"\", \"page\": 16, \"index\": 9, \"width\": 5207, \"height\": 2809}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wtbhwbcrpn/fig-010.webp\", \"caption\": \"\", \"page\": 18, \"index\": 10, \"width\": 3061, \"height\": 677}]"
motivation: VLM难以预测多时间尺度和多状态粒度的复杂未来场景。
method: 形式化MSTP任务，设计多智能体协作配合增量生成策略进行分层预测。
result: 在通用和手术数据集上展示出细粒度多尺度预测的准确性和鲁棒性。
conclusion: 多智能体协作可有效分解复杂时间预测，推动视频理解向具身决策延伸。
---

## Abstract
Accurate temporal prediction is the bridge between comprehensive scene understanding and embodied artificial intelligence. However, predicting multiple fine-grained states of scene at multiple temporal scales is difficult for vision-language models.
We formalize the Multi‐Scale Temporal Prediction (MSTP) task in general and surgical scene by decomposing multi‐scale into two orthogonal dimensions: the temporal scale, forecasting states of human and surgery at varying look‐ahead intervals, and the state scale, modeling a hierarchy of states in general and surgical scene. For instance in general scene, states of contacting relationship are finer-grained than states of spatial relationship. For instance in surgical scene, medium‐level steps are finer‐grained than high‐level phases yet remain constrained by their encompassing phase. 
To support this unified task, we introduce the first MSTP Benchmark, featuring synchronized annotations across multiple state scales and temporal scales. We further propose a novel method, Incremental Generation and Multi‐agent Collaboration (IG-MC), which integrates two key innovations. Firstly, we propose an plug-and-play incremental generation to keep high-quality temporal prediction that continuously synthesizes up-to-date visual previews at expanding temporal scales to inform multiple decision-making agents, ensuring decision content and generated visuals remain synchronized and preventing performance degradation as look‐ahead intervals lengthen.
Secondly, we propose a decision‐driven multi‐agent collaboration framework for multiple states prediction, comprising generation, initiation, and multi‐state assessment agents that dynamically triggers and evaluates prediction cycles to balance global coherence and local fidelity. Extensive experiments on the MSTP Benchmark in general and surgical scene show that IG‐MC is a generalizable plug-and-play method for MSTP, demonstrating the effectiveness of incremental generation and the stability of decision‐driven multi‐agent collaboration.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

本文聚焦于**多尺度时序预测（Multi-scale Temporal Prediction, MSTP）**这一关键问题，旨在连接全面的场景理解与具身人工智能（如手术辅助机器人、智能家居代理）。现有视觉-语言模型（VLMs）在处理动态场景时存在两大核心挑战：
- **预测粒度单一**：主流方法多关注粗粒度的阶段识别或固定时间窗口，忽视了场景中“阶段→步骤→细粒度动作”的层级化结构。
- **长时预测退化**：随着预测时间跨度增加，模型的错误会累积，且输入帧增多导致计算资源膨胀，性能明显下降。

为此，论文将多尺度分解为**时间尺度**（预测不同未来时间点的状态）和**状态尺度**（从粗到细的状态层级），并首次形式化定义了通用的 MSTP 任务，覆盖通用人类动作场景与外科手术场景，意在构建一个能同时保证短期动作准确性与长期任务一致性的可信预测框架。

### 2. 论文提出的方法论：核心思想、关键技术细节与流程

论文提出了一个统一的闭环框架 **IG-MC（Incremental Generation via Multi-agent Collaboration）**，包含两大创新模块：

**（1）增量生成机制（Incremental Generation）**
- **交替预测闭环**：框架交替执行状态预测（决策模块 DM）和视觉预览生成（视觉生成模块 VG）。在每一时间步 \(t_k\)，DM 根据当前状态 \(S_k\) 和图像 \(I_k\) 预测下一状态 \(S_{k+1}\)，随后 VG 基于 \(S_{k+1}\) 和 \(I_k\) 合成下一帧视觉预览 \(I_{k+1}\)。
- **去缓冲设计**：DM 和 VG 均为无状态（stateless）设计，仅消耗当前“状态-图像”对，避免了长历史帧的累积，降低了内存消耗并提升训练/推理效率。
- **误差修正**：状态预测与视觉合成双向互馈，视觉证据约束状态推理，生成的图像准确反映预期的进度，有效抑制了长时预测中的误差累积。

**（2）决策驱动的多智能体协作框架**
- **分层代理架构**：由 **状态转换控制器（STC）** 和一系列层级化的 **状态预测代理（\(v_1, ..., v_L\)）** 组成。STC 判断当前时间步是否需要进行状态跃迁，并定位应从哪个层级 \(l\) 开始变化。
- **逐级细化流程**：当需要转换时，从第 \(l\) 级代理开始，逐级向下传递预测结果。粗粒度代理的输出作为条件，约束细粒度代理的预测，形成一条链式推理路径（例如，先预测手术阶段，再预测具体步骤），强制实现跨尺度一致性。
- **类别平衡训练**：针对手术流程中状态变化极其稀疏的类别不平衡问题，采用围绕真实转换点的时间窗口采样和数据增强，将正负样本比例调整至1:1进行监督微调。
- **视觉生成模块（VG）**：基于修改的 Stable Diffusion 架构，通过状态嵌入、前一帧图像残差连接和解剖合理性正则化三重条件，生成符合手术流程的高保真预览。

### 3. 实验设计：数据集、Benchmark 与对比方法

**（1）MSTP Benchmark**  
论文首次构建了具有同步多层标注的 MSTP 数据集，包含两个子集：
- **MSTP-General**：基于 Action Genome (AG) 数据集构建，包含注意力、空间、接触三个状态尺度，时间尺度从1s到60s。
- **MSTP-Surgery**：基于手术场景理解数据集 GraSP（前列腺切除术）构建，包含阶段（Phase）与步骤（Step）两个状态尺度，时间尺度为1s、5s、30s、60s。

**（2）对比基线**  
以多种主流视觉语言模型为基座，评估即插即用模块的效果，包括：
- **通用 VLM**：Qwen2.5-VL-7B-Instruct、LLaVA1.5-7B、Gemma3-27B、InternVL3-8B。
- **手术专用 VLM**：SurgVLM-7B。
- 对比配置包括：纯基座模型、基座模型+DM、基座模型+DM+VG，在不同时间尺度和增量尺度下进行全面测试。

**（3）评估指标**
- **状态预测**：准确率、精确率、召回率、F1 分数、Jaccard 指数。
- **视觉预测**：像素保真度（PSNR）、结构一致性（SSIM/MS-SSIM）、感知相似度（LPIPS/CLIPScore）、分布对齐度（FID/KID）和检索一致性（R-Precision）。

### 4. 资源与算力

- **训练算力**：
  - 生成代理（VG）：基于 Stable Diffusion 3.5 Large，使用 **4 张 NVIDIA H100 GPU**，混合精度（bf16）训练 1 个 epoch，每卡批大小 34。
  - 决策代理（DM）：基于 Qwen2.5-VL-7B，使用 **4 张 NVIDIA H100 GPU**，每卡批大小 32，学习率 \(2\times10^{-5}\)。
- **推理算力**：
  - 推理延迟与计算效率分析在 **单张 NVIDIA H200 GPU** 上进行。
  - 端到端推理时间约 **68秒**，其中三个决策代理各约20-22秒（共占90%以上时间），增量生成约5.81秒。作者明确指出目前吞吐量未达实时，并规划了量化、权重共享等优化路径。

### 5. 实验数量与充分性

实验设计**非常充分且系统化**，围绕四个明确的研究问题（RQ1-RQ4）展开，从多维度验证了方法的有效性和鲁棒性：
- **主实验**：Table 1 和附录表格展示了在不同基准、不同基座模型、不同时间尺度与增量尺度组合下的性能对比，图表丰富。
- **消融实验**：独立分析了 DM 模块和 VG 模块各自的贡献，以及两者结合的增量收益；还探究了 VG 模块用于非层级化持续预测的情况。
- **定性分析**：可视化展示了预测帧与真实帧的对比（Figure 4），并对失败案例进行了深度剖析（Figure 6），解释了视觉预测误差对状态预测的影响。
- **压力测试**：对多智能体协作系统进行了累积误差分析（Table 8），证明系统鲁棒性远超各组件独立工作的乘积界；分析了决策精度与生成图像质量（FID）随时间跨度的变化关系（Table 7）。
- 整体实验设计对比基准公正，包含通用和垂直领域模型，指标全面，结论客观。

### 6. 论文的主要结论与发现

- **IG-MC 框架显著且稳定地提升了多尺度时序预测性能**。在手术基准上，仅添加 DM 模块就能使准确率从13%左右跃升至50%以上；在通用场景中，联合注意、空间、接触状态的 F1 分数有数倍提升。
- **增量生成机制有效遏制了长时预测的性能衰减**。在预测时长从5s扩展到60s时，决策准确率仅微降约2.7个百分点，而生成图像质量虽有所下降，但决策模块仍保持较高鲁棒性。
- **多智能体协作框架展现出强大的层级推理能力**。STC 代理的开关机制和共享视觉上下文使得系统在面临单代理错误时，能通过上下游协作修正，避免灾难性错误累积。
- **方法具有良好的通用性**。作为即插即用模块，IG-MC 可无缝应用于 Qwen、LLaVA、Gemma 等多种开源 VLM 上并带来显著增益，适用于通用人类行为预测和精细的手术流程分析。

### 7. 优点：方法或实验设计上的亮点

- **问题定义清晰，贡献明确**：首次形式化 MSTP 任务，将其分解为时间尺度和状态尺度两个正交维度，并构建了统一、跨领域的首个同步标注基准。
- **创新的闭环机制**：“DM-VG”交替预测的设计，将高层语义决策与底层视觉生成紧密结合，实现了双向信息校正，设计巧妙且有效。
- **层次化多智能体设计合理**：模仿实际场景中“先判断再决策”的流程，通过 STC 启停和逐级代理预测，自然地处理了状态跃迁的稀疏性和层级约束。
- **实验扎实且可复现**：覆盖多种基座模型、多组时间/状态尺度组合、定量消融与定性分析，并公开了代码和基准，可复现性强。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实时性瓶颈**：目前单步推理耗时约68秒，远未达到实时交互要求，限制了其在手术室等即时响应场景的应用。
- **生成模块的稳定性风险**：视觉生成依赖于 Stable Diffusion，在面对罕见解剖结构或极端工具形态时，可能生成视觉逼真但语义错误的图像，进而误导决策链。
- **依赖基座模型能力**：框架表现的上限受限于所搭载的预训练 VLM 的理解能力，例如在低分辨率图像中，对精细的工具-组织交互建模能力存在天花板。
- **临床验证缺失**：目前仅在公开手术视频数据集上进行回测，未涉及前瞻性临床验证，其在实际临床工作流中的辅助价值仍需进一步评估。
- **计算资源消耗大**：训练和推理均需高端 GPU（H100/H200），部署成本较高。

（完）
