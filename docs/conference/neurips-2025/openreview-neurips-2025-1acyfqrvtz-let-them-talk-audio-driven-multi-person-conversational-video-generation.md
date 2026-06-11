---
title: "Let Them Talk: Audio-Driven Multi-Person Conversational Video Generation"
title_zh: "Let Them Talk: 音频驱动的多人对话视频生成"
authors: "Zhe Kong, Feng Gao, Yong Zhang, Zhuoliang Kang, Xiaoming Wei, Xunliang Cai, Guanying Chen, Wenhan Luo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1aCYFQRvtz"
tags: ["query:talking-head"]
score: 9.0
evidence: 音频驱动的多人对话视频生成，用于说话头动画
tldr: 针对现有音频驱动人体动画在多流音频输入时存在绑定错误及指令遵循能力差的问题，本文提出了一个新任务——多人对话视频生成，并设计了MultiTalk框架。该框架通过标签旋转位置嵌入和语音到动作扩散模型实现准确的音频-人物对应，再利用视频扩散模型生成高质量视频。实验表明，MultiTalk在保持视觉质量的同时显著改善了音频一致性，推动了说话头合成由单人向多人场景的拓展，为数字人与多角色互动场景提供了重要的技术基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1245, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1242, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1265, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1259, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1430, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1438, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1397, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1135, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1acyfqrvtz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 341, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1174, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1243, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 453, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 741, \"height\": 90, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1169, \"height\": 103, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1acyfqrvtz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1165, \"height\": 99, \"label\": \"Table\"}]"
motivation: 现有说话头生成仅支持单人，多音频流时人物绑定错乱且指令遵循能力不足。
method: 提出MultiTalk框架，设计标签旋转位置嵌入和语音到动作扩散模型，实现多人音频到动作映射，并用视频扩散模型合成。
result: 生成多人对话视频中人物唇形与音频精确同步，视觉质量高，明显优于现有单独生成再拼接的方法。
conclusion: MultiTalk首次解决多人对话视频生成难题，显著提升交互真实感，为数字人多角色场景应用开辟新方向。
---

## Abstract
Audio-driven human animation methods, such as talking head and talking body generation, have made remarkable progress in generating synchronized facial movements and appealing visual quality videos. However, existing methods primarily focus on single human animation and struggle with multi-stream audio inputs, facing incorrect binding problems between audio and persons. Additionally, they exhibit limitations in instruction-following capabilities. To solve this problem, in this paper, we propose a novel task: Multi-Person Conversational Video Generation, and introduce a new framework, MultiTalk, to address the challenges during multi-person generation. Specifically, for audio injection, we investigate several schemes and propose the Label Rotary Position Embedding (L-RoPE) method to resolve the audio and person binding problem. Furthermore, during training, we observe that partial parameter training and multi-task training are crucial for preserving the instruction-following ability of the base model. MultiTalk achieves superior performance compared to other methods on several datasets, including talking head, talking body, and multi-person datasets, demonstrating the powerful generation capabilities of our approach.

---

## 论文详细总结（自动生成）

# 论文深度分析与总结：Let Them Talk: Audio-Driven Multi-Person Conversational Video Generation

## 1. 论文核心问题与整体含义
现有音频驱动人体动画技术（如 talking head、talking body）在单人生成上取得了显著进展，但在面对**多人对话场景**时存在严重不足：
- 无法处理多路音频输入，出现音频与人物错误绑定的问题；
- 生成的视频中所有人的嘴唇运动趋向一致，无法实现交替说话；
- 对文本指令遵循能力差，难以控制大范围身体动作或交互。
基于此，本文首次提出**音频驱动的多人对话视频生成**这一新任务，并构建 **MultiTalk** 框架，旨在同时满足：
- 多人出现在同一画面；
- 每人的唇部运动仅受各自音频驱动；
- 视频整体保持视觉连贯性与交互真实性。

---

## 2. 方法论
### 2.1 整体框架
MultiTalk 基于 DiT 架构的图像到视频扩散模型（Wan2.1-I2V-14B），在其各 DiT 块中插入**额外的音频交叉注意力层**，并通过以下核心设计解决多人绑定与指令遵循问题。

### 2.2 音频嵌入与注入
- 使用 **Wav2Vec** 提取音频特征，并采用上下文窗口融合前后帧特征。
- 针对 3D VAE 时间压缩导致的维度不匹配，提出**音频适配器（Audio Adapter）**：首帧与后续下采样帧分别通过多层 MLP 并拼接后编码，得到压缩后的音频条件 \(c_a\)。

### 2.3 多人音频绑定：L-RoPE
将旋转位置编码（RoPE）扩展为 **标签旋转位置编码（Label Rotary Position Embedding, L-RoPE）**，解决多路音频与多人物的精准对应问题。
- **自适应人物定位**：利用 DiT 自注意力图计算 latent token 与参考图各区域（人物1、人物2、背景）的相似度，动态定位视频中每个人物的空间区域。
- **标签分配与旋转**：
  - 对两个人物指定不同的标签范围（如人物1：0~4，人物2：20~24），背景固定为标签12；
  - 多路音频拼接后，分别赋予标签2和22；
  - 将标签转换为旋转角度 \(\theta_i = l_i \times \theta_{\text{base}}\)，对查询向量进行旋转，从而在计算音频交叉注意力时，音频仅响应其对应人物区域的 query，实现 **“软绑定”**。

### 2.4 训练策略
- **两阶段训练**：阶段一使用单说话人数据训练基础音频驱动能力；阶段二引入双人对话数据。
- **部分参数训练**：仅更新音频交叉注意力和适配器参数，冻结基础模型其余部分，避免指令遵循能力衰退和物体畸变。
- **多任务训练**：AI2V（音频+图像→视频）与 I2V（仅图像→视频）任务混合训练。I2V 任务使用包含多人交互、物体操作等多事件视频数据，以保留模型对复杂指令的遵循能力。

### 2.5 长视频生成
采用自回归策略，将前一次生成视频的最后5帧作为额外条件注入后续推理，实现数分钟级长视频生成。

---

## 3. 实验设计
### 3.1 数据集
- **训练集**：
  - 阶段一：约 2K 小时单人说话头/半身视频
  - 多任务 I2V：约 20 万段含交互的多事件视频（平均时长约 10 秒）
  - 阶段二：约 100 小时双人对话视频
- **测试集**：
  - Talking head：**HDTF**、**CelebV-HQ**
  - Talking body：**EMTD**
  - 双人对话：自建 **MTHM**（40段视频）

### 3.2 Baselines
- 单人头生成：AniPortrait、VExpress、Echomimic、Hallo3、Sonic、Fantasy Talking
- 半身生成：Echomimic v2、Fantasy Talking
- 多人对话尚无现有方法，与“独立生成后视频拼接”对比。

### 3.3 评估指标
视频质量：**FID**, **FVD**  
面部表现力：**E-FID**  
唇音同步：**Sync-C**, **Sync-D**

---

## 4. 资源与算力
- **GPU**：64 块 NVIDIA H800-80G
- **优化器**：AdamW，恒定学习率 2e-5，带 warm-up
- **Batch size**：阶段一 64，阶段二 32
- 模型仅微调少量参数，成本相对可控。

---

## 5. 实验数量与充分性
实验覆盖较全面，包括：
- **主实验**：在 talking head、talking body、多人对话三场景共四个测试集上进行定量比较（表1、表2、图6、图7）。
- **消融实验**：
  - 音频注入策略（表4，图3的四种方案）
  - L-RoPE 标签范围选择（表3）
  - 训练策略（全参数 vs. 仅交叉注意力训练，表5，图9）
  - 多任务训练影响（图5）
- **扩展分析**：情感控制（图11）、三人场景泛化（图12）、长视频生成（图10）、真实音频 vs. TTS 音频（局限性讨论）。
整体实验设计客观、公平，对比基线丰富，消融充分。

---

## 6. 主要结论与发现
1. **MultiTalk 成功实现多路音频驱动的多人对话视频生成**，唇音同步准确，且不会出现所有人同时说话的错误。
2. **L-RoPE 通过可学习的软绑定机制，显著优于直接拼接、加和或硬分割注入方式**，且对标签范围选择不敏感。
3. **仅微调音频相关模块并采用多任务混合训练，是保留基础模型指令遵循能力的关键**；全参数训练在数据量有限时导致运动控制力和物体质量下降。
4. 多人训练模型在单人测试集上的性能与仅训练单人的模型持平，证明**多路音频训练不会损害单人动画能力**。

---

## 7. 优点
- **首创新任务**：开创性地提出并解决了音频驱动多人对话视频生成问题，填补领域空白。
- **创新的绑定机制**：将 RoPE 扩展为 L-RoPE，实现高效、自适应的音频-人物对应，无需硬性分割图像。
- **训练策略务实有效**：部分参数训练和多任务混合策略在计算资源有限时保护了预训练大模型的通用视频生成能力。
- **良好的泛化性**：可扩展到三人或更多人物，支持情感控制、长视频生成。
- **系统的实验验证**：跨多种数据集和基线，涵盖定量与定性分析，消融完整。

---

## 8. 不足与局限
- **对真实音频的依赖**：模型在 TTS 合成音频上的表情生动性下降，因为训练仅使用带有自然情感的真实音频。
- **数据集偏差**：训练数据以正面、常规肢体动作为主，种族、年龄分布不均衡（白人 61%，30-49 岁占 76%），可能影响多样性场景下的公平性。
- **未完全开源**：论文本身未提供代码或预训练模型，复现门槛较高。
- **实验规模局限**：双人评估集仅 40 段视频，可能不足以完全反映真实世界复杂性。
- **社会伦理风险**：多人 deepfake 风险更高，文中虽提及但未给出具体缓解方案。

---

（完）
