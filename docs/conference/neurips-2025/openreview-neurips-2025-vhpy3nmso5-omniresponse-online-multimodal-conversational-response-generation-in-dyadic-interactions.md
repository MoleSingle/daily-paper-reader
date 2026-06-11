---
title: "OmniResponse: Online Multimodal Conversational Response Generation in Dyadic Interactions"
title_zh: OmniResponse：双人交互中的在线多模态对话响应生成
authors: "Cheng Luo, Jianghui Wang, Bing Li, Siyang Song, Bernard Ghanem"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=vhPy3NMsO5"
tags: ["query:talking-head"]
score: 7.0
evidence: 从多模态说话人输入生成同步面部反馈，用于对话式 talking head 动画
tldr: 针对在对话中实时生成与说话人输入同步的听众言语及面部反馈的困难，提出多模态大语言模型 OmniResponse。该模型利用时间戳文本标记（Chrono-Text Markup）精确对齐生成时间，自回归地产生准确的音频与面部响应，在自然双人交互数据集上验证了有效性。这一工作提升了对话式数字人反应的逼真度与同步性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhpy3nmso5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhpy3nmso5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhpy3nmso5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 599, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhpy3nmso5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vhpy3nmso5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1414, \"height\": 1119, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhpy3nmso5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhpy3nmso5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 722, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhpy3nmso5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1159, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vhpy3nmso5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1160, \"height\": 253, \"label\": \"Table\"}]"
motivation: 现有系统难以在对话中在线生成同步的言语与非言语听众反馈。
method: 采用多模态大语言模型结合 Chrono-Text Markup 精确时间戳，生成音频与面部响应。
result: 在双人交互场景下生成了高质量、同步的听众面部与声音响应。
conclusion: OmniResponse 为对话式数字人提供了更自然的响应生成方法。
---

## Abstract
In this paper, we introduce Online Multimodal Conversational Response Generation (OMCRG), a novel task designed to produce synchronized verbal and non-verbal listener feedback online, based on the speaker's multimodal inputs. OMCRG captures natural dyadic interactions and introduces new challenges in aligning generated audio with listeners' facial responses. To tackle these challenges, we incorporate text as an intermediate modality to connect audio and facial responses. We propose OmniResponse, a Multimodal Large Language Model (MLLM) that autoregressively generates accurate multimodal listener responses. OmniResponse leverages a pretrained LLM enhanced with two core components: Chrono-Text Markup, which precisely timestamps generated text tokens, and TempoVoice, a controllable online text-to-speech (TTS) module that outputs speech synchronized with facial responses. To advance OMCRG research, we offer ResponseNet, a dataset of 696 detailed dyadic interactions featuring synchronized split-screen videos, multichannel audio, transcripts, and annotated facial behaviors. Comprehensive evaluations on ResponseNet demonstrate that OmniResponse outperforms baseline models in terms of semantic speech content, audio-visual synchronization, and generation quality. Our dataset, code, and models are publicly available at https://omniresponse.github.io/.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：如何在实时（在线）双人对话中，根据说话人的多模态输入（语音、面部表情），同步生成听众的言语（音频）和非言语（面部）反馈。这是一个全新的任务，称为在线多模态对话响应生成（OMCRG）。
- **研究动机**：现有生成系统要么只生成单一模态（如仅音频或仅面部反应），要么是离线处理（需要完整输入序列），无法满足实时、同步、多模态对话需求，导致交互自然度受限。
- **整体含义**：论文试图为数字人、虚拟对话代理等应用提供一种能够像真人一样，边说边做出面部表情、在恰当时间点插话或反馈的生成能力。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：以文本为中间模态，将音频和面部同步问题分解为两个子任务：
  - (i) 联合文本与面部响应生成（预测面部参数和带时间信息的文本）；
  - (ii) 从带时间信息的文本生成同步音频。
- **整体框架 OmniResponse**：基于预训练的 MLLM，自回归地生成同步的多模态响应。
- **两个关键模块**：
  - **Chrono-Text Markup**：在文本 token 之间插入显式时间标记（`[PAUSE]` 表示沉默间隙，`[LASTING]` 表示前一单词持续），使文本序列与视觉帧序列长度精确对齐，解决文本无时间维度的问题。
  - **TempoVoice**：可控在线 TTS 模块。将生成的文本隐藏状态与声纹嵌入合并，通过 Transformer 解码器（使用零初始化占位符 token 作为 Query）自回归生成音频语义 token，再基于语义 token 重建同步语音波形。
- **模型架构**：
  - 使用视觉投影层将说话人和听众的面部特征映射到 LLM 的嵌入空间。
  - 通过全注意力机制（omni-attention）对静态文本（指令、历史）和动态多模态 token（视觉、带时间标记的文本）进行生成，动态 token 只能看到过去的 token。
  - 视觉解码器将生成的视觉嵌入还原为面部系数，再通过预训练渲染器生成 2D 帧。
- **训练目标**：加权组合文本生成损失（交叉熵）、视觉重建损失（L2 距离）、音频生成损失（语义 token 的交叉熵），如公式(1)–(4)。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：自建数据集 **ResponseNet**，包含 696 段同步双人视频（总计超过 14 小时），每段具有高分辨率（1024×1024）正脸流、分离的音轨、词级文本转录及面部行为标注。
- **评估指标**：
  - 文本：METEOR, BERTScore F1, ROUGE-L, Distinct-2；
  - 音频：UTMOSv2（自然度），LSE-D（唇音同步）；
  - 视频：FD（Fréchet Distance），FVD（Fréchet Video Distance）。
- **对比方法**：
  - 离线文本对话系统：GPT-4o, GPT-4, GPT-o1, Qwen-7B-Chat, Claude-Sonnet-4 等。
  - 在线音频对话系统：Moshi。
  - 面部反应生成系统：ReactFace, ViCo。
  - 在线多模态基线：LSTM 方法、Audio-visual LLM。
- **消融实验**：研究 Chrono-Text Markup 和 TempoVoice 各自的作用。
- **用户研究**：49 名参与者在多维偏好上进行 A/B 测试。

### 4. 资源与算力
- **GPU**：4 块 NVIDIA Tesla A100。
- **优化器**：AdamW，学习率 2×10⁻⁵，weight decay 10⁻⁴，cosine 调度。
- **训练细节**：batch size = 1，共训练 2000 个 epoch。LLM 部分采用 LoRA（秩 64，alpha 16）。
- 未明确说明训练总时长，仅给出硬件配置和训练轮次。

### 5. 实验数量与充分性
- **主要实验组数**：
  - 1 张主结果表（Table 2）对比了 10 种以上方法（含文本、音频、面部、多模态方法），共 8 项指标。
  - 1 张消融表（Table 3）验证两个关键模块的 4 种组合。
  - 1 张用户研究表（Table 4）报告 2 组对比的 4 项维度偏好。
  - 定性案例展示（Figure 5）。
- **充分性与公平性**：
  - 对比覆盖了单模态和多个代表性基线，指标涵盖语义、同步、质量等多方面，较为全面。
  - 所有比较均在自建的数据集上进行，由于缺乏现成可用在线多模态数据库，因此自建数据集是必要的。评估使用了客观指标和主观用户研究，但离线文本模型仅输出文本，无法直接比较其他模态。
  - 消融实验清晰展示了核心模块的贡献，公平性较好。
  - 缺少与其他可能的多模态对话模型的对比（因为任务新颖，基线少）。

### 6. 论文的主要结论与发现
- OmniResponse 能够在实时对话中生成语义合理、唇音同步的视频和音频听众响应。
- 引入文本中间模态和 Chrono-Text 时间标记，显著提升了音频-视觉同步和整体生成质量（LSE-D、UTMOSv2、FVD 等改善明显）。
- TempoVoice 模块对提高音频同步和质量有重要作用。
- 自建的 ResponseNet 数据集为 OMCRG 任务提供了基准，填补了数据空白。

### 7. 优点：方法或实验设计上的亮点
- **任务新颖**：首次定义并解决在线多模态对话响应生成，将言语与非言语反馈同步生成，更贴近自然交互。
- **创新性的时间对齐策略**：Chrono-Text Markup 用简单的特殊 token 实现文本与视频帧的精确对齐，避免复杂的时间戳处理。
- **模块化设计**：通过文本脱耦音频、面部生成，并可插入可控 TTS 模块，架构灵活。
- **高质量数据集**：ResponseNet 提供了详细的同步双人数据，涵盖多通道音频和面部标注，弥补了多模态对话数据的稀缺。
- **全面评估**：结合自动指标、消融实验和用户研究，验证了各方面的优越性。

### 8. 不足与局限
- **依赖训练数据**：模型性能取决于 ResponseNet 的质量与多样性，可能在非常规对话、噪声环境或非英语场景中效果下降。
- **实时性权衡**：虽然自称在线，但方法依赖文本生成后再合成语音，中间延迟未具体测量或说明，严格实时性可能受限。
- **公平性与泛化**：数据集从 YouTube 收集，可能存在人口偏差；缺少对模型在不同人群或情感强度下的公平性分析。
- **评估基准有限**：由于任务新，可对比的多模态基线较少，且离线文本模型只能比较文本指标。
- **文本预处理的隐蔽细节**：语音识别和文本校对的准确性可能影响模型训练，但论文未深入讨论这一点可能带来的误差。
- **生成质量上限**：自回归生成的唇形同步受限于 TempoVoice 的 TTS 和视觉渲染器，可能出现不自然的 artifacts。

（完）
