---
title: Enhancing Temporal Understanding in Video-LLMs through Stacked Temporal Attention in Vision Encoders
title_zh: 通过视觉编码器中的堆叠时序注意力增强视频-LLM的时序理解
authors: "Ali Rasekh, Erfan Bagheri Soula, Omid Daliran, Simon Gottschalk, Mohsen Fayyaz"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2EJrs3gUO6"
tags: ["query:tf-vl-ag"]
score: 7.0
evidence: 通过堆叠时序注意力增强视频大语言模型的时序理解
tldr: 针对当前视频大语言模型时序动态理解不足的问题，该文在视觉编码器中引入堆叠时序注意力模块，使模型在视觉令牌送入LLM前即捕获帧间动作进展与关系，从而显著提升复杂时序理解任务性能。该设计改进了视频基础模型，为更精确的视频推理铺平道路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-001.webp\", \"caption\": \"\", \"page\": 5, \"index\": 1, \"width\": 485, \"height\": 487}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-002.webp\", \"caption\": \"\", \"page\": 5, \"index\": 2, \"width\": 485, \"height\": 484}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-003.webp\", \"caption\": \"\", \"page\": 5, \"index\": 3, \"width\": 485, \"height\": 487}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-004.webp\", \"caption\": \"\", \"page\": 20, \"index\": 4, \"width\": 1792, \"height\": 224}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2ejrs3guo6/fig-005.webp\", \"caption\": \"\", \"page\": 20, \"index\": 5, \"width\": 1792, \"height\": 224}]"
motivation: 现有Video-LLM架构在理解时序动态和动作序列上存在关键局限。
method: 在视觉编码器中加入堆叠时序注意力模块，事先融合帧间时序信息。
result: 在需要时序理解的任务上性能提升，克服现有架构局限。
conclusion: 编码器内置时序注意力是提高视频模型时序理解能力的有效途径。
---

## Abstract
Despite significant advances in Multimodal Large Language Models (MLLMs), understanding complex temporal dynamics in videos remains a major challenge. Our experiments show that current Video Large Language Model (Video-LLM) architectures have critical limitations in temporal understanding, struggling with tasks that require detailed comprehension of action sequences and temporal progression. In this work, we propose a Video-LLM architecture that introduces stacked temporal attention modules directly within the vision encoder. This design incorporates a temporal attention in vision encoder, enabling the model to better capture the progression of actions and the relationships between frames before passing visual tokens to the LLM. Our results show that this approach significantly improves temporal reasoning and outperforms existing models in video question answering tasks, specifically in action recognition. We improve on benchmarks including VITATECS, MVBench, and Video-MME by up to +5.5%. By enhancing the vision encoder with temporal structure, we address a critical gap in video understanding for Video-LLMs. Project page and code are available at: https://alirasekh.github.io/STAVEQ2/

---

## 论文详细总结（自动生成）

# 论文总结：通过视觉编码器中的堆叠时序注意力增强视频-LLM的时序理解

## 1. 研究动机与核心问题
- 多模态大语言模型（MLLMs）在图像理解与空间推理上已取得显著进展，但视频-LML（Video-LLM）在理解视频中的复杂时序动态（如动作序列、时间进展）方面仍存在关键局限。
- 当前主流Video-LLM（如Qwen2-VL、InternVideo2-Chat、LLaVA-NeXT-Video）在处理时序要求高的视频问答任务时表现不佳，例如无法准确区分“从左向右拉”与“从右向左拉”等方向性动作。
- 简单的零样本提示、提供候选类别标签甚至少量样本的上下文学习（in-context learning）均无法有效提升模型的时序推理能力，说明问题出在架构层面而非训练数据层面。
- 本文核心目标是通过在视觉编码器内部引入专用时序注意力模块，在视觉令牌进入LLM之前更好地建模帧间动作演进和时序关系，从而弥补Video-LLM在时序理解上的鸿沟。

## 2. 方法论：STAVEQ2模型
- **核心思想**：在Qwen2-VL的视觉编码器中加入“堆叠时序注意力（Stacked Temporal Attention, STA）”模块，使视觉特征在送入LLM前即包含显式时序建模，帮助LLM更有效地进行时序推理。
- **架构细节**（以公式描述）：
  - 输入视频被分割为帧，每帧划分为图像块，得到嵌入序列 \(X^{(0)} \in \mathbb{R}^{T \times N \times D}\)。
  - 每个Transformer块依次包含：**空间自注意力**（Intra-frame attention）→ **时序自注意力**（Inter-frame attention）→ MLP。
  - 空间注意力：对每帧独立计算查询、键、值，得到帧内增强特征 \(S^{(m)}_t\)。
  - 时序注意力：将同一空间位置的patch在所有帧上的特征序列进行跨帧注意力，计算时序注意力权重，得到时序增强特征 \(Z^{(m)}_i\)。
  - 每个块输出：\(X^{(m)} = \text{MLP}(\text{LN}(Z^{(m)})) + Z^{(m)}\)。
  - 时序注意力模块使用**1D旋转位置编码（RoPE）**注入时序位置信息，且采用**更少的注意力头**（相比空间注意力减少最多4倍）以保持参数高效。
- **训练策略**（两阶段微调）：
  1. 第一阶段：冻结预训练模型所有参数，仅训练新增的时序注意力模块及其对应层归一化，并将时序注意力输出投影层初始化为零，渐进式融入时序建模。
  2. 第二阶段：在视觉编码器和LLM中引入LoRA适配器（低秩适配），与时序注意力模块联合训练，使时序增强的视觉特征与LLM的语言推理能力对齐。
- 训练数据：使用WebVid数据集构建多轮问答（WebVid-QA），同时保持原始指令跟随能力。

## 3. 实验设计与基准
论文在多个任务和基准上评估模型，覆盖纯视觉动作识别、时序问答、视觉相似性匹配等多个维度。

### 3.1 数据集与下游任务
- **SSv2-T10**：从Something-Something v2数据集中筛选出10个时序对立的动作类（共14,462个视频），专门用于测试时序挑战性动作识别。
- **SSv2全数据集**：包含174类动作的22万视频，用于纯视觉动作识别（vision-only）。
- **SSv2-VSM**：基于SSv2-T10构建的视觉相似性匹配子集（8,471个样本），要求模型判断查询视频与两个参考视频中的哪一个（或都不）匹配。
- **通用视频理解基准**：
  - **VITATECS**：一个诊断性数据集，解耦脱离静态信息，评估6种时序概念（方向、强度、定位等）。
  - **MVBench**：涵盖20种不能单帧解决的视频任务。
  - **Video-MME**：综合多模态视频理解基准，包含6大视觉领域和不同时长。

### 3.2 对比方法
- **基础模型**：Qwen2-VL（2B/7B/72B）、Qwen2.5-VL（7B/72B）
- **其他Video-LLM**：InternVideo2-Chat、LLaVA-NeXT-Video、ST-LLM、TG-Vid、LLaVA-OneVision、VideoLLaMA2、LLaVA-Video、GPT-4o等。
- **纯视觉基线**：VideoMAE V2、MVD、InternVideo2（1B/6B）等。
- 对于部分扩展实验，还将STA应用于**InternVideo2.5-Chat**和**VideoRoPE**等模型。

## 4. 资源与算力
- 文中明确指出实验使用 **64 块 NVIDIA A100 GPU** 进行训练和评估。
- 未提供详细的单次训练时长或总GPU小时数，但肯定在大规模并行环境下进行。
- 由于计算资源限制，作者未进行从头预训练和超过72B参数规模的实验。

## 5. 实验数量与充分性
- **实验组数丰富**：
  - 多个模型尺寸（2B、7B、72B）和多种基础架构（Qwen2-VL、Qwen2.5-VL、InternVideo2-Chat、InternVideo2.5-Chat、VideoRoPE）上的STA增强实验。
  - 在7个以上的数据集/基准上评估，包括纯视觉动作识别、时序诊断、通用视频理解、视觉相似性匹配等。
  - 大量**消融研究**：
    - 时序注意力的头数缩放（1.0、0.5、0.25）。
    - 空间与时序注意力的顺序（空间优先 vs 时序优先）。
    - 时序注意力块的数量与位置（均匀分布、早期层、全部层）。
    - 数据集正负样本比例对相似性匹配的影响。
  - 评估设计**客观公正**：使用LLM-as-a-Judge（Qwen2-7B）进行开放式回答的自动评分，避免人工偏见；与多个强基线对比，精度提升具有统计意义。
- 实验设计基本覆盖了验证所提方法有效性的关键维度，结论可靠。

## 6. 主要结论与发现
- 在视觉编码器内嵌独特的时序注意力能够**显著提升Video-LLM的时序理解能力**。
- **纯视觉任务**：InternVideo2 1B + STA在SSv2全数据集上达到 **78.0%** 准确率，超越更大规模的InternVideo2 6B（77.5%），创下新SOTA。
- **通用视频理解**：
  - STAVEQ2在VITATECS、MVBench、Video-MME上全面超越Qwen2-VL和Qwen2.5-VL，例如STAVEQ2 72B在Video-MME上达 **73.9%/79.9%**（无/有字幕），超过GPT-4o和LLaVA-Video 72B。
  - 在VITATECS的“方向”和“序列”子项上提升明显，证明专门时序建模的作用。
- **视觉相似性匹配**：STAVEQ2 7B比Qwen2-VL 7B提升 **2.9%**，表明时序特征也可提升视觉比较任务。
- STA可推广至其他架构：应用于Qwen2.5-VL、VideoRoPE、InternVideo2.5-Chat均带来一致提升，显示出方法的通用性。

## 7. 方法亮点与实验设计优点
- **设计简洁高效**：在已有的空间注意力后添加轻量级时序注意力，几乎不改动原有模型架构，且通过减少注意力头控制参数量，实现参数高效。
- **直击痛点**：通过一系列诊断性实验（混淆矩阵、零样本与上下文学习失败）清晰揭示现有模型的时序缺陷，引出方法非常有说服力。
- **两阶段渐进式训练**：先初始化零输出、冻结主干，再联合LoRA微调，既保护了预训练空间表征，又平顺融入时序能力。
- **评测维度多样**：涵盖纯视觉动作识别、多模态视频问答、视觉相似性匹配等，从不同角度验证时序提升的有效性。
- **可复现性强**：提供代码和数据集处理流程，基于开源模型和数据集，易于社区复现和比较。

## 8. 不足与局限性
- **计算资源限制**：仅对最大72B模型进行微调，未验证在更大规模模型（如百B级）上的效果，也未进行从头预训练，可能限制了模型的潜力上限。
- **训练数据均来自公开数据集**：WebVid-QA虽经扩展，但可能仍无法完全覆盖真实世界中复杂多样的时序场景，泛化性有待进一步检验。
- **时序注意力配置实验仅在2B模型上完成**：较大的模型（7B/72B）的超参设置可能非最优，但文章未针对更大模型做消融。
- **在部分基准上的提升幅度较小**：如VITATECS某些子项相对于原模型仅提升不到1个百分点，虽然一致但不够显著。
- **未讨论推理速度或显存开销**：STA模块虽参数少，但可能增加一定的计算量，文中未提供推理延迟或训练吞吐量的比较。
- **模型仅适用于短/中长视频**：InternVideo2-Chat只能处理8帧，Qwen2-VL系虽可处理更长帧，但论文未明确测试极长视频（如数小时）场景下的效果。
- 社交影响未详细论述，但作为基础研究影响较小。

（完）
