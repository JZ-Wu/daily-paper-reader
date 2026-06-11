---
title: "AdaVideoRAG: Omni-Contextual Adaptive Retrieval-Augmented Efficient Long Video Understanding"
title_zh: AdaVideoRAG：全方位自适应检索增强的高效长视频理解
authors: "Zhucun Xue, Jiangning Zhang, Xurong Xie, yuxuan cai, Yong Liu, Xiangtai Li, Dacheng Tao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FDAI0PY9Qp"
tags: ["query:tf-vl-ag"]
score: 8.0
evidence: 自适应检索增强以实现高效视频理解
tldr: 为解决多模态大模型长视频理解的效率问题，提出自适应检索增强生成框架，根据查询难度动态调整检索结构，减少冗余计算与延迟，提升长视频理解效率与信息保留。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 5138, \"height\": 2620}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-002.webp\", \"caption\": \"\", \"page\": 4, \"index\": 2, \"width\": 5404, \"height\": 1346}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-003.webp\", \"caption\": \"\", \"page\": 7, \"index\": 3, \"width\": 2774, \"height\": 1558}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-004.webp\", \"caption\": \"\", \"page\": 23, \"index\": 4, \"width\": 1788, \"height\": 1924}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fdai0py9qp/fig-005.webp\", \"caption\": \"\", \"page\": 24, \"index\": 5, \"width\": 844, \"height\": 1204}]"
motivation: 现有多模态大模型在长视频上因固定上下文和弱长程依赖而效果下降，现有RAG方案固定检索方式导致简单查询冗余计算、复杂查询信息丢失。
method: 提出AdaVideoRAG，一种自适应检索增强框架，根据查询难度动态调整检索策略，减少非必要计算。
result: 实验显示该方法在长视频理解基准上实现更优的效率与准确性平衡。
conclusion: 自适应检索增强可有效提升长视频理解的计算效率与信息保真度。
---

## Abstract
Multimodal Large Language Models (MLLMs) have demonstrated excellent performance in video understanding but suffer from degraded effectiveness when processing long videos due to fixed-length contexts and weaknesses in modeling long-term dependencies. Retrieval-Augmented Generation (RAG) technology can mitigate these limitations through dynamic knowledge expansion, but existing RAG schemes for video understanding employ fixed retrieval paradigms that use uniform structures regardless of input query difficulty. This introduces redundant computational overhead and latency (*e.g.*, complex graph traversal operations) for simple queries (*e.g.*, frame-level object recognition) while potentially causing critical information loss due to insufficient retrieval granularity for multi-hop reasoning. Such single-step retrieval mechanisms severely constrain the model's balance between resource efficiency and cognitive depth. 
To address this, we first propose a novel AdaVideoRAG framework for long-video understanding, which uses a lightweight intent classifier to dynamically and adaptively allocate appropriate retrieval schemes, ranging from the simplest to the most sophisticated, for different video understanding tasks based on query complexity. We introduce an Omni-Knowledge Indexing module to extract valuable information from multi-modal signals for context modeling and build corresponding databases, *i.e.*, a text base from clip captions, ASR, and OCR; a visual base; and a graph for deep semantic understanding. This enables hierarchical knowledge access, integration, and generation from naive retrieval to graph retrieval, achieving an optimal balance between resource consumption and video understanding capabilities.  
Finally, we construct the HiVU benchmark for deep understanding evaluation. Extensive experiments show that our framework enhances the overall efficiency and accuracy of Video-QA for long videos and can be seamlessly integrated with existing MLLMs via lightweight API calls, establishing a new paradigm for adaptive retrieval augmentation in video analysis.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：多模态大模型在处理长视频时，因**固定上下文长度**和**对长程依赖建模不足**，理解效果急剧下降。现有的检索增强生成（RAG）方案虽然能通过外部知识扩充缓解此问题，但大都采用**固定的检索范式**（如统一使用复杂的图检索或简单的向量检索），不分问题难度。
- **矛盾**：简单问题（如帧级物体识别）使用复杂检索会带来**冗余计算和延迟**；复杂问题（如多跳推理）使用简单检索又容易**丢失关键信息**。
- **整体含义**：提出 **AdaVideoRAG**，一种**自适应检索增强框架**，根据查询的复杂程度**动态分配**不同复杂度的检索策略，在资源消耗与理解深度之间取得最优平衡。

### 2. 论文提出的方法论
整体框架包含四个核心模块：

- **查询意图分类**  
  用一个轻量级的 CoT 大模型（Qwen2.5-7B）将用户查询自动划入三个难度等级：
  - **L1**：纯感知类（直接由 MLLM 回答，无需检索）
  - **L2**：简单推理（需要跨模态检索与单步推理）
  - **L3**：困难推理（需要图谱构建与多跳推理）

- **全知识索引**
  从长视频中抽取多模态信息构建三类知识库：
  - **文本库**：基于片段字幕（MiniCPM-V 生成）、ASR（FastWhisper）、OCR（EasyOCR）建立向量数据库
  - **视觉库**：通过 ImageBind 提取关键帧的跨模态视觉特征
  - **图谱**：对文本块抽取实体、关系，构建结构化知识图谱

- **自适应检索范式**
  根据分类结果自动触发不同路径：
  - **L1** → 不检索，直接 MLLM 回答
  - **L2** → 朴素跨模态检索（查询改写 → 多库相似度匹配 → 视觉‑文本对齐 → Top‑K 证据）
  - **L3** → 图检索（在图谱上匹配实体/关系 → 展开关联子图 → 与视觉证据融合）

  检索结果经过去重、LLM 精炼和时间戳重排后输入生成环节。

- **多模态信息集成与生成**  
  将检索得到的文本证据、视觉片段与对应视频块一并送入 MLLM，完成最终推理与回答。

### 3. 实验设计
- **主要数据集 / 基准**：
  - **HiVU**：本文新建的层级视频理解基准，包含 120 个长视频（1–106 分钟），覆盖知识教育、信息、娱乐三大类，设 L1/L2/L3 三级难度题型，采用胜率（Win-Rate）评估（从全面性、赋能性、可信度、深度、密度五个维度）。
  - **MLVU**：长视频多任务理解基准。
  - **Video-MME**：全谱视频分析基准（含短、中、长视频）。

- **对比方法**：
  - 基线 MLLM：Video-LLaVA、Qwen2.5-VL（7B/72B）、VideoLLaMA3。
  - 已有 RAG 方法：VideoRAG，以及分别对比加/不加 AdaVideoRAG 的效果。

### 4. 资源与算力
- **推理硬件**：文中主要提及使用**单张 H20 GPU（96 GB）** 进行响应时间测试，并行优化时扩展至 8 张 GPU 实现近线性加速。
- **数据库构建耗时**：L2 级平均 351 秒 / 视频，L3 级 412 秒 / 视频（含图谱构建）。采用多进程并行可将时间压缩至 L2 约 22 秒、L3 约 26 秒（8 GPU）。
- **响应延迟**：单任务无检索 8 秒，L2 检索 26 秒，L3 检索 27 秒，自适应平均 20 秒。
- **未明确说明**：文中未提及任何模型微调的训练算力，框架以调用 API 方式插入现有 MLLM，不涉及额外训练。

### 5. 实验数量与充分性
- 进行了 **多维度、多数据集** 的充分实验：
  - **MLVU** 上对比多种基座模型添加 AdaVideoRAG 后的性能增益（∼+10%~40%）。
  - **Video-MME** 上与 VideoRAG 横向比对，尤其在长视频子集上的优势。
  - **HiVU** 上细粒度分析不同难度下的胜率，并对比 VideoRAG。
  - **消融实验**：逐步去掉图检索、视觉检索、文本检索模块，验证各组件贡献。
  - **查询分类影响**：对比不同分类器模型，以及强制所有查询走同一路径的效果。
  - **效率分析**：详细拆解不同检索路径的构建与推理耗时。
- 实验设计**客观、公平**，基线均为公开模型，评估指标统一，消融覆盖关键组件。

### 6. 论文的主要结论与发现
- AdaVideoRAG 能根据问题难度自适应路由到“无检索‑朴素检索‑图检索”三级策略，**同时提升长视频理解的效率与准确率**。
- 在需要全局理解、多跳推理的 **困难问题** 上，相较固定检索的 VideoRAG 优势更显著。
- 该框架可作为**即插即用的轻量级增强方案**，无缝集成到各种开源 MLLM 中，显著缩小小模型与大模型之间的性能差距。
- 文章的 HiVU 基准首次提供了针对不同认知深度的层级化评估体系。

### 7. 优点
- **灵活的资源调度**：创新地引入查询意图分类，避免“一刀切”检索，平衡效能与开销。
- **全模态知识融合**：整合字幕、语音、视觉、图谱等多模态信号，构建层次化索引，覆盖从细粒度到全局语义的信息。
- **实用性强**：无需训练下游模型，通过轻量 API 即可提升现有模型的长视频处理能力。
- **评估体系创新**：HiVU 基准以三级认知复杂度 + 五维胜率评估，为长视频深度理解提供了更精细的度量尺。

### 8. 不足与局限
- **参数规模受限**：受计算资源限制，仅评估了最多 32B 参数的模型，**未验证更大规模模型**（如 70B+）上的表现。
- **难度分级粒度粗**：仅划分三级，实际应用可能需要更细粒度的路由分类。
- **潜在的工具链依赖**：外部提取器（ASR、OCR、VLM）的性能会直接影响下游检索质量；框架本身的可迁移性可能受限于这些工具的适应能力。
- **偏重于推理而非训练**：未探索通过训练提升分类或检索效率/精度的可能性，完全依赖固定管线。
- **社会风险**：可能被滥用制造虚假长视频信息，需要配套的治理机制。

（完）
