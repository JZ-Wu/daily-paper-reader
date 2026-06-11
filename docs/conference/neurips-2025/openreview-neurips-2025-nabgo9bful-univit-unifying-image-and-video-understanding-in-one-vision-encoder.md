---
title: "UniViT: Unifying Image and Video Understanding in One Vision Encoder"
title_zh: UniViT：用一个视觉编码器统一图像和视频理解
authors: "Feilong Tang, Xiang An, Haolin Yang, Yin Xie, Kaicheng Yang, Ming Hu, Zheng Cheng, Xingyu Zhou, Zimin Ran, Imran Razzak, Ziyong Feng, Behzad Bozorgtabar, Jiankang Deng, Zongyuan Ge"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NABGO9Bful"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 统一的图像和视频视觉编码器
tldr: 现有预训练方法偏重于空间或时间建模，难以同时捕捉精细细节与动态。本文提出UniViT，一种聚类驱动的统一自监督学习框架，通过事件级和对象级聚类判别，联合学习图像空间内容与视频时间动态语义。实验表明统一编码器在多种下游任务上性能优异，为通用视觉理解提供了基础模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 2797, \"height\": 2254}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 2749, \"height\": 2260}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 2970, \"height\": 2258}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-004.webp\", \"caption\": \"\", \"page\": 3, \"index\": 4, \"width\": 2666, \"height\": 747}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-005.webp\", \"caption\": \"\", \"page\": 5, \"index\": 5, \"width\": 2265, \"height\": 2268}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-006.webp\", \"caption\": \"\", \"page\": 5, \"index\": 6, \"width\": 2265, \"height\": 2268}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-007.webp\", \"caption\": \"\", \"page\": 5, \"index\": 7, \"width\": 2262, \"height\": 2268}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-008.webp\", \"caption\": \"\", \"page\": 5, \"index\": 8, \"width\": 786, \"height\": 787}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-009.webp\", \"caption\": \"\", \"page\": 6, \"index\": 9, \"width\": 790, \"height\": 790}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-010.webp\", \"caption\": \"\", \"page\": 6, \"index\": 10, \"width\": 790, \"height\": 790}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-011.webp\", \"caption\": \"\", \"page\": 6, \"index\": 11, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-012.webp\", \"caption\": \"\", \"page\": 6, \"index\": 12, \"width\": 790, \"height\": 790}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-013.webp\", \"caption\": \"\", \"page\": 7, \"index\": 13, \"width\": 4096, \"height\": 1044}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-014.webp\", \"caption\": \"\", \"page\": 9, \"index\": 14, \"width\": 924, \"height\": 924}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-015.webp\", \"caption\": \"\", \"page\": 9, \"index\": 15, \"width\": 924, \"height\": 924}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-016.webp\", \"caption\": \"\", \"page\": 9, \"index\": 16, \"width\": 924, \"height\": 924}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-017.webp\", \"caption\": \"\", \"page\": 9, \"index\": 17, \"width\": 924, \"height\": 924}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-018.webp\", \"caption\": \"\", \"page\": 9, \"index\": 18, \"width\": 924, \"height\": 924}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nabgo9bful/fig-019.webp\", \"caption\": \"\", \"page\": 9, \"index\": 19, \"width\": 924, \"height\": 924}]"
motivation: 现有视觉预训练偏重空间或时间单方面，难以同时捕获时空语义。
method: 提出聚类驱动的自监督学习框架UniViT，统一图像和视频的语义表征。
result: 在多项图像和视频理解任务中取得领先性能，实现统一模型。
conclusion: 为构建时空通用的视觉基础模型提供了有效方案，推动多模态统一。
---

## Abstract
Despite the impressive progress of recent pretraining methods on multimodal tasks, existing methods are inherently biased towards either spatial modeling (e.g., CLIP) or temporal modeling (e.g., V-JEPA), limiting their joint capture of spatial details and temporal dynamics. To this end, we propose UniViT, a cluster-driven unified self-supervised learning framework that effectively captures the structured semantics of both image spatial content and video temporal dynamics through event-level and object-level clustering and discrimination. Specifically, we leverage offline clustering to generate semantic clusters across both modalities. For videos, multi-granularity event-level clustering progressively expands from single-event to structured multi-event segments, capturing coarse-to-fine temporal semantics; for images, object-level clustering captures fine-grained spatial semantics. However, while global clustering provides semantically consistent clusters, it lacks modeling of structured semantic relations (e.g., temporal event structures). To address this, we introduce a contrastive objective that leverages these semantic clusters as pseudo-label supervision to explicitly enforce structural constraints, including temporal event relations and spatial object co-occurrences, capturing structured semantics beyond categories. Meanwhile, UniViT jointly embeds structured object-level and event-level semantics into a unified representation space. Furthermore, UniViT introduces two key components: (i) Unified Rotary Position Embedding integrates relative positional embedding with frequency-aware dimension allocation to support position-invariant semantic learning and enhance the stability of structured semantics in the discrimination stage; and (ii) Variable Spatiotemporal Streams adapt to inputs of varying frame lengths, addressing the rigidity of conventional fixed-input approaches. Extensive experiments across varying model scales demonstrate that UniViT achieves state-of-the-art performance on linear probing, attentive probing, question answering, and spatial understanding tasks.

---

## 论文详细总结（自动生成）

# UniViT 论文总结

## 1. 核心问题与研究动机
- 现有视觉预训练方法存在内在偏向：图像模型（如 CLIP）偏重空间建模，视频模型（如 V‑JEPA）偏重时间建模，难以**同时精细捕获空间细节与时间动态**。
- 缺乏统一的视觉表示学习框架，无法在**单一编码器中融合图像与视频的结构化语义**。
- 本文旨在解决：如何在一个自监督框架下，通过**结构化语义建模**联合学习图像与视频的时空表示。

## 2. 方法论

### 2.1 整体框架：聚类驱动的两阶段训练
- **聚类阶段**：离线聚类生成语义伪标签。
  - 视频：多粒度事件级聚类，由单事件逐步扩展到多事件片段，捕获粗到细的时序语义。
  - 图像：对象级聚类，捕获细粒度空间语义。
  - 得到统一的语义质心集合 \(\mathcal{C}_{\text{uni}} = \{\mathbf{c}^{\text{obj}}_k\}_{k=1}^{K_{\text{obj}}} \cup \{\mathbf{c}^{\text{evt}}_k\}_{k=1}^{K_{\text{evt}}}\)。
- **判别阶段**：以簇质心为伪标签，使用**多标签对比损失**强制学习结构化关系：
  \[
  \mathcal{L}_{\text{Joint}} = \sum_{m \in \{\text{obj},\text{evt}\}} \Big[\log(1+\sum_{j\in\Omega_{mn}}\exp(\sigma_{mj})) + \log(1+\sum_{i\in\Omega_{mp}}\exp(-\sigma_{mi}))\Big],
  \]
  其中 \(\sigma_{mu,k} = \mathbf{e}_u^\top \mathbf{c}_{mk}\) 表示特征嵌入与质心的相似度。

### 2.2 关键组件
- **统一旋转位置编码（U‑RoPE）**：将位置嵌入分解为空间与时间成分，采用频率感知分配策略——低频用于全局时间结构，高频用于局部空间细节，实现**位置不变语义学习**并增强判别阶段稳定性。
- **可变时空流（VS\(^2\)）**：支持**变长帧序列输入**（如 1,2,4,8,16 帧），灵活捕获不同时间尺度，打破传统固定输入限制。
- 模型骨干为共享的 Transformer 编码器，训练时图像与视频交替输入，不增加推理成本。

## 3. 实验设计

### 3.1 数据集与预训练
- 图像数据：LAION‑400M、COYO‑700M。
- 视频数据：InternVid。
- 总训练数据约 1.1B 图像 + 60M 视频，训练过程中模型经历约 20B 图像帧。

### 3.2 评估基准
- **线性探测与注意探测**：14 个标准数据集，覆盖场景、物体、动作识别等（如 Food‑101、CIFAR‑100、EuroSAT、Resisc45、Caltech101、ImageNet、SUN397、Kinetics‑400/600/700、HMDB51、UCF101、RareAct、SSV2）。
- **多模态问答与空间理解**：在 LLaVA‑NeXT‑Video 框架下，评估 18 个基准（MMStar、VisWiz、MMMU、GQA、POPE、Seed、MMBench、AI2D、VideoMME、MLVU、TGIF‑QA 等）。

### 3.3 对比方法
- 图像预训练模型：SigLIP v2、DINOv2、CLIP、I‑JEPA、MLCD。
- 视频预训练模型：V‑JEPA、LanguageBind、VideoMAE v2。
- 图像+视频联合预训练：PE‑Core。
- 不同架构和规模均进行比较，保持统一实验设置确保公平。

## 4. 资源与算力
- 训练硬件：**80 块 H800 GPU**。
- 训练数据量：约 20B 图像帧。
- 优化器：AdamW，学习率 0.001，权重衰减 0.2。
- 训练时图像批量大小 16K，视频批量 2K（每视频含 16 帧）。
- 高分辨率变体（336px）在 224px 预训练基础上继续训练额外 1B 帧。

## 5. 实验数量与充分性
- **主实验**：两个大表（探针评估），涵盖 14 个数据集、多种模型规模和对比方法。
- **MLLM 编码器实验**：18 个多模态基准上的雷达图对比。
- **消融实验**：5 组消融，包括预训练策略、位置编码、多事件帧采样、聚类策略、类别数量。
- **可视化分析**：PCA 展示补丁特征一致性、T‑SNE 展示对象级特征分布，以及训练曲线、帧间相似度等。
- 实验覆盖**小、基础、大三种模型尺寸**，并与强基线公平对比，研究内容充分。

## 6. 主要结论与发现
- UniViT 能在**单一视觉编码器**内统一处理图像和视频，在线性探测、注意探测、问答、空间理解多项任务上达到**最优性能**。
- 模型具有较强的**扩展性**：随着数据量、模型容量、输入分辨率增加，性能持续提升。
- 消融实验证实：U‑RoPE 和 VS\(^2\) 显著提升视频理解，多粒度事件聚类优于单一粒度，1M 类质心达到最佳平衡。

## 7. 优点
- **首次实现真正的统一**：同一编码器同时擅长静态图像和动态视频，无需模态特定分支。
- **结构化语义建模**：事件级与对象级聚类结合多标签对比学习，超越了简单的类别判别，能捕捉时序事件关系与空间物体共现。
- **位置编码与输入灵活性**：U‑RoPE 和 VS\(^2\) 设计精巧，提升时间建模的稳定性和对不同帧率的适应性。
- **大规模验证**：丰富的基准与公平的比较，展示了方法的通用性与竞争力。

## 8. 不足与局限
- **离线聚类依赖**：聚类基于预训练嵌入，可能继承初始模型的偏差，且训练过程中无法在线更新质心。
- **计算资源需求高**：VS\(^2\) 可处理变长序列，但长视频或超高分辨率输入仍带来庞大计算开销，限制资源受限环境的可扩展性。
- **语义多样性依赖**：目前视频数据的语义多样性可能仍低于图像，最佳类别数与图像预训练类似，暗示视频数据的语义覆盖面有待扩展。
- **部分实验未能开源**：因数据保密限制，代码和模型未公开，可能影响复现性。

（完）
