---
title: Long-Term TalkingFace Generation via Motion-Prior Conditional Diffusion Model
title_zh: 基于运动先验条件扩散模型的长期TalkingFace生成
authors: "Fei Shen, Cong Wang, Junyao Gao, Qin Guo, Jisheng Dang, Jinhui Tang, Tat-Seng Chua"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=aINERD9MzJ"
tags: ["query:talking-head"]
score: 10.0
evidence: 生成具有一致头部运动和唇形同步的长期说话人脸视频
tldr: 现有TalkingFace生成方法在长时序上存在运动僵化、身份漂移和口型失配问题，限制了数字人的实际应用。针对这一瓶颈，本文提出了基于运动先验的条件扩散模型MCDM，首次将历史片段与当前片段的三维运动先验共同注入扩散过程，设计多尺度时序建模模块以强化跨帧一致性。在公开与自建长视频数据集上的实验表明，MCDM在生成质量、时序稳定性和身份保真度上均显著优于主流方案，实现了长达数分钟的逼真TalkingFace视频生成。该工作为高保真长时数字人播报和虚拟角色动画提供了重要技术支撑，推动了TalkingHead生成从短片段向实际应用的跨越。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1755, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 837, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1678, \"height\": 909, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1602, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 811, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 776, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 736, \"height\": 985, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1582, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ainerd9mzj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1567, \"height\": 864, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 882, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 780, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 872, \"height\": 735, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 842, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 831, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ainerd9mzj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 520, \"height\": 166, \"label\": \"Table\"}]"
motivation: 现有方法难以保证长时间TalkingFace视频的时序一致性和口型同步。
method: 提出MCDM模型，融合存档与当前片段运动先验，通过多尺度时序建模增强生成连贯性。
result: 在多个数据集上，MCDM在生成质量、身份保持和唇形同步上均超越现有方法。
conclusion: 该工作为长时数字人播报提供了高保真解决方案，推动了TalkingHead实际应用。
---

## Abstract
Recent advances in conditional diffusion models have shown promise for generating realistic TalkingFace videos, yet challenges persist in achieving consistent head movement, synchronized facial expressions, and accurate lip synchronization over extended generations. To address these, we introduce the \textbf{M}otion-priors \textbf{C}onditional \textbf{D}iffusion \textbf{M}odel (\textbf{MCDM}), which utilizes both archived and current clip motion priors to enhance motion prediction and ensure temporal consistency. The model consists of three key elements: (1) an archived-clip motion-prior that incorporates historical frames and a reference frame to preserve identity and context; (2) a present-clip motion-prior diffusion model that captures multimodal causality for accurate predictions of head movements, lip sync, and expressions; and (3) a memory-efficient temporal attention mechanism that mitigates error accumulation by dynamically storing and updating motion features. We also introduce the {TalkingFace-Wild} dataset, a multilingual collection of over 200 hours of footage across 10 languages. Experimental results demonstrate the effectiveness of MCDM in maintaining identity and motion continuity for long-term TalkingFace generation.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以Markdown形式，对这篇论文进行结构化、深入、客观的总结。

### **论文总结：基于运动先验条件扩散模型的长期TalkingFace生成**

#### **1. 论文的核心问题与整体含义**

*   **核心问题**：尽管条件扩散模型在生成逼真的TalkingFace视频方面取得了进展，但在**长期生成**任务中仍面临巨大挑战。具体表现为：
    *   **头部运动不一致**：长时间序列中头部姿态变化不自然或僵化。
    *   **唇形同步不精确**：随着时间推移，语音与口型的对齐逐渐失准。
    *   **表情不协调**：表情动态僵硬，缺乏多样性和自然过渡。
    *   **身份一致性退化（Identity Drift）**：在长视频中，人物的面部特征逐渐变化，导致身份丢失。
*   **整体含义**：本文旨在解决TalkingFace生成从“可播放的片段”向“高质量长视频”跨越的关键瓶颈，这对于虚拟主播、数字人、电影制作等实际应用至关重要。

#### **2. 论文提出的方法论：MCDM模型**

论文的核心是**运动先验条件扩散模型（Motion-priors Conditional Diffusion Model, MCDM）**，它通过结合历史与当前的“运动先验”来增强运动预测和时序一致性。其关键思想包括：

*   **核心思想**：不直接将音频映射到视频帧，而是**先预测面部运动状态（头部姿态、表情、唇形）**，然后用这些运动状态作为“先验”信息去指导视频生成，从而将“身份”和“运动”解耦。
*   **关键技术细节与三大模块**：
    1.  **存档片段运动先验模块 （Archived-Clip Motion-Prior Module）**
        *   **目的**：从更长的历史帧（而非仅2-4帧）中引入身份和上下文信息。
        *   **流程**：
            1.  使用冻结的VAE编码器和可学习的Patchify层，将**参考帧**和**长历史帧序列（存档片段）** 的特征转换为令牌（Tokens）。
            2.  提出**帧对齐注意力（Frame-Aligned Attention）** 机制：对每一帧历史帧，其键（Key）来自参考帧令牌（保持身份不变），其值（Value）来自该具体历史帧的令牌（捕捉动态变化）。通过这种方式，将静态身份特征与动态时间信息高效融合。

    2.  **当前片段运动先验扩散模型 （Present-Clip Motion-Prior Diffusion Model）**
        *   **目的**：解耦并预测当前片段的运动状态（头、唇、表情），确保运动预测的准确性。
        *   **流程**：
            1.  **多模态特征提取**：使用Wav2Vec模型（音频编码器）、CLIP（图像编码器）、Landmark Guider（头部编码器）以及自定义的唇部和表情编码器来提取多模态特征。
            2.  **特征融合与预测**：通过FiLM层自适应学习多模态相关性，并将融合后的令牌与带噪声的头、唇、表情运动令牌一起输入到一个由**多模态因果Transformer块**和**时序交互Transformer块**组成的L层结构中。
            3.  **训练监督**：该扩散模型的训练目标是预测添加到运动令牌上的噪声，损失函数为标准MSE损失（公式3）。这使得模型能有效学习从音视频条件到面部动作的映射。

    3.  **记忆高效时序注意力机制 （Memory-Efficient Temporal Attention）**
        *   **目的**：在超长序列生成中，动态地存储、更新和融合历史运动特征，以减轻误差累积。
        *   **流程**：
            1.  **记忆更新机制**：使用公式 `M_f = α * M_{f-1} + (1-α) * F^{ref}_{ac}` 动态更新运动记忆 `M`，平衡过去与当前帧的影响（默认 `α=0.1`）。
            2.  **高效时序建模**：将当前运动先验特征 `F^{ref}_{pc}`与更新后的记忆 `M_f`拼接，然后通过基于**快速注意力（Fast Attention）** 的时序层来捕捉长程依赖。

*   **训练流程**：采用三阶段训练策略：
    *   **第一阶段**：训练存档片段运动先验模块，学习稳定的身份和上下文表征。
    *   **第二阶段**：训练当前片段运动先验扩散模型，学习预测精确的运动状态。
    *   **第三阶段**：联合训练整个模型，此时仅微调当前片段参考注意力和记忆高效时序注意力模块。

#### **3. 实验设计**

*   **数据集**：
    *   **HDTF** & **CelebV-HQ**：两个主流的TalkingHead基准数据集，用于对比和评估。
    *   **TalkingFace-Wild（自建数据集）**：一个高质量、多语种（10种语言，超200小时）的新数据集，用于测试模型在复杂野外场景下的泛化能力。
    *   **开集测试集**：由20张不同肖像和20个音频片段构成，用于评估模型的泛化性。
*   **基准对比方法**：与7种最先进的方法（SOTA）进行了全面比较，包括GAN-based方法（如Audio2Head）和Diffusion-based方法（如SadTalker, Hallo, EchoMimic, MegActor-Σ等）。
*   **评估指标**：
    *   **图像/视频质量**：FID, FVD, SSIM, E-FID。
    *   **唇形同步**：Sync-C（内容角度，越高越好），Sync-D（动态角度，越低越好）。
    *   **用户调研**：招募20名参与者，从身份一致性、运动同步和视频质量三个维度进行Rank-3偏好评价。

#### **4. 资源与算力**

*   **实验平台**：**8块 NVIDIA V100 GPU**。
*   **训练配置**：训练分为三个阶段，每个阶段**30,000次迭代**，批次大小（Batch Size）为4。视频分辨率处理为512x512。所有阶段均使用固定的学习率 $1 \times 10^{-5}$ 和AdamW优化器。

#### **5. 实验数量与充分性**

*   **实验组数**：实验设计全面且充分。
    *   **主流基准测试**：在3个数据集（HDTF, CelebV-HQ, TalkingFace-Wild）上与7个SOTA方法进行了详尽的定量和定性比较。
    *   **消融实验**：通过移除三大核心模块（存档先验、当前先验、记忆注意力）来验证各组件的有效性。
    *   **深入分析**：对存档帧数、记忆更新权重α值、先验模型设计选择（如使用Q-Former替代帧对齐注意力）等关键配置进行了分析。
    *   **鲁棒性测试**：进行了长序列生成的可视化和SSIM分析，验证模型在超长时序上的稳定性；进行了推理速度对比；测试了对不同情绪音频驱动的表达能力。
*   **公平性**：实验对比公平。在不指定使用Landmark的情况下对所有方法进行测评，确保了比较基线一致。对比方法覆盖了GAN和扩散模型两大主流路线。

#### **6. 论文的主要结论与发现**

*   MCDM在所有三个数据集上，均取得了**最优的定量结果**（FID, FVD, Sync-C/D, SSIM, E-FID），显著超越现有SOTA方法。
*   定性结果显示，MCDM生成的视频在**身份一致性、头部和唇部同步以及微表情**捕捉方面表现最佳。
*   用户调研表明，参与者在身份一致性、运动同步和视频质量三个维度上均对MCDM有最高偏好。
*   消融实验证明了**每个提出的模块（存档先验、当前先验、记忆注意力）都对最终性能有不可或缺的贡献**，尤其是在长序列生成中，存档片段运动先验对于防止身份漂移和误差累积至关重要。

#### **7. 优点**

*   **首创性**：首次将“存档片段”和“当前片段”的运动先验概念系统性地引入TalkingFace生成，有效解决了长期一致性的难题。
*   **创新的“先预测运动再生成画面”范式**：通过一个专门的扩散模型预测解耦的运动状态，将复杂的音视频映射问题分解，思路清晰，效果显著。
*   **高效的记忆注意力机制**：提出的记忆更新和快速注意力模块，巧妙地在低计算开销下实现了长程时序依赖的捕捉，避免了直接扩展上下文帧带来的内存爆炸问题。
*   **扎实的实验验证**：实验设计全面，包括多个数据集、多维度的量化指标、消融研究、用户调研和泛化性测试，结论极具说服力。
*   **有价值的开源数据贡献**：提出的TalkingFace-Wild数据集为社区提供了一个高质量、多语种的长视频评估基准。

#### **8. 不足与局限**

*   **依赖中间模态**：模型的运动预测依赖于Landmark Guider等中间模态进行监督，这些模态的准确性会影响最终生成质量。
*   **身份解耦的彻底性**：虽然通过运动先验模块进行了解耦，但长期生成中身份特征与运动特征是否会被完全解耦并在极端场景下保持稳定，仍需进一步考验。
*   **泛化到极端姿态**：实验主要在相对标准的TalkingHead数据集上进行，对于大角度、极端遮挡或非常规光照下的身份保持和运动生成能力未作充分探讨。
*   **多模态融合上限**：MCDM的性能可能受限于所用现成编码器（如Wav2Vec, CLIP）的特征表达能力。

（完）
