---
title: "Deep Video Discovery: Agentic Search with Tool Use for Long-form Video Understanding"
title_zh: Deep Video Discovery：面向长视频理解的代理搜索与工具使用
authors: "Xiaoyi Zhang, Zhaoyang Jia, Zongyu Guo, Jiahao Li, Bin Li, Houqiang Li, Yan Lu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=oQYq9L1NVT"
tags: ["query:tf-vl-ag"]
score: 9.0
evidence: 面向长视频理解的代理搜索代理
tldr: 针对长视频理解中时空复杂性与问答上下文限制，提出Deep Video Discovery（DVD）代理，采用自主搜索策略在分段视频片段上寻找答案。DVD在多个长视频QA数据集上显著优于传统方法，展示了代理式搜索在高效视频推理中的潜力，为训练无关的代理式视频理解提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-001.webp\", \"caption\": \"\", \"page\": 1, \"index\": 1, \"width\": 371, \"height\": 435}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-002.webp\", \"caption\": \"\", \"page\": 9, \"index\": 2, \"width\": 805, \"height\": 805}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-003.webp\", \"caption\": \"\", \"page\": 9, \"index\": 3, \"width\": 805, \"height\": 805}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-oqyq9l1nvt/fig-004.webp\", \"caption\": \"\", \"page\": 9, \"index\": 4, \"width\": 805, \"height\": 805}]"
motivation: 现有LLM处理信息密集的长视频时上下文长度不足，难以精准问答。
method: 设计DVD代理，通过工具使用和自主搜索分段视频片段实现高效信息定位。
result: 在长视频问答任务上显著提升准确率，降低计算开销。
conclusion: DVD展示了代理式搜索在长视频理解中的有效性，减轻了对全量视频训练的依赖。
---

## Abstract
Long-form video understanding presents significant challenges due to extensive temporal-spatial complexity and the difficulty of question answering under such extended contexts. 
While Large Language Models (LLMs) have demonstrated considerable advancements in video analysis capabilities and long context handling, they continue to exhibit limitations when processing information-dense hour-long videos. 
To overcome such limitations, we propose the $\textbf{D}eep \ \textbf{V}ideo \ \textbf{D}iscovery \ (\textbf{DVD})$ agent to leverage an $\textit{agentic search}$ strategy over segmented video clips. Different from previous video agents manually designing a rigid workflow, our approach emphasizes the autonomous nature of agents.
By providing a set of search-centric tools on multi-granular video database,
our DVD agent leverages the advanced reasoning capability of LLM to plan on its current observation state, strategically selects tools to orchestrate adaptive workflow for different queries in light of the gathered information.
We perform comprehensive evaluation on multiple long video understanding benchmarks that demonstrates our advantage.
Our DVD agent achieves state-of-the-art performance on the challenging LVBench dataset, reaching an accuracy of $\textbf{74.2\%}$, which substantially surpasses all prior works, and further improves to $\textbf{76.0\%}$ with transcripts.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以中文、使用 Markdown 形式，对《Deep Video Discovery : Agentic Search with Tool Use for Long-form Video Understanding》这篇论文进行结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：
    *   **核心挑战**：长视频（如电影、会议录像）的理解极具挑战性，因为它涉及广泛的时空复杂性。在这样长的上下文中进行精准问答，要求模型不仅能捕捉精细的局部细节，还要能理解分布于整个时间线中的复杂语义关系。
    *   **现有模型局限**：尽管大语言模型和大视觉-语言模型在视频理解和长上下文处理上取得了长足进步，但面对信息密度极高的、时长超一小时的视频时，它们的有效指令遵循能力和推理清晰度仍会显著下降。其上下文窗口长度仍不足以完全容纳和理解这些数据。
    *   **新思路的兴起**：近期，基于LLM的代理系统（如Deep Research）在复杂信息搜集任务上取得了突破。这些系统通过将复杂任务分解为子任务，实现了迭代式推理、信息搜索和内容整合。
    *   **论文核心思想**：受此启发，本文**将长视频理解问题重新定义为一个多步骤的信息搜索问题**，把视频本身视为一个待探索的环境，并将视频片段作为可管理的信息单元。

### 2. 论文提出的方法论

本文提出的 **Deep Video Discovery (DVD)** 代理，其核心是**自主、自适应的代理式搜索范式**，而非预定义的固化工作流。它主要由两个阶段组成：

#### 阶段一：多粒度视频数据库构建
目标是将原始长视频转化为一个支持高效检索且能提供原始像素细节的结构化数据库。该数据库包含三个粒度层级的信息：

*   **时空分割**：将视频统一切分为不重叠的短片段（默认为5秒），每个片段以每秒2帧的频率解码。
*   **主体为中心的全局表示 (Global Level)**：在生成片段字幕的过程中，使用VLM渐进式维护一个结构化的“主体登记表”，记录视频中出现的所有主体及其属性（如外貌、身份、动作、出现时段）。
*   **片段级字幕与嵌入 (Clip Level)**：为每个视频片段生成详细的文文字幕，并将其嵌入为稠密语义向量，用于后续的快速检索。
*   **帧像素保留 (Frame Level)**：保留解码后的原始视频帧，并与其对应片段的字幕和嵌入建立索引。

最终的数据库结构表示为 `D = {S, {fi, ci, ei}Ni=1}`，其中 `S` 是最终的主体登记表，`f_i` 是帧，`c_i` 是字幕，`e_i` 是嵌入向量。

#### 阶段二：代理式搜索与工具使用回答 (ASA)
在此阶段，一个配备推理能力的LLM作为代理的“大脑”，驱使其使用一套**以搜索为中心的工具集 T**，在数据库 `D` 中进行迭代式信息搜集和推理。

*   **工具集 T 设计 (Action Space)**:
    1.  **Global Browse (全局浏览)**：输入用户查询，返回视频级别的全局摘要，包括主体中心和事件中心的总结，提供高层语境。
    2.  **Clip Search (片段搜索)**：输入代理合成的查询，通过与数据库中的字幕嵌入进行余弦相似度匹配，返回最相关的Top-k视频片段及其字幕。这是迭代搜索的核心。
    3.  **Frame Inspect (帧检视)**：输入一个时间范围`[ts, te]`和一个由代理自由定义的细粒度问题，调用VLM分析该时间段内的原始帧，以获取字幕或全局摘要中缺失的像素级细节。
    4.  **Answer (回答)**：代理调用此动作以结束流程并输出最终答案。

*   **代理工作流程 (Agentic Design)**:
    *   遵循 **观察-推理-行动 (Observe-Reason-Act)** 的迭代循环，类似 ReAct 模式。
    *   对于给定的用户查询 `Q`，LLM 代理 `M` 会持续推理当前状态，从动作空间 `A = T ∪ {ANSWER}` 中战略性地选择下一步动作 `A_i` 及其参数 `P_i`，与工具交互获取观察结果 `O_i`，并将所有信息累积到历史记录 `H_i` 中。
    *   此过程不断循环，直至代理选择 `ANSWER` 动作或达到预设的最大步数 `N`，最终输出答案。整个过程由LLM自主决策，无需人工预设工具使用顺序。

### 3. 实验设计

实验评估旨在全面验证DVD在长视频理解任务上的有效性。

*   **数据集/基准**：
    *   **LVBench**：**主要评估基准**，包含来自103个长视频的1549道多选题，极具挑战性。
    *   **LongVideoBench**：重点关注时长在 (900s, 3600s] 的“Long”子集，含188个视频的564个问题。
    *   **Video MME**：使用其中时长30-60分钟的“Long”子集（无字幕），含300个视频的900个问题。
    *   **EgoSchema**：作为诊断基准，在其包含500个视频和500个问题的验证集上评估。

*   **对比方法**：
    *   **商业VLM**：Gemini-1.5-Pro/2.0-Flash, GPT-4o, OpenAI o3, GLM-4V-Plus。
    *   **开源VLM**：InternVL2.5, VideoLLaMA3, Qwen2.5-VL, VideoChat-Flash, AdaRETAKE。
    *   **视频代理与其他方法**：VideoTree, VideoAgent, VCA, MR. Video。

### 4. 资源与算力

*   **模型使用**：
    *   **数据库构建 VLM**：使用 **GPT-4.1** 生成高质量字幕（其他基准测试用 GPT-4.1-mini 以降低成本）。
    *   **代理推理 LLM**：使用 **OpenAI o3** 作为核心推理模型，同时也测试了 GPT-4o、o4-mini 及开源模型 DeepSeek-R1/V3 等。
    *   **帧检视 VLM**：根据消融实验，默认也使用 **OpenAI o3**。
*   **计算成本**：论文提到了采用API方式调用模型，并计算了处理单个问题的平均成本，约为 **$2.05 美元** 和 **20,803个Token**。
*   **算力细节缺失**：论文**未明确说明**使用何种 GPU、GPU 数量、训练时长等信息。其框架是基于API调用的，不涉及大规模模型训练，因此上述API调用成本即是主要的算力开销体现。

### 5. 实验数量与充分性

论文设计了较为丰富的实验，整体来看比较充分，能够支撑其核心论点。

*   **主要性能对比实验**：在 **4个不同的长视频基准**（LVBench, LongVideoBench, Video-MME, EgoSchema）上与超过 **15种** 现有方法进行了对比，实验规模庞大，覆盖广泛。
*   **消融实验**：
    *   **模型选择消融**：针对数据库构建模型 (`M_database`)、推理模型 (`M_reasoning`)、帧检视模型 (`M_tool`) 这个三个关键组件，分别替换为性能更低的模型（如 GPT-4.1-mini, GPT-4o），设计了 **6组** 实验来验证各个模型的重要性。
    *   **工具集消融**：通过移除 `Global Browse`、`Clip Search`、`Frame Inspect` 中的任意一个工具，设计了 **3组** 实验，以量化每种工具的贡献。
    *   **工作流与步数消融**：比较了DVD的自适应工作流与强制使用 VideoAgent 固定工作流的性能差异，并探讨了不同最大步数限制（8, 12, 15）对效率的影响。
*   **行为分析**：对代理使用不同推理模型时的工具调用模式进行了深入分析，将其分为5种行为类型（简单行动、迭代搜索等），并结合准确率进行了探讨，为未来代理设计提供了有价值的洞察。
*   **公平性**：对比基准的结果主要来自官方排行榜或已发表论文，对于未评测的模型（如o3），作者遵循了其他工作的设置进行评测，整体比较是公平和客观的。

### 6. 论文的主要结论与发现

*   **SOTA性能**：提出的DVD代理在多个长视频理解基准上达到了最先进的性能。尤其在极具挑战性的LVBench上，以**74.2%的准确率**大幅超越所有先前工作（超过第二名 MR. Video 13.4%），加入字幕辅助后进一步提升至**76.0%**。
*   **自适应代理的有效性**：与固定工作流（如VideoAgent的流程）相比，DVD的自适应搜索策略在**需要更少步骤（7.3 vs 11.1步）** 的同时，取得了**更高的准确率（74.2% vs 70.2%）**，证明了自主编排工具的价值。
*   **核心组件的关键性**：
    *   **推理模型 (`M_reasoning`)** 是系统中最关键的组件，其推理能力的强弱直接决定了最终性能。使用性能弱的模型会导致代理行为“崩溃”（如GPT-4o的“过度自信”）。
    *   **Clip Search** 工具是三项工具中贡献最大的，移除它会导致性能急剧下降12.3%，因为它破坏了代理的精细化迭代搜索能力。
*   **代理行为洞察**：揭示了推理模型的双重性。单个模型内，更长的推理链往往意味着不确定性增加和准确率下降；但跨模型比较时，性能更强的模型恰能执行更深入、更长的推理过程。

### 7. 优点

*   **方法论创新**：
    *   创新性地将长视频理解**形式化为代理式信息搜索问题**，为解决上下文长度限制问题提供了优雅的思路。
    *   设计了**多粒度的视频数据库和对应的搜索工具集**，巧妙平衡了信息检索效率和细节准确度。
    *   **强调代理的自主性与自适应性**，区别于以往手动设计固定搜索路径的方法，充分释放了LLM的推理和规划潜力。
*   **实验扎实**：
    *   在**多个主流和挑战性的基准**上进行了全面的评估和详尽的消融研究，论证深入且令人信服。
    *   对代理行为的**定性分析**（如5种行为模式）非常有洞察力，不仅解释了“为什么有效”，也为未来研究提供了方向。
*   **性能显著**：在核心基准LVBench上取得了**大幅领先的SOTA成绩**，证明了方法的有效性。

### 8. 不足与局限

*   **计算开销高**：该方法依赖多次、迭代的LLM/VLM API调用，处理单个问题的平均成本高达$2.05，成本高昂，难以应用于实时或大规模视频处理场景。论文本身也承认这是其主要局限。
*   **依赖特定商业模型**：核心性能严重依赖性能强大的商业模型（如GPT-4.1、OpenAI o3），虽然实验证明可以接入开源模型，但性能会有明显下降。这使得方法的可复现性和普及性受到限制。
*   **API内容过滤干扰**：论文提到所使用的Azure OpenAI Service存在内容安全过滤机制，会误判并阻止部分请求，这影响了其基线和自身方法的性能，为性能比较引入了潜在偏差。
*   **人工设计组件**：虽然工作流是自适应的，但数据库的构建方式（如固定的5秒分段）和工具的定义（如`Clip Search`默认返回Top-16结果）仍然依赖于人工先验知识。
*   **缺乏错误恢复与不确定性校准**：行为分析揭示了“Frame Inspect陷阱”和“Clip Search陷阱”两种失败模式。代理在面对错误信息或无法检索到信息时，缺乏有效的自我纠错或不确定性校准机制。

（完）
