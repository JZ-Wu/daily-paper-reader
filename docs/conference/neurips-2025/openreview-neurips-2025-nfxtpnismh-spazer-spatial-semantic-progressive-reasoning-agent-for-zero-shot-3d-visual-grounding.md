---
title: "SPAZER: Spatial-Semantic Progressive Reasoning Agent for Zero-shot 3D Visual Grounding"
title_zh: SPAZER：面向零样本3D视觉接地的空间-语义渐进式推理代理
authors: "Zhao Jin, Rong-Cheng Tu, Jingyi Liao, Wenhao Sun, Xiao Luo, Shunyu Liu, Dacheng Tao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=nfxTpNiSMH"
tags: ["query:tf-vl-ag"]
score: 5.0
evidence: VLM驱动的代理，通过渐进式空间-语义推理实现零样本3D视觉接地
tldr: 现有零样本3D视觉接地方法偏重空间或语义单方面，该文提出SPAZER代理，组合2D语义与3D空间信息，以渐进式推理框架实现零样本3D接地。其先分析场景生成最优视角3D渲染，再通过锚引导候选框逐步定位目标。该方法为训练无关的接地代理提供了新范式，虽面向3D场景，其思路或可迁移至视频域。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-001.webp\", \"caption\": \"\", \"page\": 2, \"index\": 1, \"width\": 486, \"height\": 363}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-002.webp\", \"caption\": \"\", \"page\": 2, \"index\": 2, \"width\": 486, \"height\": 363}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-003.webp\", \"caption\": \"\", \"page\": 2, \"index\": 3, \"width\": 887, \"height\": 746}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-004.webp\", \"caption\": \"\", \"page\": 2, \"index\": 4, \"width\": 786, \"height\": 670}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-005.webp\", \"caption\": \"\", \"page\": 2, \"index\": 5, \"width\": 655, \"height\": 355}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-006.webp\", \"caption\": \"\", \"page\": 2, \"index\": 6, \"width\": 513, \"height\": 358}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-007.webp\", \"caption\": \"\", \"page\": 2, \"index\": 7, \"width\": 572, \"height\": 401}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-008.webp\", \"caption\": \"\", \"page\": 2, \"index\": 8, \"width\": 452, \"height\": 337}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-009.webp\", \"caption\": \"\", \"page\": 4, \"index\": 9, \"width\": 339, \"height\": 458}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-010.webp\", \"caption\": \"\", \"page\": 4, \"index\": 10, \"width\": 535, \"height\": 354}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-011.webp\", \"caption\": \"\", \"page\": 8, \"index\": 11, \"width\": 1218, \"height\": 801}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-012.webp\", \"caption\": \"\", \"page\": 8, \"index\": 12, \"width\": 1217, \"height\": 803}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-013.webp\", \"caption\": \"\", \"page\": 8, \"index\": 13, \"width\": 1212, \"height\": 755}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-014.webp\", \"caption\": \"\", \"page\": 8, \"index\": 14, \"width\": 1212, \"height\": 757}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-015.webp\", \"caption\": \"\", \"page\": 8, \"index\": 15, \"width\": 1212, \"height\": 757}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-016.webp\", \"caption\": \"\", \"page\": 8, \"index\": 16, \"width\": 1397, \"height\": 895}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-017.webp\", \"caption\": \"\", \"page\": 8, \"index\": 17, \"width\": 1396, \"height\": 893}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-018.webp\", \"caption\": \"\", \"page\": 8, \"index\": 18, \"width\": 1395, \"height\": 894}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-019.webp\", \"caption\": \"\", \"page\": 8, \"index\": 19, \"width\": 1539, \"height\": 1138}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-020.webp\", \"caption\": \"\", \"page\": 8, \"index\": 20, \"width\": 1539, \"height\": 1137}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-021.webp\", \"caption\": \"\", \"page\": 8, \"index\": 21, \"width\": 1542, \"height\": 1136}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-022.webp\", \"caption\": \"\", \"page\": 27, \"index\": 22, \"width\": 1342, \"height\": 1104}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-023.webp\", \"caption\": \"\", \"page\": 27, \"index\": 23, \"width\": 1498, \"height\": 1019}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-024.webp\", \"caption\": \"\", \"page\": 27, \"index\": 24, \"width\": 1458, \"height\": 1082}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-025.webp\", \"caption\": \"\", \"page\": 27, \"index\": 25, \"width\": 1506, \"height\": 1090}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-026.webp\", \"caption\": \"\", \"page\": 27, \"index\": 26, \"width\": 1237, \"height\": 977}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nfxtpnismh/fig-027.webp\", \"caption\": \"\", \"page\": 27, \"index\": 27, \"width\": 1420, \"height\": 1030}]"
motivation: 零样本3DVG方法常偏重空间或语义一端，在复杂场景中效果受限。
method: VLM驱动的代理，结合2D语义和3D空间信息进行渐进式推理定位。
result: 在零样本设定下提升复杂场景3D接地准确率。
conclusion: 空间-语义渐进式推理显著增强零样本接地能力，具备跨任务潜力。
---

## Abstract
3D Visual Grounding (3DVG) aims to localize target objects within a 3D scene based on natural language queries. To alleviate the reliance on costly 3D training data, recent studies have explored zero-shot 3DVG by leveraging the extensive knowledge and powerful reasoning capabilities of pre-trained LLMs and VLMs. However, existing paradigms tend to emphasize either spatial (3D-based) or semantic (2D-based) understanding, limiting their effectiveness in complex real-world applications. In this work, we introduce SPAZER — a VLM-driven agent that combines both modalities in a progressive reasoning framework. It first holistically analyzes the scene and produces a 3D rendering from the optimal  viewpoint. Based on this, anchor-guided candidate screening is conducted to perform a coarse-level localization of potential objects. Furthermore, leveraging retrieved relevant 2D camera images, 3D-2D joint decision-making is efficiently performed to determine the best-matching object. By bridging spatial and semantic reasoning neural streams, SPAZER achieves robust zero-shot grounding without training on 3D-labeled data. Extensive experiments on ScanRefer and Nr3D benchmarks demonstrate that SPAZER significantly outperforms previous state-of-the-art zero-shot methods, achieving notable gains of $\mathbf{9.0\}$% and $\mathbf{10.9\}$% in accuracy.

---

## 论文详细总结（自动生成）

# SPAZER：空间–语义渐进推理代理用于零样本3D视觉接地

## 1. 论文的核心问题与整体含义
零样本3D视觉接地（3DVG）旨在不依赖昂贵的人工标注3D训练数据，仅凭自然语言查询在三维场景中定位目标物体。现有零样本方案分化为两种范式：
- **3D‐based 方法**（如 LLM‑Grounder、ZSVG3D）聚焦空间关系，却难以捕捉精细属性；
- **2D‐based 方法**（如 VLM‑Grounder）擅长视觉细节匹配，但缺乏明确的空间感知。

复杂真实场景需要**空间定位**与**语义理解**协同工作。论文提出 **SPAZER**，一个由视觉‑语言模型（VLM）驱动的代理，通过**渐进式推理**桥接两种神经流，在不利用3D标注数据的前提下实现鲁棒的零样本3D视觉接地。

## 2. 方法论核心思想与技术细节
SPAZER 遵循“粗到细”的空间–语义渐进推理流程，以 GPT‑4o 等 VLM 为“大脑”，搭配3D与2D感知工具。

### 2.1 整体流程
1. **三维全局视图选择**（Sec. 3.2）  
   利用多视角渲染，让 VLM 直接观察场景本身，而非依赖不稳定的文本化描述。  
   - **多视图观察**：从场景正上方生成鸟瞰图（BEV），并沿上方圆周均匀分布 \(n\) 个视角（间距 \(360^\circ/n\)，固定倾角 \(45^\circ\)，距离由场景尺寸和视场角按公式 \(d = \frac{1}{2}\times \max(l_x,l_y)/\tan(\theta/2)\) 计算）。  
   - **视图选择**：VLM 根据查询文本从所有渲染视图中选出最有利于观察目标物体的视角 \(I^*_{3d}\)。

2. **候选对象筛选**（Sec. 3.3）  
   利用现成3D检测器提取物体布局 \(O = \{(b_i,c_i)\}\)，在此基础上粗定位。  
   - **检索增强锚过滤**：先用文本匹配从查询中推断目标类别 \(c^*\)，若与检测到的类别相似度 \(s(c^*,c_{i^*})\) 低于阈值 \(\tau\)，则构建“视觉对象表”（拼接裁剪的物体图像），转由 VLM 基于视觉过滤无关物体。  
   - **候选筛选**：在选中的渲染视图上标注剩余物体 ID 作为视觉锚，VLM 选出置信度最高的 Top‑k 候选对象。

3. **3D‑2D 联合决策**（Sec. 3.4）  
   对 Top‑k 候选，通过相机内外参（\(K, T_{cw}\)）将3D边界框顶点和中心点投影到二维相机图像平面，对比深度图判断可见性，选取最完整显示该物体的关键帧作为其对应2D视图 \(I_{2d}\)。  
   VLM 同时接收 **全局3D渲染**（用于视角无关关系如“在房间中间”）与 **2D相机图像**（用于色彩、材质等语义验证及视角依赖关系如“左边”），最终输出最佳匹配物体的3D边界框 \(b^*\)。

### 2.2 关键设计要点
- **直接用渲染图观察场景**，避免文本化中间表示带来的误差传播。
- **检索增强锚过滤**：当文本匹配不可靠时自适应切换到视觉匹配，提升了物体类别歧义下的鲁棒性。
- **仅需少量2D关键帧**：利用3D空间推理得到的候选锚直接定位相关相机图像，大幅减少图像处理量，提升效率。

## 3. 实验设计与对比方法
### 3.1 数据集与基准
- **ScanRefer**：基于 ScanNet 的 51,583 条自然语言描述，评估 Acc@0.25 和 Acc@0.5（IoU 阈值），分类为“Unique”和“Multiple”。
- **Nr3D**：41,503 条描述，提供真实边界框，评估选择准确率，分“Easy/Hard”和“View‑Dependent/Independent”。
- 主实验在**与 VLM‑Grounder 相同的子集（250样本）** 上进行以节省成本，论文额外验证了子集与全集的性能一致性。
- 另在 **RIORefer** 上进行了跨数据集泛化测试。

### 3.2 对比方法
| 类型 | 方法 |
|------|------|
| 全监督 | ScanRefer、3DVG‑Transformer、BUTD‑DETR、ViL3DRel、3D‑VisTA、MiKASA、SceneVerse、ChatScene、Video‑3D LLM、GPT4Scene 等 |
| 零样本 | OpenScene、LLM‑Grounder、ZSVG3D、VLM‑Grounder、SeeGround、CSVG、EaSe、Transcrib3D 等 |

## 4. 资源与算力
- 默认使用 **GPT‑4o**（gpt‑4o‑2024‑08‑06），**无需GPU**。
- 开源模型实验（Qwen2‑VL‑72B、Qwen2.5‑VL‑72B）使用**多块 NVIDIA H100 GPU**。
- 方法**无训练过程**，因此不涉及训练时长；渲染和投影计算对GPU无特殊要求。
- 推理时间：SPAZER 单样本总耗时约 **23.5 秒**（视图选择 5.2s + 候选筛选 8.5s + 联合决策 9.8s），远快于 VLM‑Grounder 的 50.3 秒。

## 5. 实验数量与充分性
论文进行了大量且系统的实验：
- **主对比实验**：ScanRefer（表1）与 Nr3D（表2），覆盖多个零样本和全监督基线。
- **消融实验**（表3）：从3D‑only到3D+2D，逐步验证视图选择、锚过滤、联合决策的贡献。
- **参数敏感度**（图4）：Top‑k k值（1‑5）和多视图数量 n（0‑8）对性能的影响。
- **VLM 影响**（表4）：对比 GPT‑4o、GPT‑4o‑mini、GPT‑4.1、Qwen2‑VL‑72B、Qwen2.5‑VL‑72B。
- **错误类型分析**（图5）：将错误分为语义、空间、检测、其他四类，揭示 3D+2D 联合的改善。
- **跨数据集泛化**（表11）：RIORefer 上零样本 SPAZER 超越监督基线。
- **阶段消融**（表12）：逐阶段替换为弱 VLM，显示最终决策阶段对模型能力最敏感。
- **案例研究**：定性对比（图3）、隐含对象接地（图6）、失败案例（图7）。

实验设计公平，使用了标准基准、与同行一致的子集、充分的消融和误差分析，结论客观可靠。

## 6. 主要结论与发现
- SPAZER 在 ScanRefer 和 Nr3D 上分别以 **+9.0%** 和 **+10.9%** 的显著优势超越先前最优零样本方法。
- 在 Nr3D 上接近全监督先进方法（差距仅约 1%），且 Acc@0.25 已超过部分全监督基线。
- 空间‑语义渐进推理比仅3D或仅2D的范式更有效，联合决策带来平均 **11.6%** 的提升。
- 检索增强锚过滤提高了文本匹配失败时的鲁棒性，视图选择和多视角数量对性能有显著影响。
- VLM 能力越强，代理性能越高，但最终推理阶段对模型能力最为依赖。

## 7. 优点
- **训练无关，部署灵活**：完全零样本，无需任何3D‑VG标注数据。
- **渐进式空间‑语义融合**：模拟人脑双流推理，同时利用3D几何与2D视觉细节。
- **多视角渲染直接观察**：避免了文本化描述带来的坐标不确定性。
- **高效的关键帧采样**：仅需少量2D图像，推理速度远优于逐帧处理的 VLM‑Grounder。
- **实验充分**：涵盖多个数据集、大量基线、详尽的消融和错误分析，结论可信。
- **泛化能力强**：跨数据集（RIORefer）表现优于监督基线，证明方法不绑定特定数据分布。

## 8. 不足与局限
- **依赖外部3D检测器**：定位精度受 Mask3D 等预训练模型影响，检测错误会向下传导。
- **投影映射易受参数影响**：不准确的相机内外参或深度图可能导致关键帧选取失败。
- **空间关系理解仍为主误差**：复杂方向词（如“西北角”）和视角依赖关系仍是挑战。
- **语义细节易遗漏**：当候选集中有多件外观相近的物体时，可能遗漏真正的目标。
- **数据集标注歧义**：部分样本存在多个合理匹配对象，评估结果可能受数据质量影响。
- **VLM 决策不可解释性**：虽然输出可读理由，但内部推理仍是黑盒。
- **当前仅适用室内场景**：评估主要集中在 ScanNet 相关数据集，扩展到户外或动态环境的能力未知。
- **成本**：虽然推理效率较高，但每次推理需调用商用 VLM API，大规模部署时存在费用问题。

（完）
