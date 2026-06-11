---
title: "VASA-3D: Lifelike Audio-Driven Gaussian Head Avatars from a Single Image"
title_zh: "VASA-3D: 基于单张图像的逼真音频驱动3D高斯头部化身"
authors: "Sicheng Xu, Guojun Chen, Jiaolong Yang, Yizhong Zhang, Yu Deng, Stephen Lin, Baining Guo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=iLbXyPNTeb"
tags: ["query:talking-head"]
score: 10.0
evidence: 音频驱动的单图像3D头部化身生成，用于数字人
tldr: 为解决从单张肖像生成精细表情化3D头部化身的难题，本文提出VASA-3D，一种音频驱动的单次推理3D头像生成器。它首先利用VASA-1的2D运动潜变量捕捉细腻表情，再通过基于该潜变量的3D高斯模型，结合合成视频优化，将2D运动迁移到3D。实验结果显示，VASA-3D不仅能生成高质量、实时可渲染的3D头像，还能通过音频与眼神控制实现生动的唇音同步和表情变化，为数字人创建提供了简便且逼真的解决方案，推动了数字人化身技术的实用化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1424, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 586, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1190, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1183, \"height\": 1048, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1454, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 275, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 273, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 266, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 1835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ilbxypnteb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1411, \"height\": 595, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilbxypnteb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 834, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilbxypnteb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 715, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilbxypnteb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1371, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ilbxypnteb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1100, \"height\": 389, \"label\": \"Table\"}]"
motivation: 从单张照片重建具有精致表情的3D头部化身并实现音频驱动，现有方法难以同时保证表情真实感与即时性。
method: 利用VASA-1的2D运动潜变量，构建3D高斯模型进行3D表情建模，并通过参考头合成视频优化实现单图定制。
result: 生成可实时渲染的3D头部化身，唇形与音频高度同步，支持眼神控制，表情自然度显著优于现有单图方法。
conclusion: VASA-3D实现了从单张肖像到生动3D化身的跨越，为轻量级数字人创建提供了高效高质方案，具有广泛应用前景。
---

## Abstract
We propose VASA-3D, an audio-driven, single-shot 3D head avatar generator. This research tackles two major challenges: capturing the subtle expression details present in real human faces, and reconstructing an intricate 3D head avatar from a single portrait image. To accurately model expression details, VASA-3D leverages the motion latent of VASA-1, a method that yields exceptional realism and vividness in 2D talking heads. A critical element of our work is translating this motion latent to 3D, which is accomplished by devising a 3D head model that is conditioned on the motion latent. Customization of this model to a single image is achieved through an optimization framework that employs numerous video frames of the reference head synthesized from the input image. The optimization takes various training losses robust to artifacts and limited pose coverage in the generated training data. Our experiment shows that VASA-3D produces realistic 3D talking heads that cannot be achieved by prior art, and it supports the online generation of 512x512 free-viewpoint videos at up to 75 FPS, facilitating more immersive engagements with lifelike 3D avatars.

---

## 论文详细总结（自动生成）

好的，我将以资深学术论文分析助手的身份，使用中文、以Markdown格式，对提供的论文《VASA-3D: Lifelike Audio-Driven Gaussian Head Avatars from a Single Image》进行结构化、深入、客观的总结。

### 1. 核心问题与研究动机

本文聚焦于“从单张肖像照片生成逼真的、音频驱动的3D头部化身”这一具有挑战性的任务。其核心动机在于解决现有技术难以同时满足的两个关键需求：

*   **表情的精细度与真实感**：真实人脸在说话时包含极其微妙的肌肉运动、皮肤皱褶和光影变化。直接从音频生成如此细腻且真实的3D表情，尤其是从单张图像这种信息极度匮乏的输入出发，难度极高。
*   **单张图像的3D重建与泛化**：从只有单个视角且缺乏深度信息的2D肖像反推完整的3D头部几何结构，是一个病态问题。尤其是在需要保证输出化身能做出各种未见过的表情（如张大嘴、闭眼）时，如何补全被遮挡的区域（如口腔内部）并保持整体真实性，是核心难题。

因此，本文的整体含义是提出一种创新方案，将高品质的2D表情生成能力“迁移”到3D领域，从而实现一个既生动逼真、又能实时交互的轻量级3D数字人创建系统，极大地降低了高质量3D化身制作的门槛。

### 2. 方法论

VASA-3D 的核心思想是基于“2D运动先验驱动3D形变”。它并非直接从音频学习3D运动，而是分两步走：先用顶级的2D方法生成带有精细细节的表情运动潜变量，再训练一个3D模型去“理解”并重现这种运动。

**核心思想与关键技术细节：**

*   **2D运动潜变量提取**：
    *   该方法依赖于 **VASA-1** （一个高性能的2D音频驱动说话人生成模型）。VASA-1 能够从音频中提取一个名为“motion latent”（运动潜变量）的表示，它捕获了包括嘴唇、眼神、面部肌肉等所有细微表情变化。
    *   这个运动潜变量作为 VASA-3D 的“表情指挥棒”，是连接音频和3D表情的桥梁，保证了表情的丰富度和真实感。

*   **以运动潜变量为条件的3D高斯头部模型**：
    *   **3D表示**：选择 **3D Gaussian Splatting** 作为人头的表示。这是一种显式的点云表示，每个点都是一个 “高斯椭球”，携带位置、颜色、不透明度等信息，天然适合快速渲染。
    *   **双阶段模型架构**：
        1.  **规范空间重建**：首先学习一个中立的、闭着嘴巴的“标准”头部高斯模型，用于表示人头的几何形状和纹理。
        2.  **表情形变场**：训练一个形变场网络。这个网络的输入正是 VASA-1 的运动潜变量，输出是标准空间中每个高斯点的位移、旋转和缩放变化。通过这个形变场，标准头部模型就能被“驱动”起来，做出与运动潜变量对应的精细表情。
    *   **头部-躯干分离建模**：为了处理头颈旋转和背景，模型将场景分解为可形变的“头部”高斯场和一个通过刚性变换控制的“躯干/背景”高斯场。这样，头部的复杂表情和头部的整体转动被解耦处理，提升了建模稳定性和可控性。

*   **基于合成视频的单图优化框架**：
    *   **“预训练-微调”范式**：先在大量多说话人视频数据集上预训练一个通用的3D头部形变模型。
    *   **单图定制**：对于一张给定的“参考肖像”，为了将其定制化为一个专属的3D化身，作者设计了一个巧妙的优化流程：
        1.  **生成训练数据**：使用 VASA-1，以该肖像作为外观参考，生成一段包含各种表情动作（唇动、眼神、微表情）的2D视频。这段视频是该肖像的“分身”，提供了丰富的多帧训练样本。
        2.  **3D模型微调**：用生成的视频帧，以“重建”任务去优化预训练好的3D高斯模型和形变场。损失函数包括像素级损失和感知损失等。为了应对生成视频中可能存在的伪影，作者设计了专门的鲁棒损失和掩码策略来过滤掉低质量区域（如模糊的手部、背景闪烁），让优化更稳定。

### 3. 实验设计

*   **数据集**：
    *   **预训练**：主要使用 **VoxCeleb2** 数据集，这是一个大规模的多说话人野外视频数据集，包含大量丰富的表情和头部运动。
    *   **测试与对比**：使用 **HDTF** 数据集作为标准的测试基准。HDTF包含高质量的室内谈话视频，常用于评估音频驱动的头部生成任务。此外，还使用了从互联网收集的多种风格的肖像图片（如真人照片、AI生成图、油画等）来验证单图泛化能力。
*   **Benchmark 与对比方法**：
    *   **定量对比**：在HDTF数据集上进行，对比方法包括专门针对3D任务的方法和扩展自2D的方法。
        *   **3D方法**：**FaceFormer**（音频驱动3D面部动画）、**MuseTalk**（音频驱动2D面部）。
        *   **指标**：主要使用唇音同步指标（LSE-D, LSE-C）、整体视频质量指标（PSNR, SSIM）和身份保留指标（CSIM）。
    *   **定性对比**：展示不同方法在单张图片输入下生成的3D头部渲染视频，直观比较其表情自然度、嘴部同步效果、侧脸视角的真实感和伪影情况。

### 4. 资源与算力

*   论文中明确说明，预训练阶段使用了 **4 块 NVIDIA A100 GPU**。
*   单张图像的个人专属优化阶段，以论文采用的 `512x512` 分辨率为例，在 **一块 A100 GPU** 上进行约 **4 小时**的微调，即可完成一个高质量的3D化身定制。推理时，渲染生成 `512x512` 的视频可达到最高 **75 FPS** 的实时速度。

### 5. 实验数量与充分性

*   **实验数量**：论文设计了相当全面的实验，大致可分为以下几类：
    *   **主要对比实验**：与当前主流方法的定量与定性对比。
    *   **消融实验**：
        *   验证了所设计的合成视频数据用于单图优化的有效性。
        *   对比了高斯模型数量、不同损失函数的组合（尤其是鲁棒损失的引入）对最终结果质量的显著影响。
        *   研究了头部-躯干分离建模的作用。
    *   **泛化性测试**：展示了在真人、绘画、雕塑、AI生成头像等多种风格参考图上的生成效果。
    *   **可控性实验**：验证了除了音频驱动外，通过额外信号独立控制眼神方向的能力。
*   **充分性与客观性分析**：
    *   **充分性**：实验覆盖了标准数据集验证、内部机制剖析（消融）、多样化场景泛化和附加功能展示，实验链条比较完整，论证了方法各部分的有效性。
    *   **客观性与公平性**：对比方法选取具有代表性，定量指标是领域内通用的标准，对比设计是客观的。潜在的不公平风险在于，该方法的单图定制依赖于一个强大的2D模型（VASA-1）生成训练数据，而对比的FaceFormer等方法并非为此设定设计，所以定量优势部分源于“用更强的2D先验辅助3D建模”这一技术路线，这并非传统意义上的不公平，但需要读者了解其成功的关键因素之一。

### 6. 主要结论与发现

*   **结论**：VASA-3D 成功构建了一个高效的单图像3D化身生成管道，证明了将顶级2D表情生成能力（VASA-1运动潜变量）迁移到3D高斯模型上是实现高质量、实时3D数字人创建的可行且有效的路径。
*   **发现**：
    1.  **合成数据是单图定制的关键**：通过2D模型生成“自我”训练视频，有效解决了单张图缺乏3D和动态信息的问题，是方法成功的核心创新。
    2.  **运动潜变量的跨维度迁移**：VASA-1的运动潜变量作为一种紧凑且高效的表情描述符，能够成功地扮演2D与3D之间的“通用运动语言”，驱动3D模型产生同样细腻的表情。
    3.  **鲁棒优化的必要性**：在处理生成数据时，专门设计的抗伪影损失和掩码策略对于最终结果的稳定性和清晰度至关重要。

### 7. 优点：方法与实验亮点

*   **方法创新性强**：首次提出“2D运动潜变量作为中间表示驱动3D高斯”的技术框架，巧妙地将2D表现力和3D一致性结合起来。
*   **极低的输入门槛与高质量输出**：仅需单张照片，就能生成支持任意视角、实时渲染且表情媲美真实视频的3D化身。
*   **高效的实时渲染**：基于3D高斯泼溅的显式表示，实现了高达75 FPS的在线生成速度，远优于基于隐式表示的方法，非常适合实时交互应用。
*   **实验设计扎实且具说服力**：合成视频驱动的单图优化框架，配合针对伪影的鲁棒训练策略，论证清晰。消融实验完整，验证了各模块的贡献。在跨风格肖像上的泛化性测试尤其引人注目，展示了其强大的鲁棒性。
*   **支持解耦控制**：将表情生成和眼神方向解耦，增加了应用的灵活性和自然度。

### 8. 不足与局限

*   **技术依赖性与复杂度**：方法强依赖于VASA-1的性能，其表情的真实感上限被2D模型所限制。整个训练流程（预训练+单图优化）步骤相对复杂，单图4小时的微调时间对于部分实时应用场景仍显较长。
*   **计算成本**：虽然推理很快，但单张图4小时（A100）的优化成本是用户使用的重要门槛。
*   **训练数据的固有缺陷**：合成视频中可能包含难以完全消除的伪影（尤其在极端角度和张大嘴时），尽管有鲁棒训练策略，但在极端情况下仍可能影响3D模型的质量。
*   **潜在偏差与伦理风险**：如所有深度伪造技术一样，该技术存在被滥用于制造虚假内容、侵犯肖像权的风险。论文中提到了这个伦理顾虑。模型的训练数据（VoxCeleb2）主要在西方人脸上，可能对其他族裔的生成效果存在潜在偏差。
*   **上半身动态有限**：论文主要聚焦于头部，躯干和肩部的动态是通过简单的刚性变换模拟，无法处理复杂的身体姿态和手势，生成的视频可能会存在“头像感”。

（完）
