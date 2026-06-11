---
title: "Time-R1: Post-Training Large Vision Language Model for Temporal Video Grounding"
title_zh: Time-R1：后训练大视觉语言模型进行时间视频定位
authors: "Ye Wang, Ziheng Wang, Boshen Xu, Yang Du, Kejun Lin, Zihan Xiao, Zihao Yue, Jianzhong Ju, Liang Zhang, Dingyi Yang, Xiangnan Fang, Zewen He, Zhenbo Luo, Wenxuan Wang, Junqi Lin, Jian Luan, Qin Jin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=gJ05Gm5VxQ"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 通过强化学习后训练大视觉语言模型进行时间视频定位
tldr: 现有大视觉语言模型在时间视频定位上经过微调后泛化能力依然有限。本文提出Time-R1，一种推理引导的强化学习后训练框架，设计可验证奖励来优化模型。实验显示该方法在多个TVG基准上泛化性能领先，证明了RL在视频定位任务中的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-001.webp\", \"caption\": \"\", \"page\": 6, \"index\": 1, \"width\": 946, \"height\": 393}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-002.webp\", \"caption\": \"\", \"page\": 6, \"index\": 2, \"width\": 937, \"height\": 394}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-003.webp\", \"caption\": \"\", \"page\": 6, \"index\": 3, \"width\": 936, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-004.webp\", \"caption\": \"\", \"page\": 6, \"index\": 4, \"width\": 939, \"height\": 400}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 2634, \"height\": 738}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-006.webp\", \"caption\": \"\", \"page\": 9, \"index\": 6, \"width\": 2250, \"height\": 1750}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-007.webp\", \"caption\": \"\", \"page\": 28, \"index\": 7, \"width\": 6400, \"height\": 4800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-008.webp\", \"caption\": \"\", \"page\": 28, \"index\": 8, \"width\": 6400, \"height\": 4800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-009.webp\", \"caption\": \"\", \"page\": 30, \"index\": 9, \"width\": 672, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-010.webp\", \"caption\": \"\", \"page\": 30, \"index\": 10, \"width\": 672, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-011.webp\", \"caption\": \"\", \"page\": 30, \"index\": 11, \"width\": 672, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-012.webp\", \"caption\": \"\", \"page\": 30, \"index\": 12, \"width\": 672, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-013.webp\", \"caption\": \"\", \"page\": 30, \"index\": 13, \"width\": 672, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-014.webp\", \"caption\": \"\", \"page\": 30, \"index\": 14, \"width\": 672, \"height\": 378}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-015.webp\", \"caption\": \"\", \"page\": 30, \"index\": 15, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-016.webp\", \"caption\": \"\", \"page\": 30, \"index\": 16, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-017.webp\", \"caption\": \"\", \"page\": 30, \"index\": 17, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-018.webp\", \"caption\": \"\", \"page\": 30, \"index\": 18, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-019.webp\", \"caption\": \"\", \"page\": 30, \"index\": 19, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-020.webp\", \"caption\": \"\", \"page\": 30, \"index\": 20, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-021.webp\", \"caption\": \"\", \"page\": 31, \"index\": 21, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-022.webp\", \"caption\": \"\", \"page\": 31, \"index\": 22, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-023.webp\", \"caption\": \"\", \"page\": 31, \"index\": 23, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-024.webp\", \"caption\": \"\", \"page\": 31, \"index\": 24, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-025.webp\", \"caption\": \"\", \"page\": 31, \"index\": 25, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-026.webp\", \"caption\": \"\", \"page\": 31, \"index\": 26, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-027.webp\", \"caption\": \"\", \"page\": 32, \"index\": 27, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-028.webp\", \"caption\": \"\", \"page\": 32, \"index\": 28, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-029.webp\", \"caption\": \"\", \"page\": 32, \"index\": 29, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-030.webp\", \"caption\": \"\", \"page\": 32, \"index\": 30, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-031.webp\", \"caption\": \"\", \"page\": 32, \"index\": 31, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-032.webp\", \"caption\": \"\", \"page\": 32, \"index\": 32, \"width\": 596, \"height\": 336}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-033.webp\", \"caption\": \"\", \"page\": 33, \"index\": 33, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-034.webp\", \"caption\": \"\", \"page\": 33, \"index\": 34, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-035.webp\", \"caption\": \"\", \"page\": 33, \"index\": 35, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-036.webp\", \"caption\": \"\", \"page\": 34, \"index\": 36, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-037.webp\", \"caption\": \"\", \"page\": 34, \"index\": 37, \"width\": 480, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gj05gm5vxq/fig-038.webp\", \"caption\": \"\", \"page\": 34, \"index\": 38, \"width\": 480, \"height\": 360}]"
motivation: 监督微调的大模型在时间视频定位任务上泛化性不足。
method: 提出推理引导的RL后训练框架Time-R1，设计可验证奖励。
result: 在多个数据集上取得最佳泛化性能，超越监督微调基线。
conclusion: 为视频定位提供了一种有效的RL后训练范式，增强模型推理泛化能力。
---

## Abstract
Temporal Video Grounding (TVG), the task of locating specific video segments based on language queries, is a core challenge in long-form video understanding. While recent Large Vision-Language Models (LVLMs) have shown early promise in tackling TVG through supervised fine-tuning (SFT), their ability to generalize remains limited. To address this, we propose a novel post-training framework that enhances the generalization capabilities of LVLMs via reinforcement learning (RL).
Specifically,  our contributions span three key directions:
(1) Time-R1: we introduce a reasoning-guided post-training framework via RL with verifiable reward to enhance capabilities of LVLMs on the TVG task. 
(2) TimeRFT: we explore post-training strategies on our curated RL-friendly dataset, which trains the model to progressively comprehend more difficult samples, leading to better generalization.
(3) TVGBench: we carefully construct a small but comprehensive and balanced benchmark suitable for LVLM evaluation, which is sourced from available public benchmarks.
Extensive experiments demonstrate that Time-R1 achieves state-of-the-art performance across multiple downstream datasets using significantly less training data than prior LVLM approaches, while improving its general video understanding capabilities. 
Project Page: https://xuboshen.github.io/Time-R1/.

---

## 论文详细总结（自动生成）

好的，以下是基于所提供论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **研究问题**：论文聚焦于**时间视频定位**任务，即根据自然语言查询，在长视频中定位出对应的视频片段。这是一个长视频理解领域的核心挑战。
*   **研究动机**：
    *   现有的**大视觉语言模型**虽然在预训练上投入巨大，但在TVG任务上通过**监督微调**后，其性能常不如传统的、参数更少的特征方法，**泛化能力有限**。
    *   作者将LVLMs性能不佳的原因归结为监督微调对“假阴性”样本（即预测合理但与标准答案不完全一致的样本）的**过度惩罚**，这导致了模型过拟合，牺牲了其泛化能力。
*   **整体含义**：本文旨在探索以**强化学习**替代监督微调，作为一种更有效的后训练范式，来解锁LVLMs在TVG任务上的潜力，实现更优的泛化性能和数据效率。

### 2. 论文提出的方法论

论文核心方法论包含三大贡献：一个强化学习框架、一个配套的训练策略和一个评估基准。

*   **Time-R1: 推理引导的强化学习后训练框架**
    *   **核心思想**：利用**具有可验证奖励的强化学习**，引导LVLM先生成思维链推理过程，再预测时间戳，从而直接优化任务特定指标。
    *   **奖励建模**：
        *   **时间感知的IoU奖励**：对标准IoU进行修正，加入了对起始和结束时间戳偏差的惩罚项 `(1 - |ts - t's| / t) * (1 - |te - t'e| / t)`，以此避免标准IoU在某些场景下高估预测质量，提供更精细的定位信号。
        *   **推理模板奖励**：一种二元格式奖励，鼓励模型输出结构化的思维链（`<think>...</think>`）和答案（`<answer>...</answer>`）。
        *   **总奖励**：以上两项之和，`r(o) = rtIoU(o) + rform(o)`。
    *   **优化算法**：采用**群组相对策略优化**进行训练，冻结视觉编码器，仅更新大语言模型的参数。

*   **TimeRFT: 时间感知的强化学习友好型微调策略**
    *   **RL友好型数据集构建**：
        *   从多个来源收集了**33.9万**条TVG数据。
        *   提出一种基于训练难度的数据筛选策略，使用基础模型预测的IoU作为难度分数，从围绕IoU 0.3的高斯分布中采样了**2500条**中等难度的样本，以平衡学习效率与稀疏奖励问题。
    *   **RFT训练策略**：
        *   **动态困难样本采样**：采用多轮训练策略，并在每轮训练后过滤掉IoU > 0.7的简单样本，让模型循环聚焦于更难样本。
        *   **冷启动微调**：先用少量带思维链格式（生成结构化视频描述+时间戳）的数据进行监督微调，以稳定早期强化学习训练过程中的推理格式，抑制幻觉，尤其对小型模型有效。

*   **TVGBench: 面向LVLM的综合评估基准**
    *   从五个公开基准中精心挑选并构建了一个包含**800条**样本的平衡测试集。
    *   平衡了视频时长、视频域、查询中心时间等分布，并人工定义了**11类**查询语义（涵盖人类、物体、环境），以支持细粒度的评估分析。

### 3. 实验设计

*   **数据集/场景**：
    *   **TVG任务**：在 **Charades-STA, ActivityNet-Captions** 和自建的 **TVGBench** 上进行评估。
    *   **通用视频理解任务**：在**短时视频问答**（MVBench, TempCompass）和**长时视频问答**（EgoSchema, VideoMME）基准上测试泛化能力。
*   **对比方法**：
    *   **传统VLP方法**：如2D-TAN, UniVTG, SnAG, EaTR等。
    *   **基于SFT的LVLM方法**：如VideoChat-Flash, TimeSuite, TRACE, VideoMind, VideoChat-TPO等。
    *   **闭源模型**：Gemini-2.5-Pro。
    *   **消融实验**中对比了**全量SFT**和**SFT-LoRA**。
*   **评估指标**：
    *   **TVG任务**：采用“R@n, IoU=m”协议（即预测片段与真值的IoU大于阈值m的前n个召回率），m ∈ {0.3, 0.5, 0.7}。同时也使用mIoU作为补充。
    *   **视频问答任务**：准确率。

### 4. 资源与算力

*   论文中**未明确说明**训练所用的具体GPU型号、数量及总训练时长。
*   文中仅提及为了平衡训练效率和内存消耗，以2 FPS采样视频帧，并将每帧分辨率调整至约96x96，视频总像素数约280万。强化学习训练阶段使用了批次大小为8，训练5个轮次。

### 5. 实验数量与充分性

*   **实验数量充足且系统**：论文设计了多组实验来全面验证所提方法的有效性。
    *   **主要结果**：在3个TVG基准（其中1个是自建）上进行了零样本和微调后的性能对比，涉及十余个基线模型。
    *   **泛化能力**：在4个短时/长时视频问答基准上对比了Base、SFT、SFT-LoRA和RL方法。
    *   **消融实验**：
        *   对**TimeRFT数据筛选和训练策略**的不同组合（tIoU、高斯过滤、多轮训练、样本过滤）进行了详尽的消融研究。
        *   对**奖励函数设计**的多个变体（仅格式、仅IoU、中心对齐、绝对误差、RMSE）进行了比较。
        *   分析了**冷启动策略**对3B和7B模型的影响。
        *   验证了框架在**不同基座模型**（Qwen-2.5-VL, MiMo-VL, InternVL3）和不同参数量上的通用性。
        *   对比了RL与全量/ LoRA监督微调在同等数据量下的表现。
    *   **对比公平性**：通过在多个公开基准和自建的平衡基准上进行评估，与广泛的现有方法对比，并进行了多维度消融，实验设计客观、公平。

### 6. 论文的主要结论与发现

*   Time-R1在TVG任务上实现了**最优性能**，在零样本和微调设置下均超越了基于SFT的LVLM方法和许多传统VLP方法。
*   RL后训练范式**数据效率极高**，仅用2.5K样本训练的Time-R1就超越了使用33.9万样本进行SFT-LoRA的模型。
*   与SFT相比，**RL能更好地保持甚至提升模型的泛化能力**。SFT（尤其是全量微调）会严重损害通用视频问答性能，而RL则能带来提升。
*   提出的**tIoU奖励函数**比标准IoU和其他距离度量指标更有效，能够提供更稳定和精细的训练信号。
*   Time-R1框架具有**通用性**，能够有效提升不同架构和参数量的多种LVLM的TVG性能。

### 7. 优点

*   **范式创新**：首次将具有可验证奖励的强化学习成功应用于长视频时间定位任务，为解决视觉定位问题提供了超越监督微调的新范式。
*   **数据效率显著**：使用极少数据即可实现超越大量数据监督训练的SOTA性能，证明了RL在LVLM对齐上的巨大潜力。
*   **方法论扎实**：对奖励函数设计（tIoU）和训练策略（TimeRFT）的探讨细致深入，逻辑清晰，并通过详尽的消融实验进行了验证。
*   **评估全面**：不仅评估了核心任务性能，还考察了通用视频理解能力的保持和提升，并建立了平衡性更好的新基准TVGBench，使评估更客观、多维。
*   **框架通用性强**：证明了该方法对多种主流LVLM架构均有效，具有广泛的适用性。

### 8. 不足与局限

*   **计算效率问题**：论文坦诚RL训练和推理速度较慢，因其依赖于大模型的自回归生成过程。
*   **视频处理限制**：
    *   为控制显存使用了较低的帧率（2 FPS），可能丢失精细的动作信息。
    *   当前框架**无法处理超长视频**（如整部电影），应用场景受限。
*   **实验细节缺失**：文中未提供训练所消耗的**具体算力资源**（如GPU型号、数量、训练时长），使得无法准确评估其计算成本与可复现性。
*   **基准规模**：自建基准TVGBench旨在“轻量但全面”，800样本虽具代表性，但其规模可能仍无法覆盖长尾分布的复杂场景。
*   **语义分类主观性**：TVGBench的查询语义类别由人工定义并用LLM标注，可能存在主观性和错误，带来微小偏差。

（完）
