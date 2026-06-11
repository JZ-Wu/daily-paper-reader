---
title: "DynaMind: Reasoning over Abstract Video Dynamics for Embodied Decision-Making"
title_zh: DynaMind：面向具身决策的抽象视频动态推理
authors: "Ziru Wang, Mengmeng Wang, Jade Dai, Teli Ma, Guo-Jun Qi, Yong Liu, Guang Dai, Jingdong Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ziDKPXJBYL"
tags: ["query:tf-vl-ag"]
score: 5.0
evidence: 提出基于自适应帧评分的视频动态推理框架，用于具身决策
tldr: 针对具身智能体需平衡语言指令简洁性与视频内容丰富性的挑战，提出DynaMind框架，通过自适应FrameScorer评估帧重要性并提取时空动态表示，增强决策推理能力，在具身决策任务中验证了其有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1759, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 815, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1735, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 810, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 831, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 855, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 990, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1082, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1025, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1028, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 547, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 969, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1299, \"height\": 1010, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 970, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1034, \"height\": 333, \"label\": \"Table\"}]"
motivation: 现有方法难以平衡语言命令简洁性与视频丰富性，限制了具身决策。
method: 提出DynaMind，设计自适应FrameScorer评估帧重要性，提取动态表示进行推理。
result: 在具身决策任务中，DynaMind提升了基于视频的决策准确性。
conclusion: DynaMind为视频动态推理和具身智能体提供了一种有效的表示学习框架。
---

## Abstract
Integrating natural language instructions and visual perception with decision-making is a critical challenge for embodied agents. Existing methods often struggle to balance the conciseness of language commands with the richness of video content. To bridge the gap between modalities, we propose extracting key spatiotemporal patterns from video that capture visual saliency and temporal evolution, referred to as dynamic representation. Building on this, we introduce DynaMind, a framework that enhances decision-making through dynamic reasoning. Specifically, we design an adaptive FrameScorer to evaluate video frames based on semantic consistency and visual saliency, assigning each frame an importance score. These scores are used to filter redundant video content and synthesize compact dynamic representations. Leveraging these representations, we predict critical future dynamics and apply a dynamic-guided policy to generate coherent and context-aware actions. Extensive results demonstrate that DynaMind significantly outperforms the baselines across several simulation benchmarks and real-world scenarios.

---

## 论文详细总结（自动生成）

好的，我将以资深学术论文分析助手的身份，使用中文、以Markdown形式，对提供的论文《DynaMind: Reasoning over Abstract Video Dynamics for Embodied Decision-Making》进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

-   **研究背景与动机**：具身智能体在执行任务时，需要将简洁、抽象的自然语言指令与丰富、复杂的视觉（视频）感知信息相结合来进行决策。现有方法（如视觉-语言-动作模型或语言到视频生成模型）往往试图在这两种模态间建立直接、僵硬的映射，这难以弥合语言简洁性与视频细节丰富性之间的巨大鸿沟。
    -   一个核心的矛盾在于，单个语言指令可以对应多种不同的视频执行过程，这暴露了依赖语言信息来弥补视频复杂性的局限性。
-   **核心问题**：如何有效地整合语言指令和视频内容，以提升具身智能体的决策能力，而非在两者之间进行简单的对齐或转换。
-   **整体含义与核心思想**：本文提出，解决模态差距的关键不在于进一步细化或分解语言，而在于从视频侧进行**抽象**。由此，作者提出了**DynaMind**框架，其核心思想是将视频转化为一种名为**动态表示**的高层时空特征序列。这种动态表示能捕捉视觉显著性和时序演化，过滤掉冗余信息。以此为桥梁，DynaMind通过预测未来的动态来做决策，而非像以往方法那样逐帧生成视频图像，从而实现从“视频生成”到“动态推理”的范式转换。

### 2. 论文提出的方法论

DynaMind是一个端到端训练框架，包含三个紧密集成的模块，整体架构如下图所示（文字描述）：

-   **核心思想**：将原始视频抽象为紧凑的动态表示序列，然后基于历史动态表示预测未来动态，最后根据预测的未来动态来指导动作决策。

-   **关键技术模块与流程**：
    1.  **视频动态抽象**：
        -   **自适应帧评分器**：该模块的核心是一个可训练的自适应FrameScorer，它是一个带Sigmoid激活的双层全连接网络。它根据每帧的**语义一致性**（与语言指令的相关性）和**视觉显著性**（外观的独特程度）为视频每一帧打分，输出一个0到1之间的重要性分数 `wt`。
        -   **滑动窗口融合**：视频被划分为不重叠的窗口（`C` 帧/窗口），在每个窗口内，根据FrameScorer给出的重要性分数，对帧的特征向量进行加权平均，得到一个窗口级别的动态表示向量 `hn`。
            -   公式：`hn = (∑ wt * et) / (∑ wt)`，其中 `et` 是第 `t` 帧经过CNN编码后的特征。
        -   所有窗口的动态表示向量按顺序组合，形成该视频的全局动态表示序列 `H`。
        -   **训练监督**：FrameScorer通过两个软损失项进行优化，不依赖显式的关键帧标注：
            -   **语义一致性损失（Lconsistency）**：最大化动态表示序列 `H` 与语言嵌入 `q` 之间的余弦相似度。
            -   **视觉显著性损失（Lsaliency）**：确保`H`与语言的相似度，高于窗口内最高方差帧（纯视觉显著帧）的序列与语言的相似度，迫使模型学习有语义关联的显著帧，而非单纯的视觉噪音。
    2.  **视频动态推理**：
        -   采用一个**自回归Transformer模型**（简称Tformer），该模型结合了自注意力（带因果掩码）和交叉注意力机制。
        -   输入：历史动态表示序列 `H_{1:n-1}`、语言嵌入 `qi` 和时间位置编码。
        -   输出：预测的未来动态表示序列 `\tilde{H}_{2:n}`。
        -   **训练**：最小化预测的 `\tilde{H}` 与由真实未来帧抽象出的真实 `H` 之间的均方误差（MSE）。
    3.  **动态引导的动作决策**：
        -   同样使用一个Transformer模型（与推理模块结构相同但参数独立）。
        -   输入：历史帧特征、历史动作序列，以及一个代表“目标”的特殊token `gt`。这个 `gt` 在训练早期可能来自真实未来帧特征（以稳定训练），后期和推理时则来自**视频动态推理模块**预测的未来动态表示。
        -   输出：预测的动作序列。
        -   **训练**：对于离散动作使用二元交叉熵损失，对于连续动作使用MSE损失，最小化预测动作与真实动作的差异。

### 3. 实验设计

-   **数据集/场景**：
    -   **模拟基准测试**：
        1.  **LOReL Sawyer**：基于MetaWorld的桌面级机械臂操作任务，包含6个子任务（如开关抽屉、旋转水龙头、移动杯子）。数据由伪专家和回放缓冲区数据混合生成，带有自然语言标注，难度在于数据的非最优性和随机性。
        2.  **Franka Kitchen**：更具挑战性的长序列操作环境，要求智能体顺序完成4个子任务（例如，开微波炉、激活灶台、开柜子）。
        3.  **BabyAI**：网格世界中的导航任务，要求智能体根据复杂指令执行多步骤导航。特别评估了在**低数据量**（仅用0.1%的专家数据）条件下的表现。
    -   **真实世界场景**：使用Franka Research 3机械臂，设计了5个任务（按按钮、捡起牛奶盒、推盒子、放零食进篮子、叠毛巾），每个任务仅用20个演示进行训练，验证其在小样本真实环境下的有效性。

-   **对比方法**：
    -   **朴素模仿学习**：Vanilla BC、决策Transformer（DT）。
    -   **多模态对齐方法**：GR-1（视频预测预训练+动作微调）、MT-R3M（在GR-1基础上引入R3M视觉编码器进行显式对齐）。
    -   **语言分解方法**：LISA（将指令分解为语义技能再执行）、SkillDiffuser（生成技能条件视频帧，再用逆动力学模型预测动作）。

### 4. 资源与算力

-   论文中提到，训练效率对比实验（Table 4）是在**NVIDIA A800 GPU**上进行的，使用了统一的批量大小（64）。实验比较了DynaMind与LISA和SkillDiffuser的参数量、GPU显存占用和最终成功率。
-   除此之外，论文未明确提及其他实验中使用的具体GPU数量、单次训练总时长或总能耗。这是一个信息缺失点。

### 5. 实验数量与充分性

-   **实验数量**：实验设计较为充分，覆盖了：
    -   **3个不同的模拟环境**（LOReL Sawyer, Franka Kitchen, BabyAI）和**1个真实世界环境**，与**6个基线方法**进行了全面比较。
    -   **消融实验**：针对动态抽象模块（替换为等权、随机权重、随机选帧）、动态推理模块（调整推理间隔 `C`）、动作决策模块（移除动态引导、语言引导对比、移除历史动作）分别进行了消融研究。
    -   **分析性实验**：包括训练效率对比、指令泛化测试（未见过的名词/动词/人类指令）、数据规模扩展性测试、在更复杂/组合任务上的迁移能力测试、互信息可视化分析。
-   **客观性与公平性**：
    -   实验设计的客观性和公平性较高。作者在LOReL Sawyer上确保模型参数量与基线模型相当，并使用相同的视觉和语言编码器架构。
    -   在数据稀缺性等多个维度进行了评估，测试了方法的鲁棒性。

### 6. 论文的主要结论与发现

-   **性能显著提升**：DynaMind在所有模拟基准测试（LOReL Sawyer, Franka Kitchen, BabyAI）和真实世界任务中，成功率均显著优于各类基线方法，尤其是在长序列任务和低数据量场景下优势更明显。
-   **范式有效性**：结果表明，将视频抽象为高层动态并进行推理，比直接对齐语言和视频、或分解语言指令更有效，有效弥合了模态间的差距。
-   **动态抽象的作用**：自适应FrameScorer能有效识别并加权任务相关的关键帧，过滤冗余信息，其学习到的动态表示与语言指令的相关性（互信息）随训练稳步提升。
-   **泛化能力**：DynaMind展现出强大的泛化能力，不仅能理解未经训练的指令表述，还能将学习到的动态表示迁移到更复杂或组合的任务中，表现出超越训练任务的泛化潜力。
-   **效率与性能的平衡**：与一些高计算成本的基线方法相比，DynaMind在参数量和计算开销较小的情况下，取得了更高的成功率。

### 7. 优点

-   **新颖的视角转换**：创新性地从“抽象视频”而非“细化语言”的角度来解决模态差异问题，为具身智能研究提供了新思路。
-   **全面且合理的模型设计**：三个模块（抽象、推理、决策）分工明确、结构紧凑，端到端训练。特别是无监督的自适应帧评分器设计巧妙，通过软约束提升了模型的可解释性。
-   **扎实的实证验证**：实验覆盖了操作、导航等多种任务环境，从模拟到真实世界，并充分测试了在数据匮乏、指令泛化等挑战性条件下的性能，结论可信度高。
-   **良好的泛化性能**：不仅在同等条件下性能优异，在任务迁移和指令泛化方面也展现出巨大潜力，表明其学习到的动态表示具有较好的通用性。

### 8. 不足与局限

-   **固定的推理间隔**：模型使用固定的窗口大小 `C` 进行动态抽象和推理，这可能不是所有任务的最优解。对于需要快速反应的精细操作或节奏变化很大的任务，固定的粒度可能不够灵活。
-   **算力细节缺失**：论文未报告除效率对比实验外的其他主要实验的算力详情（如总GPU时、训练时长），使得其方法在大规模应用上的成本难以全面评估。
-   **真实世界实验的规模**：真实世界实验的任务（5个）和每任务的演示数量（20个）相对有限，其在更广泛、更复杂的真实场景下的稳健性仍有待进一步验证。
-   **架构探索有限**：虽然进行了架构消融，但对于Transformer的层数、头数等超参数的探索不够深入，仅验证了共享参数和使用预训练编码器的负面影响。

（完）
