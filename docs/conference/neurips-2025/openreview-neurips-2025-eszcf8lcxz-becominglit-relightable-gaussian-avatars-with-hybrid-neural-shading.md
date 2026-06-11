---
title: "BecomingLit: Relightable Gaussian Avatars with Hybrid Neural Shading"
title_zh: "BecomingLit: 可重光照高斯头像与混合神经着色"
authors: "Jonathan Schmidt, Simon Giebenhain, Matthias Nießner"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=eSZcf8LCxz"
tags: ["query:talking-head"]
score: 10.0
evidence: 重建可重光照的高分辨率头部头像
tldr: 该论文提出一种新方法BecomingLit，用于从多视角序列重建可重光照的高分辨率头部头像。设计低成本光场采集系统并构建包含多样光照和表情的数据集，基于3D高斯原语和参数化头部模型实现表情动画，结合神经漫反射BRDF与解析高光BRDF的混合着色。实验展示其交互式新视角渲染和重光照能力，为数字人真实感呈现提供实用方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 1252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 979, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 658, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 237, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eszcf8lcxz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1451, \"height\": 710, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-eszcf8lcxz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1243, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eszcf8lcxz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1200, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eszcf8lcxz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1285, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eszcf8lcxz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1186, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eszcf8lcxz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1082, \"height\": 239, \"label\": \"Table\"}]"
motivation: 现有头部头像重建缺乏高效可重光照方案，且采集成本高。
method: 提出低成本光场采集、3D高斯动态头像模型和混合神经着色。
result: 实现交互式新视角渲染和高质量重光照，构建新数据集。
conclusion: 为可重光照头部头像提供新基准，简化捕捉并提升真实感。
---

## Abstract
We introduce *BecomingLit*, a novel method for reconstructing relightable, high-resolution head avatars that can be rendered from novel viewpoints at interactive rates. Therefore, we propose a new low-cost light stage capture setup, tailored specifically towards capturing faces. Using this setup, we collect a novel dataset consisting of diverse multi-view sequences of numerous subjects under varying illumination conditions and facial expressions. By leveraging our new dataset, we introduce a new relightable avatar representation based on 3D Gaussian primitives that we animate with a parametric head model and an expression-dependent dynamics module. We propose a new hybrid neural shading approach, combining a neural diffuse BRDF with an analytical specular term. Our method reconstructs disentangled materials from our dynamic light stage recordings and enables all-frequency relighting of our avatars with both point lights and environment maps. In addition, our avatars can easily be animated and controlled from monocular videos. We validate our approach in extensive experiments on our dataset, where we consistently outperform existing state-of-the-art methods in relighting and reenactment by a significant margin.

---

## 论文详细总结（自动生成）

好的，这是按照您的要求生成的结构化论文分析总结。

### 1. 论文核心问题与整体含义

- **研究动机**：创建逼真、可重光照的3D头部头像在影视、虚拟现实等领域至关重要。
    - 传统方法依赖昂贵的专业采集设备，且材质与光照的联合估计是高度欠约束问题。
    - 现有大多数主流3D头像方法将训练环境的光照“烘焙”到模型内部，导致其在新的虚拟环境下无法重光照，视觉效果大幅下降。
- **核心问题**：如何从经济、低成本的动态采集数据中，重建出具有解耦材质属性、可实时重光照和动画的逼真3D头部头像。
- **整体含义**：本工作旨在推动高质量可重光照头像的大众化，通过提出**低成本的采集方案**、**新的公开数据集**以及**基于3D高斯与混合神经着色的新头像表示方法**，克服了现有技术对昂贵设备的依赖和重光照能力的不足。

### 2. 方法论

论文提出 *BecomingLit* 框架，核心思想是将**3D高斯原语**作为几何表示，并采用**混合神经着色**方案来建模面部复杂的反射特性。

- **几何表示与动画**：
    - **基础几何**：使用参数化头部模型**FLAME**，从全亮帧中通过VHAP追踪器获取姿态、形状和表情系数。
    - **高斯原语生成与驱动**：在FLAME网格的UV贴图上定义可学习的静态3D高斯参数。设计了一个**表情依赖的动态模块（ \(F_g\) ）**，它是一个卷积神经网络，输入FLAME表情系数，预测每个高斯原语的位置偏移、旋转、尺度、不透明度以及表情特征向量 \(f_{expr}\)。此模块将大部分偏移定义为表情无关的静态量，并对表情相关偏移进行正则化，从而提升表情泛化能力，避免伪影。

- **材质与着色（核心创新）**：
    - **混合着色方案**：将人脸的反射函数分解为**与视角无关的漫反射项**和**与视角相关的镜面反射项**。
    - **神经漫反射 BRDF（ \(F_d\) ）**：
        - **目的**：建模传统解析模型难以处理的全局光照效果，如皮肤常见的次表面散射。
        - **实现**：一个轻量级的、所有原语共享的MLP网络。输入为入射光的球谐系数（6阶）和表情特征向量 \(f_{expr}\)，输出单通道的反射率值。渲染时对RGB三通道分别评估，再与每个原语上学习到的反照率 \(a_k\) 逐元素相乘，得到最终漫反射颜色。
        - **公式**：\(c_d^k = a_k \cdot F_d(SH_m(L_i), f_{expr}^k)\)
    - **解析镜面反射 BRDF**：
        - **模型**：基于**Cook-Torrance模型**，并采用了由Riviere等人提出的双Blinn-Phong混合法向分布函数（NDF）。
        - **视角依赖的镜面参数预测**：使用一个小的卷积网络 \(F_v\)，输入表情特征 \(f_{expr}\) 和观察方向 \(\omega_o\)，预测镜面反射强度 \(s_k\) 和法线偏移 \(\delta_n\)。最终着色法线由粗糙的FLAME网格法线与 \(\delta_n\) 相加并归一化得到。此法线预测方式比同类工作（RGCA）所需的网络参数更少。

- **优化**：
    - **损失函数**：包括光度损失（L1 + SSIM）和一系列正则化损失。
    - **关键正则化**：`L_normal` 约束法线偏移趋近于0；`L_alpha` 约束渲染的Alpha遮罩与背景抠图结果一致，这对解决因只有前半球光源导致的环境图渲染伪影至关重要；`L_scale` 和 `L_pos` 分别约束高斯原语的尺度和位置偏移动量。

### 3. 实验设计

- **数据集**：
    - **主要数据集**：该工作引入的自建多视角OLAT人脸数据集。包含10位受试者，16个相机视角，40个LED光源。从16个视角中取15个用于训练，保留1个中心视角做测试。同时，保留4种未在训练中出现的光照模式用于评估重光照能力。
    - **额外数据集**：在Goliath-4数据集上进行了跨数据集的泛化性验证。
- **评估基准**：
    - **任务**：重光照和自重建（Self-Reenactment）。
    - **指标**：PSNR、SSIM、LPIPS。
- **对比方法**：
    - **RGCA**（Relightable Gaussian Codec Avatars）：近期先进的可重光照高斯头像方法。
    - **RGCA_FLAME**：一个增强基线，将RGCA学习到的个性化表情空间替换为FLAME系数。

### 4. 资源与算力

- **硬件**：所有实验（训练与运行时测量）均在**单个NVIDIA RTX A6000 GPU**上完成。
- **训练时长**：在1100x1604分辨率下训练25万次迭代，batch size为4，耗时约**30小时**。
- **推理速度**：渲染同样分辨率的图像，总耗时为**17毫秒**（显式分割了各组件耗时），实现了交互式实时渲染。

### 5. 实验数量与充分性

- **主要对比实验**：在有4名受试者的测试集上进行了2组定量对比实验，分别评估了在训练片段和测试片段上的重光照及重光照+自重建性能。
- **消融实验**：对5个关键模块/设计进行了消融研究，具体包括：
    1.  将混合神经着色替换为纯PBR着色。
    2.  将神经漫反射替换为基于预计算辐射传输（PRT）的漫反射。
    3.  将Cook-Torrance镜面反射替换为简单的球面高斯（SG）。
    4.  移除Alpha损失。
    5.  移除表情依赖特征。
- **分析**：实验设计充分且客观。不仅在自建数据集上与SOTA方法进行了多指标、多场景的定量定性对比，还通过详细的消融实验验证了各个关键组件的有效性。此外，在Goliath-4数据集上的额外实验进一步证明了其泛化能力。

### 6. 主要结论与发现

- **新数据集价值**：所提出的多视角OLAT人脸数据集，在分辨率、帧率和捕获条件多样性上具有显著优势，为可重光照头像研究提供了新的基准。
- **SOTA性能**：*BecomingLit* 方法在重光照和自重建任务上，无论是在训练集还是测试集（包括未见过的光照和表情），其定量和定性结果均**显著优于**现有的RGCA方法。
- **关键设计有效性**：
    - **混合着色**是核心，神经漫反射能有效捕捉皮肤复杂的次表面散射，而解析镜面反射则能产生更逼真、更锐利的毛孔级高光细节。
    - **Alpha正则化**对于解决由于半球采集带来的后方光照伪影至关重要，使得可以使用更经济的采集设备。
    - **表情依赖特征**和**视角依赖的法线预测**对捕捉动态下的细节变化十分重要。

### 7. 优点

- **技术创新**：提出混合神经漫反射与解析镜面反射相结合的高斯原语着色方案，成功平衡了渲染逼真度与泛化能力。
- **实用性强**：整个采集系统成本较以往方案降低了一个数量级，训练只需单GPU且可交互式渲染，极大地提升了方法的实用性和可及性。
- **可驱动性**：头像可被FLAME参数直接驱动，易于从现有的单目视频追踪器获取驱动信号，实现了跨身份重演。
- **数据贡献**：发布的高质量、多视角OLAT面部数据集，为社区提供了宝贵的研究资源。
- **科学严谨**：通过在自建数据集和跨数据集上的全面实验与消融分析，有力地支撑了其核心贡献和设计选择。

### 8. 不足与局限

- **捕捉与训练代价**：虽然采集成本降低，但仍需使用专门搭建的光场系统进行数分钟的拍摄，且训练仍需数万帧数据及多种表情，无法从随手拍的手机视频直接生成可重光照头像。
- **基础几何限制**：依赖的FLAME基础几何模型表达能力有限，不包含口腔内部，且对追踪失败（尤其是视线方向）较为敏感。这些局限性会遗传给最终重建的头像。
- **模型泛化**：神经漫反射着色器是与个体头像联合从头训练的，尚未利用大量数据学习人脸外观的先验，限制了从极少量数据创建头像的潜力。
- **伦理风险**：创建出的逼真、可驱动头像具有被滥用于深度伪造和身份盗用的潜在风险。论文通过限制数据集访问和使用权限（仅限经批准的非商业学术研究）来缓解此风险。

（完）
