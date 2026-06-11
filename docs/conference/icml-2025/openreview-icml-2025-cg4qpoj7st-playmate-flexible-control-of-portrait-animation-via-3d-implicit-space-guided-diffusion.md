---
title: "Playmate: Flexible Control of Portrait Animation via 3D-Implicit Space Guided Diffusion"
title_zh: "Playmate: 基于3D隐空间引导扩散的人像动画灵活控制"
authors: "Xingpei Ma, Jiaran Cai, Yuansheng Guan, Shenneng Huang, Qiang Zhang, Shunsi Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=CG4QPoJ7ST"
tags: ["query:talking-head"]
score: 10.0
evidence: 提出基于扩散的说话人脸生成模型，利用3D引导实现灵活的肖像动画
tldr: 现有的扩散模型说话人脸生成方法在唇同步和表情控制方面存在不足。本文提出Playmate框架，通过解耦的隐式3D表示和运动解耦模块，在语音音频驱动下生成更逼真的面部表情和说话人脸视频。实验表明，该方法有效提升了唇同步精度和表情自然度，为可控肖像动画提供了新颖的解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1418, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 692, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1594, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 774, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1599, \"height\": 1663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-cg4qpoj7st/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1598, \"height\": 1270, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-cg4qpoj7st/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1572, \"height\": 545, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cg4qpoj7st/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 819, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cg4qpoj7st/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 779, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cg4qpoj7st/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 828, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-cg4qpoj7st/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 783, \"height\": 158, \"label\": \"Table\"}]"
motivation: 现有说话人脸生成模型面临唇同步不准确、头部姿态不当和表情控制不足等挑战。
method: 提出两阶段训练框架Playmate，利用解耦的隐式3D表示和运动解耦模块，结合扩散模型实现肖像动画的灵活控制。
result: 在语音音频驱动的说话人脸生成中，Playmate能够生成更逼真的面部表情和准确唇同步的视频。
conclusion: Playmate通过引入3D隐空间引导，提升了说话人脸合成中的表情控制和运动自然度。
---

## Abstract
Recent diffusion-based talking face generation models have demonstrated impressive potential in synthesizing videos that accurately match a speech audio clip with a given reference identity. However, existing approaches still encounter significant challenges due to uncontrollable factors, such as inaccurate lip-sync, inappropriate head posture and the lack of fine-grained control over facial expressions. In order to introduce more face-guided conditions beyond speech audio clips, a novel two-stage training framework Playmate is proposed to generate more lifelike facial expressions and talking faces. In the first stage, we introduce a decoupled implicit 3D representation along with a meticulously designed motion-decoupled module to facilitate more accurate attribute disentanglement and generate expressive talking videos directly from audio cues. Then, in the second stage, we introduce an emotion-control module to encode emotion control information into the latent space, enabling fine-grained control over emotions and thereby achieving the ability to generate talking videos with desired emotion. Extensive experiments demonstrate that Playmate not only outperforms existing state-of-the-art methods in terms of video quality, but also exhibits strong competitiveness in lip synchronization while offering improved flexibility in controlling emotion and head pose. The code will be available at https://github.com/Playmate111/Playmate.

---

## 论文详细总结（自动生成）

# Playmate: 基于3D隐空间引导扩散的人像动画灵活控制

## 1. 核心问题与研究动机
现有的基于扩散模型的说话人脸生成方法虽能合成与语音匹配的视频，但仍面临三大核心挑战：
- **唇同步不准**：唇动与音频内容存在偏差
- **头部姿态不自然**：缺少对头部姿态的精细控制
- **表情控制能力弱**：难以独立调节情绪表情，导致生成结果呆板或单调

因此，研究如何**在保留音频同步精度的同时，实现对表情、头部姿态等面部属性的灵活解耦与控制**，是该领域的关键瓶颈。Playmate正是为此提出，旨在从一张静态肖像和一段语音出发，生成既可信又可灵活控制的多模态说话人脸视频。

## 2. 方法论：两阶段3D隐空间引导扩散框架

Playmate的核心思路是**在高度解耦的3D隐式人脸空间中引入扩散模型，分两阶段分别实现运动生成和情绪控制**。

### 2.1 解耦的3D隐式人脸空间构建
- 基于LivePortrait框架，将人脸信息分解为：
  - 外观特征 (fₛ)
  - 运动特征：正则关键点 (x_c)、表情形变 (δ)、旋转矩阵 (R)、平移向量 (t)、缩放 (s)
- 引入**表情-姿态解耦迁移损失**，随机采样两帧，相互交换姿态与表情，并施加感知损失（VGG19），强制学习到更干净的解耦表示。

### 2.2 第一阶段：音频条件扩散Transformer与运动解耦模块
- **自适应归一化**：表情参数使用全数据集均值和标准差进行归一化，而头部姿态参数则按每个身份独立计算私有统计量，以此促进两者的分离。
- **语音表征**：采用Wav2Vec2提取音频特征，并通过自注意力模块与运动特征对齐。
- **扩散Transformer**：以DDPM方式训练，输入带噪运动序列 `m_t`、音频特征 `f_a`、身份特征 `f_id` 和时间步，预测所加噪声，损失函数为：
  ```
  L_diff = E[||ε - ε̂_θ(m_t, f_a, f_id, t)||²]
  ```
- 架构上使用多个全连接层、Conformer、Pose-MLP与Exp-MLP组合实现。

### 2.3 第二阶段：情绪控制模块
- 冻结第一阶段扩散Transformer的参数，训练一个基于**DiT块**的情绪控制器。
- 该控制器接收Conformer输出与情绪条件，输出替换原Exp-MLP的输入，从而将情绪信息注入表情生成支路。
- 推理时采用**多条件无分类器引导(CFG)**，分别对音频和情绪条件设置引导尺度 `w_a` 和 `w_e`：
  ```
  ε̂_θ = ε̂_θ(m_t, ∅, ∅, f_id, t)
       + w_a [ε̂_θ(m_t, f_a, ∅, f_id, t) - ε̂_θ(m_t, ∅, ∅, f_id, t)]
       + w_e [ε̂_θ(m_t, f_a, f_e, f_id, t) - ε̂_θ(m_t, f_a, ∅, f_id, t)]
  ```
- 同步采用上一帧运动的高斯噪声增强策略，提升生成视频的时序一致性和对污染的抗干扰能力。

## 3. 实验设计

### 数据集
- 训练集：AVSpeech, CelebV-Text, Acappella, MEAD, MAFW 及自采数据集，共约80k视频片段（第一阶段）；MEAD、MAFW与自采数据中带有情绪标签的30k片段（第二阶段）。
- 测试集：
  - **HDTF**（域外公开数据集），约362个视频，原始分辨率720P/1080P
  - **自建测试集**（训练中未出现的采集视频）

### 对比基准
- 主流扩散/音频驱动方法：Hallo, Hallo2, MEMO, Sonic, JoyVASA
- 表情控制类方法：EAMM, DreamTalk, EDTalk, EAT

### 评估指标
- **视频质量**：FID、FVD、LPIPS、CSIM（身份保持）
- **唇同步**：Sync-C、Sync-D（预训练SyncNet）
- **情绪控制**：Emo-A（独立情绪分类器准确率）
- **用户研究**：MOS评分（唇同步、清晰度、自然度、视觉吸引力）

## 4. 算力资源
- 第一阶段：4块 NVIDIA A100 GPU，训练3天（从头初始化）
- 第二阶段：2块 NVIDIA A100 GPU，训练2天（冻结扩散Transformer）
- 优化器：Adam

## 5. 实验数量与充分性评估
Playmate进行了**多层次、多维度**的实验验证，包括：
- 两个测试集上的全面定量对比（6种指标，与5种SOTA方法比较）
- 多方法定性可视化对比（含唇动、牙齿渲染、姿态等多个细节）
- 不同风格肖像（真人、卡通、艺术图像、动物）的驱动效果展示
- 不同情绪条件下的生成对比
- 情绪控制的定量对比（与4种方法）
- 10人用户研究（MOS评估）
- 消融实验：
  - 自适应归一化的消融（定性）
  - 音频与情绪CFG尺度的消融（定量表）
  - 高斯噪声增强的消融（定性）
- 附录中补充了姿态控制评估（APD指标）和解耦可视化

实验覆盖了视频质量、唇同步、身份保持、情绪控制、姿态控制、跨风格泛化等多个关键维度，比较方法均为近期SOTA，指标选择合理，消融实验针对核心模块，整体**充分且客观**。

## 6. 主要结论与发现
- Playmate在HDTF和自建测试集上，**FID和FVD均大幅优于所有对比方法**，视频质量提升显著（FID降低约30%）。
- 身份保持（CSIM）和感知相似度（LPIPS）均取得最优，表明生成图像保真度高。
- 唇同步指标（Sync-C、Sync-D）达到第二或接近第一的水平，表现出强大竞争力，虽略低于Sonic（纯音频驱动），但Playmate提供了**远更灵活的属性控制能力**。
- 情绪控制实验表明，Playmate在视频质量和情绪识别准确率（Emo-A）上均超越专门的表情控制方法，实现了精准的情绪注入。
- 用户研究验证了在视觉清晰度和吸引力上的优势。

## 7. 优点与亮点
- **解耦能力强**：通过3D隐空间与自适应归一化、迁移损失，实现了表情与头部姿态的有效分离，属性可独立控制。
- **训练策略巧妙**：两阶段范式既保证了音频驱动的基本运动质量，又可在不破坏原有能力的前提下引入情绪控制。
- **控制灵活**：支持语音、情绪、参考姿态等多条件组合驱动，跨风格适应性强（真人、卡通、动物等）。
- **实验扎实全面**：定量、定性、用户研究、消融实验环环相扣，对比方法新、指标全，验证可信度高。

## 8. 不足与局限
- **处理范围受限**：仅生成面部区域，未包含上半身或全身，无法驱动全身动作。
- **极端姿态下伪影**：由于缺乏显式3D面片模型，大角度转头时可能出现边缘模糊、纹理粘连等问题。
- **背景一致性不足**：复杂背景下偶有轻微不一致现象。
- **表达多样性有限**：不同角色在相同音频下可能呈现较相似的表情模式，未探索更细粒度的风格控制。
- **训练数据偏向**：自建数据集的域外泛化性未详细讨论，可能存在身份、光照等偏差。

---

（完）
