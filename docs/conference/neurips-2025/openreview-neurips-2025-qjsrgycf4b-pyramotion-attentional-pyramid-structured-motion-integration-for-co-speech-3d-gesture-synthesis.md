---
title: "PyraMotion: Attentional Pyramid-Structured Motion Integration for Co-Speech 3D Gesture Synthesis"
title_zh: PyraMotion：用于语音同步 3D 手势合成的注意力金字塔运动集成
authors: "Zhizhuo Yin, Yuk Hang Tsui, Pan Hui"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=QJSrgYcf4b"
tags: ["query:talking-head"]
score: 8.0
evidence: 音频驱动的包含面部表情的全身手势合成，用于虚拟 avatar 创建
tldr: 针对现有方法因固定帧数令牌而无法捕捉全身手势中面部、身体等部件在不同时间尺度上的运动模式的问题，提出一种注意力金字塔结构的运动集成框架 PyraMotion。该框架能够从音频中生成包含面部、身体、手部及全局运动的多尺度同步手势，并自适应地融合不同身体部位的运动模式，显著提升了虚拟 avatar 手势的自然度和表现力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjsrgycf4b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1371, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjsrgycf4b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1117, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjsrgycf4b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1388, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qjsrgycf4b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1394, \"height\": 486, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjsrgycf4b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 776, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjsrgycf4b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1160, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjsrgycf4b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjsrgycf4b/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 537, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qjsrgycf4b/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 216, \"label\": \"Table\"}]"
motivation: 现有语音手势合成固定帧数令牌，无法捕获不同身体部位和不同时间尺度的运动模式。
method: 提出基于注意力金字塔的多尺度运动集成框架，自适应融合不同身体部位的运动模式。
result: 成功生成包含面部动作的同步全身手势，提升了虚拟 avatar 的表现力。
conclusion: PyraMotion 为语音驱动的虚拟 avatar 动画提供了更自然的手势合成方案。
---

## Abstract
Generating full-body human gestures encompassing face, body, hands, and global movements from audio is crucial yet challenging for virtual avatar creation. Existing systems tokenize gestures frame-wise, predicting tokens of each frame from the input audio. However, expressive human gestures consist of varied patterns with different frame lengths, and different body parts exhibit motion patterns of varying durations. Existing systems fail to capture motion patterns across body parts and temporal scales due to the fixed frame-count setting of their gesture tokens. Inspired by the success of the feature pyramid technique in the multi-scale visual information extraction, we propose a novel framework named PyraMotion and an adaptive multi-scale feature capturing model called Attentive Pyramidal VQ-VAE (APVQ-VAE). Objective and subjective experiments demonstrate that the PyraMotion outperforms state-of-the-art methods in terms of generating natural and expressive full-body human gestures. Extensive ablation experiments highlight that the self-adaptiveness integration through attention maps contributes to performance.

---

## 论文详细总结（自动生成）

好的，我将根据您提供的论文内容，为您生成一份详细的结构化中文总结。

### 论文核心问题与整体含义
本研究聚焦于**音频驱动的全身3D手势合成**这一挑战性问题，旨在从语音和文本中生成包含面部表情、身体姿态、手部动作及全局移动的虚拟人动画。其核心动机在于指出现有方法的根本缺陷：当前主流方案（如基于VQ-VAE的模型）通常将手势切分为固定帧数的静态姿态令牌进行预测，这忽略了自然手势中**运动模式在时间尺度上的多变性**。例如，面部微表情的持续时间与身体大幅摆动的持续时间截然不同，且不同身体部位（如手指与下肢）对运动时间粒度的需求也各异。

因此，本文的核心思想是：**通过金字塔结构，从粗细不同的时间粒度上捕捉并融合手势中的多尺度运动模式**，从而生成更自然、更具表现力的全身手势。这为解决虚拟化身动作僵硬、无法表达丰富语义信息的问题提供了新思路。

### 方法论
论文提出的 **PyraMotion** 框架包含两个核心阶段，并设计了 **注意力金字塔VQ-VAE（APVQ-VAE）** 这一关键组件。

*   **整体工作流**：
    1.  **第一阶段**：训练 **APVQ-VAE**，将连续的手势序列编码为不同时间尺度的离散令牌，并学习从这些令牌中忠实地重建原始动作。
    2.  **第二阶段**：训练一个**金字塔令牌预测器**，根据输入的音频和文本特征，预测出多尺度的手势令牌序列。之后，利用第一阶段训练好的APVQ-VAE解码器，将这些令牌序列重建为最终的全身动画。

*   **核心组件：APVQ-VAE**
    *   **多尺度编码**：与普通VQ-VAE使用单尺度编码器不同，APVQ-VAE使用 *n* 个不同感受野的时序卷积网络（TCN）将手势序列编码成 *n* 个长度依次减半的嵌入序列 `F = [f1, ..., fn]`。这对应了从细粒度到粗粒度的运动模式。
    *   **共享码本量化**：所有尺度的嵌入共享一个离散码本进行量化，确保了不同尺度下运动语义的一致性，得到多尺度令牌序列 `Q`。
    *   **金字塔解码与注意力融合**：解码器使用对应感受野的转置TCN将每个尺度的量化嵌入解码回原始动作序列。为了融合这些重建结果，论文提出了一个**注意力融合机制**：先计算所有尺度重建的平均值，再将平均后的动作与各尺度重建动作堆叠，通过注意力机制计算出残差分量。最终的重建动作是“**平均值 + 注意力残差**”。这种设计允许模型自适应地整合粗细粒度的信息。

*   **核心组件：金字塔令牌预测器**
    *   **多模态特征融合**：利用注意力机制动态融合音频的韵律特征和文本的语义内容特征。
    *   **身体部位分离与多尺度潜在表示生成**：考虑到面部表情与肢体动作的弱相关性，对两者分别建模。对于肢体部分，进一步解耦为上肢、下肢和手部。为捕捉多尺度信息，对每部分的隐藏状态进行两种金字塔操作，生成多尺度的潜在表示：
        1.  **均值金字塔表示**（`H_mean`）：通过平均连续的 `2^i` 帧表示来获得。
        2.  **TCN金字塔表示**（`H_tcn`）：通过一个与APVQ-VAE编码器中同构的TPN网络来提取。
    *   **跨尺度与跨部位信息交互**：通过时序交叉注意力（TCAT）和全身体特征融合，学习不同尺度间的关联以及不同身体部位间的协同关系。
    *   **由粗到细的令牌预测**：最终，模型从最粗略的尺度开始，迭代地预测下一尺度的令牌分布，实现了从粗到细的令牌生成过程。

### 实验设计
*   **数据集**：在公开的高质量多模态数据集 **BEAT2** 上进行了评估，该数据集包含30位说话人在8种情绪下共计76小时的动作捕捉数据。实验遵循现有工作设置，使用其标准版本中的 Speaker2 数据，并按85%/7.5%/7.5%划分训练/验证/测试集。

*   **评估基准与对比方法**：
    *   **评估指标**：
        *   身体动作质量：弗雷歇手势距离（FGD）、多样性（Diversity）、节拍对齐度（Beat Align）。
        *   面部表情质量：均方误差（MSE）、L1顶点差（LVD）。
    *   **对比方法**：与多达13种经典和当前最优的（SOTA）方法进行了比较，包括 S2G, Trimodal, HA2G, DisCo, CaMN, Diffusestylegesture, HoloGest, RAG-Gesture, AMUSE, MambaTalk, Habibie et al., TalkSHOW, DiffSHEG, EMAGE, ProbTalk 和 SynTalker 等。

### 资源与算力
*   **硬件资源**：在配有一张 **32GB 显存的GPU** 和 256GB 内存的 Ubuntu 服务器上进行训练。
*   **软件环境**：Python 3.9，PyTorch 2.4.1。
*   **训练时长**：APVQ-VAE 模型的所有身体部位训练完毕约需 **24小时**，整个 PyraMotion 框架达到最佳性能约需 **48小时**。

### 实验数量与充分性
本研究的实验设计**非常全面且充分**，通过多组具备统计学意义的实验验证了方法的有效性、客观性和公平性。
*   **整体性能对比**：在统一的BEAT2数据集上，与十多种SOTA方法进行了全面比较，包括定量的客观指标和定性的用户感知研究。
*   **消融实验**：设计了**5个变体**，系统地验证了模型中每个关键组件（如身体部位分离、文本输入、TCN编码器、全身体潜在表示融合、TransTCN解码器）的贡献。
*   **重构能力对比**：单独比较了 APVQ-VAE 与普通 VQ-VAE 及平均池化变体 MPVQ-VAE 的运动重建精度，证明了多尺度令牌和注意力融合的优越性。
*   **关键参数分析**：验证了金字塔层数（1至5层）对性能的影响，并找到了性能与计算效率的最佳平衡点。
*   **可视化分析**：通过可视化注意力热力图（图3），为“不同身体部位对不同时间尺度有不同偏好”的论点提供了直观且强有力的证据。
*   **结果可信度**：所有定量实验结果均报告了**5次独立运行得到的均值和标准差**，并对主要结果给出了**p值**进行显著性检验，确保了结果的客观性和可复现性。

### 主要结论与发现
*   **性能优越性**：PyraMotion 在生成全身手势质量（FGD、LVD）和面部表情精度（MSE）上显著优于现有最先进方法，能生成与真实动作更接近、更自然的动画。
*   **多尺度建模的必要性**：APVQ-VAE 在动作重构任务上远超单尺度 VQ-VAE，证实了从多时间尺度表示手势运动模式的巨大优势。
*   **自适应融合机制**：注意力融合操作（而非简单平均）对模型性能至关重要。注意力热力图的可视化清晰地揭示了一个关键发现：**面部倾向于细粒度特征，而下半身更依赖粗粒度特征，上肢和手部则均衡地融合了各尺度信息**。这完美地解释了模型自适应性的来源。

### 优点
*   **问题洞察深刻**：准确指出了现有方法“固定帧数令牌”假设的根本性缺陷，创新性高。
*   **方法设计精巧**：提出的APVQ-VAE和金字塔令牌预测器结构完整、逻辑缜密，从编码、量化到解码和预测，形成了闭环的解决方案。
*   **实验论证体系强大**：从宏观性能对比、微观模块消融、重构能力验证、参数分析再到可视化解释，形成了一条完整且无可辩驳的证据链，极具说服力。
*   **可解释性好**：通过注意力热力图，对模型为何有效提供了直观的物理解释，提升了模型的可解释性。

### 不足与局限
*   **超参数适应性**：论文明确指出，金字塔的**层数是一个固定的超参数**，无法根据不同的数据集或应用场景进行自适应调整，这可能限制其泛化能力。
*   **部位间耦合度问题**：研究发现，完全独立建模会不自然，而过度强制关联不同身体部位的动作分布会导致性能下降，如何找到一个自适应的耦合比例是未来的挑战。
*   **计算开销**：尽管理论复杂度是单尺度模型的常数倍，但实际推理时间（41秒）约为单尺度模型（22秒）的近两倍，在实时性要求高的场景中是一个局限。
*   **实验公平性**：在对比实验中，部分方法的指标（如CaMN的FGD）是基于其论文结果或使用绝对真值面部表情辅助计算得到的，这可能使直接比较存在细微偏差，尽管这已是该领域常见的处理方式。
*   **未探索的模态**：当前模型主要依赖音频和文本，未探索如何加入如情感标签、个人风格等多模态控制信号，生成的可控性有提升空间。

（完）
