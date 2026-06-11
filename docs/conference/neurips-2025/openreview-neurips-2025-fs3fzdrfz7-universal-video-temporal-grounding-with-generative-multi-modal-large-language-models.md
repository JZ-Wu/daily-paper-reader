---
title: Universal Video Temporal Grounding with Generative Multi-modal Large Language Models
title_zh: 使用生成式多模态大语言模型的通用视频时序定位
authors: "Zeqian Li, Shangzhe Di, Zhonghua Zhai, Weilin Huang, Yanfeng Wang, Weidi Xie"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FS3FzdrFZ7"
tags: ["query:tf-vl-ag"]
score: 10.0
evidence: UniTime利用生成式多模态大语言模型进行通用视频时序定位，直接匹配需求1。
tldr: 现有视频时序定位模型常局限于特定领域或时长。本文提出UniTime，利用生成式多模态大语言模型的强大理解力实现通用视频定位。通过引入时间令牌生成精确时间戳，模型能够处理多视角、多类型、任意长度的视频和复杂语言查询。实验表明其跨域泛化能力领先，推动大模型在视频定位任务上的落地应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fs3fzdrfz7/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 3094, \"height\": 2475}]"
motivation: 现有方法领域受限，需要一种通用的跨域视频定位模型。
method: 基于生成式MLLM，引入时间令牌，通过引导模型生成精确时间戳进行定位。
result: 在多种视频域和复杂查询下取得最优性能，超越特定领域训练的方法。
conclusion: 大语言模型的通用理解力可大幅提升视频时序定位的鲁棒性和泛化性。
---

## Abstract
This paper presents a computational model for universal video temporal grounding, which accurately localizes temporal moments in videos based on natural language queries (e.g., questions or descriptions). 
Unlike existing methods that are often limited to specific video domains or durations, we propose **UniTime**, a robust and universal video grounding model leveraging the strong vision-language understanding capabilities of generative Multi-modal Large Language Models (MLLMs).
Our model effectively handles videos of diverse views, genres, and lengths while comprehending complex language queries.
The key contributions include:
(i) We consider steering strong MLLMs for temporal grounding in videos. To enable precise timestamp outputs, we incorporate temporal information by interleaving timestamp tokens with video tokens.
(ii) By training the model to handle videos with different input granularities through adaptive frame scaling, our approach achieves robust temporal grounding for both short and long videos.
(iii) Comprehensive experiments show that UniTime outperforms state-of-the-art approaches in both zero-shot and dataset-specific finetuned settings across five public temporal grounding benchmarks.
(iv) When employed as a preliminary moment retriever for long-form video question-answering (VideoQA), UniTime significantly improves VideoQA accuracy, highlighting its value for complex video understanding tasks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：现有视频时序定位（Video Temporal Grounding）模型通常局限于特定领域（如烹饪、自我中心视频）或特定时长（仅短/长视频），难以泛化到多样化的真实世界视频场景。
- **研究动机**：通用视频理解需要一种能处理任意视角（第一/第三人称）、任意类型（烹饪、体育、影视）、任意时长（数秒到数小时）并对复杂自然语言查询实现精准时刻定位的模型。
- **整体含义**：本文提出了**UniTime**，利用生成式多模态大语言模型（MLLM）的强视觉-语言理解和生成能力，构建一个通用、鲁棒的时序定位框架，为下游长视频问答等任务提供有效的时刻检索器。

### 2. 论文提出的方法论
- **核心思想**：将时序定位转化为MLLM的生成式检索任务——在视频帧序列中插入显式的时间戳文本令牌，让模型根据查询直接生成包含起止时间的自然语言边界。
- **关键技术细节**：
    - **自适应帧缩放（Adaptive Frame Scaling）**：根据视频总时长动态分配每帧的令牌预算（$N_{\text{res}} = \lfloor N_{\text{total}} / N_f \rfloor$）。短视频（$<N_f^{\text{short}}$）使用高空间分辨率并靠调整图像尺寸匹配预算；中长视频通过特征图的**双线性令牌压缩**降低冗余；极长视频（$>N_f^{\text{long}}$）分割为多段处理。
    - **时间戳交织序列构建**：对每一帧 $f_i$ 的时间戳 $t_i$，插入文本令牌 $\tau_i = \text{“timestamp: } t_i \text{ seconds”}$，形成 $[T_1; V_1; T_2; V_2; \dots; T_{N_f}; V_{N_f}; Q]$ 的序列输入LLM，输出格式为“From $s_k$ seconds to $e_k$ seconds”。对粗粒度预测，则在固定长度片段前插入单个时间戳。
    - **多阶段粗-细推理（Coarse-to-Fine）**：长视频先以粗粒度分段检索相关片段，再在该片段内以细粒度（高帧率、高空间解析度）精确定位时刻边界，可递归进行。
    - **视频中心训练（Video-centric Training）**：对一个视频同时加载其所有查询-答案对，通过注意力掩码避免对间干扰并复用视频编码，显著减少I/O和重复计算。
    - **训练损失**：仅对目标答案令牌计算自回归负对数似然。

### 3. 实验设计
- **预训练数据集**：INaQ、DiDeMo、QuerYD、HiRest、COIN、Momentor、YouCook2 共7个多样化数据集，涵盖开放场景、烹饪、自我中心/外部视角等。
- **评估基准与任务**：
    - **长视频时序定位**：Ego4D-NLQ、TACoS。
    - **短时序定位**：Charades-STA、ActivityNet-Captions、QVHighlights。
    - **视频问答（VideoQA）**：Grounded VideoQA（QaEgo4D、CG-Bench）与通用VideoQA（MLVU、LongVideoBench），以检验时刻检索对下游任务的作用。
- **对比方法**：覆盖传统/判别式方法（2D-TAN、VSLNet、SG-DETR、UnLoc-L、RGNet等）、MLLM方法（Qwen2-VL、Qwen2.5-VL、Mr.BLIP、TimeSuite、VTimeLLM、TimeChat、TimeMarker等）及部分闭源模型（Gemini-2.5、GPT-4o等）。
- **评估设置**：包含**零样本**（仅用Part I数据训练）、**数据集专属微调**和**通用设定**（用全量预训练数据不微调直接测试）三种模式。

### 4. 资源与算力
- 文中**未明确说明**使用的具体GPU型号与数量。
- 训练配置：基于 **Qwen2-VL-7B**，使用 **LoRA**（r=8, alpha=8）微调，优化器 **AdamW**，学习率2e-4，batch size 8，训练**1个epoch**（前3%步数线性预热），视觉编码器冻结。
- 受限于GPU显存，设定最大令牌预算 $N_{\text{total}} = 16384$，长视频阈值 $N_f^{\text{long}} = 1024$，短视频阈值 $N_f^{\text{short}} = 128$。
- 附录提及不同帧处理策略（token压缩 vs. resize）会显著影响训练时间（如全压缩训练超24.5小时，混合策略约21小时），可间接推断单次实验算力需求，但未提及并行规模。

### 5. 实验数量与充分性
- 实验**十分丰富且系统**，涵盖约20+对比方法和9个评估基准。
- 核心消融：
    - 各模块贡献（自适应缩放、多阶段推理、分段检索）在Ego4D-NLQ上的消融。
    - 超参数消融：分段长度、长/短视频阈值、令牌预算、数据复制因子。
    - 视频处理策略对比（resize vs. 压缩）。
    - 时间信息编码方式对比（时间戳插入 vs. 密集位置编码）。
- 鲁棒性分析：
    - 事件时间偏移测试（对抗分布偏差）。
    - 查询分解为对象问题，检验定位可靠性和幻觉。
    - 在Charades-CON和ActivityNet-CON上评估定位一致性（Rephrased Grounding和Shifted Grounding）。
- 模型灵活性验证：在多个基座MLLM（Qwen2-VL 2B/7B, Qwen2.5-VL-7B, InternVL2.5 2B/8B）上验证方法即插即用性。
- 整体实验设计**公平、客观**，包含零样本、微调、跨域多种设定，以及与闭源模型的比较，能充分支撑论文主张。

### 6. 论文的主要结论与发现
- UniTime在所有5个公开时序定位基准上，无论是零样本、专属微调还是通用设定，**均一致超越现有最优方法**，尤其在长视频（Ego4D-NLQ、TACoS）上提升显著。
- 自适应帧缩放与粗-细多阶段推理是处理各种长度视频的关键，使得单一模型能有效应对从秒级到小时级的视频。
- 显式时间戳交织方式比隐式位置编码更有效地赋予MLLM时间定位能力，且方法对基础LLM架构具有高灵活性。
- 作为下游长视频问答的时刻检索器，UniTime大幅提升了VideoQA准确率，证明了其通用定位能力对复杂视频理解的实用价值。
- 在鲁棒性测试中，UniTime相比其他MLLM方法对数据分布偏差和复杂查询展现出更强的抗干扰能力和更低的幻觉。

### 7. 优点
- **通用性强**：单一模型统一处理长短视频、多域、多视角及复杂查询，破解了此前模型领域受限的痛点。
- **设计巧妙且高效**：利用文本时间戳令牌直接让LLM“读出”时刻，避免了额外对齐学习；自适应帧缩放与视频中心训练在性能和算力间取得平衡。
- **实验极为扎实**：覆盖多个维度（不同长度、不同域、零样本/微调、鲁棒性、下游任务），消融细致，与大量最新方法和闭源模型对比，说服力强。
- **即插即用**：方法可适配多种MLLM，具有很好的推广潜力。

### 8. 不足与局限
- **算力资源信息缺失**：文中未给出具体GPU型号与数量，不利于精确复现算力成本评估。
- **任务聚焦单一**：目前仅限于时序定位，尚未拓展至稠密视频描述等更复杂的时间密集任务。
- **分段长度固定**：长视频处理依赖预设的固定分段长度，缺乏基于信息密度的自适应分段策略。
- **推理依赖生成式MLLM**：尽管通过视频中心训练提高了效率，但大规模推理时的自回归解码计算开销仍可能较大。
- **标注偏差风险**：部分数据集的标注不完备（如ActivityNet-Captions的多事件标注缺失）可能限制模型在该类数据上的表现上限，但这不是模型本身的问题。

（完）
