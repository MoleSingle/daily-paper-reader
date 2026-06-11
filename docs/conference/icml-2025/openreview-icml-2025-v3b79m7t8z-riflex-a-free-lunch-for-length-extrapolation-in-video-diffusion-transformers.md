---
title: "RIFLEx: A Free Lunch for Length Extrapolation in Video Diffusion Transformers"
title_zh: "RIFLEx: 视频扩散Transformer长度外推的免费午餐"
authors: "Min Zhao, Guande He, Yixiao Chen, Hongzhou Zhu, Chongxuan Li, Jun Zhu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=v3B79m7t8Z"
tags: ["query:talking-head"]
score: 4.0
evidence: 视频生成长度外推方法适用于talking head视频合成
tldr: 该论文针对视频扩散Transformer生成长视频时出现的时间重复或运动减速问题，通过降低位置嵌入中的固有频率来抑制重复，实现高质量2倍长度外推，无需额外修改。这一方法可潜在地改善talking head视频合成中的时间连贯性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 1167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 928, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 886, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1768, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1548, \"height\": 1407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1777, \"height\": 1781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1697, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1776, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1764, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1768, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1701, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v3b79m7t8z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1719, \"height\": 1447, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-v3b79m7t8z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1552, \"height\": 1658, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3b79m7t8z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1760, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v3b79m7t8z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1503, \"height\": 409, \"label\": \"Table\"}]"
motivation: 现有视频生成的时长外推方法导致时间重复或运动减速。
method: 降低位置嵌入中的固有频率，抑制重复同时保持运动一致性。
result: 实现高质量2倍视频长度外推，无需额外修改。
conclusion: RIFLEx为视频生成的长度外推提供了一种简单有效的免费午餐方法。
---

## Abstract
Recent advancements in video generation have enabled models to synthesize high-quality, minute-long videos. However, generating even longer videos with temporal coherence remains a major challenge and existing length extrapolation methods lead to temporal repetition or motion deceleration. In this work, we systematically analyze the role of frequency components in positional embeddings and identify an intrinsic frequency that primarily governs extrapolation behavior. Based on this insight, we propose RIFLEx, a minimal yet effective approach that reduces the intrinsic frequency to suppress repetition while preserving motion consistency, without requiring any additional modifications. RIFLEx offers a true free lunch—achieving high-quality $2\times$ extrapolation on state-of-the-art video diffusion transformers in a completely training-free manner. Moreover, it enhances quality and enables $3\times$ extrapolation by minimal fine-tuning without long videos.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视频生成模型（尤其是基于扩散Transformer）在生成长视频时会遇到难以保持时间连贯性的问题，现有的长度外推方法（如位置插值、NTK感知缩放等）应用于视频外推时，会导致 **时间上的内容重复（temporal repetition）** 或 **动作减速/慢动作（motion deceleration）**，无法自然地生成新颖且平滑演进的内容。
- **整体含义**：本工作旨在通过分析位置嵌入中不同频率分量的作用，提出一种极简且无需额外训练（或仅需极小量微调）的“免费午餐”式解决方案，在已有的先进视频扩散Transformer上实现2倍甚至3倍的视频长度外推，并同时抑制重复与保持运动一致性。

### 2. 论文提出的方法论

- **核心思想**：在RoPE（旋转位置嵌入）中，存在一个“固有频率”（intrinsic frequency），其主要决定了视频在外推时是否及如何出现重复。通过降低该固有频率，使其周期在外推长度后仍然大于一个完整周期，即可抑制重复。
- **技术细节**：
  - **频率分量分析**：
    - 高频对应短时依赖，引起快速变化和时间重复；低频对应长时依赖，导致慢动作。
    - 每个频率分量 $\theta_j$ 的周期为 $N_j = 2\pi/\theta_j$，在训练长度 $L$ 内的重复次数为 $r_j = L/N_j = L\theta_j/(2\pi)$。
    - **固有频率** $k$ 定义为周期 $N_j$ 最接近视频中首次观察到的重复帧 $N$ 的那个频率分量，该分量在不同视频中基本一致。
  - **RIFLEx 方法**：将固有频率 $\theta_k$ 修改为 $\theta'_k = \frac{2\pi}{Ls}$，其中 $s$ 为外推倍数，使得 $N'_k \ge Ls$，确保外推后仍在一个周期内，从而避免重复。算法流程如论文 Algorithm 1 所示：计算各频率周期，识别固有频率，然后直接修改该频率值。
  - **训练/免训练特性**：对于 $2\times$ 外推，RIFLEx 能以完全训练自由（training-free）的方式工作；为实现更高视觉质量或 $3\times$ 外推，仅需在原始长度视频上进行极少量微调（如 $20,000$ 条视频，计算量仅为预训练的 $1/50,000$）。
- **对现有方法的解释**：位置外推（PE）和 NTK 因为固有频率仍不满足公式(8)而导致重复；位置插值（PI）和 YaRN 则因过度压缩高频分量而导致慢动作；TASR 则同时出现这两种问题。

### 3. 实验设计

- **数据集**：
  - 微调所用私有数据集：$20,000$ 条视频。
  - CogVideoX-5B 实验：采用 VBench 的提示词以保持一致性。
  - HunyuanVideo 实验（因计算开销大）：使用 100 条多样化的提示词测评。
- **基线方法**：位置外推（PE）、位置插值（PI）、NTK、YaRN、TASR。
- **评估指标**：
  - **自动指标**：Imaging Quality（图像质量）、Dynamic Degree（动态程度）、Overall Consistency（整体一致性）、**NoRepeat Score**（无重复分数，新提出）。
  - **用户调研**：10 位参与者，对视觉质量、运动质量和整体偏好进行排序（允许平局）；同时进行成对比较（训练长度正常生成 vs. RIFLEx 结果）。
- **场景**：时间维度 $2\times$ 外推（CogVideoX-5B 从 49 帧到 97 帧，HunyuanVideo 从 129 帧到 261 帧等）；时间+空间联合外推；HunyuanVideo $2.3\times$ 外推；微调场景等。

### 4. 资源与算力

- **微调配置**（见论文 Table 3）：
  - CogVideoX-5B $2\times$ 时间外推微调：$2500$ 迭代，batch size $8$，$8$ 块 A100-80G GPU。
  - HunyuanVideo $2\times$ 时间外推微调：$1000$ 迭代，batch size $8$，$24$ 块 A100-80G GPU。
  - CogVideoX-5B $3\times$ 时间外推微调：$5000$ 迭代，$8$ 块 A100-80G。
  - $2\times$ 空间外推或时空联合外推均有轻微计算量，基本在 $8$ 块 A100-80G 级别。
  - 论文强调微调计算量仅为预训练的 $1/50,000$。
- 推理设置未明确详述，但方法本身以免训练为主，额外开销极小。

### 5. 实验数量与充分性

- **实验组数较多**：
  - 两个主流模型（CogVideoX-5B, HunyuanVideo）上的多组对比。
  - 涵盖训练自由和微调设置，$2\times$、$2.3\times$、$3\times$ 外推。
  - 消融实验：仅调整固有频率与调整所有更低频率的对比，调整更高或更低频率的影响。
  - 空间外推与联合外推实验。
  - 与多种现有方法（PE, PI, NTK, YaRN, TASR）的横向对比。
- **充分性**：实验覆盖了主要外推场景，自动指标和用户调研结合，提供了质性对比和消融分析。未见在大规模多样性基准（如 VBench 完整套件）上报告全部维度，但 VBench 提示词已用于评估。总体充分，能够支撑核心论述。

### 6. 论文的主要结论与发现

- RIFLEx 通过降低固有频率，能从根源上抑制视频长度外推中的时间重复，同时保留自然的运动速度。
- 该方法在 $2\times$ 外推时无需任何训练，实现了真正的“免费午餐”；借助极少微调可进一步提升质量并支持 $3\times$ 外推。
- 分析揭示了各频率分量的角色：高频致重复、低频致慢动作，并给出了现有方法失败的一致解释。
- 方法可无缝扩展到空间外推与时空联合外推。

### 7. 优点

- 方法极简且有效，改动极小（只修改一个频率值），无需结构重设计。
- 训练自由的特性大幅降低了使用门槛。
- 提供了对 RoPE 频率分量作用的清晰机理解释，具有较强的理论启发性。
- 实验覆盖两个主流大规模视频模型，对比基准全面，评估指标较系统。

### 8. 不足与局限

- 最大外推倍数受限（约 $3\times$），超过此范围因频率过度降低导致位置区分能力减弱，视频质量急剧下降。
- 固有频率的识别目前依赖人工视觉观察，缺乏自动化或理论推导的普适方法。
- 用户调研样本量较小（10 人），且未详细说明被试背景，可能影响结论稳健性。
- 仅在视频扩散Transformer上验证，对其他生成架构（如自回归模型）的泛化性未进行探索。
- 微调虽轻量，但仍需访问原始模型和一定算力，并非完全零资源。

（完）
