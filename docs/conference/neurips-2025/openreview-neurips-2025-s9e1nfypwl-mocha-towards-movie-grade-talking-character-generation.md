---
title: "MoCha: Towards Movie-Grade Talking Character Generation"
title_zh: MoCha：迈向电影级说话角色生成
authors: "Cong Wei, Bo Sun, Haoyu Ma, Ji Hou, Felix Juefei-Xu, Zecheng He, Xiaoliang Dai, Luxin Zhang, Kunpeng Li, Tingbo Hou, Animesh Sinha, Peter Vajda, Wenhu Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=S9E1nfYPwl"
tags: ["query:talking-head"]
score: 9.0
evidence: 从语音和文本生成说话角色动画，扩展了说话头生成
tldr: 当前视频生成虽取得进展，但忽略角色驱动的故事叙述；为此提出MoCha，首个从语音和文本生成完整肖像的说话角色动画模型。通过局部音频注意力机制实现语音与视频的精确同步。实验表明MoCha能生成电影级质量的说话角色视频，推动了自动动画生成的发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 1071, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1014, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 873, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1395, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1327, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1331, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1429, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1431, \"height\": 174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1436, \"height\": 172, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 702, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 661, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 708, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1279, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1393, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 297, \"label\": \"Table\"}]"
motivation: 现有视频生成忽略角色驱动的故事叙述，缺乏从语音和文本生成说话角色的能力。
method: 提出MoCha模型，采用局部音频注意力机制对齐语音和视频令牌，实现语音到视频的精准同步。
result: 实验显示MoCha能生成电影级质量的说话角色动画，超越仅限面部区域的说话头任务。
conclusion: MoCha实现了首个电影级说话角色生成，为自动电影和动画制作开辟新可能。
---

## Abstract
Recent advancements in video generation have achieved impressive motion realism, yet they often overlook character-driven storytelling, a crucial task for automated film, animation generation. 
We introduce Talking Characters, a more realistic task to generate talking character animations directly from speech and text. Unlike talking head tasks, Talking Characters aims at generating the full portrait of one or more characters beyond the facial region. 
In this paper, we propose MoCha, the first of its kind to generate talking characters. To ensure precise synchronization between video and speech, we propose a localized audio attention mechanism that effectively aligns speech and video tokens.
To address the scarcity of large-scale speech-labelled video datasets, we introduce a joint training strategy that leverages both speech-labelled and text-labelled video data, significantly improving generalization across diverse character actions. We also design structured prompt templates with character tags, enabling, for the first time, multi-character conversation with turn-based dialogue—allowing AI-generated characters to engage in context-aware conversations with cinematic coherence.
Extensive qualitative and quantitative evaluations, including human evaluation studies and benchmark comparisons, demonstrate that MoCha sets a new standard for AI-generated cinematic storytelling, achieving superior realism, controllability and generalization.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

*   **现状与空白**：当前的视频生成模型（如Sora、Pika等）在运动真实性上取得突破，但普遍忽略了**角色驱动的电影级叙事**，生成的对话场景缺乏与语音同步的唇部运动、表情和肢体语言，人物显得呆板无力。与此同时，现有的说话头生成（Talking Head）技术仅能生成裁剪后的面部区域，依赖参考图像、姿态等辅助信号，无法处理全身动作、摄像机运动和多人交互，难以应用于真实的影视制作。
*   **提出新任务**：为填补这一空白，论文正式定义了一个新任务——**“Talking Characters”**（说话角色生成），其目标是直接基于**自然语言文本和原始语音**，生成具有完整肖像（全身或多个角色）、同步语音、真实情感、复杂动作和动态镜头运动的数字角色视频，旨在实现**自动化的、以对话为核心的电影制作**。

## 2. 论文提出的方法论（核心思想、关键技术细节）

### 2.1 整体架构：端到端的DiT模型 (MoCha)
*   **核心思想**：MoCha是一个**完全端到端的扩散Transformer (DiT)**，摒弃了传统说话头方法依赖的人脸关键点、姿态骨架等**辅助控制信号**，直接从语音和文本联合条件下学习生成视频。
*   **架构流程**：
    *   **视频编码**：使用3D VAE将视频压缩为时空潜在表示 $x_0$，下采样倍率为空间8倍、时间4倍（r=4）。
    *   **文本编码**：联合UL2、ByT5和MetaCLIP三个编码器，提取语义特征。
    *   **语音编码**：使用Wav2Vec2提取所有中间层的特征，并通过插值确保语音令牌数与原始视频帧数一致，再经MLP投影。
    *   **生成过程**：在DiT模块内部，视频令牌先进行自注意力，再依次与文本令牌和音频令牌进行交叉注意力，采用流匹配（Flow Matching）目标进行训练。
    *   **优势**：完全令牌化设计表明，仅依赖端到端训练即可实现强大的音视频对齐，无需额外的掩码或关键点监督。

### 2.2 局部音频注意力（Localized Audio Attention）
*   **问题**：3D VAE的时间压缩导致视频令牌（步长为 $\tau$）与原始语音令牌（步长为 $T$）之间存在**时间分辨率不匹配**（$\tau = T/r$）。全局注意力会让视频令牌建立错误的音视频关联。
*   **方法**：提出一种**局部窗口注意力机制**。对于时间步 $i$ 的视频令牌，限制其只关注一个窄窗口内的音频令牌：
    $$j \in [\max(1, (i-1)r - 1), \min(T, ir + 1)]$$
    该窗口大小为 $r+2$，对应于该视频令牌所覆盖的原始时段并包含1个令牌的上下文填充。
*   **作用**：此设计强制模型关注局部音素模式，有效提升了**唇形同步精度**和时序连贯性。

### 2.3 多角色轮次对话与结构化提示词
*   **多段生成**：MoCha利用自注意力跨所有视频令牌，能够**并行生成**包含多个镜头的视频（如两人对话），无需自回归扩展或额外结构。音频中说话人的切换隐式引导镜头切换。
*   **字符标记机制**：为解决传统文本描述冗长、易混淆角色的问题，设计了结构化提示模板：
    *   定义区：“Characters: (Person1) 角色外貌描述, (Person2) ...”
    *   叙述区：每个镜头描述仅使用`Person1`、`Person2`等唯一标签，而非重复外貌。
    *   **效果**：使多角色对话提示词更简洁、清晰，保证了跨镜头的**角色一致性**。

### 2.4 基于课程学习的多模态训练策略
*   **混合模态采样**：每次迭代中，使用**80%的语音+文本数据**（用于细粒度音视频对齐）和**20%的纯文本数据**（用于保持视觉多样性）。当输入纯文本时，语音嵌入向量置零。
*   **镜头类型课程学习**：训练从简单到困难分阶段进行：
    *   **阶段0**：在大规模纯文本视频数据上预训练，建立视觉先验。
    *   **阶段1-N**：逐步引入语音标注数据，从高音画相关性的**特写镜头**（1个角色）开始，再逐渐加入中景、全景、多角色、多镜头等复杂场景。在每个阶段，按比例减少上一阶段的简单样本占比。
*   **目的**：解决了语音标注数据稀缺且多样性不足的问题，并使模型能渐进地掌握从细微口型到复杂全身动作的生成能力。

## 3. 实验设计

*   **评估基准**：作者构建了针对该任务的专用基准**MoCha-Bench**，包含**200个**多样化样本，每个样本均有文本提示和音频。基准覆盖了不同的镜头类型（特写、中景等）、摄像机运动、人类活动、情绪、面部朝向和物体交互等。
*   **对比方法**：选取了当前最优的音频驱动说话脸生成模型：**SadTalker**、**AniPortrait** 和 **Hallo3**。由于这些方法需要参考图像作为输入，为确保公平，实验中使用MoCha生成视频的**首帧**（经过裁剪/缩放）作为它们的初始图像。
*   **评估指标**：
    *   **自动指标**：**Sync-C**和**Sync-D**（基于SyncNet的唇同步指标）。
    *   **人类评估**：邀请标注员对五个维度（**唇同步质量、表情自然度、动作自然度、文本对齐、视觉质量**）进行1-4分评分（4分接近真实视频/电影级）。
    *   **消融实验**：对局部音频注意力模块设计（与RoPE、Sinusoidal等对比）、课程多模态训练策略、字符标记机制进行了消融研究。

## 4. 资源与算力

*   **模型规模**：MoCha建立在预训练的**30B参数**MovieGen骨干网络之上。
*   **训练资源**：论文中提到训练分布在 **64个计算节点** 上，并在课程学习的不同阶段使用了不同规模的GPU集群（如1024、512块GPU）。但文中**未明确说明**GPU的具体型号（如A100/H100）、单节点数量以及具体的总训练时长。

## 5. 实验数量与充分性

*   **实验丰富度**：实验设计**非常充分和全面**。
    *   包含**1组主实验**（与3个SOTA模型的定性和定量对比）、**3组大型消融实验**（整体架构、训练策略、提示词策略），以及一组针对**音频交叉注意力模块内部设计的微型消融研究**（对比了6种不同的注意力方案，并使用4B小模型进行实验以节省算力）。
    *   评估方法客观立体，结合了**自动指标、大规模人类评估（每模型超1000次评分）和大量可视化对比**。
*   **公平性**：与需要辅助输入的基线方法对比时，采用了其生成的视频首帧作为输入，尽可能减少了非对称条件带来的偏差。但不同方法的任务设定（如是否生成全身）的根本不同依然存在，这在评估维度中已做区分。

## 6. 主要结论与发现

*   **性能优越**：MoCha在所有五个评估维度上均**显著优于**现有最佳方法（在人类评估中相对第二名平均提升约1.5分），生成质量已接近真实影视制作水平。
*   **端到端可行性**：实验证明，无需面部关键点、姿态等复杂辅助信号，仅通过充分的端到端训练，DiT模型就能从语音中学习到强大且精确的音视频对齐能力。
*   **关键设计有效**：**局部音频注意力**是处理时序错配、提升唇同步的关键；**混合多模态课程学习**对于保证模型在多样复杂场景下的泛化能力至关重要；**字符标记**机制是实现连贯多角色对话视频生成的基础。

## 7. 优点

*   **任务引领性**：首次定义了“说话角色生成”这一更具挑战性和应用价值的任务，并提供了首个解决方案和基准。
*   **架构简洁有效**：作为首个针对此任务的端到端DiT模型，抛开了传统方法的辅助信号依赖，证明了“语音+文本”直接条件的可行性。
*   **技术创新**：提出的**局部音频注意力**机制巧妙解决了DiT架构下的音视频对齐难题，是技术上的一大亮点。
*   **系统级解决策略**：通过**课程学习、混合数据采样和结构化提示词**一整套策略，系统性地解决了数据稀缺、任务复杂度差异和多角色一致性等实际训练难题。
*   **评估严谨**：建立了专用基准，进行了包含自动指标和精细人类评估的全面对比，以及深入的组件消融实验，论证极为扎实。

## 8. 不足与局限

*   **极端场景表现不佳**：
    *   **广角镜头唇同步失效**：当文本提示模糊导致生成全景镜头时，由于唇部区域过小，像素信息不足，模型无法完成精确的唇形同步。
    *   **多角色同镜头混淆**：当多个角色的面部清晰出现在同一镜头内时，模型有时会混淆谁是当前说话者，导致唇同步质量下降，这源于训练数据中此类场景的稀缺。
*   **参数敏感性**：过高的语音分类器引导（CFG）值可能导致角色表情和身体动作**过度夸张**，破坏真实感。
*   **潜在偏见**：与所有生成模型一样，输出可能反映出训练数据中存在的肤色、行为或文化表征方面的偏见，需要持续关注和治理。
*   **伦理风险**：尽管不克隆真实身份，但生成的说话角色视频仍可能被滥用于制造虚假信息，带来合成媒体伦理风险。

（完）
