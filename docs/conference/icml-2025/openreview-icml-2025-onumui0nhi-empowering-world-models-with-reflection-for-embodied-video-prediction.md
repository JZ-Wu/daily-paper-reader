---
title: Empowering World Models with Reflection for Embodied Video Prediction
title_zh: 以反思赋能世界模型进行具身视频预测
authors: "Xiaowei Chi, Chun-Kai Fan, Hengyuan Zhang, Xingqun Qi, Rongyu Zhang, Anthony Chen, Chi-Min Chan, Wei Xue, Qifeng Liu, Shanghang Zhang, Yike Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=onumui0nHi"
tags: ["query:tf-vl-ag"]
score: 5.0
evidence: 利用预训练视觉语言模型和视频生成模型，通过反思策略增强视频预测，属于多模态视频推理
tldr: 现有具身视频预测方法主要依赖视频生成模型，但缺乏对物理世界动态的深层理解，导致在多步预测和分布外场景下表现不佳。为此，本文提出反思生成（RoG）框架，在预测过程中引入中间推理步骤，融合视觉语言模型的语义理解与视频生成模型的动态生成能力，有效提升了预测的鲁棒性和准确性。在EVA-Bench等基准上的实验表明，RoG在长时域预测和场景泛化方面优于现有方法，为构建更通用的世界模型提供了新方向。该研究为具身智能和视频推理领域提供了重要的方法借鉴。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 800, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1737, \"height\": 1216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1759, \"height\": 1223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1737, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 1170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1723, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1669, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1502, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 1780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 918, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 843, \"height\": 1004, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1707, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 824, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1075, \"height\": 963, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1774, \"height\": 762, \"label\": \"Table\"}]"
motivation: 现有模型缺乏鲁棒理解，难以进行多步预测或处理分布外场景。
method: 提出RoG策略，利用预训练VLM和视频生成模型进行中间推理。
result: 在EVA-Bench上展示了增强的多步预测和OOD处理能力。
conclusion: 反思生成策略提升了具身视频预测的世界模型能力。
---

## Abstract
Video generation models have made significant progress in simulating future states, showcasing their potential as world simulators in embodied scenarios. However, existing models often lack robust understanding, limiting their ability to perform multi-step predictions or handle Out-of-Distribution (OOD) scenarios.  To address this challenge, we propose the Reflection of Generation (RoG), a set of intermediate reasoning strategies designed to enhance video prediction.  It leverages the complementary strengths of pre-trained vision-language and video generation models, enabling them to function as a world model in embodied scenarios. To support RoG, we introduce Embodied Video Anticipation Benchmark(EVA-Bench), a comprehensive benchmark that evaluates embodied world models across diverse tasks and scenarios, utilizing both in-domain and OOD datasets. Building on this foundation, we devise a world model, Embodied Video Anticipator (EVA), that follows a multistage training paradigm to generate high-fidelity video frames and apply an autoregressive strategy to enable adaptive generalization for longer video sequences. Extensive experiments demonstrate the efficacy of EVA in various downstream tasks like video generation and robotics, thereby paving the way for large-scale pre-trained models in real-world video prediction applications. The video demos are available at https://sites.google.com/view/icml-eva.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

*   **研究动机与背景**
    *   视频生成模型在具身场景中展现出作为世界模拟器的潜力，可辅助机器人规划、自动驾驶仿真等。
    *   现有模型存在明显短板：缺乏对当前及未来状态的**深层语义理解**，导致预测能力受限。
    *   主要痛点包括：只能进行**固定帧数的单轮预测**，无法自适应判断任务是否完成；**无法检测生成质量**，依赖人工纠错；在**分布外（OOD）场景**下性能严重退化。

*   **核心问题**
    *   如何为视频预测世界模型注入**理解与推理能力**，使其能进行**多步、长时域的自适应预测**，并有效应对**分布外情况**。

## 2. 论文提出的方法论

*   **核心思想：反思生成（Reflection of Generation, RoG）**
    *   将视频预测过程分解为**理解模块**（基于预训练视觉语言模型 VLM）与**生成模块**（基于预训练视频扩散模型 VDM），在二者之间引入**中间推理步骤（反思）**。
    *   世界模型在生成视频片段后，会自我检查任务是否完成，根据判断结果决定 **“扩展生成”、“重新生成”或“输出”**，从而实现迭代式自纠正。

*   **关键技术与公式**
    *   **视频预测层次定义**：将视频预测分为帧级、任务级和串行任务级。本文聚焦于**任务级预测**，即完成一条高层指令（如“拿起书”）所需的完整帧序列。
    *   **RoG 世界模型化形式**：
        \[
        W_{\text{RoG}}(O_0, I) = \text{Reflect}(\mathbf{H}) \cdot P(\{O_t\}_{t=1}^T | O_0, I, \mathbf{H})
        \]
        其中 \(O_0\) 为初始观测，\(I\) 为指令，\(\mathbf{H}\) 为编码状态。Reflect 函数输出三种动作：Extend、Regenerate 或 Output。
    *   **EVA 模型架构**：
        *   以 7B VLM（ChatUniVi）作为理解骨干，1.5B VDM（DynamiCrafter 微调）作为生成骨干。
        *   引入**交互令牌**（如 `<image>`, `<IMG_P>`）桥接视觉与文本输入。
        *   设计**生成适配器（Cross-Attention Generation Adapter）**，通过线性变换和交叉注意力将 VLM 隐状态对齐到 VDM 的文本条件空间，并用扩散去噪损失训练。
        *   提出**集成 LoRA（Ensemble-LoRA）**，为不同领域（人类第一视角、真实机器人、仿真机器人）分别训练低秩适配模块，通过任务令牌控制的门控进行混合，实现高效多域泛化。
    *   **分块自回归帧扩展**：每次生成 16 帧视频，用 VLM 判断任务完成状态。若未完成，则取最后若干关键帧作为下一轮输入继续生成，拼接形成长视频。

*   **基准与任务分解**
    *   构建 **EVA-Bench** 基准，将 RoG 分解为四类元任务：
        1.  **Action-Description**：根据视频简述动作。
        2.  **Finish-Thinking**：判断任务是否完成。
        3.  **How-To**：将指令转化为视频和文本指导。
        4.  **Next-Step**：预测下一步的动作并生成对应视频。

## 3. 实验设计

*   **数据集与场景**
    *   **训练数据（EVA-Instruct）**：共 500K 对问答，源自 Open-X-Embodiment、Ego4D、Ego-Exo4D 和 CALVIN，覆盖人类第一视角、真实机器人、仿真机器人。
    *   **评估基准（EVA-Bench）**：手工筛选 125 个高质量样本，涵盖烹饪、修理自行车、COVID 检测、桌面操作等场景，并专门设计了**分布外（OOD）评估样本**。

*   **对比方法**
    *   **视频问答（VQA）**：零样本 VLM（ChatUniVi、LLaVA 系列、Qwen2、GPT-4o）以及经过微调的 VLM。
    *   **视频生成**：DynamiCrafter、其全量微调版本、EVA 的生成模块（EVA-Gen）。
    *   **两阶段模型（VLM→VDM）**：不同 VLM+EVA-Gen 的组合、EVA 的二阶段消融版本（EVA-2Stage）。
    *   **机器人规划**：AVDC、不含 RoG 的 EVA 版本。

*   **评估指标**
    *   **语言理解**：BLEU、METEOR、ROUGE-L、CIDEr、SPICE、CLIPScore、GPT-4o 评判得分。
    *   **视频质量**：Subject Consistency (SC)、Background Consistency (BC)、Motion Smoothness (MS)、Fréchet Video Distance (FVD)、Goal Completion Estimation (GCE)。
    *   **机器人任务**：在 RT-1 和 CALVIN 环境下的任务成功率（人工评估与仿真环境评估）。

## 4. 资源与算力

*   **训练硬件**：使用 **8 张 NVIDIA A800 GPU**。
*   **关键训练参数**：
    *   EVA 扩散模型：训练步数 20,000，批量大小 4，学习率 0.0001。
    *   VLM 第一阶段：批量大小 128，学习率 2e-3。
    *   VLM 第二阶段：批量大小 128，学习率 2e-5。

## 5. 实验数量与充分性

*   **实验组数丰富**：
    *   **VQA 理解实验**（Table 1）：对比 10 余种模型变体，涵盖零样本与微调版本，评估指标超过 7 项。
    *   **视频生成质量实验**（Table 2）：对比 10 种生成式框架，评估 5 项视频质量指标。
    *   **图文交错生成实验**（Table 3）：针对 How-To 和 Next-Step 任务，对比 4 种模型。
    *   **机器人规划评估**（Table 4 & 5）：在 RT-1（域内+OOD）和 CALVIN（视频级+仿真级）进行成功率测试，并对是否使用 RoG 进行消融对比。
*   **实验充分性**：实验覆盖了理解、生成、理解-生成联合、下游机器人任务等多个层面，且同时包含域内与 OOD 场景，多指标、多基线对比较为充分。
*   **客观性与公平性**：采用了统一的基准 EVA-Bench，并在相同数据微调条件下对比了不同 VLM 底座；生成模型部分也严格固定输入条件对比，评估方式较为客观。

## 6. 主要结论与发现

*   **RoG 显著提升具身视频预测**：通过引入中间反思步骤，模型不仅能生成高质量视频，还能自主判断任务完成状态，实现长序列扩展。
*   **EVA 模型在理解-生成联合任务上达到最优**：在 How-To 和 Next-Step 任务中，EVA 的 EVA-Score 遥遥领先于二阶段或单一生成模型，说明理解能力的增强直接带来生成质量的提升。
*   **泛化能力突出**：在 OOD 场景和机器人规划任务（RT-1、CALVIN）中，EVA 相比基线方法成功率高 20% 以上，且 RoG 模块贡献显著。
*   **专用基准 EVA-Bench 有效**：细粒度的任务分解与综合指标能更全面地反映具身世界模型的能力。

## 7. 优点

*   **创新性强**：首次将“反思”机制引入具身视频预测，将“理解-生成-反思”形成闭环，具备模块化和可解释性。
*   **方法设计精巧**：
    *   集成 LoRA 用极少的额外参数实现了多领域的高质量生成。
    *   分块自回归策略巧妙解决了长视频生成的连贯性与错误累积问题。
*   **评估体系完善**：自建 EVA-Bench 涵盖多任务、多指标和 OOD 场景，并延伸到真实机器人规划，验证维度全面。
*   **实际应用价值高**：在真实机器人指令执行上取得高成功率，为世界模型在具身智能中的落地提供了新思路。

## 8. 不足与局限

*   **复杂场景下的感知挑战**：论文提到对于透明物体（如玻璃门）的“开/关”任务仍比较困难，说明模型对特殊材质的理解与生成仍有局限。
*   **任务复杂度边界**：实验主要集中在单任务或简单子任务串联，对于极长周期、复杂操作间存在强依赖的任务表现未知。
*   **数据集偏差风险**：EVA-Instruct 主要基于现有具身数据集构建，高质量的 OOD 样本依赖人工标注，覆盖面可能有限。
*   **计算资源需求**：涉及 7B VLM 和 1.5B VDM 的联合训练与推理，离轻型化边缘部署仍有距离。

（完）
