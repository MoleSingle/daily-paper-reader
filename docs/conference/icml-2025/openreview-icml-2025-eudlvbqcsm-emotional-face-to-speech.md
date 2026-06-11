---
title: Emotional Face-to-Speech
title_zh: "情绪面孔到语音: 从表情生成情感语音"
authors: "Jiaxin Ye, Boyuan Cao, Hongming Shan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EuDlvBqcSm"
tags: ["query:talking-head"]
score: 4.0
evidence: 从面部线索合成情感语音用于虚拟角色配音
tldr: 从表情面孔推断情感语音具有挑战性，现有方法难以生成多样化的情感风格。本文提出DEmoFace框架，利用离散扩散Transformer和多模态对齐技术，直接从面部表情生成情感语音。实验结果显示，该方法能合成富有表现力的语音，为虚拟角色配音和辅助表达障碍人士提供了新的可能性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1669, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1674, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1747, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1655, \"height\": 708, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1714, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 826, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1839, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1544, \"height\": 1329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1681, \"height\": 676, \"label\": \"Table\"}]"
motivation: 现有面部到语音方法难以生成具有情感表达的多变语音风格，限制了虚拟角色配音等应用。
method: 提出DEmoFace框架，采用离散扩散Transformer和课程学习，结合多级神经音频编解码器，并通过多模态DiT块动态对齐面部表情与语音。
result: DEmoFace能够从表情丰富的面部线索合成情感丰富的语音，生成多样的情感声音风格。
conclusion: DEmoFace为从面部表情生成情感语音提供了新途径，有助于虚拟角色配音和辅助表达障碍人群。
---

## Abstract
How much can we infer about an emotional voice solely from an expressive face? This intriguing question holds great potential for applications such as virtual character dubbing and aiding individuals with expressive language disorders. Existing face-to-speech methods offer great promise in capturing identity characteristics but struggle to generate diverse vocal styles with emotional expression. In this paper, we explore a new task, termed *emotional face-to-speech*, aiming to synthesize emotional speech directly from expressive facial cues. To that end, we introduce  **DEmoFace**, a novel generative framework that leverages a discrete diffusion transformer (DiT) with curriculum learning, built upon a multi-level neural audio codec. Specifically, we propose multimodal DiT blocks to dynamically align text and speech while tailoring vocal styles based on facial emotion and identity. To enhance training efficiency and generation quality, we further introduce a coarse-to-fine curriculum learning algorithm for multi-level token processing. In addition, we develop an enhanced predictor-free guidance to handle diverse conditioning scenarios, enabling multi-conditional generation and disentangling complex attributes effectively. Extensive experimental results demonstrate that DEmoFace generates more natural and consistent speech compared to baselines, even surpassing speech-driven methods. Demos of DEmoFace are shown at our project https://demoface.github.io.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 格式对这篇《Emotional Face-to-Speech》论文进行结构化、深入且客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题：** 论文探讨了一个核心科学问题：“我们能在多大程度上仅从一张富有表情的面孔推断出其情感化的声音？” 这本质上是研究视觉线索（面部表情）与听觉预期（情感语音）之间的跨模态映射关系。
*   **研究动机与背景：**
    *   **现有技术局限：** 当前的主流技术“面部到语音”旨在根据人脸图像生成匹配其身份的语音，但往往忽略了面部本身携带的丰富“情感”信息，导致生成的语音风格单一、情感平淡，无法满足虚拟角色配音、人机交互等领域对富有表现力语音的需求。
    *   **任务拓展：** 为填补这一空白，论文将传统的F2S任务拓展，首次提出了一个新任务——**情感面部到语音**。该任务的目标是仅从一张人脸图像中解耦出“身份”和“情感”双重信息，并据此生成既符合说话人身份特征，又饱含对应情感表现力的语音。

### 2. 方法论

论文提出了一个名为 **DEmoFace** 的生成式框架，其核心思想是利用离散扩散模型处理压缩的语音 Token，并通过多模态条件控制实现情感语音生成。关键技术细节总结如下：

*   **核心思想：**
    *   将高维、连续的语音波形压缩到低维、离散的 Token 空间（使用残差向量量化， RVQ 音频编解码器），以简化生成任务，提高效率和稳定性。
    *   使用**离散扩散模型 (DDM)** 在离散 Token 空间上进行生成，通过迭代式并行解码，比传统的自回归模型更高效、更多样。
    *   设计精巧的多模态条件注入机制，将文本内容、人脸身份、面部表情三类条件有效地融合进扩散模型的逆扩散过程中。

*   **关键技术细节：**
    *   **多级语音 Token 化与扩散**：首先使用 RVQ 编解码器将语音波形转化为 12 层递进的离散 Token 序列，然后在这些离散 Token 上执行“吸收态”掩码扩散和去噪过程。
    *   **多模态 DiT 模块**：作为模型骨干，它通过两种方式注入条件：
        1.  **身份和情感条件**：通过自适应层归一化注入全局的“面部风格”条件（身份 `cid` + 情感 `cemo`）。
        2.  **文本条件**：通过交叉注意力机制注入，以动态对齐语音的文本内容 `ctext`， 学习与面部风格相关的语言学表达。
    *   **粗到细的课程学习**：观察到不同层级的 RVQ Token 呈现从低频到高频的信息分布，因此提出课程学习策略。训练从低层（含主要语义信息）Token 开始，每隔 3 个 epoch 逐步引入更高层（含声学细节）的 Token，以提升训练效率和生成质量。
    *   **增强的无分类器引导**：为了解决复杂的多条件（身份、情感、文本）生成问题，从能量模型的角度提出，将“组合式”得分（解耦各个局部条件的影响）与“联合式”得分（统一所有条件的影响）相乘，得到一个最终的调制得分，从而更精细地控制多条件生成过程。

### 3. 实验设计

*   **数据集：**
    *   **预训练（增强语义）**：引入了来自 LRS3 的 10 小时数据子集。
    *   **主实验数据集**：合并了三个包含人脸视频和语音配对的数据集，总计 31.33 小时，包含 26,767 条语音，7 种基本情绪（如生气、厌恶、恐惧、高兴、中性、悲伤、惊讶）和 953 个说话人。
        1.  RAVDESS
        2.  MEAD
        3.  MELD-FAIR

*   **基准方法 (Benchmarks)**：严格遵循任务设定，对比方法分为两类：
    *   **声学引导的语音生成**：这些方法在训练或推理时，使用了参考语音的声学特征作为身份引导，属于“非公平比较”的上限参照。包括 EmoSpeech， FastSpeech2， V2C-Net， HPM 和 StyleDubber。
    *   **视觉引导的语音生成**：这是与 `DEmoFace` 更为公平的比较对象，模型仅依赖视觉输入生成语音。主要是 **Face-TTS**。

*   **评估指标：**
    *   **客观指标**：情感相似度（`EmoSim`）， 说话人相似度（`SpkSim`）， 基频（F0）的均方根误差（`RMSE`）， 梅尔倒谱失真（`MCD`）， 词错误率（`WER`）。
    *   **主观指标**：进行了用户研究，评估语音的自然度（`MOS nat`）、身份相似度（`MOS id`）和情感相似度（`MOS emo`）。

### 4. 资源与算力

*   **GPU 型号**：24GB NVIDIA RTX 4090 GPU。提及不同模块（如扩散模型、身份编码器）的训练均使用了该型号 GPU。
*   **GPU 数量**：文中提到音频编码器训练使用 1 张 GPU，未明确指出 `DEmoFace` 整体训练是否是多卡。
*   **训练时长/迭代次数**：`DEmoFace` 主体模型训练总迭代次数为 300k， 批大小为 32。身份编码器训练步数为 80k。时长预测器训练步数至少为 100k。

### 5. 实验数量与充分性

实验设计严谨且全面，充分验证了方法的有效性。

*   **主实验对比**：与 6 种先进方法进行了全面的客观指标（5 项）和主观指标（3 项）对比，覆盖声学引导和视觉引导两大类别。
*   **消融实验**：设计了 5 组有说服力的消融实验，分别验证了身份条件、情感条件、课程学习、身份跨模态对齐、增强无分类器引导等各组件的关键作用。
*   **可视化实验**：通过 t-SNE 可视化了生成语音的情感特征和身份特征分布，直观地展示了模型解耦和生成多样化风格的能力；通过梅尔频谱和 F0 曲线对比，定性展示了生成语音的自然度和表现力。
*   **超参数分析**：对增强无分类器引导中的多个尺度参数进行了网格搜索，并对采样步数进行了效率与性能的权衡分析，实验充分且客观。
*   **公平性**：与仅使用视觉输入的 `Face-TTS` 进行直接对比，公平地展示了在纯视觉驱动任务上的巨大进步；同时也与使用声学信息的“上限”方法比较，以证明其优越性。

### 6. 主要结论与发现

*   **首次实现**：`DEmoFace` 是首个成功的、仅从人脸视觉线索同时定制身份和情感的语音合成框架。
*   **性能优越**：在仅使用视觉输入的情况下，`DEmoFace` 在自然度和表现力一致性上不仅显著优于同等设定下的基线模型 `Face-TTS`（例如，情感相似度提升 17.35%，说话人相似度提升 47.11%），甚至超越了部分**声学引导**的 SOTA 方法。
*   **高质量合成**：该框架能生成与参考面部在身份和情感上高度一致、且音质自然清晰的高质量语音。
*   **方法有效性**：提出的多模态 DiT、课程学习策略、增强无分类器引导被证明对于处理多条件生成、提升训练效率和生成质量至关重要。

### 7. 优点

*   **新颖的任务定义**：提出了“情感面部到语音”这一更具挑战性和应用价值的新任务，开辟了新的研究方向。
*   **创新的方法论**：首次将离散扩散模型引入此领域，并结合多模态 DiT、RVQ 课程学习和增强无分类器引导，形成了一套完整且高效的解决方案。基于能量模型的引导方法设计尤为精巧。
*   **强大的解耦能力**：成功从面部图像中解耦出身份和情感信息，并能分别控制生成的语音属性，解决了多条件生成的难题。
*   **实验全面且令人信服**：无论是客观指标、主观测试还是定性可视化结果，都强有力地支持了论文的主张。消融实验设计清晰，揭示了各模块的贡献。

### 8. 不足与局限

*   **声音真实性偏差**：论文坦诚地指出了“视觉-声音偏差”问题，即数据集中的关联可能导致模型倾向于生成“平均化”的声音，而非完全还原某个特定人物的真实嗓音。
*   **数据集规模与发音**：当前数据集（31.33小时）规模有限，可能影响了模型的发音准确性和泛化能力。模型在更大规模数据上的表现有待验证。
*   **视觉信号依赖**：模型性能严重依赖面部识别和表情识别模型的准确率，这些前置模型的误差会直接传导至语音生成。
*   **伦理与隐私风险**：能够从面部图像生成逼真语音的技术具有被滥用于深度伪造的风险，论文在最后部分虽提及此影响，但技术本身带来的挑战不容忽视。

（完）
