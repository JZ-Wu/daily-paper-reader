---
title: "Video-R1: Reinforcing Video Reasoning in MLLMs"
title_zh: Video-R1：在多模态大语言模型中强化视频推理
authors: "Kaituo Feng, Kaixiong Gong, Bohao Li, Zonghao Guo, Yibing Wang, Tianshuo Peng, Junfei Wu, Xiaoying Zhang, Benyou Wang, Xiangyu Yue"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=a2JTVVvcEl"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 通过类R1强化学习强化多模态大语言模型中的视频推理
tldr: 受DeepSeek-R1启发，首次将R1范式应用于多模态大语言模型的视频推理，提出T-GRPO算法以增强时序建模，并融入图像推理数据缓解数据稀缺。在多个基准上取得领先的视频推理性能，证明了强化学习在激励视频理解能力方面的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 480, \"height\": 320}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 480, \"height\": 320}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 480, \"height\": 320}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-004.webp\", \"caption\": \"\", \"page\": 2, \"index\": 4, \"width\": 480, \"height\": 320}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-005.webp\", \"caption\": \"\", \"page\": 2, \"index\": 5, \"width\": 480, \"height\": 320}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-006.webp\", \"caption\": \"\", \"page\": 4, \"index\": 6, \"width\": 285, \"height\": 547}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-007.webp\", \"caption\": \"\", \"page\": 22, \"index\": 7, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-008.webp\", \"caption\": \"\", \"page\": 22, \"index\": 8, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-009.webp\", \"caption\": \"\", \"page\": 22, \"index\": 9, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-010.webp\", \"caption\": \"\", \"page\": 22, \"index\": 10, \"width\": 640, \"height\": 360}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-a2jtvvvcel/fig-011.webp\", \"caption\": \"\", \"page\": 22, \"index\": 11, \"width\": 640, \"height\": 360}]"
motivation: 现有MLLMs视频推理缺乏时序建模且高质量推理数据稀缺，限制复杂推理能力。
method: 提出T-GRPO算法加强时序信息利用，并混合图像推理数据训练Video-R1模型。
result: 在视频推理任务上显著超越基线，展现出强时序推理能力。
conclusion: Video-R1为视频推理提供了新的训练范式，提升了MLLMs的时序理解水平。
---

## Abstract
Inspired by DeepSeek-R1's success in eliciting reasoning abilities through rule-based reinforcement learning (RL), we introduce Video-R1 as the first attempt to systematically explore the R1 paradigm for incentivizing video reasoning within multimodal large language models (MLLMs). However, directly applying RL training with the GRPO algorithm to video reasoning presents two primary challenges: (i) a lack of temporal modeling for video reasoning, and (ii) the scarcity of high-quality video-reasoning data. To address these issues, we first propose the T-GRPO algorithm, which encourages models to utilize temporal information in videos for reasoning. Additionally, instead of relying solely on video data, we incorporate high-quality image-reasoning data into the training process. We have constructed two datasets: Video-R1-CoT-165k for SFT cold start and Video-R1-260k for RL training, both comprising image and video data. Experimental results demonstrate that Video-R1 achieves significant improvements on video reasoning benchmarks such as VideoMMMU and VSI-Bench, as well as on general video benchmarks including MVBench and TempCompass, etc. Notably, Video-R1-7B attains a 37.1\% accuracy on video spatial reasoning benchmark VSI-bench, surpassing the commercial proprietary model GPT-4o. All code, models, and data will be released.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，我将基于提供的论文内容，为您生成一份结构化、深入、客观的中文总结。

### **1. 论文的核心问题与整体含义**

*   **核心问题**：当前的多模态大语言模型在视频推理方面存在两个主要挑战：
    1.  **缺乏时序建模**：标准的强化学习算法（如GRPO）没有显式奖励时序推理能力，导致模型倾向于通过分析单帧图像走“捷径”，而非基于视频的时间顺序进行深度推理。
    2.  **高质量推理数据稀缺**：现有视频训练数据多集中在简单的识别任务上，缺乏需要强推理能力和长推理链的高质量样本，限制了强化学习的效果。
*   **整体含义**：本文首次系统性地探索了将DeepSeek-R1的规则化强化学习范式应用于视频推理领域，旨在激发多模态大语言模型通过长思维链进行复杂时序推理的能力。

### **2. 论文提出的方法论**

论文的核心思想是弥补现有方法在时序建模和训练数据两方面的不足，提出了 **T-GRPO 算法** 和 **混合数据训练策略**。

*   **T-GRPO 算法 (Temporal Group Relative Policy Optimization)**
    *   **核心思想**：显式地鼓励模型利用视频的时序信息进行推理。它通过对比模型在**时序正常帧**和**随机打乱帧**（破坏时序关系）上的表现来提供额外的奖励信号。
    *   **技术细节**：
        1.  对于同一个问题，模型会看到两组输入：一组是时序正常排列的视频帧，另一组是随机打乱次序的视频帧。
        2.  模型对两组输入分别生成一组回答，并计算各自组内的正确答案比例 `p` 和 `\~p`。
        3.  定义一个**时序奖励 `r_t`**：仅当正常组的正确比例 `p` **不低于** 打乱组的比例 `\~p` 时，为正常组中的每个正确答案赋予一个正的奖励 `α`（本文设为0.3）。这个设计迫使模型只有在利用时序信息时才能获得额外奖励。
        4.  **最终奖励**：将正确性奖励、格式奖励和时序奖励 `r_t` 结合，再用GRPO算法进行策略优化。T-GRPO仅对视频数据生效。

*   **数据集构建**
    *   **Video-R1-CoT-165k**：用于监督微调冷启动，包含由大模型生成的思维链推理过程。
    *   **Video-R1-260k**：用于强化学习训练，是一个混合数据集，主要由视频数据和图像数据构成。
        *   **视频数据 (44%)**：用于训练时序理解与推理能力。
        *   **图像数据 (56%)**：包含通用、图表、OCR、数学、知识、空间等类型的推理数据，用于引导和泛化模型的通用推理技能，缓解视频推理数据稀缺的问题。
    *   **奖励函数设计**：针对不同题型（选择题、数值题、OCR、自由格式、回归题）设计了清晰的、基于规则的奖励函数，以保证RL训练的稳定和有效。

*   **训练策略**
    *   **两阶段训练**：首先在 `Video-R1-CoT-165k` 上进行SFT冷启动，得到基础模型；然后在 `Video-R1-260k` 上使用T-GRPO进行强化学习训练。
    *   **长度奖励**：引入一个额外的奖励机制，鼓励模型在正确回答的前提下，生成长度适中（320-512 tokens）的推理过程，旨在平衡深度思考和过度思考。

### **3. 实验设计**

*   **数据集与基准测试**：在6个标准基准上进行评估，分为两类。
    *   **视频推理基准**：VSI-Bench, VideoMMMU, MMVU（多重选择题部分），主要评估推理能力。
    *   **通用视频理解基准**：MVBench, TempCompass, VideoMME，包含感知和推理的混合任务。
*   **对比方法**：将提出的Video-R1-7B与多种领先模型进行了对比，包括：
    *   **商业闭源模型**：GPT-4o。
    *   **开源视频MLLMs**：LLaMA-VID, VideoLLaMA2, LongVA-7B, VILA-1.5 (8B/40B), Video-UTR-7B, LLaVA-OneVision-7B, Kangaroo-8B。
    *   **基线模型**：基础模型 Qwen2.5-VL-7B-Instruct 及其仅做SFT冷启动的版本 `Qwen2.5-VL-7B-SFT`，均在多个帧数设定下（16/32/64帧）进行测试。
*   **消融实验**：设计了三种变体模型来验证各组件的有效性。
    *   `Video-R1-7B-wo-image`：移除所有图像数据，仅用视频数据训练。
    *   `Video-R1-7B-wo-temporal`：用原始GRPO替换T-GRPO算法。
    *   `Video-R1-zero`：跳过SFT冷启动，直接进行RL训练。

### **4. 资源与算力**

*   **训练硬件**：使用了最多 **8块 NVIDIA A100 (80GB) GPU**。
*   **训练时长**：SFT阶段每轮约需 **40小时**；RL阶段，训练1000步约需 **15小时**。由于算力限制，只在RL阶段训练了1000步便观察到显著提升。

### **5. 实验数量与充分性**

*   **实验组数**：实验设计充分且多样，覆盖了6个基准测试、多种帧数设定下的评估，并设置了3组消融实验来验证方法的关键组成部分。此外，还分析了训练曲线、时序奖励的效果、RL步数扩展（1k vs 10k步）和超参数（`α`）的敏感性。
*   **充分性与公平性**：实验对比是公平和客观的。
    *   **对比基线广泛**：涵盖了当时主流的开源模型和商业模型（GPT-4o），并在相同帧数下与自身基线和SFT版本对比。
    *   **消融实验清晰**：明确证明了图像数据融和、T-GRPO算法和SFT冷启动三者各自对最终性能的贡献，实验设计逻辑清晰。
    *   **量化分析**：不仅报告了最终分数，还通过计算“时序推理响应百分比”量化了T-GRPO带来的行为改变。不过，由于训练MLLMs计算成本高昂，**论文未提供标准差或多次运行的统计显著性检验**，这是一个小的遗憾。

### **6. 论文的主要结论与发现**

*   **Video-R1模型显著有效**：通过结合T-GRPO算法和图像-视频混合数据训练，Video-R1在所有视频推理和通用视频理解基准上均取得了显著提升。
*   **RL远优于SFT**：单纯的SFT冷启动甚至可能导致性能下降，而基于RL的Video-R1在仅1k步训练后就实现了巨大的性能飞跃，证明了RL在解锁模型泛化推理能力上的关键作用。
*   **时序建模至关重要**：T-GRPO算法能有效引导模型利用时序信息（75.0% 对比 60.2%的时序推理响应率），显著优于不使用时序感知的版本。
*   **图像数据对视频推理有益**：引入高质量的图像推理数据，能够有效指导模型的通用推理技能，缓解视频推理数据的瓶颈，提升最终性能。
*   **小模型超越大模型**：7B参数的Video-R1在具有挑战性的视频空间推理基准VSI-Bench上，以37.1%的准确率超越了商业闭源模型GPT-4o和许多参数量更大的模型。

### **7. 优点**

*   **新颖性**：首次将R1推理范式成功拓展到视频领域，填补了研究空白。
*   **方法论清晰有效**：提出的T-GRPO算法巧妙且直观地解决了视频推理中的时序建模难题，通过对比有序/乱序输入提供了一个很强的学习信号，无需复杂的标注。
*   **数据策略务实**：引入图像推理数据来弥补视频推理数据稀缺的策略非常务实且高效，展示了跨模态知识迁移的巨大潜力。
*   **实验扎实**：实验在多个权威基准上进行，消融实验设计严谨，分析深入（如“aha moment”、时序推理比例分析），充分验证了各个方法的有效性。

### **8. 不足与局限**

*   **训练帧数有限**：模型目前仅在16帧下训练，可能限制了其对长视频或需要捕捉长距离时序依赖关系的任务的处理能力。
*   **计算开销**：T-GRPO算法需要为每个问题处理有序和乱序两组输入，带来了额外的计算开销。
*   **响应长度控制较简单**：长度奖励机制对所有样本一视同仁，未能根据问题复杂度动态调整期望的推理长度。
*   **图像到视频的迁移方法粗粒度**：图像数据仅被简单混入训练集，未来可以设计更精细的迁移学习方法。
*   **奖励模型依赖规则**：当前使用了针对不同任务的规则化奖励函数，未来可探索能提供更一致、可扩展奖励信号的通用视频奖励模型。

（完）
