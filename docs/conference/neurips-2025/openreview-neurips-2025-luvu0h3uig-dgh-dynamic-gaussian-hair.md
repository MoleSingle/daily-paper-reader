---
title: "DGH: Dynamic Gaussian Hair"
title_zh: 动态高斯头发
authors: "Junying Wang, Yuanlu Xu, Edith Tretschk, Ziyan Wang, Anastasia Ianina, Aljaz Bozic, Ulrich Neumann, Tony Tung"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=LUvu0H3uIG"
tags: ["query:talking-head"]
score: 8.0
evidence: 数字人建模的动态头发方法
tldr: 该论文针对数字人建模中动态头发的复杂运动、遮挡和光散射难题，提出动态高斯头发框架DGH。通过粗到细模型学习时序一致的头发运动动态，并利用股引导优化模块学习动态3D高斯外观表示，支持可微分渲染。实验表明该方法能高效生成逼真动态头发，推动数字人真实感渲染。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 645, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 711, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 708, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 704, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 719, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1443, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1452, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 920, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1448, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1439, \"height\": 1396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1446, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1455, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1447, \"height\": 908, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1398, \"height\": 796, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1269, \"height\": 2172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1305, \"height\": 2269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1431, \"height\": 1655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1452, \"height\": 1740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1451, \"height\": 1726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-luvu0h3uig/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1459, \"height\": 1791, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-luvu0h3uig/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-luvu0h3uig/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-luvu0h3uig/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-luvu0h3uig/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-luvu0h3uig/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1040, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-luvu0h3uig/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 187, \"label\": \"Table\"}]"
motivation: 解决数字人动态头发建模中运动复杂、计算开销大的难题。
method: 提出粗到细时序运动模型和股引导3D高斯优化模块。
result: 高效生成逼真动态头发，支持可微分渲染。
conclusion: 为数字人动态头发提供高效逼真的解决方案，提升实时渲染能力。
---

## Abstract
The creation of photorealistic dynamic hair remains a major challenge in digital human modeling because of the complex motions, occlusions, and light scattering. Existing methods often resort to static capture and physics-based models that do not scale as they require manual parameter fine-tuning to handle the diversity of hairstyles and motions, and heavy computation to obtain high-quality appearance. In this paper, we present Dynamic Gaussian Hair (DGH), a novel framework that efficiently learns hair dynamics and appearance. We propose: (1) a coarse-to-fine model that learns temporally coherent hair motion dynamics across diverse hairstyles; (2) a strand-guided optimization module that learns a dynamic 3D Gaussian representation for hair appearance with support for differentiable rendering, enabling gradient-based learning of view-consistent appearance under motion. Unlike prior simulation-based pipelines, our approach is fully data-driven, scales with training data, and generalizes across various hairstyles and head motion sequences. Additionally, DGH can be seamlessly integrated into a 3D Gaussian avatar framework, enabling realistic, animatable hair for high-fidelity avatar representation. DGH achieves promising geometry and appearance results, providing a scalable, data-driven alternative to physics-based simulation and rendering.

---

## 论文详细总结（自动生成）

好的，以下是对论文《DGH: Dynamic Gaussian Hair》的结构化深度中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：在数字人建模中，创建逼真且动态的头发是一个核心挑战。其复杂性源于头发的精细几何、复杂运动（如惯性、摆动、阻尼）、自遮挡以及复杂的光散射效果。
*   **现有方法的局限**：
    *   **物理模拟方法**：能生成高质量动态，但计算开销巨大，需要针对每种发型进行繁琐的手动参数调整（如刚度、密度、阻尼），不具备数据驱动的可扩展性，难以泛化。
    *   **神经渲染方法（NeRF/3DGS）**：在静态或准静态（仅刚性变换）头发渲染上效果良好，但缺乏对非刚性运动及次级动态效果（如长发飘动）的建模能力。
*   **论文核心目标**：提出一个全新的、完全数据驱动的框架，名为**动态高斯头发（DGH）**，能够从给定的静态发型和头部运动序列中，高效地学习头发的动态变形与外观，从而替代计算昂贵且不可微的物理模拟流程。

### 2. 论文提出的方法论

DGH框架分为两个主要阶段，其核心思想是将复杂的动态头发问题分解为动态建模和外观优化两部分，并用一个“由粗到细”的策略来处理运动。

**阶段一：由粗到细的动态头发建模（Coarse-to-Fine Dynamic Hair Modeling）**
*   **输入**：静态标准发型的点云、头部姿态序列、上身网格。
*   **粗阶段（时间无关的形变预测）**：
    *   将静态头发根据头部姿态进行刚性变换，与上身姿态网格一起，分别体素化为符号距离函数（SDF）体积，并通过3D CNN编码为特征网格。
    *   对刚性变换后的头发点云上的每个点，从特征网格采样插值特征，融合位置编码和头部姿态，通过一个MLP（`M`）预测该点的位移`Δpi`，从而得到初步变形的头发点云。
    *   **关键公式**：总损失 `L_total = λ_p * L_point + λ_SDF * L_SDF`，其中`L_point`是预测位移与真值的MSE损失，`L_SDF`惩罚头发穿入身体网格的碰撞。
*   **细阶段（时间相关的动态精炼）**：
    *   提取前两帧（`t-1`, `t-2`）的变形头发SDF体积，通过3D CNN编码，并使用**交叉注意力**模块融合，以捕捉时序动态信息。
    *   对上一帧（`t-1`）头发点云上的每个点，从融合特征体积中采样特征，结合当前头部姿态和前序光流向量，通过一个精炼网络`D*`预测其当前帧的**3D光流向量**，从而对头发运动进行精炼。
    *   **关键公式**：损失函数 `L = L_flow = MSE(F^t_flow, F^t_GT)`，直接监督预测的帧间光流。

**阶段二：动态头发外观优化（Dynamic Hair Appearance Optimization）**
*   **表示**：将每根发丝表示为一系列相连的**圆柱形3D高斯基元**，其数量在帧间固定。
*   **外观模型**：一个轻量级MLP（`D`），它不直接传播静态帧的颜色，而是根据每帧的头发动态来调整高斯参数（颜色`c'`、比例`s'`、不透明度`α'`）。
*   **关键输入**：除了从编码后发丝体积中采样的点特征、点的位置编码和视角方向，MLP特别引入了**发丝切线向量`t`**，以更好地表达头发各向异性的光散射效果。
*   **曲率自适应的基元混合**：为缓解因发丝弯曲导致的相邻高斯基元间着色不连续问题，引入了一种基于**局部曲率`κ_i`** 的自适应混合算法，对相邻高斯的颜色（球谐系数）和不透明度进行平滑插值。
*   **渲染与训练**：通过可微分光栅化器`R`合成最终图像，并使用L1、SSIM和LPIPS损失进行端到端优化。

### 3. 实验设计

*   **数据集**：
    *   由于缺乏真实的动态头发追踪数据，论文构建了一个**全新的合成数据集**。
    *   **几何数据集**：包含多种发型（卷发、波浪、马尾等），每种发型使用基于物理的XPBD模拟引擎生成100个运动序列，总计10K帧，包含变形头发位置、头部运动参数和上身网格。
    *   **外观数据集**：对每种发型的500帧序列，在Blender中使用24个多视角相机进行渲染，生成逼真的多视角视频。
*   **评估基准**：
    *   **对比方法**：将论文提出的动态建模方法，与**3DGS**和**Gaussian Haircut (GH)** 两款基础方法的静态版本集成，进行公平对比。同时，将“刚性变换的静态头发”作为变形模型的下限，将“XPBD物理模拟结果”作为上限。
    *   **评估指标**：
        *   **变形精度**：L2误差，Chamfer距离，光流向量的L2误差。
        *   **渲染质量**：PSNR、SSIM、LPIPS。

### 4. 资源与算力

*   所有实验均在**单块NVIDIA A100 GPU**上完成。
*   **训练时长**：
    *   动态头发粗阶段：约20小时。
    *   动态头发细阶段：约20小时。
    *   外观模型：约26小时。

### 5. 实验数量与充分性

*   **实验覆盖度**：
    *   在5位不同发型的受试者上进行了全面的定量与定性评估。
    *   进行了严格的**消融实验**，逐项验证了各模块的有效性：
        *   **动态建模**：对比了完整模型 vs 移除SDF约束（`Ours w/o SDF`）、仅使用粗阶段（`Ours w/o motion`）、移除细阶段的交叉注意力（`Ours w/o atten.`）。同时还分析了帧间光流误差。
        *   **外观优化**：对比了完整模型 vs 移除切线特征和曲率混合（`w/o tan. & blend`）、仅移除曲率混合（`w/o blend`）。同时还分析了不同损失函数（LPIPS/SSIM）的影响。
*   **充分性评估**：实验设计较为充分和客观。通过在统一合成数据集上重新训练所有基线方法，并将论文的运动模块外挂于这些方法进行对比，确保了公平性。消融研究系统地验证了从粗到细策略、SDF约束、交叉注意力和曲率混合等关键设计组件的贡献。

### 6. 论文的主要结论与发现

*   DGH是一种高效、可扩展的数据驱动方法，成功替代了传统物理模拟，实现了由头部运动驱动的动态头发变形和逼真外观渲染。
*   **由粗到细的策略**是有效的：粗阶段提供了物理上合理的变形初始化，细阶段通过时序交叉注意力成功捕捉了惯性、阻尼等高频动态效果。
*   **动态外观优化至关重要**：引入发丝切线和曲率自适应混合机制，显著缓解了动态场景下的着色不连续问题，提升了渲染质量。
*   DGH能够与3D高斯头像框架无缝集成，为创建高保真、可动画化的虚拟化身提供了有力支持。

### 7. 优点

*   **完全数据驱动**：摆脱了对物理模拟引擎的依赖，避免了繁琐的手动参数调整，并且模型可以微分，能够从数据中学习。
*   **创新的两阶段框架**：“由粗到细”的层次化设计思路清晰，将复杂问题解耦，既保证了基础变形的稳定性，又提升了动态细节的时序连贯性。
*   **外观建模新颖有效**：利用发丝切线和曲率引导的基元混合来优化3DGS外观，是处理高曲率细长结构（如头发）渲染的有效实践。
*   **高品质合成数据集**：论文创建并计划公开的规模化动态头发数据集，填充了该领域的空白，对后续研究具有积极意义。

### 8. 不足与局限

*   **数据依赖性**：模型完全基于合成数据训练，其在真实世界数据上的泛化能力未经验证，可能存在“合成到真实”的域间隙问题。
*   **运动范围有限**：模型目前仅考虑头部旋转驱动的运动，尚未处理全身运动（如跳跃、下蹲）以及头发与环境（如风）的交互影响。
*   **实时性挑战**：虽然推理速度（变形约2FPS，渲染约2.22FPS）快于高精度物理模拟，但距离实时应用（>30FPS）仍有差距，尤其是对于高密度发丝。
*   **光照条件固定**：外观模型在恒定光照下训练，不具备动态重新打光的能力。

（完）
