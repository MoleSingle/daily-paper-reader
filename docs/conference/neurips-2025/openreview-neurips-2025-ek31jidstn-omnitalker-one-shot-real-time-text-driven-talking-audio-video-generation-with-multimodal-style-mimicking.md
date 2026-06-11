---
title: "OmniTalker: One-shot Real-time Text-Driven Talking Audio-Video Generation With Multimodal Style Mimicking"
title_zh: "OmniTalker: 一次实时文本驱动的多模态风格模仿说话音视频生成"
authors: "Zhongjian Wang, Peng Zhang, Jinwei Qi, wang guang yuan, Sheng Xu, Bang Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=eK31JidsTN"
tags: ["query:talking-head"]
score: 10.0
evidence: 从输入文本生成同步的说话音频视频内容，并模仿多模态风格
tldr: 针对文本驱动说话头生成研究不足的问题，提出OmniTalker统一框架，通过双分支扩散Transformer从文本联合生成同步的说话音频和视频，并模仿目标身份的语言和面部动态风格。实验证明其能实时生成高质量、风格一致的内容，拓展了说话头生成的应用场景。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1395, \"height\": 1152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 775, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1195, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1430, \"height\": 1344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1434, \"height\": 1326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 1174, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1331, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1100, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1311, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1163, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1390, \"height\": 388, \"label\": \"Table\"}]"
motivation: 现有说话头生成主要依赖音频驱动，文本驱动方法未被充分探索。
method: 采用双分支扩散Transformer架构，一个分支生成音频，另一个生成视频，浅层融合跨模态信息。
result: 实现实时生成，在说话风格模仿和唇音同步方面表现优异。
conclusion: OmniTalker实现了从文本到说话音视频的统一生成，推动了多模态虚拟人交互。
---

## Abstract
Although significant progress has been made in audio-driven talking head generation, text-driven methods remain underexplored. In this work, we present OmniTalker, a unified framework that jointly generates synchronized talking audio-video content from input text while emulating the target identity's speaking and facial movement styles, including speech characteristics, head motion, and facial dynamics. Our framework adopts a dual-branch diffusion transformer (DiT) architecture, with one branch dedicated to audio generation and the other to video synthesis.
At the shallow layers, cross-modal fusion modules are introduced to integrate information between the two modalities. In deeper layers, each modality is processed independently, with the generated audio decoded by a vocoder and the video rendered using a GAN-based high-quality visual renderer. Leveraging DiT’s in-context learning capability through a masked-infilling strategy, our model can simultaneously capture both audio and visual styles without requiring explicit style extraction modules.  Thanks to the efficiency of the DiT backbone and the optimized visual renderer, OmniTalker achieves real-time inference at 25 FPS.
To the best of our knowledge, OmniTalker is the first one-shot framework capable of jointly modeling speech and facial styles in real time. Extensive experiments demonstrate its superiority over existing methods in terms of generation quality, particularly in preserving style consistency and ensuring precise audio-video synchronization, all while maintaining efficient inference.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：当前的说话头生成（Talking Head Generation, THG）技术主要依赖于**音频驱动**，而**文本驱动**的方法研究不足。现有的文本驱动方案通常采用“文本转语音（TTS）+ 音频驱动说话头”的级联架构，存在**计算冗余、误差累积、音视频风格不一致**三大缺陷。
- **研究动机**：随着对话式AI和大型语言模型的发展，文本驱动的音视频生成需求日益增长，亟需一种能够直接从文本生成同步、高质量、且具有身份特有说话风格（语音特征、头部运动、面部动态）的端到端框架。
- **整体含义**：论文提出了 **OmniTalker**，一个统一的、**一次性（One-shot）**、**实时**的文本驱动说话人生成框架，旨在从输入文本联合生成同步的说话音频和视频，并模仿目标人物的多模态说话风格。

### 2. 论文提出的方法论
- **核心思想**：采用**双分支扩散Transformer**架构，并结合**上下文学习**能力，通过**掩码填充**策略统一建模音视频风格，无需显式的风格提取模块。
- **多模态特征对齐**：
    - **音频特征**：参考视频音频 $A_r$ 转为梅尔频谱 $M_r$，经MLP编码为 $x_a$。
    - **视觉特征**：参考视频 $V_r$ 每帧提取包括表情、头部姿势和眼球运动系数的视觉代码 $C_r$，经MLP编码为 $x_v$。
    - **文本特征**：驱动文本 $T_d$ 和参考文本 $T_r$（由ASR从$A_r$转录）转为字符序列，通过ConvNeXt-V2模块编码为条件嵌入 $c_t$。
- **关键技术细节**：
    - **双分支DiT架构**：
        - **浅层**：引入**跨模态融合模块**，在音频和视频分支间进行信息整合。论文通过实验对比了多种融合策略（Add、Linear、Cross-Attention），最终采用**多模态联合注意力**以获得最佳音视频同步效果。
        - **深层**：融合后的特征分别进入**单模态DiT块**，独立处理以精细化各自模态的生成。
    - **上下文风格化生成**：采用**掩码填充**策略，在训练时随机遮蔽音视频序列片段，迫使模型根据上下文（参考片段和文本）重建被遮蔽部分，从而隐式学习风格。推理时，输入由参考音视频对、驱动文本和目标序列的噪声占位符组成。
    - **生成范式**：采用 **Flow Matching** 方法训练模型，相比传统扩散模型具有更优的训练和采样效率。其条件流匹配损失函数约束模型预测向量场，以将噪声分布转换为目标数据分布。
    - **无分类器引导(CFG)**：在训练时随机丢弃条件输入，推理时通过多条件CFG增强生成质量和风格复刻。
    - **解码器**：生成的梅尔频谱通过声码器解码为音频；生成的视觉代码结合GAN渲染器，合成最终的高质量说话人视频。

### 3. 实验设计
- **数据集**：使用了多套数据集进行评估。
    - **音频评估**：SEED 数据集（中文和英文）
    - **视频评估**：VoxCeleb2（随机选取500段）和一个包含100段中文真实场景的Custom数据集。
    - **训练数据**：在大规模开源说话头数据集上预训练，并在一个收集的**690小时高质量数据集**上进行微调。
- **Benchmark与对比方法**：
    - **TTS模块对比**：MaskGCT、F5TTS 和 CosyVoice，评估指标为**词错误率(WER)** 和**说话人相似度(SIM-A)**。
    - **说话头生成对比**：GAN方法（SadTalker、AniTalker）、扩散模型方法（EchoMimic、Hallo）和风格保持方法（StyleTalk）。评估指标包括**FVD**（视频质量）、**Sync-C**（唇音同步）、**CSIM**（身份保持）以及新提出的**E-FID**和**P-FID**（面部表情和头部姿势的风格保真度）。
    - **用户研究**：50名志愿者对语音相似度、节奏、视觉质量、说话风格、唇音同步和姿势同步进行MOS评分。

### 4. 资源与算力
- **训练算力**：模型在 **8 块 NVIDIA A100 GPU** 上进行训练，批量大小为每GPU 12,800帧，共迭代 75 万次。
- **推理算力**：模型在单个 **NVIDIA RTX 4090 GPU** 上实现**实时推理**，速度达到 **25 FPS**。
- **模型规模**：总参数量为 **0.8B**。

### 5. 实验数量与充分性
- **实验数量**：论文设计了充足且多维度的实验。
    - **量化评估**：在多个标准数据集上进行量化对比。
    - **模块化评估**：由于无直接竞品，将任务分解为TTS和THG两个子任务，分别与各自领域内最先进的方法进行比较，设计客观。
    - **消融实验**：专门对比了不同的跨模态融合策略。
    - **定性分析**：通过可视化头部姿势轨迹、人脸运动热力图、眼球运动时间序列和情绪生成效果，直观对比了模型的优越性。
    - **用户研究**：补充了主观感受评估。
    - **公平性**：在视频对比中，所有音频驱动方法均统一使用OmniTalker生成的音频作为输入，确保了公平性。实验覆盖全面，验证充分。

### 6. 论文的主要结论与发现
- **统一框架优势**：OmniTalker作为首个端到端统一框架，成功地从文本直接生成同步且高质量的音视频，在生成质量上超越了传统级联方案。
- **风格模仿卓越**：在表情保真度（E-FID）和头部姿势保真度（P-FID）上，OmniTalker表现远超所有基线模型，证明了其在精确模拟个人说话风格方面的显著优势。
- **实时高性能**：通过紧凑的模型架构和Flow Matching技术，OmniTalker在保持高质量输出的同时，实现了25FPS的实时推理性能。
- **模态融合有效性**：消融实验证实，多模态联合注意力（MM-Attention）是融合音频和视觉特征最有效的方法，对提升整体性能至关重要。

### 7. 优点
- **架构创新**：首次提出双分支DiT架构用于联合生成音视频，并在浅层进行跨模态融合，在深层进行单模态精细化的设计，有效平衡了跨模态交互和模态内质量。
- **风格模仿简洁高效**：利用DiT的上下文学习能力和掩码填充策略，无需设计复杂的、独立于框架的风格提取与注入模块，即可实现优秀的多模态风格迁移。
- **实时性**：在保证生成质量和风格一致性的同时，实现了25FPS的实时推理，具备很强的应用潜力。
- **评估全面**：提出E-FID和P-FID指标，细致地评估面部动态风格，并辅以充分的消融和用户研究，论证严谨。

### 8. 不足与局限
- **生成范围局限**：当前方法仅聚焦于头部区域的动态生成，未包含手势和身体姿态建模，限制了内容表达的完整性和交互性。
- **视觉渲染瓶颈**：GAN渲染器在处理大幅度头部运动时，仍可能出现纹理模糊和边界不连续等伪影，影响极端情况下的视觉真实性。
- **多语言扩展性**：文中仅展示了中英文能力，其性能在其他语言或方言上的泛化能力有待验证。
- **数据与伦理风险**：该技术存在被滥用于制作深度伪造视频的潜在风险，尽管论文提到了添加水印等缓解措施，但伦理风险依然存在。

（完）
