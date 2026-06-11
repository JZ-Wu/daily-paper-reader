---
title: "LV-XAttn: Distributed Cross-Attention for Long Visual Inputs in Multimodal Large Language Models"
title_zh: LV-XAttn：多模态大语言模型中长视觉输入的分布式交叉注意力
authors: "Tzu-Tao Chang, Shivaram Venkataraman"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kuIwMEHXMT"
tags: ["query:tf-vl-ag"]
score: 8.0
evidence: 针对多模态大语言模型中长视觉输入（如视频）的高效分布式交叉注意力机制
tldr: 针对多模态大语言模型处理视频等长视觉输入时交叉注意力层内存消耗大且分布式通信开销高的问题，本文提出LV-XAttn，一种具有最小通信开销的分布式精确交叉注意力机制。该方法能显著降低内存需求，加速训练和推理，适用于视频理解任务，为高效视频处理提供了解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 688, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 833, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kuiwmehxmt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 968, \"height\": 785, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 872, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 739, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1649, \"height\": 896, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kuiwmehxmt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 502, \"label\": \"Table\"}]"
motivation: 多模态大语言模型处理视频等长视觉输入时，交叉注意力层内存消耗大，分布式计算通信开销高。
method: 提出LV-XAttn，一种最小通信开销的分布式精确交叉注意力机制。
result: 未给出具体数据，但声称大幅降低内存需求，提升效率。
conclusion: LV-XAttn实现了多模态大语言模型高效处理长视觉输入。
---

## Abstract
Cross-attention is commonly adopted in multimodal large language models (MLLMs) for integrating visual information into the language backbone. However, in applications with large visual inputs, such as video understanding, processing a large number of visual tokens in cross-attention layers leads to high memory demands and often necessitates distributed computation across multiple GPUs. Existing distributed attention mechanisms face significant communication overheads, making cross-attention layers a critical bottleneck for efficient training and inference of MLLMs. To address this, we propose LV-XAttn, a distributed, exact cross-attention mechanism with minimal communication overhead. We observe that in applications involving large visual inputs, the size of the query block is typically much smaller than that of the key-value blocks.  Thus, in LV-XAttn we keep the large key-value blocks locally on each GPU and exchange smaller query blocks across GPUs. We also introduce an efficient activation recomputation technique to support longer visual context. We theoretically analyze the communication benefits of LV-XAttn and show that it can achieve speedups for a wide range of models. Our evaluations with Llama 3-V, mPLUG-Owl3 and OpenFlamingo models find that LV-XAttn achieves up to 10.62$\times$ end-to-end speedup compared to existing approaches.

---

## 论文详细总结（自动生成）

## 论文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题背景**：多模态大语言模型（MLLMs）常采用交叉注意力（cross-attention）将视觉信息（如图像、视频帧）融入语言主干。在处理长视频等大视觉输入时，交叉注意力层需要计算大量的视觉 token（键值块），导致单 GPU 显存不足，必须使用多 GPU 分布式计算。
- **核心瓶颈**：现有的分布式注意力机制（如 Ring Attention）在跨注意力场景中需要频繁传输巨大的键值块，通信开销极高，成为训练与推理的主要瓶颈。例如，在 Ring Attention 下，仅占参数量 3% 的交叉注意力层可能消耗高达 88% 的迭代时间。
- **研究目标**：提出一种针对交叉注意力的分布式精确计算方法 LV-XAttn，以最小化通信代价，大幅加速长视觉输入下的 MLLMs。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心观察**：在长视觉输入应用中，来自文本的**查询块（Q）尺寸远小于来自视觉的键值块（K, V）**。例如，Video-MME 基准中平均 Q 序列长度约 5500，而 K 序列长度可达 1500 万。
- **LV-XAttn 设计思想**：
  - 每个 GPU **本地存储其分配到的键值块（Ki, Vi）**，不再整体传输。
  - 在 GPU 之间以环形方式**只轮转较小的查询块（Qi）、输出块（Oi）和 softmax 统计量（Li）**。
  - 每轮中，worker i 接收来自邻居的 Q 块，利用本地 K、V 计算部分注意力，然后通过 rescale 更新 O 和 L，最后将更新后的块向后继节点传递。经过 `n`（worker 数）轮后，各 worker 得到完整的输出。
- **通信计算重叠**：在计算注意力的同时，并行进行数据的发送与接收，使通信开销几乎完全被计算遮盖。
- **激活重计算技术**：
  - 观察：所有交叉注意力层共享同一视觉特征 y（经过编码与投影的视觉 token），而语言特征 x 在每一层发生变化。
  - 方法：前向传播时只保留一份视觉特征 y 和必要的输出 O、统计量 L，不保存各层的 K、V 激活。反向传播时，从 y 重新计算 K、V，从而大幅节省显存，支持更长的视觉上下文。
  - 代价：额外计算导致迭代时间增加不超过 8%，但可处理 1.6 倍以上的视觉 token。
- **理论分析**：给出 LV-XAttn 与 Ring Attention 的每轮运行时间模型（式1、式2），指出当 `SKV >> SQ` 且跨节点带宽有限时，LV-XAttn 是计算受限的，而 Ring Attention 是通信受限的，因而加速明显。

### 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法
- **模型**：在 6 个公开 MLLMs 上进行评估——Llama 3-V-11b、mPLUG-Owl3-7b/2b/1b、OpenFlamingo-9b/3b。各模型每帧生成的视觉 token 数不同（6404 / 729 / 64）。
- **基准与对比方法**：
  - 主要基线：对 LM 块使用 Ring Attention，对交叉注意力分别采用 **Ring Attention** 或 **LV-XAttn**；两者均使用激活重计算以支持长上下文。
  - 另一对比方法：**DeepSpeed-Ulysses**（头并行 + 序列并行），对比显存与速度极限。
- **评测任务与场景**：
  - 采用合成输入进行可控的准确时间测试。输入规模参考 Video-MME 长视频基准：视频平均时长 2386 秒，文本平均 3128 单词，对应不同帧率下的 SQ 与 SKV 值。
  - 测试不同文本长度、不同帧数（即不同 SQ 和 SKV）组合下的**每迭代时间**。
- **集群环境**：
  - 16×A100 80GB（节点内 NVLink，节点间 25 GB/s）
  - 8×A30 24GB（节点间 1.25 GB/s，资源受限场景）
  - 12×A100 40GB（混合互联，用于消融实验）

### 4. 资源与算力
- 论文明确给出了所有测试使用的 GPU 类型与数量，以及互联带宽。
- 未报告训练总时长或完整训练轮数，因为评测侧重于**单次迭代时间**的比较。每个数据点为 5 次运行的平均（含 2 次预热）。
- 因此，总计算资源消耗无法从文中直接推算，但硬件配置详实。

### 5. 实验数量与充分性
- **多模型多尺度测试**：
  - 在 16 A100 上完成了 6 个模型、多个（SQ, SKV）组合的对比实验（表 3），共约 20 组测量。
  - 在 8 A30 上同样进行了上述模型的对比（表 4），同样约 20 组。
- **与 DeepSpeed-Ulysses 对比**：
  - A100 上针对 mPLUG-Owl3-2b 的不同 worker 数和输入尺寸（表 5）。
  - A30 上针对 OpenFlamingo-3b 的可处理长度极限对比（表 6）。
- **消融实验**：
  - 通信计算重叠效果（图 5），使用 OpenFlamingo-3b 在 6 A100 40GB 上。
  - 激活重计算对可处理帧数及速度的影响（图 6），使用 mPLUG-Owl3-7b 和 OpenFlamingo-3b 在 3 A30 24GB 上。
- **理论加速比分析**（图 4、图 7），覆盖不同 SQ 与 SKV 范围。
- 实验设计**充分且系统**，涵盖不同规模模型、不同并行度、不同硬件带宽条件，并通过消融实验验证各组件贡献，对比公平（基线统一使用 FlashAttention 与相同并行策略，仅交叉注意力实现不同）。

### 6. 论文的主要结论与发现
- LV-XAttn 在交叉注意力层可获得高达 **45.85 倍**的速度提升，端到端迭代加速最高达 **10.62 倍**。
- 通信量降至 Ring Attention 的 **0.04%**，且通信与计算完全重叠，开销接近零通信基线（<0.42% 的额外开销）。
- MLLM 专用的激活重计算技术可节约显存，使可处理的视觉 token 数量最多提高 **1.6 倍**，速度代价小于 8%。
- 在资源受限（低速互联、小显存 A30）的场景下，加速效果更为突出。
- 当文本输入长度大幅增加时，LV-XAttn 的相对优势降低，但仍保持显著加速（例如 OpenFlamingo 中仍有 1.5–2 倍加速）。

### 7. 优点：方法或实验设计上有哪些亮点
- **洞察直接且有效**：牢牢抓住“Q 小，KV 大”的不对称性，从根本上改变分布式的数据传输对象。
- **通信开销接近零**：理论分析与实验充分证明在长视频等典型场景下，方法可将通信完全隐藏在计算之后。
- **显存优化技巧实用**：利用视觉特征在各交叉注意力层共享的性质进行激活重计算，简单高效。
- **评估全面**：在多种模型架构、多种 GPU 型号与互联带宽下进行测试，并与主流分布式方案直接比较，结果可靠。
- **实现可复现**：开源代码仓库，并验证了输出精度与 PyTorch 标准实现一致。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **适用架构受限**：该方法专门针对**交叉注意力型** MLLM，对于视觉 token 与文本拼接再送入自注意力层的模型（如 LLaVA）不直接适用，需借助混合架构才能受益。
- **文本长度制约**：当查询端序列长度 SQ 与 KV 端长度 SKV 处于同一数量级时（如某些文本极长的场景或自注意力），加速效果会大幅降低，甚至可能劣于 Ring Attention（图 7 左下象限）。
- **仅测量迭代时间**：实验未涉及完整训练收敛、最终下游任务精度（如视频问答准确率）的验证，未能证明在真实训练中无负面影响（尽管方法为精确计算，无精度损失风险）。
- **未讨论梯度通信等同步开销**：集中在注意力层本身的通信，对整体分布式训练中参数梯度同步等可能隐藏的额外开销未深入分析。
- **激活重计算适用范围**：依赖视觉特征 y 在所有交叉注意力层不变的特性，对架构中 y 也存在变换的模型不适用。

（完）
