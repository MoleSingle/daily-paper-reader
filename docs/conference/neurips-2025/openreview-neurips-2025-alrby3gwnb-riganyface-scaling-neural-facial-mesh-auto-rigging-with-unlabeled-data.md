---
title: "RigAnyFace: Scaling Neural Facial Mesh Auto-Rigging with Unlabeled Data"
title_zh: RigAnyFace：利用无标签数据扩展神经面部网格自动绑定
authors: "Wenchao Ma, Dario Michael Kneubuehler, Maurice Chu, Ian Sachs, Haomiao Jiang, Sharon X Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=alrbY3gwNB"
tags: ["query:talking-head"]
score: 9.0
evidence: 面向面部网格的神经自动绑定框架，为数字人 avatar 创建混合形状绑定
tldr: 本文针对数字人 avatar 创建中面部绑定成本高且难以扩展的问题，提出一种可扩展的神经自动绑定框架 RigAnyFace。该框架利用 FACS 参数驱动三角剖分无关的表面学习网络，将静态中性网格变形为产业标准的混合形状绑定，并通过专业艺术家绑定的小规模数据集与无标签数据联合训练。实验表明，该方法能有效处理多种拓扑结构，大幅降低手动绑定的工作量，为高效制作可驱动的数字人脸提供了关键工具，推动了数字人动画制作流程的自动化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1165, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1276, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 775, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1288, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 605, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1013, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1024, \"height\": 1156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 968, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1350, \"height\": 1188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1434, \"height\": 982, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 859, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-alrby3gwnb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 696, \"height\": 669, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-alrby3gwnb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 701, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-alrby3gwnb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 706, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-alrby3gwnb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 689, \"height\": 141, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-alrby3gwnb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 1341, \"label\": \"Table\"}]"
motivation: 手动面部绑定成本高、难以扩展，限制了数字人 avatar 的快速创建。
method: 提出三角剖分无关的表面学习网络，以 FACS 参数为条件预测网格变形，形成混合形状绑定。
result: 在人工绑定的小规模监督与大量无标签数据下，成功绑定多种拓扑结构的面部网格。
conclusion: RigAnyFace 为数字人面部动画提供了高效的自动绑定方案，有望降低制作门槛。
---

## Abstract
In this paper, we present RigAnyFace (RAF), a scalable neural auto-rigging framework for facial meshes of diverse topologies, including those with multiple disconnected components. RAF deforms a static neutral facial mesh into industry-standard FACS poses to form an expressive blendshape rig. Deformations are predicted by a triangulation-agnostic surface learning network augmented with our tailored architecture design to condition on FACS parameters and efficiently process disconnected components. For training, we curated a dataset of facial meshes, with a subset meticulously rigged by professional artists to serve as accurate 3D ground truth for deformation supervision. Due to the high cost of manual rigging, this subset is limited in size, constraining the generalization ability of models trained exclusively on it. To address this, we design a 2D supervision strategy for unlabeled neutral meshes without rigs. This strategy increases data diversity and allows for scaled training, thereby enhancing the generalization ability of models trained on this augmented data. Extensive experiments demonstrate that RAF is able to rig meshes of diverse topologies on not only our artist-crafted assets but also in-the-wild samples, outperforming previous works in accuracy and generalizability. Moreover, our method advances beyond prior work by supporting multiple disconnected components, such as eyeballs, for more detailed expression animation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：面部绑定（facial rigging）是让静态面部网格可动画化的关键步骤，广泛应用于数字人、游戏和影视中。传统手动绑定费时费力，专业艺术家需数十小时完成单个资产；现有自动绑定方法多依赖模板混合形状或固定拓扑，限制了对多样化拓扑（尤其是含眼球等非连通组件）的泛化能力。
- **核心问题**：如何构建一个无需模板、可处理任意拓扑（包括多个不连通组件）的面部网格自动绑定框架，并能在仅有少量高质量三维标注数据的情况下，通过利用大量无标签网格提升泛化性。
- **整体含义**：提出 **RigAnyFace (RAF)**，一个可扩展的神经自动绑定框架，接收中性面部网格和显式的 FACS 参数，直接预测各姿态的顶点位移，生成混合形状绑定。

### 2. 论文提出的方法论
- **核心思想**：基于改进的 DiffusionNet（三角剖分无关的表面网络）构建变形网络，以 FACS 编码为条件，从单一中性网格预测所有 FACS 姿态的网格位移；并设计二维监督策略，利用二维面部动画生成模型和光流估计为无绑定的中性网格提供监督，实现规模化训练。
- **关键技术细节**：
  - **变形网络**：输入为中性网格 `M0` 和 FACS 姿态向量 `Ai`，输出位移 `^di`，获得到姿态网格 `^Mi = M0 + ^di`。网络基于 DiffusionNet：
    - **全局编码器**：一个小型 DiffusionNet 结合全局平均池化，将整个网格（含多个不连通组件）压缩为全局特征向量 `G0`，提供组件间全局信息。
    - **FACS 条件注入**：将 `Ai` 与 `G0` 拼接，注入每个条件扩散块，通过复制和融合方式与主网络特征结合，引导姿态生成。
  - **二维监督**：对于无绑定网格，利用二维面部动画模型（基于 MegActor）从无绑定网格的渲染图和一个来自已绑定网格的驱动姿态图生成对应的姿态图像；再用光流估计模型（RAFT）预测中性图到生成姿态图的像素位移 `d2d_i` 作为伪真值。损失包括图像损失、掩码损失、二维位移损失等。二维位移损失可提供对细微表情的稠密运动监督。
  - **训练流程**：两阶段训练。
    - 第一阶段：大量已绑定和无绑定网格，仅用二维监督（图像、掩码、位移、正则化损失），增强泛化性。
    - 第二阶段：仅用已绑定网格，加入三维真值损失 `L_mse-3d`、关键点损失和闭眼损失，微调得到精确三维变形。
- **公式/算法流程简述**：
  1. 全局编码器输出 `G0 = AvgPool(DiffusionNet(M0))`。
  2. 姿态条件 `C = Concat(Ai, G0)`。
  3. 主 DiffusionNet 以 `C` 为条件输出每顶点位移 `^di`。
  4. 损失：`L_s1 = α1 L_img + α2 L_mask + α3 L_dis2d + α4 L_reg`；`L_s2 = ... + L_mse3d + L_lmk + L_ec`。

### 3. 实验设计
- **数据集**：
  - **自建数据集**：包含多种形状的艺术家制作面部网格，含多个不连通组件（眼球、牙齿等）。其中 161 个已绑定（包含 96 个 FACS/修正姿态），175 个未绑定。测试集：24 个已绑定人头（定量），37 个多样未绑定头（定性，出分布）。
  - **外部数据**：ICT FaceKit、Objaverse、CGTrader 的 in-the-wild 网格，仅作定性对比。
- **基准与对比方法**：
  - **NFR**：唯一直接基于 FACS 参数的无模板自动绑定方法，但仅处理单连通组件，需预处理（删除内部组件、修剪内唇和眼睑）。
  - **变形传递（Deformation Transfer）**：需要模板姿态网格和用户标注点对应。
- **评价指标**：对于有三维真值的已绑定网格，计算所有姿态下顶点平均绝对误差（MAE）和 95% 分位数误差（MAE Q95）。

### 4. 资源与算力
- **GPU 配置**：8 块 NVIDIA A100 GPU，总批大小 8（每卡 1）。
- **训练时长**：第一阶段 15 周期约 1.5 天，第二阶段 20 周期约 1 天，总计约 2 – 2.5 天。
- **推理**：Apple M2 Max CPU 上约 8.72 秒，Nvidia T4 GPU 上约 3.1 秒生成一副混合形状绑定；模型参数 5.4M。

### 5. 实验数量与充分性
- **消融实验**（精确对比各组件有效性）：
  - 移除全局编码器：错误增加、非连通组件穿透严重。
  - 移除二维损失（仅用三维监督）：MAE 上升。
  - 移除未绑定数据训练：MAE 升高，动物闭眼等挑战场景表现差。
  - 移除二维位移损失：MAE 上升，细微姿态（如 Jaw Left）改善有限。
  - 对全局编码器的额外分析：通过穿透率和 t-SNE 可视化证明其有效编码组件位置。
- **对比实验**：与 NFR 和变形传递在艺术家标注的人形头上定量比较（MAE 和 Q95）；在 in-the-wild 数据上与 NFR 定性对比。
- **应用展示**：用户控制动画、视频表情重定向、文本生成 3D 面部动画化。
- 实验覆盖了内部测试、外部泛化、消融组件、多场景应用，对比基准选取合理（NFR 是当前 SOTA），但比较基于预处理后的网格（对 NFR 公平），RAF 能处理更复杂的原始网格。

### 6. 论文的主要结论与发现
- RAF 成功实现了对任意拓扑面部网格（含多组件）的自动绑定，生成符合 FACS 标准的混合形状绑定，无需模板。
- 全局编码器和 FACS 条件注入使得 DiffusionNet 能够处理非连通组件并生成准确变形。
- 二维监督策略（含二维位移损失）有效利用大量无绑定数据，显著提升泛化能力，尤其在细微表情和出分布样本上。
- 在艺术资产和 in-the-wild 样本上全面超越 NFR 和变形传递，且无需用户交互或预处理。

### 7. 优点
- **无模板、拓扑无关**：彻底摆脱了对模板混合形状和固定拓扑的依赖。
- **多组件支持**：首次实现将眼球、牙齿等不连通组件纳入统一变形框架，提升表情真实感。
- **可扩展训练**：通过二维监督引入无绑定数据，解决了三维标注稀缺问题，显著提高泛化性。
- **针对性架构改进**：全局编码器与条件扩散块的创新设计，简单有效。
- **丰富的实验验证**：消融、对比、跨数据、应用演示，全面支撑主张。

### 8. 不足与局限
- **特殊拓扑退化**：对于与训练数据差异过大的壳状网格（缺乏细致几何细节），变形质量下降。
- **差三角剖分**：若面部主要部分被分割为多个不连通的碎片，模型无法维持空间一致性。
- **数据限制**：训练数据仍依赖艺术家制作，极端多样的非人形面部可能覆盖不足。
- **实验比较不完整**：与 NFR 对比时，NFR 需预处理（移除组件），而 RAF 可直接处理，虽展示了 RAF 的优势，但可能导致比较基准不完全对等（NFR 在预处理后可能丢失信息）。未将更多近期方法如 Shape Transformers 等纳入对比。
- **二维监督质量依赖**：依赖二维动画生成模型和光流模型的性能，对极度风格化面部可能不准确。

（完）
