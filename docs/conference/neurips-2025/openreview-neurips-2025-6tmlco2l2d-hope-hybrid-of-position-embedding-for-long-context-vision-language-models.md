---
title: "HoPE: Hybrid of Position Embedding for Long Context Vision-Language Models"
title_zh: HoPE：面向长上下文视觉语言模型的混合位置嵌入
authors: "Haoran Li, Yingjie Qin, Baoyuan Ou, Lai Xu, Ruiwen Xu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6TmLco2L2D"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 混合位置嵌入增强长上下文VLM
tldr: 针对长视频中视觉语言模型位置编码无法有效捕获时空依赖的问题，经理论分析后提出HoPE混合频率分配策略，提升模型的长上下文理解能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-001.webp\", \"caption\": \"\", \"page\": 9, \"index\": 1, \"width\": 1411, \"height\": 799}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-002.webp\", \"caption\": \"\", \"page\": 9, \"index\": 2, \"width\": 1412, \"height\": 799}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-003.webp\", \"caption\": \"\", \"page\": 9, \"index\": 3, \"width\": 1427, \"height\": 800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-004.webp\", \"caption\": \"\", \"page\": 9, \"index\": 4, \"width\": 1750, \"height\": 800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-005.webp\", \"caption\": \"\", \"page\": 9, \"index\": 5, \"width\": 1420, \"height\": 800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-006.webp\", \"caption\": \"\", \"page\": 25, \"index\": 6, \"width\": 1200, \"height\": 669}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-007.webp\", \"caption\": \"\", \"page\": 25, \"index\": 7, \"width\": 1200, \"height\": 671}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-008.webp\", \"caption\": \"\", \"page\": 25, \"index\": 8, \"width\": 800, \"height\": 800}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-009.webp\", \"caption\": \"\", \"page\": 25, \"index\": 9, \"width\": 1200, \"height\": 670}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6tmlco2l2d/fig-010.webp\", \"caption\": \"\", \"page\": 25, \"index\": 10, \"width\": 1200, \"height\": 671}]"
motivation: 现有VLMs在长视频中因RoPE分配策略启发式且缺乏理论而性能退化。
method: 提出HoPE，一种混合频率分配策略优化旋转位置嵌入以编码3D时空信息。
result: 理论分析和实验表明该策略优于现有启发式方法。
conclusion: 理论指导的位置嵌入设计可显著提升长视频VLMs。
---

## Abstract
Vision-Language Models (VLMs) have made significant progress in multimodal tasks. However, their performance often deteriorates in long-context scenarios, particularly long videos. While Rotary Position Embedding (RoPE) has been widely adopted for length generalization in Large Language Models (LLMs), extending vanilla RoPE to capture the intricate spatial-temporal dependencies in videos remains an unsolved challenge. Existing methods typically allocate different frequencies within RoPE to encode 3D positional information. However, these allocation strategies mainly rely on heuristics, lacking in-depth theoretical analysis. In this paper, we first study how different allocation strategies impact the long-context capabilities of VLMs. Our analysis reveals that current multimodal RoPEs fail to reliably capture semantic similarities over extended contexts. To address this issue, we propose HoPE, a Hybrid of Position Embedding designed to improve the long-context capabilities of VLMs. HoPE introduces a hybrid frequency allocation strategy for reliable semantic modeling over arbitrarily long contexts, and a dynamic temporal scaling mechanism to facilitate robust learning and flexible inference across diverse context lengths. Extensive experiments across four video benchmarks on long video understanding and retrieval tasks demonstrate that HoPE consistently outperforms existing methods, confirming its effectiveness.

---

## 论文详细总结（自动生成）

# 论文总结：HoPE — 面向长上下文视觉语言模型的混合位置嵌入

## 1. 核心问题与研究动机
- 视觉语言模型（VLM）在长上下文场景（特别是长视频理解与检索）中存在严重的性能退化问题。
- 旋转位置嵌入（RoPE）在纯文本大语言模型中已成功实现长度泛化，但直接将其扩展至多模态视频输入，以编码复杂的三维时空依赖关系，仍是一个未解决的挑战。
- 现有的多模态 RoPE 方法（如 M‑RoPE、VideoRoPE）主要通过启发式策略将不同频率分配给时间、水平空间和垂直空间分量，**缺乏深入的机理分析**，导致在超长上下文中无法可靠地保持语义相似性偏好。

## 2. 方法论：HoPE 的核心思想与技术细节
HoPE 由两大组件构成：

### 2.1 混合频率分配策略（Hybrid Frequency Allocation, HFA）
- **思想**：
  - 将**较高频率**分配给空间分量（x, y，采用交织方式避免偏倚），以更好捕获局部语义。
  - 将**最低的若干频率直接置零**（等同 NoPE 的性质）并分配给时间分量（t），以获得最强的长程语义偏好保障。
- **理论支撑**：
  - 先形式化定义“语义偏好”（Semantic Preference）：语义相似的 token，其注意力得分应始终高于无关 token，且该性质应与相对距离无关。
  - 证明现有频率分配策略在上下文超过临界长度时必然违反语义偏好（定理 3.1）。
  - 证明将时间维度的频率设为零最大化了语义偏好的保障（引理 4.1、定理 4.1），形成上界。

### 2.2 动态时间缩放机制（Dynamic Temporal Scaling, DTS）
- **动机**：视觉 token 与文本 token 的信息密度不同，且真实视频的速度差异很大，固定且单向的缩放因子不够灵活。
- **实现**：
  - 预定义一组缩放因子 \(\Gamma = \{0.5, 0.75, 1, 1.25, 1.5\}\)，涵盖压缩（<1）和扩展（>1）。
  - **训练时**，为每个视频随机选取一个 \(\gamma\) 并应用于视觉 token 的时序索引。
  - **推理时**，可灵活选择缩放因子，以适应不同长度的任务（例如长检索宜用较小因子，长理解宜用较大因子）。
  - 公式化给出多模态输入中每个 token 的三维位置索引计算方法。

## 3. 实验设计
### 3.1 模型与训练
- **骨干模型**：Qwen2‑1.5B 和 Qwen2‑7B，搭配 Qwen2‑VL‑2B/7B‑Instruct 的视觉编码器，构成 Qwen2‑2B/7B‑Video。
- **训练数据**：LLaVA‑Video‑178k 的子集（30k 短于 2 分钟的视频 + 3k 2‑3 分钟视频，约 300k 对指令样本）。
- **训练配置**：训练上下文长度 8k，最大视频帧数 128，采样率 2；batch size 128；学习率 1e‑5(2B)/2e‑5(7B)，余弦调度。

### 3.2 评估基准与对比方法
- **长视频理解**：LongVideoBench、Video‑MME、MLVU（视频时长从几秒到 2 小时）。
- **长视频检索**：V‑NIAH（视觉“大海捞针”），在 1 小时视频中随机插入目标图，评估检索准确性。
- **对比基线**：
  - 原始 RoPE（vanilla RoPE）
  - M‑RoPE（Qwen2‑VL 采用）
  - VideoRoPE（专用视频 RoPE，含固定时序缩放）
- **评估上下文长度**：8k、16k、32k、64k。

## 4. 资源与算力
- 训练使用 **H800‑80GB GPU**，总计算量约 **304 GPU 小时**。
- 未提及推理所需的额外算力开销。

## 5. 实验数量与充分性
- **核心对比实验**：覆盖 2 种模型规模（2B/7B）、3 个基准、4 种上下文长度的全面对比表格。
- **消融实验**：
  - 逐步叠加模块（从 vanilla RoPE → +3D 结构 → +HFA → +DTS）验证各组件贡献。
  - 分析推理时动态缩放因子对长视频理解与检索的不同影响。
- **专项分析**：在 V‑NIAH 上展示了不同帧深度的准确率热力图，定性展示长度外推能力。
- **公平性**：所有方法使用相同训练数据、相同训练上下文长度、相同超参设置。评估时保持对齐，客观性较好。但未报告误差棒或多轮统计检验。

## 6. 主要结论与发现
- HoPE 在长视频理解和检索任务中一致超越现有 RoPE 变体，尤其在长视频检索上相对于最佳基线**提升 22.23%**。
- 理论分析揭示了：
  1. 原始 RoPE 的展平操作破坏了视频时空局部性先验。
  2. 当前多模态 RoPE 的频率分配策略（无论是高频还是低频给时间）都无法在充分长上下文中维持语义偏好。
  3. 将时间维度的频率置零是理论最优保证。
- 动态时间缩放使模型对视频速度变化更鲁棒，并能在推理时适配不同上下文长度。

## 7. 优点与亮点
- **首次理论分析**多模态 RoPE 的频率分配对长上下文语义建模的影响，提供了严谨的命题、引理和定理。
- 提出的 **HFA 策略**简洁有效，将语义偏好保障形式化并最大化。
- **DTS 机制**同时支持训练期多尺度学习和推理期灵活调整，考虑了真实场景的视频速度差异。
- 实验覆盖两种模型规模、多个长视频基准和不同外推长度，验证了方法的有效性和可扩展性。

## 8. 不足与局限
- **模型规模有限**：仅验证到 7B 参数，未在数十亿参数的大模型上进行测试，不清楚在大规模骨干下的增益幅度。
- **训练数据与长度**：训练限制在 8k 上下文和最多 3 分钟的视频，且未使用大规模长上下文专门数据，导致 64k 时所有方法性能仍大幅下降，HoPE 虽最优但绝对性能仍低。
- **评估多样性**：主要集中于理解与检索，未探讨生成、推理等更复杂的视频任务，也未涉及图像、图文交错等更广泛多模态场景。
- **统计显著性未报告**：缺少多次运行的方差分析。
- **应用限制**：由于依赖骨干模型的能力，小型模型的提升幅度有限；且动态缩放因子的最佳选择可能需要按任务手工调整。

（完）
