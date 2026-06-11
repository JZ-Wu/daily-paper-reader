---
title: Training-free Online Video Step Grounding
title_zh: 无需训练的在线视频步骤定位
authors: "Luca Zanella, Massimiliano Mancini, Yiming Wang, Alessio Tonioni, Elisa Ricci"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=got7rMaVin"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: 使用零样本大模型的无需训练在线视频步骤定位
tldr: 现有视频步骤定位依赖标注数据和离线处理，成本高且不适用于在线决策。本文利用大语言模型的零样本能力实现在线视频步骤定位，无需训练。实验表明，该在线零样本策略在多个基准上超越了离线有监督方法，为低成本、实时的视频理解提供了新途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-001.webp\", \"caption\": \"\", \"page\": 5, \"index\": 1, \"width\": 1344, \"height\": 1088}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-002.webp\", \"caption\": \"\", \"page\": 5, \"index\": 2, \"width\": 1280, \"height\": 720}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-003.webp\", \"caption\": \"\", \"page\": 27, \"index\": 3, \"width\": 1563, \"height\": 309}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-004.webp\", \"caption\": \"\", \"page\": 27, \"index\": 4, \"width\": 1550, \"height\": 362}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-005.webp\", \"caption\": \"\", \"page\": 27, \"index\": 5, \"width\": 1550, \"height\": 362}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-006.webp\", \"caption\": \"\", \"page\": 27, \"index\": 6, \"width\": 1550, \"height\": 362}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-007.webp\", \"caption\": \"\", \"page\": 27, \"index\": 7, \"width\": 1563, \"height\": 309}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-got7rmavin/fig-008.webp\", \"caption\": \"\", \"page\": 27, \"index\": 8, \"width\": 1555, \"height\": 307}]"
motivation: 视频步骤定位依赖昂贵标注和离线批处理，限制实时应用。
method: 利用大语言模型零样本推理，在线预测局部帧对应的步骤。
result: 零样本在线定位性能超过训练依赖的离线方法，实现高效实时定位。
conclusion: 为无需训练的实时视频理解与决策提供可行方案，降低应用门槛。
---

## Abstract
Given a task and a set of steps composing it, Video Step Grounding (VSG) aims to detect which steps are performed in a video. Standard approaches for this task require a labeled training set (e.g., with step-level annotations or narrations), which may be costly to collect. Moreover, they process the full video offline, limiting their applications for scenarios requiring online decisions. Thus, in this work, we explore how to perform VSG online and without training. We achieve this by exploiting the zero-shot capabilities of recent Large Multimodal Models (LMMs). In particular, we use LMMs to predict the step associated with a restricted set of frames, without access to the whole video. We show that this online strategy without task-specific tuning outperforms offline and training-based models. Motivated by this finding, we develop Bayesian Grounding with Large Multimodal Models (BaGLM), further injecting knowledge of past frames into the LMM-based predictions. BaGLM exploits Bayesian filtering principles, modeling step transitions via (i) a dependency matrix extracted through large language models and (ii) an estimation of step progress. Experiments on three datasets show superior performance of BaGLM over state-of-the-art training-based offline methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **问题**：视频步骤定位（Video Step Grounding, VSG）旨在根据给定任务步骤列表，检测视频中执行了哪些步骤。现有方法依赖标注训练集（步骤级标签或叙述），收集成本高昂，且需要离线处理完整视频，限制了在线实时决策场景的应用。
- **动机**：探索**无需训练**、**在线**完成 VSG 的可行性，利用大型多模态模型（LMM）的零样本能力，仅根据当前视频片段预测步骤，从而降低数据门槛并适应流式视频处理。
- **含义**：如果成功，将大幅降低 VSG 系统的部署成本，并推动实时程序指导（如 AR/XR 辅助）等实际应用发展。

### 2. 论文提出的方法论
- **核心思想**：将 VSG 视为在线序列决策问题，结合贝叶斯滤波（Bayesian filtering）与 LMM/LLM 的零样本推理。
- **技术框架（BaGLM）**：
  - **状态与观测**：状态为当前片段执行的步骤 \( a \)，观测为视频片段 \( S_t \)。
  - **预测步（Predict）**：
    - 使用 LLM（如 LLaMA3-70B）查询出步骤间的依赖矩阵 \( D \)，表示一个步骤是否为另一步骤的前置条件，以此初始化静态转移矩阵 \( T \)。
    - 用 LMM 估计每个步骤在片段的执行进度（0‑9 级别）。
    - 定义**就绪度（readiness）**和**有效度（validity）**，分别衡量前置步骤是否足够完成、后继步骤是否尚未完成，从而动态修正转移矩阵 \( \tilde{T}_t \)，避免无效的状态跳转。
    - 先验信念通过修正转移矩阵与上一时刻的后验递归计算。
  - **更新步（Update）**：
    - 利用 LMM 预测当前片段属于各步骤的概率（多选一问答，包含“none”选项），结合均匀先验，更新后验信念 \( bel_t \)。
  - **最终公式**：\( bel_t(a_i) = \frac{1}{Z} \cdot f_{\text{LMM}}(S_t, \pi_{\text{VSG}})[i] \cdot \sum_{a_j} \tilde{T}_t[j, i] \cdot bel_{t-1}(a_j) \)。
- **关键创新**：无需训练任何任务特定参数，完全依赖预训练的 LMM 和 LLM；通过贝叶斯框架将历史信息注入零样本预测。

### 3. 实验设计
- **数据集**：
  - HT-Step（120 项活动，每项 5 个视频，标准测试集部分不可用，使用验证集）
  - CrossTask（18 个主要任务、65 个相关任务）
  - Ego4D Goal-Step（851 个长视频，步骤来自层级标注）
- **评价指标**：Recall@1（HT-Step, Ego4D Goal-Step），Average Recall@1（CrossTask）；补充 mAP@IoU 评估定位精度。
- **对比方法**：
  - 离线训练方法：VINA, NaSVA, MPTVA, VSLNet, Zhukov et al., HT100M, VideoCLIP, MCN, DWSA, MIL-NCE, VT-TWINS, UniVL 等。
  - 在线变体：NaSVA 的因果遮掩版本。
  - 零样本 LMM 基线：InternVL2.5‑8B, InternVL3‑8B, LLaVA‑OV‑7B, Qwen2.5‑VL‑7B。
- **实验类型**：
  - 离线训练方法 vs. 在线无训练方法对比。
  - BaGLM 的成分消融（转移模型中的就绪度/有效度、LLM 选择、LMM 选择、片段时长）。
  - Oracle 实验（真实依赖矩阵与进度）。
  - 定位性能（mAP）评估。
  - 推广性测试（COIN 数据集）。
  - 鲁棒性分析（依赖矩阵违反率）。
  - 细粒度分析（按步骤时间位置、候选步骤数分组）。

### 4. 资源与算力
- **GPU**：
  - 单张 NVIDIA H100 64GB 用于 LMM 推理（如 InternVL2.5‑8B）。
  - 4 张 H100 用于 LLaMA3‑70B‑Instruct 生成依赖矩阵（每个任务仅执行一次）。
- **训练时长**：方法本身无需训练，仅推理。实验侧重推理速度，文中给出示例视频的逐段处理时间（约 2.1 秒/段，接近实时），依赖矩阵生成时间约 88 秒/任务。

### 5. 实验数量与充分性
- 实验覆盖 **3 个主流 VSG 数据集**，与 **超过 10 种现有方法**对比，包含多种领域（烹饪、维修、自我中心）和不同颗粒度（短/长视频）。
- **消融实验**详尽：转移模型的三个子模块（静态、就绪度、有效度）组合测试；不同 LLM（LLaMA vs GPT‑4.1）的影响；4 种 LMM 搭配不同片段时长（1‑4 秒）；先验分布的不同选择；多选 vs 二值提问。合计 **约 15 组以上对比**。
- 额外分析：Oracle 上限实验、依赖矩阵鲁棒性、按步骤位置/候选数分组、COIN 跨域测试、定位 mAP 评估。
- **评价标准公平**：沿用已有公开评测协议，与离线方法对比时维持一致输入（如提供完整步骤集），并特意实现在线版 NaSVA 作为竞争基线。
- 整体实验设计**充分且客观**，能够支撑论文核心声明。

### 6. 论文的主要结论与发现
- 零样本 LMM（如 InternVL2.5‑8B）本身在在线 VSG 上已可接近甚至超越部分离线训练方法。
- BaGLM 结合贝叶斯滤波和 LLM 提取的步骤依赖，在所有三个数据集上均**显著超越现有最先进的离线训练方法**（HT-Step：+4.3%；CrossTask：+13.1%；Ego4D Goal-Step：+19% 对比 VSLNet 等）。
- 动态调整的就绪度与有效度能进一步提升性能，尤其在 CrossTask 和 Ego4D 上。
- Oracle 实验表明，若依赖矩阵和进度估计更准确，性能可大幅提升（如 Ego4D 提升 38.9%），说明框架有效，但当前受限于进度估计和依赖质量。

### 7. 优点
- **场景创新**：首次定义并解决“在线+无训练”的 VSG，更贴近实际部署需求。
- **简单有效**：不用任何训练或微调，仅靠预训练模型配合贝叶斯规则，即获 SOTA。
- **理论结合实践**：将经典贝叶斯滤波显式适配到步骤依赖和进度感知的转换模型，设计清晰。
- **实验扎实**：多数据集、多对比、丰富消融和上限实验，提供了深刻的性能归因分析。
- **实时性可行**：推理速度接近 2 秒/段，具备实时应用潜力。

### 8. 不足与局限
- **依赖 LLM 质量**：步骤依赖矩阵完全由 LLM 生成，若 LLM 对任务知识不足，将影响后验，特别是对长尾或专业领域。
- **进度估计粗糙**：使用 LMM 的 0‑9 离散进度估计可能不够精细，Oracle 实验显示更好的进度能大幅提升性能。
- **先验简单**：使用了均匀状态先验，未来可引入更丰富的任务时长或顺序先验。
- **长视频挑战**：在 Ego4D 长视频、步骤标注粗粒度的场景下，BaGLM 提升有限，甚至基础 LMM 表现较差。
- **计算资源**：虽然无需训练，但推理仍需高端 GPU（H100）与多个模型服务，LLM 生成依赖矩阵需额外算力。
- **偏差风险**：继承自大规模预训练模型的偏见未在本文中被评估。

（完）
