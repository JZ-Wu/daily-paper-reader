---
title: "ReAgent-V: A Reward-Driven Multi-Agent Framework for Video Understanding"
title_zh: ReAgent-V：一种奖励驱动的多智能体视频理解框架
authors: "Yiyang Zhou, Yangfan He, Yaofeng Su, Siwei Han, Joel Jang, Gedas Bertasius, Mohit Bansal, Huaxiu Yao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=D1Iw4Unvfc"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 奖励驱动的多智能体视频推理框架
tldr: 为克服单通路推理缺乏自我校正的局限，提出ReAgent-V，一个奖励驱动的多智能体框架，通过多角色交互与实时奖励信号提升视频推理的准确性与效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 2052, \"height\": 1110}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-002.webp\", \"caption\": \"\", \"page\": 3, \"index\": 2, \"width\": 2999, \"height\": 899}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-003.webp\", \"caption\": \"\", \"page\": 7, \"index\": 3, \"width\": 4458, \"height\": 2119}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-004.webp\", \"caption\": \"\", \"page\": 8, \"index\": 4, \"width\": 2254, \"height\": 756}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-005.webp\", \"caption\": \"\", \"page\": 8, \"index\": 5, \"width\": 3947, \"height\": 716}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-006.webp\", \"caption\": \"\", \"page\": 8, \"index\": 6, \"width\": 512, \"height\": 512}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-007.webp\", \"caption\": \"\", \"page\": 8, \"index\": 7, \"width\": 805, \"height\": 220}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-008.webp\", \"caption\": \"\", \"page\": 8, \"index\": 8, \"width\": 496, \"height\": 402}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-009.webp\", \"caption\": \"\", \"page\": 8, \"index\": 9, \"width\": 453, \"height\": 322}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-010.webp\", \"caption\": \"\", \"page\": 8, \"index\": 10, \"width\": 765, \"height\": 192}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-011.webp\", \"caption\": \"\", \"page\": 8, \"index\": 11, \"width\": 453, \"height\": 323}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-012.webp\", \"caption\": \"\", \"page\": 8, \"index\": 12, \"width\": 496, \"height\": 401}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-013.webp\", \"caption\": \"\", \"page\": 8, \"index\": 13, \"width\": 384, \"height\": 322}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 724, \"height\": 192}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-015.webp\", \"caption\": \"\", \"page\": 32, \"index\": 15, \"width\": 984, \"height\": 454}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-016.webp\", \"caption\": \"\", \"page\": 32, \"index\": 16, \"width\": 1780, \"height\": 736}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-017.webp\", \"caption\": \"\", \"page\": 33, \"index\": 17, \"width\": 984, \"height\": 476}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-018.webp\", \"caption\": \"\", \"page\": 33, \"index\": 18, \"width\": 1628, \"height\": 712}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-019.webp\", \"caption\": \"\", \"page\": 34, \"index\": 19, \"width\": 1556, \"height\": 1040}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-020.webp\", \"caption\": \"\", \"page\": 34, \"index\": 20, \"width\": 1583, \"height\": 893}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-021.webp\", \"caption\": \"\", \"page\": 35, \"index\": 21, \"width\": 1573, \"height\": 858}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-022.webp\", \"caption\": \"\", \"page\": 35, \"index\": 22, \"width\": 1592, \"height\": 859}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-023.webp\", \"caption\": \"\", \"page\": 36, \"index\": 23, \"width\": 2278, \"height\": 1254}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-024.webp\", \"caption\": \"\", \"page\": 36, \"index\": 24, \"width\": 2269, \"height\": 1252}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-025.webp\", \"caption\": \"\", \"page\": 36, \"index\": 25, \"width\": 2288, \"height\": 1259}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-026.webp\", \"caption\": \"\", \"page\": 36, \"index\": 26, \"width\": 2269, \"height\": 1236}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-027.webp\", \"caption\": \"\", \"page\": 36, \"index\": 27, \"width\": 2274, \"height\": 1246}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-028.webp\", \"caption\": \"\", \"page\": 36, \"index\": 28, \"width\": 2282, \"height\": 1244}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-029.webp\", \"caption\": \"\", \"page\": 37, \"index\": 29, \"width\": 1979, \"height\": 871}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-030.webp\", \"caption\": \"\", \"page\": 37, \"index\": 30, \"width\": 1589, \"height\": 729}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-031.webp\", \"caption\": \"\", \"page\": 37, \"index\": 31, \"width\": 1979, \"height\": 875}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-032.webp\", \"caption\": \"\", \"page\": 37, \"index\": 32, \"width\": 1979, \"height\": 874}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-033.webp\", \"caption\": \"\", \"page\": 37, \"index\": 33, \"width\": 1979, \"height\": 872}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-034.webp\", \"caption\": \"\", \"page\": 37, \"index\": 34, \"width\": 1979, \"height\": 864}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-035.webp\", \"caption\": \"\", \"page\": 37, \"index\": 35, \"width\": 1979, \"height\": 879}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-036.webp\", \"caption\": \"\", \"page\": 37, \"index\": 36, \"width\": 1979, \"height\": 879}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-037.webp\", \"caption\": \"\", \"page\": 37, \"index\": 37, \"width\": 1979, \"height\": 879}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-038.webp\", \"caption\": \"\", \"page\": 37, \"index\": 38, \"width\": 1979, \"height\": 880}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-039.webp\", \"caption\": \"\", \"page\": 37, \"index\": 39, \"width\": 1979, \"height\": 980}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-040.webp\", \"caption\": \"\", \"page\": 37, \"index\": 40, \"width\": 1979, \"height\": 879}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-d1iw4unvfc/fig-041.webp\", \"caption\": \"\", \"page\": 38, \"index\": 41, \"width\": 2030, \"height\": 1380}]"
motivation: 现有视频理解方法多为单通路推理，无动态反馈；奖励模型标注成本高且无法捕获实时状态。
method: ReAgent-V采用多智能体协作，结合奖励模型与强化学习进行动态反馈与自我修正。
result: 在视频推理任务上，相比单通路方法错误率降低，推理过程更可靠。
conclusion: 多智能体框架可增强视频理解的鲁棒性与推理效率。
---

## Abstract
Video understanding is fundamental to tasks such as action recognition, video reasoning, and robotic control. Early video understanding methods based on large vision-language models (LVLMs) typically adopt a single-pass reasoning paradigm without dynamic feedback, limiting the model’s capacity to self-correct and adapt in complex scenarios. Recent efforts have attempted to address this limitation by incorporating reward models and reinforcement learning to enhance reasoning, or by employing tool-agent frameworks. However, these approaches face several challenges, including high annotation costs, reward signals that fail to capture real-time reasoning states, and low inference efficiency. To overcome these issues, we propose ReAgent-V, a novel agentic video understanding framework that integrates efficient frame selection with real-time reward generation during inference. These reward signals not only guide iterative answer refinement through a multi-perspective reflection mechanism—adjusting predictions from conservative, neutral, and aggressive viewpoints—but also enable automatic filtering of high-quality data for supervised fine-tuning (SFT), direct preference optimization (DPO), and group relative policy optimization (GRPO). ReAgent-V is lightweight, modular, and extensible, supporting flexible tool integration tailored to diverse tasks. Extensive experiments on 12 datasets across three core applications—video understanding, video reasoning enhancement, and vision-language-action model alignment—demonstrate significant gains in generalization and reasoning, with improvements of up to 6.9%, 2.1%, and 9.8%, respectively, highlighting the effectiveness and versatility of the proposed framework.

---

## 论文详细总结（自动生成）

### 论文总结：ReAgent-V: A Reward-Driven Multi-Agent Framework for Video Understanding

#### 1. 论文的核心问题与整体含义
- **核心问题**：现有基于大视觉语言模型（LVLMs）的视频理解方法大多采用**单次前向推理范式**，缺乏动态反馈和自我纠正能力，难以应对复杂多步推理任务。
- **现有挑战**：
    - **高标注成本**：获取高质量标注数据费用高昂。
    - **奖励信号滞后**：预训练奖励模型无法捕捉模型推理过程中的实时状态，可能导致强化不当的推理模式；静态奖励模板缺乏适应性。
    - **推理效率低**：部分多模型辩论或工具代理框架耗时过长且功能有限。
- **整体含义**：论文旨在构建一个**能在推理时生成实时奖励信号**的代理框架，以驱动迭代式答案精炼，同时实现推理效率与性能的平衡，并将反馈信号用于提升后续训练。

#### 2. 论文提出的方法论
- **核心思想**：提出 **ReAgent-V**，一个统一、轻量、模块化的多智能体视频理解框架，融合高效帧选择、工具增强推理和基于实时奖励的多视角反思机制。
- **关键技术细节**：
    - **熵校准帧选择**：引入 **熵校准相关性分数**，联合考虑帧与查询的语义相似度（CLIP分数）及帧自身的信息熵。通过迭代阈值筛选，动态保留信息量高且与问题相关的关键帧，抑制冗余。
    - **工具增强推理**：目标代理根据任务需求从工具工厂动态选择并调用工具（如OCR、ASR、目标检测、场景图生成等），生成辅助信息辅助初步答案生成。
    - **评价与多视角反思**：
        - **评价代理**对初始答案进行多维度评分，生成结构化反馈报告及标量奖励。
        - **目标代理**基于反馈报告，分别从**保守**（仅微调最终答案）、**中立**（修正场景实体感知）和**激进**（重推理步骤并修正实体）三个视角进行反思性答案修订，生成各自修正答案及置信度。
        - 通过比较置信度或融合高置信度答案的共有部分，输出最终答案。
    - **数据筛选**：利用推理时生成的奖励分数，自动筛选高质量样本，用于后续的监督微调、直接偏好优化和群体相对策略优化。
- **算法流程**：算法1详细描述了从帧选择（熵校准迭代筛选）到工具增强推理，再到评价报告生成与多视角反思输出的完整流水线。

#### 3. 实验设计
- **数据集/场景与应用**：在 **12个数据集** 上覆盖 **三大应用**：
    - **视频理解**：6个基准测试集（LongBench, NextQA, EgoSchema, LVBench, MLVU, VideoMME）。
    - **视频LLM推理增强**：从Video-R1-260k数据集中筛选样本，在6个视频推理/通用基准上评估（VSI-Bench, VideoMMMU, MMVU, MVBench, TempCompass, VideoMME）。
    - **视觉-语言-动作模型对齐**：在SIMPLER机器人仿真环境中评估，覆盖4种泛化场景。
- **对比方法**：
    - **视频理解**：对比闭源模型（GPT-4o, Gemini-1.5-Pro）、开源LVLMs（ShareGPT4Video, VideoChat2, LLaVA-Video, Qwen系列, InternVL, BIMBA等）及通用视频代理框架（VideoAgent, VideoMemAgent）。
    - **视频推理**：对比全量数据SFT、Vanilla GRPO（使用116k数据）等方法。
    - **VLA对齐**：对比OpenVLA-SFT、OpenVLA-DPO及使用模板奖励的OpenVLA-TPO+GRAPE。

#### 4. 资源与算力
- **视频理解实验**：使用 **2块 H100-96GB GPU** 配备NVLink，输入64帧。
- **视频LLM推理实验**：在 **8块 NVIDIA H100 80GB GPU** 上对Qwen2.5-VL进行微调。
- **VLA对齐实验**：在 **单块 NVIDIA A100 80GB GPU** 上使用LoRA进行轨迹偏好优化训练，训练步数6800步。

#### 5. 实验数量与充分性
- **实验组数丰富**：覆盖了三个差异化的核心应用，涉及12个数据集，对比了大量基线模型。
- **消融研究充分**：包含对**帧选择机制**的分析（有无帧选择的性能与时间对比，ECRS与CLIP/熵基线的对比）、**反思机制**的有效性验证（有无反思、三种反思策略的单独贡献分析）、**视觉工具**的消融实验，以及在不同参数量和架构的基座模型上的广泛适配验证。
- **客观性与公平性**：所有对比实验严格统一了输入帧数等设定，对闭源模型之外的基线进行了重新评估，确保了比较的公平性。

#### 6. 论文的主要结论与发现
- **性能提升显著**：ReAgent-V在视频理解、视频推理增强和VLA模型对齐三个任务上分别取得了最高 **6.9%**、**2.1%** 和 **9.8%** 的性能提升。
- **效率与效果兼备**：帧选择机制在提升准确率的同时显著减少了推理时间；多视角反思机制通过融合不同策略有效缓解了模型过度自信导致的偏差，提高了修正答案的总体准确率。
- **数据高效**：在视频推理任务中，ReAgent-V仅使用45%的训练数据就超越了全量数据SFT和Vanilla GRPO的效果，证明了其奖励信号对高质量数据筛选的有效性。

#### 7. 优点
- **统一框架**：将实时奖励生成、反思精炼和数据筛选集成于一体，兼顾推理与训练优化。
- **实时自适应奖励**：克服静态奖励模型局限，提供与推理过程紧密耦合的细粒度反馈。
- **多视角反思机制**：创新的保守-中立-激进三策略设计，系统性地处理不同类型的推理错误，提升鲁棒性。
- **轻量与高效**：模块化架构，支持灵活的工具扩展；熵校准帧选择在保持或提升精度的同时降低了计算开销。
- **迁移性强**：成功应用于通用视频理解、推理能力增强和机器人操作对齐等多个领域。

#### 8. 不足与局限
- **长视频挑战**：尽管有关键帧选择，长视频中的信息冗余和复杂语义关联仍对模型全面理解构成挑战。
- **反思机制依赖启发式规则**：评价和反思机制基于预设模板和启发式规则，缺乏端到端的自适应学习能力，可能限制极端场景下的自动纠错有效性。
- **未明确提及的局限**：论文未讨论多轮工具调用和反思带来的额外计算开销对实时性的影响；未深入分析在多主体交互场景下，评价代理自身存在误差带来的风险；数据筛选的阈值（重要性分数<5）设定依赖经验，泛化性有待考究。

（完）
