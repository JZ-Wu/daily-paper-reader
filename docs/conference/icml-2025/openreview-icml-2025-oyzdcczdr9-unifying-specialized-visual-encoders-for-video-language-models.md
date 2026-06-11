---
title: Unifying Specialized Visual Encoders for Video Language Models
title_zh: 统一专用视觉编码器用于视频语言模型
authors: "Jihoon Chung, Tyler Zhu, Max Gonzalez Saez-Diez, Juan Carlos Niebles, Honglu Zhou, Olga Russakovsky"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oYzDcCZdR9"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 提出多编码器视频表示MERV，提升视频语言模型的视频理解
tldr: "针对当前视频大语言模型仅使用单一视觉编码器导致信息有限的局限，提出多编码器视频表示MERV，通过对齐、投影和交叉注意力融合异构特征，在公平比较下获得最高4.62%的准确率提升，为视频理解提供了更丰富的视觉表征。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1686, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 772, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 846, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 798, \"height\": 822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1681, \"height\": 1586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1752, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1706, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1591, \"height\": 2048, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1687, \"height\": 1377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oyzdcczdr9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1702, \"height\": 887, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 497, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 500, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 510, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1431, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1613, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1260, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 943, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 942, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1603, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1686, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 587, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1690, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1693, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oyzdcczdr9/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1605, \"height\": 360, \"label\": \"Table\"}]"
motivation: 现有视频LLM仅使用单一视觉编码器，限制视觉信息的丰富度。
method: 提出MERV，采用多编码器进行时空对齐、统一投影和交叉注意力融合。
result: "在多个视频理解任务上，MERV比单一编码器模型准确率提升高达4.62%。"
conclusion: 多编码器视频表示能有效提升视频LLM性能，为多模态融合提供新方法。
---

## Abstract
Recent advances in vision backbones have yielded powerful and diverse visual and video encoders. Yet, current Video Large Language Models encode visual inputs using an encoder from a single backbone family, limiting the amount and type of visual information they can process. We propose MERV, a Multi-Encoder Video Representation, which utilizes multiple encoders for a comprehensive video representation. To optimize heterogeneous features from a broad spectrum of encoders and ensure efficient and coherent feature integration, MERV first aligns encoder features spatio-temporally, then projects them into a unified structure, and finally fuses them through cross-attention. Under fair comparison, MERV achieves up to 4.62% higher accuracy than its base model, while introducing minimal extra parameters and training faster than equivalent single-encoder methods after parallelizing visual processing. Qualitative analysis shows MERV successfully captures and integrates domain knowledge from each encoder, opening new possibilities for scaling enhanced video understanding.

---

## 论文详细总结（自动生成）

好的，这是对论文《Unifying Specialized Visual Encoders for Video Language Models》的结构化深度总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前主流的视频大语言模型在编码视觉信息时，普遍依赖单一视觉编码器。这限制了模型能够处理的视觉信息类型和广度，导致模型能力受限于该特定编码器的固有弱点（例如，擅长语义理解但缺乏时序推理能力）。
*   **整体含义**：为了打破单一编码器的局限，本文提出了一种整合多个功能各异的视觉编码器的方法，旨在构建一个更全面、更强大的视频表征，从而提升视频语言模型在各类任务上的推理和理解能力。

### 2. 论文提出的方法论

论文提出了一种名为 **MERV (Multi-Encoder Representation of Videos)** 的框架，其核心思想是并行地利用多个具有不同专长的视觉编码器，并将其特征有效融合。

**关键技术细节与流程如下：**

1.  **多编码器特征提取**：
    *   精心选择了四个在专长、架构和训练目标上互补的预训练RGB编码器：
        *   **空间专家 (Spatial Expert)**：DINOv2，擅长细粒度物体理解。
        *   **时序专家 (Temporal Expert)**：ViViT，擅长长时序依赖关系建模。
        *   **图文对比专家**: SigLIP，擅长视觉-语言关联。
        *   **视频-语言对比专家**: LanguageBind，擅长视频-文本高层语义对齐。
    *   输入视频并行地通过这些冻结的编码器，提取出各自具有不同时空形状和维度的特征。

2.  **时空对齐与预融合投影**：
    *   **时序对齐**：通过为每个编码器选择不同的输入帧数，确保所有编码器输出的时间维度相同。
    *   **空间对齐与压缩**：设计了一个轻量级的预融合投影器。使用自适应2D平均池化将来自不同编码器的特征图空间尺寸统一压缩至 \( h \times w \)。
    *   **维度统一**：为每个编码器添加一个线性层，将其特征维度 \( d_e \) 统一投影到与大语言模型维度相同的 \( d \) 维空间。
    *   **公式表达**：\( x_e := P(v_e)W_e \in \mathbb{R}^{\ell \times d} \)，其中 \( v_e \) 是编码器原始特征，\( P \) 是池化操作，\( W_e \) 是线性投影层，\( \ell = t \times h \times w \) 是token序列长度。

3.  **特征融合**：
    *   采用交叉注意力机制来动态融合多个编码器的信息。它使用一个可学习的查询向量 \( Q \)，将所有投影并平均后的特征 \( X \) 作为键，所有投影后的完整token序列 \( \mathcal{X} \) 作为值。
    *   **公式表达**：\( O := \text{Softmax}\left(\frac{QX^\top}{\sqrt{d}}\right)\mathcal{X} \in \mathbb{R}^{\ell \times d} \)。该机制通过学习到的权重，将来自不同编码器的信息进行“加性混合”。

4.  **高效实现**：
    *   利用PyTorch的完全分片数据并行技术并行化视觉处理过程，显著减少了因多编码器带来的计算开销。

### 3. 实验设计

*   **训练数据集**：
    *   **第一阶段**：使用来自LLaVA和Valley的单轮简洁描述数据（约126万图像/视频-文本对）。
    *   **第二阶段**：使用来自LLaVA和Video-ChatGPT的多轮对话、详细描述和推理指令数据（约76.5万图像/视频-文本对）。
*   **评估基准 (Benchmarks)**：
    *   **开放域问答**：MSVD-QA, MSRVTT-QA, TGIF-QA, ActivityNet-QA。
    *   **多项选择**：NExT-QA, VLEP, TVQA, Perception Test。
    *   **专项分析数据集**：为分析模型的时序与通用理解能力，引入了Something-Something v2 数据集，并将其改造为5选1的多项选择题形式。
*   **对比方法**：
    *   **主要基线 (相同训练数据)**：Video-LLaVA。
    *   **其他先进方法 (可能使用了不同数据)**：Video-Chat, LLaMA-Adapter, Video-LLaMA, Video-ChatGPT, SeViLA, LLaMA-VID等。

### 4. 资源与算力

*   **训练资源**：模型的训练主要使用了两种配置的GPU：
    *   8块L40-48GB GPU
    *   8块H100 GPU
*   **训练时长**：得益于高效的并行化，MERV的训练非常迅速。
    *   使用8块L40 GPU，完整训练（MERV frozen）少于24小时。
    *   使用8块H100 GPU，训练时间可缩短至约8小时。
    *   相比之下，作为基线的Video-LLaVA在相同L40配置下仅第二阶段训练就需要约38小时。

### 5. 实验数量与充分性

实验设计非常详尽、充分且力求公平，主要包括以下几个层面：

*   **性能对比实验**：在8个主流视频理解基准上，与至少8种现有方法进行了系统的性能比较，展示了MERV的优越性。
*   **消融实验**：对模型的关键组件进行了深入分析，确保设计的合理性和最优性。
    *   **投影器消融**：对比了无投影器、2D/3D池化、注意力重采样、卷积等6种方案及其参数量与计算量。
    *   **Token长度消融**：测试了从1到256共7种不同的输出token长度对性能的影响。
    *   **融合策略消融**：比较了交叉注意力、通道/序列拼接、学习权重、固定混合权重等5种融合方式。
    *   **训练策略消融**：对比了仅第二阶段训练（MERV frozen），两阶段训练（MERV full）以及单阶段混合数据训练的效果。
    *   **编码器组合消融**：通过逐一移除编码器构建了4个子模型，以及训练了4个单编码器模型，以验证多编码器组合的有效性和每个编码器的贡献。
*   **定性分析**：通过可视化交叉注意力权重、分析模型在不同类型问题上的表现以及在SSv2数据集上的专项测试，深入解析了MERV如何整合和利用不同编码器的知识。

这些实验不仅覆盖了性能对比，更深入到方法论的每个环节，并严格控制了数据、算力等变量，保证了对比的客观与公平。

### 6. 论文的主要结论与发现

*   MERV能够成功整合来自不同领域专家的视觉知识，在多个基准上取得了比单一编码器模型和先前工作更好的性能。在公平对比下，其性能比基础模型Video-LLaVA最高提升了4.62%（例如在TVQA上）。
*   MERV中的交叉注意力机制能够动态地为不同视频内容分配合适的编码器权重，例如为运动剧烈的视频赋予ViViT更高的权重，实现了对专长知识的有效利用。
*   通过并行化处理，MERV引入多编码器所带来的额外计算开销极小，其训练效率甚至优于某些单编码器方法。
*   定量和定性分析证明，MERV可以同时捕捉到来自纯视觉模型的细粒度时序能力和图文对比模型的通用语义理解能力，而不像单编码器模型那样在两者间进行折衷。

### 7. 优点

*   **创新的多专家融合范式**：首次系统性地在视频LLM领域探索并验证了融合不同RGB域视觉专家的有效性，为模型能力扩展提供了新思路。
*   **高效的架构设计**：提出的时空对齐和交叉注意力融合模块设计轻量、高效，在极小的参数量和计算开销下实现性能大幅提升。
*   **扎实的分析与诊断**：实验设计极为周全，不仅通过与SOTA模型对比证明性能，更通过大量消融、权重可视化和专门构造的诊断数据集深入分析了模型为何有效以及各部件的作用。
*   **公平的对比与可复现性**：作者严格固定数据混合与对比基线，致力于实现公平对比，并承诺将开源代码和模型权重。

### 8. 不足与局限

*   **基础模型依赖性**：MERV的性能根本上受限于其所使用的LLaMA-2 7B模型和四个预训练编码器的能力上限，无法弥补编码器自身的根本缺陷。
*   **计算资源需求**：尽管通过并行化实现了高效，但模型仍需同时加载一个7B的大语言模型和四个视觉编码器，对显存和计算资源仍有一定要求，可能限制了在资源极度受限环境下的应用。
*   **训练策略的优化空间**：作者指出MERV (frozen) 未利用第一阶段的对齐数据，而MERV (full) 虽然有所改善，但两阶段训练并未在所有基准上都严格优于仅第二阶段训练。最优的训练策略仍待进一步探索。
*   **并行化潜在的进一步优化空间**：作者提到当前使用的FSDP通用策略可能不是最优的，若能实现更精细的模块放置策略，模型效率有望进一步提升。

（完）
