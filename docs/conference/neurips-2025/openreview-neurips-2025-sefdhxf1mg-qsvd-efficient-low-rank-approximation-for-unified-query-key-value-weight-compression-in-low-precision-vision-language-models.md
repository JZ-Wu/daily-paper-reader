---
title: "QSVD: Efficient Low-rank Approximation for Unified Query-Key-Value Weight Compression in Low-Precision Vision-Language Models"
title_zh: QSVD：低精度视觉语言模型中统一查询-键-值权值压缩的高效低秩近似
authors: "Yutong Wang, Haiyu Wang, Sai Qian Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=sEFDhxF1mG"
tags: ["query:tf-vl-ag"]
score: 6.0
evidence: 视觉语言模型的低秩权值压缩以降低计算成本
tldr: 针对视觉语言模型高计算成本限制实时应用的问题，该文提出对QKV联合权值矩阵进行SVD低秩近似，并引入动态秩分配策略，结合量化压缩，显著降低内存开销和计算量。该方法在保持精度的同时实现高效推理，为部署资源受限的视频理解VLM提供关键技术支撑。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 588, \"height\": 436}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 923, \"height\": 744}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 1090, \"height\": 408}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-004.webp\", \"caption\": \"\", \"page\": 6, \"index\": 4, \"width\": 844, \"height\": 824}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-005.webp\", \"caption\": \"\", \"page\": 6, \"index\": 5, \"width\": 844, \"height\": 823}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-006.webp\", \"caption\": \"\", \"page\": 6, \"index\": 6, \"width\": 513, \"height\": 236}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-007.webp\", \"caption\": \"\", \"page\": 6, \"index\": 7, \"width\": 1884, \"height\": 1793}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-008.webp\", \"caption\": \"\", \"page\": 6, \"index\": 8, \"width\": 1875, \"height\": 1793}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-009.webp\", \"caption\": \"\", \"page\": 6, \"index\": 9, \"width\": 1868, \"height\": 1793}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-010.webp\", \"caption\": \"\", \"page\": 6, \"index\": 10, \"width\": 577, \"height\": 390}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-011.webp\", \"caption\": \"\", \"page\": 10, \"index\": 11, \"width\": 544, \"height\": 290}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-012.webp\", \"caption\": \"\", \"page\": 10, \"index\": 12, \"width\": 708, \"height\": 516}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-013.webp\", \"caption\": \"\", \"page\": 27, \"index\": 13, \"width\": 563, \"height\": 405}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-014.webp\", \"caption\": \"\", \"page\": 29, \"index\": 14, \"width\": 750, \"height\": 429}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-015.webp\", \"caption\": \"\", \"page\": 30, \"index\": 15, \"width\": 515, \"height\": 406}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sefdhxf1mg/fig-016.webp\", \"caption\": \"\", \"page\": 31, \"index\": 16, \"width\": 704, \"height\": 358}]"
motivation: VLM计算成本高、内存占用大，制约扩展性和实时应用。
method: 对QKV联合权重进行SVD分解，动态分配秩并量化压缩。
result: 大幅降低内存和计算开销，保持模型精度。
conclusion: 低秩近似加动态秩分配是一种有效的VLM压缩方法，兼顾效率与精度。
---

## Abstract
Vision-Language Models (VLMs) are integral to tasks such as image captioning and visual question answering, but their high computational cost, driven by large memory footprints and processing time, limits their scalability and real-time applicability. In this work, we propose leveraging Singular-Value Decomposition (SVD) over the joint query (Q), key (K), and value (V) weight matrices to reduce KV cache size and computational overhead. We in addition introduce an efficient rank allocation strategy that dynamically adjusts the SVD rank based on its impact on VLM accuracy, achieving a significant reduction in both memory usage and computational cost. Finally, we extend this approach by applying quantization to both VLM weights and activations, resulting in a highly efficient VLM. Our method outperforms previous approaches that rely solely on quantization or SVD by achieving more than $10$% accuracy improvement while consuming less hardware cost, making it better for real-time deployment on resource-constrained devices. We open source our code at https://github.com/SAI-Lab-NYU/QSVD.

---

## 论文详细总结（自动生成）

# 论文结构化总结：QSVD — 低精度视觉语言模型中统一查询-键-值权值压缩的高效低秩近似

## 1. 研究动机与核心问题
- **核心痛点**：视觉语言模型 (VLM) 虽然广泛应用于图像描述、视觉问答等任务，但其巨大的参数量、KV 缓存以及计算开销严重限制了在资源受限设备上的实时部署和扩展性。
- **现有局限**：已有的压缩方法（如单独使用 SVD 或量化）大多独立应用，未能充分利用 QKV 权值矩阵之间的结构共性，在保持精度的同时难以实现极致的硬件效率。
- **论文目标**：提出一种将联合低秩分解与低精度量化深度融合的压缩框架（QSVD），在显著降低权值存储、KV 缓存和计算量的前提下，尽可能维持甚至提升模型精度。

## 2. 方法论
QSVD 框架由三个核心部分组成：联合 SVD 分解、跨层自适应秩分配、以及面向低秩特性的后训练量化。

### 2.1 联合 QKV 权值的 SVD 分解
- **核心思想**：将传统多头注意力中的查询（\(W_q\)）、键（\(W_k\)）、值（\(W_v\)）三个 \(E \times E\) 的权值矩阵**拼接**成一个 \(E \times 3E\) 的联合矩阵 \(W_{concat}\)，然后对其进行低秩 SVD。
- **分解形式**：
  \[
  [W_q, W_k, W_v] = W_{concat} \approx U_r \Sigma_r V_r^T
  \]
  进一步拆分成**共享下投影** \(W_{d}^{qkv} = U_r \Sigma_r^\beta\) 和**独立上投影** \(W_u^q, W_u^k, W_u^v = \Sigma_r^{1-\beta} V_r^T\)。
- **推理时的收益**：
  - 只需一次下投影计算 \(C_{qkv} = X \cdot W_{d}^{qkv}\)，即可重构出 query、key、value。
  - 存储只需要缓存 \(C_{qkv}\)（维度 \(L \times r\)），大幅降低 KV 缓存和中间结果体积。
  - 权值参数量从 \(3E^2\) 降至 \(4rE\)，计算量从 \(3LE^2\) 降至 \(4LrE\)，在 \(r < 0.75E\) 时即可带来收益，而实际实验中该条件极易满足且几乎无损。

### 2.2 跨层自适应秩分配
- **目的**：并非所有奇异值对模型精度同等重要，需要智能决定每个自注意力层的截断秩 \(r\)。
- **重要性评分**：基于一阶泰勒展开和 Fisher 信息，推导出每个奇异值 \(\sigma_i\) 对训练损失变化的近似影响：
  \[
  \hat{I}_{\sigma_i} = \frac{1}{N} \sum_{n=1}^{N} \sigma_i^2 \left[ U^T G_W^{(n)} V \right]_{i,i}^2
  \]
  其中 \(G_W\) 是权值梯度，\(U, \Sigma, V\) 为 SVD 分解结果。该评分可在 \(O(E^2)\) 内存内高效计算，避免直接构造满秩扰动矩阵。
- **全局秩分配**：计算所有层的所有奇异值的重要性得分，然后**全局排序**，保留得分最高的 \(k\) 个奇异值（对应全局秩预算），其余截断。这使得重要层保留更多秩，非关键层压缩更激进。

### 2.3 低秩适应的后训练量化
- **挑战**：VLM 的激活和中间结果 \(C_{qkv}\) 存在严重的通道异常值，直接量化会带来巨大误差。
- **旋转平滑**：引入正交矩阵 \(H_1, H_2\)，通过等价变换 \(Y = (X H_1^T)(H_1 W_d^{qkv} H_2^T)(H_2 W_u^{qkv})\) 来平滑激活与权重中的异常值，且不改变前传结果。
- **动态 \(\beta\) 优化**：中间结果 \(C_{qkv}\) 受 \(\beta\) 影响显著，因为 \(\Sigma_r^\beta\) 会放大奇异值差异。为此，在标定数据集上最小化量化前后输出误差，**逐层学习最优 \(\beta\)**，进一步抑制异常值。
- 最终实现端到端的低精度（W8A8、W8A4 甚至 W4A4）VLM 推理。

## 3. 实验设计
### 3.1 模型与数据集
- **评测模型**：LLaVA‑v1.5 7B / 13B、LLaVA‑Next 7B / 13B 以及轻量级 SmolVLM‑Instruct 2B。
- **主要基准数据集**：ScienceQA‑IMG、VizWiz、SEED‑Bench‑IMG，遵循 LLaVA 等主流评测协议。
- **额外评测**：长序列场景使用 HRBench‑4K (4K 分辨率) 测试；幻觉评测使用 HallusionBench。

### 3.2 对比方法
- **纯 SVD 基线**：ASVD（逐矩阵 SVD）、SVD‑LLM（截断感知 SVD）。
- **纯量化基线**：QuaRot、DuQuant、QVLM。
- **混合方法**：QASVD（ASVD 后接 QuaRot 量化）、以及 QSVD‑noQ（仅联合 SVD，不量化）。
- **公平性**：所有方法使用相同标定样本（ScienceQA 训练集 256 例）、相同随机种子，并报告最佳性能。压缩程度通过权重/计算比 \(R_1\) 和中间缓存比 \(R_2\) 统一度量。

### 3.3 量化配置
- 测试三种量化精度：W8A8、W8A4、W4A4。激活量化采用逐 token 对称量化，权值量化采用逐通道对称量化 + 可学裁剪因子。

## 4. 资源与算力
- 评估设备：NVIDIA RTX A6000 GPU（运行 VLMEvalKit 评测）。
- 推理延迟测试：在 NVIDIA RTX 4070 (12 GB) 上进行，batch size=1，序列长度 4K。
- 论文未明确说明压缩或标定过程的时间开销（如 GPU 小时数），但所有实验均在单卡或少量卡上即可完成，硬件门槛较低。

## 5. 实验数量与充分性
- **实验规模**：覆盖 5 个不同规模的 VLM、3 个主要基准数据集、4 种压缩程度（不同 \(R_1/R_2\)）、3 种量化位宽。
- **消融实验**：
  - 验证跨层自适应秩分配 vs. 均匀秩 vs. 基于 Fisher 的秩分配。
  - 分析可学习 \(\beta\) 的影响。
  - 长序列鲁棒性测试（HRBench‑4K）。
  - 对幻觉的影响分析（HallusionBench）。
- **对照设计**：对比了纯 SVD、纯量化以及 SVD+量化组合多种方法，且统一硬件成本度量指标，确保对比公平客观。
- 总体而言，实验设计全面，覆盖了不同压缩力度和模型规模，充分支持论文结论。

## 6. 主要结论与发现
1. **联合 SVD 优势明显**：QSVD‑noQ 在远低于基线的 \(R_1\) 和 \(R_2\) 下，精度全面超越 ASVD 和 SVD‑LLM。在 SmolVLM 上，后者已失效而 QSVD 仍保持 70%+ 的准确率。
2. **量化配合鲁棒**：QSVD 在 W8A8、W8A4 下接近甚至达到 FP16 精度，并将 KV 缓存减少至原生模型的 9.38%–18.75%，其他量化方法在 W4A4 下则完全失效。
3. **反面提升现象**：在部分数据集（如 VizWiz）上，QSVD 压缩后的准确率**超过 FP16 基线**，推测低秩近似起到了正则化、抑制幻觉的作用，HallusionBench 实验也证实了这一猜想。
4. **推理加速**：在消费级 GPU 上，量化版 QSVD 最高实现 **13.1×** 的推理加速，且完全免于 CPU‑GPU offloading。

## 7. 论文优点
- **方法创新**：首次将 Q/K/V 联合低秩分解、全局重要性秩分配与低精度量化融于一体，形成统一高效的 VLM 压缩范式。
- **理论支撑**：推导了基于一阶泰勒展开的重要性评分，避免 \(O(E^3)\) 内存，使跨层自适应秩分配可实际应用。
- **工程友好**：共享下投影结构天然适合硬件实现，缓存的 \(C_{qkv}\) 体积小且可复用；可学习 \(\beta\) 增强量化鲁棒性而不引入额外推理开销。
- **实验扎实**：多模型、多数据集、多配置下的充分对比，消融完备，开放源代码。

## 8. 不足与局限
- **范围局限**：SVD 压缩主要作用在自注意力层的 QKV 权值，未来需扩展到 FFN 等其它线性层，实现全模型全局优化。
- **安全性与社会影响**：论文自身指出，高效 VLM 可能被滥用于监控、虚假信息等领域；正文未给出具体防御方案。
- **硬件与任务边界**：虽然验证了主流 VLM 架构，但并未测试基于 MLA（Multi‑head Latent Attention）等更先进注意力的模型；此外，除标准 VQA/描述外，缺乏更复杂的多模态交互任务评估。

---

（完）
