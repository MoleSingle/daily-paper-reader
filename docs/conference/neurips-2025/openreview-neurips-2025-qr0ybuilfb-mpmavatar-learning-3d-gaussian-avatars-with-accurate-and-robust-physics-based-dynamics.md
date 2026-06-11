---
title: "MPMAvatar: Learning 3D Gaussian Avatars with Accurate and Robust Physics-Based Dynamics"
title_zh: "MPMAvatar: 学习具有精确鲁棒物理动力学的3D高斯化身"
authors: "Changmin Lee, Jihyun Lee, Tae-Kyun Kim"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Qr0YbuilFb"
tags: ["query:talking-head"]
score: 10.0
evidence: 创建具有物理动力学驱动的逼真3D人体化身
tldr: 针对从多视角视频创建具有物理真实性的人体化身这一难题，MPMAvatar提出基于物质点法模拟器的框架，精确模拟宽松服装的复杂变形，实现高保真渲染和鲁棒动画。实验表明该方法在动态精度和泛化性上优于现有技术，为数字人化身生成提供了可靠方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qr0ybuilfb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qr0ybuilfb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1332, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qr0ybuilfb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1412, \"height\": 703, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qr0ybuilfb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qr0ybuilfb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 446, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qr0ybuilfb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qr0ybuilfb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qr0ybuilfb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qr0ybuilfb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qr0ybuilfb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 205, \"label\": \"Table\"}]"
motivation: 现有3D化身创建工作在建模宽松服装的物理动力学方面精度和鲁棒性不足。
method: 基于物质点法模拟器，量身定制以建模服装的复杂变形，结合3D高斯实现逼真渲染。
result: 在多视角视频上学习后，可从新视角生成高保真动画，且对未见动画输入具有鲁棒性。
conclusion: 提出了一种精确且鲁棒的人体化身创建框架，推动了物理真实感数字人的发展。
---

## Abstract
While there has been significant progress in the field of 3D avatar creation from visual observations, modeling physically plausible dynamics of humans with loose garments remains a challenging problem. Although a few existing works address this problem by leveraging physical simulation, they suffer from limited accuracy or robustness to novel animation inputs. In this work, we present MPMAvatar, a framework for creating 3D human avatars from multi-view videos that supports highly realistic, robust animation, as well as photorealistic rendering from free viewpoints. For accurate and robust dynamics modeling, our key idea is to use a Material Point Method-based simulator, which we carefully tailor to model garments with complex deformations and contact with the underlying body by incorporating an anisotropic constitutive model and a novel collision handling algorithm. We combine this dynamics modeling scheme with our canonical avatar that can be rendered using 3D Gaussian Splatting with quasi-shadowing, enabling high-fidelity rendering for physically realistic animations. In our experiments, we demonstrate that MPMAvatar significantly outperforms the existing state-of-the-art physics-based avatar in terms of (1) dynamics modeling accuracy, (2) rendering accuracy, and (3) robustness and efficiency. Additionally, we present a novel application in which our avatar generalizes to unseen interactions in a zero-shot manner—which was not achievable with previous learning-based methods due to their limited simulation generalizability. Our code will be publicly available.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文内容和要求，以下是对论文《MPMAvatar: Learning 3D Gaussian Avatars with Accurate and Robust Physics-Based Dynamics》的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：从多视角视频中创建具有物理真实感动态的3D人类化身，尤其是精确、鲁棒地模拟宽松服装（如裙子）的复杂变形和与身体的交互，仍是一个重大挑战。
*   **研究动机**：
    *   现有基于学习的动画方法（如线性混合蒙皮、姿态相关几何校正）在处理宽松服装时，难以捕捉复杂形变且易对训练动作过拟合，泛化性差。
    *   少数基于物理模拟的化身方法（如PhysAvatar）虽然尝试解决此问题，但其模拟器（X-PBD, C-IPC）在动画输入有微小自穿透时容易失效，鲁棒性不足，且渲染保真度有限。
*   **整体含义**：本文提出了MPMAvatar框架，旨在创建一个既能实现高保真自由视角渲染，又能进行物理精确、鲁棒动画，甚至能零样本泛化到新场景交互的3D人类化身。

### 2. 论文提出的方法论

MPMAvatar的核心思想是采用**物质点法(MPM)模拟器**来驱动服装动态，并结合**3D高斯泼溅(3D Gaussian Splatting)** 进行渲染，形成一个混合化身表达。其关键技术细节如下：

*   **化身表示 (Hybrid Avatar Representation)**：
    *   **几何与物理**：用一个规范的3D三角网格表示化身几何，并关联一组物理参数用于MPM模拟。
    *   **外观**：使用附着在网格面上的3D高斯泼溅(Gaussian Splats)表示外观，每个高斯的空间参数定义在父网格面的局部坐标系中，使其能跟随网格自然形变。
*   **基于物理的动态建模 (Physics-Based Dynamics Modeling)**：
    *   **核心模拟器**：选用MPM模拟器，因为它擅长处理大形变和自碰撞，相比PhysAvatar所用的C-IPC更加鲁棒。
    *   **各向异性本构模型 (Anisotropic Constitutive Model)**：为更好地模拟服装这种二维流形结构的物理特性（如法线方向难压缩，平面方向易拉伸），引入了各向异性应变能函数 ψ。该函数基于变形梯度 F 的QR分解 R，对不同方向（法向、剪切、平面内）的形变进行不同刚度的惩罚。
    *   **新型碰撞处理算法**：传统MPM的碰撞处理需将碰撞体解析为水平集（如球体），不适用于三角网格表示的SMPL-X人体。本文提出通过B样条权重，将碰撞体网格面的速度 `vf` 和法向 `nf` 传递至欧拉网格节点，得到扩展速度 `vci` 和法向 `nci`。然后，若物体网格速度 `vi` 与 `vci` 的相对速度指向碰撞体内部，则投影掉其法线分量，以此防止穿透。此算法的复杂度为 O(Nf)（Nf为碰撞体面数），远低于传统方法的 O(N^3_grid)，效率更高。
    *   **静态几何建模 (Rest Geometry Modeling)**：为解决从真实世界获取的规范几何已受重力形变的问题，引入参数 α 来补偿重力方向上的拉伸，从而推断出未形变的“休息态”几何，作为模拟的初始状态。
*   **学习流程 (Learning from Multi-View Videos)**：
    *   **物理参数学习**：通过有限差分法（Finite-Difference）优化物理参数（杨氏模量 E、密度 ρ、休息态参数 α），最小化模拟网格与多视角视频跟踪得到的真实网格之间的顶点 L2 距离。
    *   **外观学习**：在规范空间统一优化高斯泼溅参数。渲染时，高斯体会随跟踪网格变形到不同帧并进行可微渲染，通过最小化渲染图像与真实图像的差异（L1, SSIM, LPIPS损失）来优化，并采用了自适应密度控制。此外，还引入了基于网格环境光遮蔽特征的**准阴影 (Quasi-shadowing)** 技术来增强渲染真实感。

### 3. 实验设计

*   **数据集**：
    *   **ActorsHQ**: 主要评测基准，选取了4个主体（2个穿宽松连衣裙，2个穿两件套），其中24帧用于物理参数学习，200帧用于外观学习，200帧用于测试。
    *   **4D-DRESS**: 用于更广泛的比较，选取了4个序列（2个上衣配裙子，2个上衣配紧身牛仔裤），其中11帧用于物理学习，100帧用于外观学习，100帧用于测试。
*   **基准方法 (Baselines)**：
    *   **核心对比**: 与当前最先进的物理模拟化身方法 **PhysAvatar** 进行重点比较。
    *   **其他对比**: 与4个开源的化身重建方法进行比较：ARAH, TAVA, GS-Avatar。
*   **评估指标 (Evaluation Metrics)**：
    *   **动态建模精度**: 倒角距离（Chamfer Distance）和 F-Score。
    *   **渲染精度**: LPIPS, PSNR, SSIM。
    *   **鲁棒性与效率**: 模拟成功率（单帧模拟是否在20小时内完成）和每帧模拟时间。

### 4. 资源与算力

*   **模拟效率**: 论文在实验部分明确指出，其MPM模拟器在单张 **NVIDIA GeForce RTX 4090** GPU上，每帧的模拟时间约为 **1.1秒**。
*   **训练细节**: 提到了优化物理参数使用了200次迭代，以及外观学习中的优化细节，但**未明确提及整个训练流程（包括物理参数和外观学习）所需的总GPU小时数或总时长**。

### 5. 实验数量与充分性

*   **实验组数**:
    1.  **主实验**: 在两个数据集上，与5个基线方法（PhysAvatar, ARAH, TAVA, GS-Avatar）进行了全面的几何和外观指标对比。
    2.  **鲁棒性和效率对比**: 专门针对PhysAvatar进行了模拟成功率和耗时对比。
    3.  **消融实验**: 在 ActorsHQ 数据集上，对三个关键组件进行了消融研究：去除各向异性本构模型、去除物理参数学习、去除准阴影渲染。
    4.  **零样本场景交互应用**: 展示了与椅子、沙子等未见物体交互的定性结果。
    5.  **补充实验（附录）**: 包含了超参数鲁棒性分析、与更多并行工作的对比等。
*   **评价**: 实验设计较为**充分和客观**。使用了多个公开数据集和标准指标，对比了当前最先进的方法，并通过消融实验验证了各模块的有效性。对比PhysAvatar时，因原始代码和数据不完全公开，作者也说明了其保证公平性的处理方式。

### 6. 论文的主要结论与发现

*   MPMAvatar 在动态建模精度和渲染质量上均显著优于现有最先进的物理化身方法 PhysAvatar。
*   定制的MPM模拟器在处理宽松服装的复杂变形方面更加精确，且具有**100%的模拟成功率**，而PhysAvatar的成功率仅为37.6%，显示出极高的鲁棒性。
*   在效率上，MPMAvatar（1.1秒/帧）比PhysAvatar（170.0秒/帧）快两个数量级。
*   基于物理的模拟方法使其化身具备了**零样本泛化能力**，能够自然地与新物体（如椅子、沙堆）进行交互，这是纯粹基于学习的方法难以实现的。

### 7. 优点

*   **技术创新**: 将MPM模拟器引入化身创建，并针对服装动态进行了两项关键定制（各向异性模型、高效网格碰撞处理），是方法论上的亮点。
*   **性能优异**: 在准确性、渲染质量、鲁棒性和效率上全面超越现有SOTA，成果显著。
*   **零样本泛化**: 首次在物理化身领域实证了与未见物体交互的零样本泛化能力，展示了物理先验的强大优势。
*   **系统完整**: 提供了一个从多视角视频输入到可驱动、可渲染、可交互化身的端到端学习框架。
*   **算法优化**: 提出的碰撞处理算法复杂度从 O(N^3_grid) 降至 O(Nf)，兼顾了实用性和效率。

### 8. 不足与局限

*   **不支持重光照**: 与 PhysAvatar相比，当前的渲染管线不支持场景重光照功能。
*   **非服装区域动画**: 对于非服装区域（如头发），仍沿用简单的线性混合蒙皮，未采用更高级的物理模拟（如基于发丝的模拟）。
*   **优化扩展性**: 物理参数优化采用有限差分法，其计算量随参数数量线性增长，当未来需要扩展为逐顶点优化等更细粒度的参数时，可能面临计算瓶颈。
*   **遮挡区域退化**: 外观学习主要基于可见区域，当新动画或视角暴露出训练集中被遮挡的部位时，渲染质量可能会下降。
*   **潜在伦理风险**: 与所有高保真数字人技术一样，存在被滥用于制造深度伪造的风险。

（完）
