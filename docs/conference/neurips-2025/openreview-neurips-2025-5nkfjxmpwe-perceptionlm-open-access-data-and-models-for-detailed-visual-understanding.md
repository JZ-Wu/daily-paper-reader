---
title: "PerceptionLM: Open-Access Data and Models for Detailed Visual Understanding"
title_zh: PerceptionLM：面向精细视觉理解的开放数据与模型
authors: "Jang Hyun Cho, Andrea Madotto, Effrosyni Mavroudi, Triantafyllos Afouras, Tushar Nagarajan, Muhammad Maaz, Yale Song, Tengyu Ma, Shuming Hu, Suyog Jain, Miguel Martin, Huiyu Wang, Hanoona Abdul Rasheed, Peize Sun, Po-Yao Huang, Daniel Bolya, Nikhila Ravi, Shashank Jain, Tammy Stark, Seungwhan Moon, Babak Damavandi, Vivian Lee, Andrew Westbury, Salman Khan, Philipp Kraehenbuehl, Piotr Dollar, Lorenzo Torresani, Kristen Grauman, Christoph Feichtenhofer"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=5NkfjxMpWe"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 构建开放的视觉语言模型用于图像和视频理解
tldr: 该论文针对当前闭源高性能视觉语言模型阻碍研究透明度的问题，提出了完全开放可复现的感知语言模型（PLM）框架，探索不使用专有模型蒸馏的标准训练流程，旨在促进图像和视频理解领域的透明研究。所建模型和数据集公开可得，为社区提供了可信基线，有助于推动科学进步和公平比较。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 1033, \"height\": 580}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 1033, \"height\": 580}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 527, \"height\": 495}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-004.webp\", \"caption\": \"\", \"page\": 5, \"index\": 4, \"width\": 1232, \"height\": 1064}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-005.webp\", \"caption\": \"\", \"page\": 5, \"index\": 5, \"width\": 569, \"height\": 419}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-006.webp\", \"caption\": \"\", \"page\": 5, \"index\": 6, \"width\": 569, \"height\": 419}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-007.webp\", \"caption\": \"\", \"page\": 5, \"index\": 7, \"width\": 665, \"height\": 489}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-008.webp\", \"caption\": \"\", \"page\": 5, \"index\": 8, \"width\": 641, \"height\": 478}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-009.webp\", \"caption\": \"\", \"page\": 5, \"index\": 9, \"width\": 641, \"height\": 478}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-010.webp\", \"caption\": \"\", \"page\": 5, \"index\": 10, \"width\": 799, \"height\": 610}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-011.webp\", \"caption\": \"\", \"page\": 5, \"index\": 11, \"width\": 852, \"height\": 634}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-012.webp\", \"caption\": \"\", \"page\": 5, \"index\": 12, \"width\": 852, \"height\": 634}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-013.webp\", \"caption\": \"\", \"page\": 5, \"index\": 13, \"width\": 786, \"height\": 572}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-014.webp\", \"caption\": \"\", \"page\": 6, \"index\": 14, \"width\": 572, \"height\": 322}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-015.webp\", \"caption\": \"\", \"page\": 6, \"index\": 15, \"width\": 566, \"height\": 319}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-016.webp\", \"caption\": \"\", \"page\": 6, \"index\": 16, \"width\": 582, \"height\": 327}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-017.webp\", \"caption\": \"\", \"page\": 6, \"index\": 17, \"width\": 594, \"height\": 326}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-018.webp\", \"caption\": \"\", \"page\": 6, \"index\": 18, \"width\": 591, \"height\": 324}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-019.webp\", \"caption\": \"\", \"page\": 6, \"index\": 19, \"width\": 593, \"height\": 325}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-020.webp\", \"caption\": \"\", \"page\": 6, \"index\": 20, \"width\": 756, \"height\": 422}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-021.webp\", \"caption\": \"\", \"page\": 6, \"index\": 21, \"width\": 756, \"height\": 422}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-022.webp\", \"caption\": \"\", \"page\": 6, \"index\": 22, \"width\": 756, \"height\": 422}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-023.webp\", \"caption\": \"\", \"page\": 7, \"index\": 23, \"width\": 478, \"height\": 358}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-024.webp\", \"caption\": \"\", \"page\": 7, \"index\": 24, \"width\": 476, \"height\": 841}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-025.webp\", \"caption\": \"\", \"page\": 7, \"index\": 25, \"width\": 546, \"height\": 722}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-026.webp\", \"caption\": \"\", \"page\": 7, \"index\": 26, \"width\": 558, \"height\": 314}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-027.webp\", \"caption\": \"\", \"page\": 7, \"index\": 27, \"width\": 636, \"height\": 424}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-028.webp\", \"caption\": \"\", \"page\": 7, \"index\": 28, \"width\": 558, \"height\": 314}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-029.webp\", \"caption\": \"\", \"page\": 10, \"index\": 29, \"width\": 732, \"height\": 1010}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-030.webp\", \"caption\": \"\", \"page\": 25, \"index\": 30, \"width\": 1930, \"height\": 1500}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-031.webp\", \"caption\": \"\", \"page\": 25, \"index\": 31, \"width\": 612, \"height\": 417}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-032.webp\", \"caption\": \"\", \"page\": 25, \"index\": 32, \"width\": 2048, \"height\": 1153}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-033.webp\", \"caption\": \"\", \"page\": 25, \"index\": 33, \"width\": 2048, \"height\": 1153}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-034.webp\", \"caption\": \"\", \"page\": 25, \"index\": 34, \"width\": 2048, \"height\": 1157}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-035.webp\", \"caption\": \"\", \"page\": 25, \"index\": 35, \"width\": 704, \"height\": 836}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-036.webp\", \"caption\": \"\", \"page\": 25, \"index\": 36, \"width\": 2046, \"height\": 1500}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-037.webp\", \"caption\": \"\", \"page\": 25, \"index\": 37, \"width\": 2048, \"height\": 1365}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-038.webp\", \"caption\": \"\", \"page\": 37, \"index\": 38, \"width\": 3696, \"height\": 392}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-039.webp\", \"caption\": \"\", \"page\": 38, \"index\": 39, \"width\": 1918, \"height\": 1290}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-040.webp\", \"caption\": \"\", \"page\": 38, \"index\": 40, \"width\": 2048, \"height\": 1131}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-041.webp\", \"caption\": \"\", \"page\": 44, \"index\": 41, \"width\": 3300, \"height\": 340}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-042.webp\", \"caption\": \"\", \"page\": 48, \"index\": 42, \"width\": 1510, \"height\": 1130}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-043.webp\", \"caption\": \"\", \"page\": 48, \"index\": 43, \"width\": 1510, \"height\": 1130}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-044.webp\", \"caption\": \"\", \"page\": 48, \"index\": 44, \"width\": 4246, \"height\": 2386}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-045.webp\", \"caption\": \"\", \"page\": 49, \"index\": 45, \"width\": 2296, \"height\": 1268}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-046.webp\", \"caption\": \"\", \"page\": 49, \"index\": 46, \"width\": 2296, \"height\": 1268}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-047.webp\", \"caption\": \"\", \"page\": 50, \"index\": 47, \"width\": 2016, \"height\": 1718}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-048.webp\", \"caption\": \"\", \"page\": 51, \"index\": 48, \"width\": 1430, \"height\": 202}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-049.webp\", \"caption\": \"\", \"page\": 52, \"index\": 49, \"width\": 1367, \"height\": 2048}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-050.webp\", \"caption\": \"\", \"page\": 52, \"index\": 50, \"width\": 360, \"height\": 540}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-051.webp\", \"caption\": \"\", \"page\": 52, \"index\": 51, \"width\": 1152, \"height\": 2048}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-052.webp\", \"caption\": \"\", \"page\": 52, \"index\": 52, \"width\": 1394, \"height\": 2048}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-053.webp\", \"caption\": \"\", \"page\": 52, \"index\": 53, \"width\": 1100, \"height\": 733}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-054.webp\", \"caption\": \"\", \"page\": 54, \"index\": 54, \"width\": 473, \"height\": 841}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-055.webp\", \"caption\": \"\", \"page\": 54, \"index\": 55, \"width\": 473, \"height\": 843}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-056.webp\", \"caption\": \"\", \"page\": 54, \"index\": 56, \"width\": 473, \"height\": 841}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-057.webp\", \"caption\": \"\", \"page\": 54, \"index\": 57, \"width\": 473, \"height\": 844}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-058.webp\", \"caption\": \"\", \"page\": 54, \"index\": 58, \"width\": 485, \"height\": 844}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-059.webp\", \"caption\": \"\", \"page\": 54, \"index\": 59, \"width\": 473, \"height\": 841}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-060.webp\", \"caption\": \"\", \"page\": 54, \"index\": 60, \"width\": 473, \"height\": 841}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-061.webp\", \"caption\": \"\", \"page\": 55, \"index\": 61, \"width\": 714, \"height\": 397}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-062.webp\", \"caption\": \"\", \"page\": 55, \"index\": 62, \"width\": 714, \"height\": 398}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-063.webp\", \"caption\": \"\", \"page\": 55, \"index\": 63, \"width\": 714, \"height\": 397}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-064.webp\", \"caption\": \"\", \"page\": 55, \"index\": 64, \"width\": 714, \"height\": 397}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-065.webp\", \"caption\": \"\", \"page\": 55, \"index\": 65, \"width\": 707, \"height\": 387}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-066.webp\", \"caption\": \"\", \"page\": 55, \"index\": 66, \"width\": 697, \"height\": 387}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-067.webp\", \"caption\": \"\", \"page\": 55, \"index\": 67, \"width\": 697, \"height\": 390}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-5nkfjxmpwe/fig-068.webp\", \"caption\": \"\", \"page\": 55, \"index\": 68, \"width\": 707, \"height\": 389}]"
motivation: 高性能视觉语言模型多闭源，阻碍科学度量和透明研究。
method: 构建完全开放的感知语言模型，采用标准训练流程不依赖专有模型蒸馏。
result: 提供了开放数据和模型，分析标准训练有效性。
conclusion: 开放可复现的框架有助提升视觉语言模型研究的透明度与可复现性。
---

## Abstract
Vision-language models are integral to computer vision research, yet many high-performing models remain closed-source, obscuring their data, design and training recipe. The research community has responded by using distillation from black-box models to label training data, achieving strong benchmark results, at the cost of measurable scientific progress. However, without knowing the details of the teacher model and its data sources, scientific progress remains difficult to measure. In this paper, we study building a Perception Language Model (PLM) in a fully open and reproducible framework for transparent research in image and video understanding.  We analyze standard training pipelines without distillation from proprietary models and explore large-scale synthetic data to identify critical data gaps, particularly in detailed video understanding. To bridge these gaps, we release 2.8M human-labeled instances of fine-grained video question-answer pairs and spatio-temporally grounded video captions. Additionally, we introduce PLM–VideoBench, a suite for evaluating challenging video understanding tasks focusing on the ability to reason about ''what'', ''where'', ''when'', and ''how'' of a video. We make our work fully reproducible by providing data, training recipes, code & models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：
    *   当前高性能的视觉语言模型（VLM）多为闭源，其训练数据、模型设计、训练细节不公开，严重阻碍了科学进步的可度量性。
    *   开源社区为了追赶闭源模型，普遍采用从黑盒专有模型蒸馏（即用闭源模型生成训练标签）的方式。这种做法虽然在基准测试上效果显著，但无法区分性能提升是源于方法创新还是对评估集的“污染”，导致对“从零训练VLM”方法的有效性产生根本性误解。
*   **核心问题**：
    *   研究社区缺乏一个完全不依赖专有模型蒸馏的、完全开放可复现的VLM训练框架，来透明地衡量科学进步。同时，标准的训练数据与合成数据在详细的视频理解（如时空推理、细粒度活动理解）方面存在关键缺口。
*   **整体含义**：
    *   本文旨在通过构建一个完全开放、可复现的**感知语言模型（PerceptionLM, PLM）**，重新审视不依赖专有模型蒸馏的标准训练流程的有效性，并通过发布大规模高质量人工标注数据集和全新基准，填补精细视频理解的数据空白，为该领域的透明研究奠定坚实基础。

### 2. 论文提出的方法论

*   **核心思想**：
    *   构建一个从数据到训练流程完全透明、不带入任何专有模型偏差的视觉语言模型框架，系统性分析合成数据的缩放规律，定位其局限性，并通过高质量人工标注数据集来弥补关键能力缺口。
*   **关键技术细节与流程**：
    *   **模型架构**：PLM由一个预训练的感知编码器（Perception Encoder）+ 一个2层MLP连接器 + Llama 3语言解码器（1B/3B/8B）构成。支持动态图像切片（最高36块）和视频帧采样（最高32帧），并通过2x2池化压缩视觉token。
    *   **三阶段训练流程**：
        1.  **阶段1（对齐热身）**：冻结视觉编码器和LLM，仅在约1M合成图像-描述对上训练连接器。
        2.  **阶段2（大规模中训练）**：在约64.7M样本的混合合成数据上训练整个模型，以建立基础视觉理解能力。
        3.  **阶段3（监督微调）**：在约19.1M高质量、多样化的数据混合（包含现有人工标注数据和自建数据）上，以更高分辨率和更多帧数进行微调，聚焦于复杂任务。
    *   **合成数据引擎**：完全使用开源模型（如Llama 3）为图像和视频生成描述和问答对。视频合成数据涉及场景检测、关键帧描述、视频描述生成、以及融合元数据（动作标签、时间戳）的LLM精炼。
    *   **核心数据贡献**：
        *   **PLM–FGQA**：一个280万规模的细粒度视频问答数据集。通过多阶段数据引擎（生成问题、用早期PLM作答、人工修正答案），聚焦于动作“如何”执行的细节，如移动方向、物体状态、空间关系等。
        *   **PLM–STC**：一个时空定位视频描述数据集。标注流程为：1）用SAM 2生成并人工精修活动对象的分割掩膜（masklet）；2）人工为对象在不同时间段的动作撰写局部化描述。
    *   **基准测试套件**：提出 **PLM–VideoBench**，包含：
        *   **细粒度问答（FGQA）**：评估对活动细节的精细理解。
        *   **智能眼镜问答（SGQA）**：模拟佩戴智能眼镜时的真实场景问答。
        *   **视频区域描述（RCap）**：根据掩膜和时间区间生成描述。
        *   **区域时间定位（RTLoc）**：根据掩膜和文本描述定位事件发生的时间段。
        *   **区域密集视频描述（RDCap）**：生成覆盖整个视频、带有时间戳的密集描述序列。

### 3. 实验设计

*   **数据集与场景**：实验覆盖了广泛的视觉感知场景。
    *   **评估基准**：论文在超过40个图像和视频基准上进行了评估。
    *   **图像基准**：涵盖文档/图表理解（DocVQA, ChartQA）、通用感知与推理（MMMU, VQAv2, OK-VQA）、抗幻觉能力（POPE）等。
    *   **视频基准**：涵盖视频描述（DREAM-1K）、短片问答（MVBench, NExT-QA）、长视频理解（EgoSchema）、细粒度视频问答（TemporalBench, MotionBench）、视频幻觉检测（VideoHallucer）等。
    *   **自有基准**：使用 **PLM–VideoBench**（FGQA, SGQA, RCap, RTLoc, RDCap）进行专项评估。
*   **对比方法**：
    *   **专有模型**：GPT-4o, Gemini 1.5 Pro, Gemini 2.0 Flash。
    *   **开源模型**：与同参数级别的模型进行了严格对比，包括Qwen2-VL/Qwen2.5-VL, InternVL2.5, LLaVA-OneVision, Molmo等。

### 4. 资源与算力

*   **训练资源**：论文详细列出了训练PLM跨不同规模模型的计算开销。
    *   **硬件**：实验主要使用 **NVIDIA H100 GPU**。
    *   **具体开销**：
        *   **PLM-1B**：阶段1（8 GPUs, 3小时）+ 阶段2（128 GPUs, 1.5天）+ 阶段3（128 GPUs, 2.0天）。
        *   **PLM-3B**：阶段1（8 GPUs, 4小时）+ 阶段2（128 GPUs, 3.0天）+ 阶段3（128 GPUs, 2.5天），**完整训练约需5.5天（128块H100）**。
        *   **PLM-8B**：阶段1（8 GPUs, 6小时）+ 阶段2（256 GPUs, 3.0天）+ 阶段3（256 GPUs, 2.5天）。
    *   **推理资源**：所有模型均可单卡高效推理：1B（24GB）、3B（40GB）、8B（80GB）。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了非常大规模的实验验证。
    *   **基准测试**：在超过40个图像和视频基准上对三个量级（1B, 3B, 8B）的PLM进行了全面评估。
    *   **缩放定律分析**：通过改变合成数据规模、LLM解码器大小（1B, 3B, 8B）、视觉编码器大小（3亿, 20亿）以及输入尺寸（分辨率/帧数），系统性地建立了合成数据的性能缩放定律。
    *   **消融实验**：针对所提出的每种数据（合成数据、PLM-STC、PLM-FGQA）以及训练阶段划分，进行了明确的消融分析，量化了每个组件对各类任务性能的增益（见文章表6、图7及附录）。
*   **充分性与公平性**：
    *   **充分性**：实验设计全面，覆盖了从底层数据影响、模型规模效应到广泛下游任务性能的各个层面。消融实验有力地支撑了其核心论点，即特定的精细化视频理解能力无法仅通过扩展合成数据获得，必须依赖高质量人工标注。
    *   **公平性**：对比基线广泛，涵盖了专有和开源模型，并明确标注了不同参数量级。在完全排除专有模型蒸馏影响的环境下进行对比，实验设置客观、公平。

### 6. 论文的主要结论与发现

*   PLM在完全不依赖专有模型蒸馏的前提下，在绝大多数图像和视频基准上，实现了与当前最先进的同级别开源模型（如InternVL2.5）相媲美的性能，并大幅超越了完全开放模型（如Molmo）。
*   **合成数据的缩放定律**：验证了合成数据在通用VLM任务（视频QA、OCR、自然图像QA）上的确符合幂律缩放关系，但在需要时空精细推理的“挑战性视频任务”上，缩放合成数据几乎无法带来提升（缩放指数仅为-0.03），揭示了合成数据的根本局限性。
*   **高质量人工标注数据的关键作用**：发布的PLM-FGQA和PLM-STC数据集有效弥补了合成数据的缺陷。消融实验证实，加入PLM-STC显著提升了时空定位和描述任务，而加入PLM-FGQA则显著改善了细粒度活动理解和抗幻觉能力。两种数据结合效果最佳。
*   **可复现性的成功实践**：论证了建立一个完全透明、可复现且具有竞争力的VLM训练流程是可行的，为社区追踪真正的科学进步提供了清晰的基线和框架。

### 7. 优点

*   **高度的可复现性与透明度**：论文的核心优点在于其设计哲学。整个流程从数据、模型、代码到训练配方完全公开，且坚决不使用任何专有模型，为学界提供了无偏见的、可信的基线。
*   **大规模高质量数据集建设**：创建的PLM-FGQA（280万）和PLM-STC（约47.6万训练样本）是同类数据集中规模最大的，填补了精细时空视频理解训练数据的空白，具有很高的研究价值。
*   **系统性的实验设计**：合成数据缩放定律的研究深入，清晰揭示了现有范式的瓶颈，为相关研究指明了方向。消融实验设计精炼，结论有力。
*   **全面的评估体系**：PLM-VideoBench的推出，与标准基准形成互补，专门针对现有模型在理解视频“when”、“where”、“how”上的能力短板，评估维度更为全面。

### 8. 不足与局限

*   **模型能力上限**：尽管具有竞争力，但PLM在部分基准上仍弱于专有模型（如GPT-4o）。例如，在MMMU、SGQA等涉及深层知识或复杂推理的任务上，其性能受限于基础LLM（Llama 3）的能力。
*   **长视频建模未深入探索**：作者承认，未在模型架构层面探索如自适应token压缩等长视频处理技术，导致其在长视频理解基准（如LVBench）上的性能并非最优，这是未来可改进的方向。
*   **数据聚焦的偏差**：模型数据混合主要围绕视觉感知设计，缺乏多步推理、机器人操作或广泛的“世界知识”数据，这可能在需要此类知识的应用场景中表现欠佳。模型在自建的SGQA任务上表现不佳也侧面印证了此点。
*   **实验成本限制**：由于训练大模型的成本高昂，论文未能进行重复实验以提供误差范围，这一点已由作者明确指出。

（完）
