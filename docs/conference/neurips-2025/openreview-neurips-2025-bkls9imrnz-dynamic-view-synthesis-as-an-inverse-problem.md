---
title: Dynamic View Synthesis as an Inverse Problem
title_zh: 动态视图合成作为逆问题
authors: "Hidir Yesiltepe, Pinar Yanardag"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=BKLS9IMrNZ"
tags: ["query:talking-head"]
score: 4.0
evidence: 基于视频扩散模型的无训练单目视频动态视图合成
tldr: 针对单目视频动态视图合成通常需要逐场景优化的问题，该工作提出一种无训练方法，通过重新设计预训练视频扩散模型的噪声初始化，引入K阶递归噪声表示，并采用随机反演处理遮挡区域，实现高保真度的动态新视图合成。该方法在合成与真实场景上验证了渲染质量的提升，具有通用性，有潜力应用于说话头视频的多视角生成，但未专门针对人脸动画设计。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 551, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 586, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1292, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1313, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-bkls9imrnz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1299, \"height\": 1775, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 737, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 930, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 652, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1007, \"height\": 1108, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-bkls9imrnz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 620, \"height\": 408, \"label\": \"Table\"}]"
motivation: 现有动态视图合成依赖测试时优化或辅助模块，难以高效泛化到新视频。
method: 将动态视图合成建模为逆问题，在预训练视频扩散模型中重新设计噪声初始化和随机反演，无需训练。
result: 在多种真实视频上实现高保真新视图渲染，克服遮挡与抖动，超越以往方法。
conclusion: 提供了通用无训练动态视图合成框架，有望辅助说话头等多视角视频生成，但未做人脸专项验证。
---

## Abstract
In this work, we address dynamic view synthesis from monocular videos as an inverse problem in a training-free setting. By redesigning the noise initialization phase of a pre-trained video diffusion model, we enable high-fidelity dynamic view synthesis without any weight updates or auxiliary modules. We begin by identifying a fundamental obstacle to deterministic inversion arising from zero-terminal signal-to-noise ratio (SNR) schedules and resolve it by introducing a novel noise representation, termed K-order Recursive Noise Representation. We derive a closed form expression for this representation, enabling precise and efficient alignment between the VAE-encoded and the DDIM inverted latents. To synthesize newly visible regions resulting from camera motion, we introduce Stochastic Latent Modulation, which performs visibility aware sampling over the latent space to complete occluded regions. Comprehensive experiments demonstrate that dynamic view synthesis can be effectively performed through structured latent manipulation in the noise initialization phase.

---

## 论文详细总结（自动生成）

好的，基于提供的论文内容，以下是以 Markdown 形式组织的中文详细总结。

### 论文核心问题与整体含义

本文的核心研究问题是如何从一个单目视频（单摄像头拍摄的视频）中，高效地生成任意新视角下的动态场景，即**动态视图合成**。这项任务对于电影制作、机器人感知等领域具有重要意义。
*   **研究动机**：传统方法（如动态NeRF、3D/4D高斯泼溅）通常需要精确的相机标定、多视角监督或针对每个场景进行耗时的优化。近期基于视频扩散模型的方法虽有所突破，但普遍依赖于更新模型参数、添加辅助模块、在大量合成数据上进行预训练或对单个视频进行微调，这些方式可能导致泛化能力不足、计算成本高或域差距问题。
*   **整体含义与目标**：本文的核心思想是将动态视图合成视为一个**无训练的反问题**。其目标是完全通过巧妙操控一个预训练视频扩散模型在生成初期的**初始噪声**，在不进行任何模型权重更新或添加任何辅助模块的情况下，实现高保真度的动态新视图合成。

### 方法论

论文的核心方法论包含两大创新组件，均围绕扩散模型生成过程初期的噪声初始化和潜在空间操作展开：

1.  **核心挑战：零终端信噪比坍塌问题（Zero-Terminal SNR Collapse Problem）**
    *   **问题识别**：作者指出，预训练视频模型如 CogVideoX 为提升生成质量采用了“零终端信噪比”的噪声调度（即在扩散过程的最后一步，信号成分降为零）。这导致前向扩散映射失去了单射性，使得标准的确定性反演（DDIM Inversion）无法唯一地恢复出原始视频内容，从而破坏了重建的保真度。

2.  **解决方案一：K阶递归噪声表示（K-order Recursive Noise Representation， K-RNR）**
    *   **核心思想**：为解决零终端信噪比带来的问题，K-RNR 不对模型做任何改动，而是设计一种新的初始噪声构造方式。它以VAE编码后的原始视频潜在向量 \( x_0 \) 为“枢轴”，递归地将其与带有正信噪比的地地反演噪声 \( \epsilon_{inv} \) 进行混合。
    *   **技术细节**：给定一个信噪比非零的时间步 \( t \)（\( \bar{\alpha}_t > 0 \)），递归定义为：
        \( \epsilon^{(1)} = \sqrt{\bar{\alpha}_t} x_0 + \sqrt{1 - \bar{\alpha}_t} \epsilon_{inv} \)
        \( \epsilon^{(k)} = \sqrt{\bar{\alpha}_t} x_0 + \sqrt{1 - \bar{\alpha}_t} \epsilon^{(k-1)} \)
        作者推导出了该递归过程的封闭形式解，使得 \( \epsilon^{(k)} \) 能够随着阶数 \( k \) 的增加，越来越对齐 \( x_0 \) 的结构，从而实现高保真重建。
    *   **自适应变体**：原始 K-RNR 会导致噪声的均值和方差随 \( k \) 增长而爆炸。为此，引入**自适应K-RNR**，通过 AdaIN操作，将最终噪声 \( \epsilon^{(k)} \) 的统计特性与一个中间递归步骤的噪声 \( \epsilon^{(\delta)} \) 对齐，从而稳定生成过程，消除视觉伪影。

3.  **解决方案二：随机潜在调制（Stochastic Latent Modulation， SLM）**
    *   **核心思想**：当相机视角移动时，场景中会出现原本被遮挡、现在新暴露出来的区域。这些区域在输入的渲染视频和其反演噪声中都是缺失的（黑色区域）。SLM 旨在直接于潜在空间中，以一种符合物理场景结构的方式推断并补全这些区域。
    *   **技术细节**：SLM 构建一个基于深度估计的背景可见性掩码，然后定义一个随机置换算子。该算子会在潜在向量和噪声向量的通道中，将**被遮挡区域**的数值，随机替换为从**可见且属于背景的区域**采样来的数值。这种操作在潜在空间为缺失区域注入了上下文相关的信号，使得扩散模型能够在生成过程中自然、连贯地补全新视图的未知部分。

4.  **相机信息条件注入**：使用单目深度估计模型获取输入视频的深度图，结合相机内参重建每一帧的3D动态点云。然后，根据目标相机轨迹对点云进行变换并渲染出新视角图像，以此作为后续扩散模型的输入条件。

### 实验设计

*   **评估数据集与策略**：
    *   构建了一个包含 **1100 个视频** 的测试集以评估在不同内容和运动复杂度下的性能：
        *   **1000 个视频** 来自 **OpenVid-1M** 数据集，包含丰富的语义场景。
        *   **50 个视频** 来自 **DAVIS** 数据集，以高风险运动场景检验时序稳定性。
        *   **50 个视频** 为 **AI 生成** 的视频，以评估对合成输入的泛化能力。
    *   对每个视频，使用 **10 种预定义的相机轨迹**（包括平移、摇摄、倾斜、弧形等）进行新视角渲染与合成，作为评估的基准。

*   **对比方法**：
    *   与 **5 种** 主流的基于扩散模型的动态视图合成基线方法进行了比较：
        1.  **GCD (Generative Camera Dolly)**
        2.  **TrajectoryAttention**
        3.  **ReCamMaster**
        4.  **TrajectoryCrafter**
        5.  **Diffusion-as-Shader (DaS)**

*   **评估指标**：
    *   **相机姿态准确度**：旋转误差（RotErr）和平移误差（TransErr）。
    *   **源-目标视图同步性**：匹配像素数、FVD-V、CLIP-V。
    *   **视觉质量**：FID、FVD、CLIP-T、CLIP-F。
    *   **全参考重建质量**：PSNR、SSIM、LPIPS（仅在可与真值比较时使用）。

### 资源与算力

*   论文明确指出，所有实验均在 **单张 NVIDIA L40 GPU** 上进行。
*   该方法是**无训练**的，其核心计算成本仅在于推理阶段（包括DDIM反演、K-RNR计算和扩散模型的前向生成过程）。

### 实验数量与充分性

*   **实验组数**：实验规模相当全面。论文不仅提供了与5个基线方法在**三个不同场景域（自然、高风险运动、AI生成）**上的对比，还进行了丰富的消融实验来验证每个核心组件的有效性。
    *   **主实验**：在两个主表中全面对比了所有方法在1100个视频上的视觉质量、相机精度、同步性和重建指标。
    *   **组件消融研究**：
        *   对 **K-RNR、自适应缩放（AS）和SLM** 的效果进行逐步叠加的消融研究。
        *   对**不同的初始噪声策略**（随机噪声、地地反演、KV缓存等）进行消融研究。
        *   对 **K-RNR的递归深度 \( k \)** 的影响进行详细分析。
        *   对**自适应缩放参考深度 \( \delta \)** 的影响进行详细分析。
*   **充分性与客观公平性**：实验设计较为充分和公平。对比的基线方法包含了同期最具代表性的工作，且覆盖了不同的骨干模型。消融研究系统地论证了每个提出模块的贡献。量化指标涵盖了生成质量、几何精度、时序一致性和像素级保真度，评估维度全面。

### 主要结论与发现

*   **动态视图合成无需权重更新**：论文成功证明了，仅通过**在预训练扩散模型的噪声初始化和潜在空间进行结构化操纵**，即可实现高质量的单目动态视图合成，完全无需微调或架构修改。
*   **K-RNR 解决了反演难题**：提出的 K-RNR 有效地解决了零终端信噪比调度带来的确定性反演障碍，使得在保持生成多样性的前提下，仍能实现高保真的身份和场景重建。
*   **SLM 完成了场景补全**：SLM 机制能够在潜在空间合理地推断并填充因相机移动而新出现的遮挡区域，生成符合物理结构的连贯内容。
*   **性能先进**：量化结果表明，该方法在视觉保真度、相机控制精度、视角同步等方面的表现**全面地超越了**现有所有基线方法。

### 优点

*   **无需训练**：该方法最显著的优点是它完全“开箱即用”，不需要任何额外的训练数据、场景特定的微调或模型权重的更新，通用性强，易于部署。
*   **理论创新**：对零终端信噪比坍塌问题的形式化定义和 K-RNR 的提出，为理解和解决扩散模型的反演问题提供了新的理论视角和实用工具。
*   **简洁高效**：方法仅涉及对输入噪声和潜在向量的前馈式数学运算，无需修改复杂的模型注意力机制或架构，且能在单张商用GPU上完成整个流程。
*   **性能优越**：在全面的量化评估中，该方法在多个关键指标上均达到了先进水平，验证了其设计的有效性。

### 不足与局限

*   **对基础模型偏见的继承**：作为一个无训练方法，其性能高度依赖于底层预训练视频扩散模型的固有能力与偏见。模型难以处理其训练数据中不常见的物体、复杂动作或大量遮挡的场景。
*   **SLM 的稳定性问题**：当相机移动导致大面积新区域暴露时，随机潜在调制可能会产生不稳定或不连贯的补全结果，因为其本质是一种随机的、启发式的补全策略，而非基于真实3D几何推理的预测。
*   **依赖外部模块**：方法依赖于单目深度估计和相机姿态估计等外部工具，这些工具的精度直接影响最终的渲染和合成质量。
*   **潜在的社会风险**：该技术能够生成逼真的合成视频，存在被滥用于制造深度伪造（deepfakes）等虚假内容的潜在风险。论文提及了该风险，但未提出具体的技术缓解措施。

（完）
