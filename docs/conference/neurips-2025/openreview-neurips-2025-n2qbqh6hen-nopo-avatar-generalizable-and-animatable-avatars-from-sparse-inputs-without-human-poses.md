---
title: "NoPo-Avatar: Generalizable and Animatable Avatars from Sparse Inputs without Human Poses"
title_zh: "NoPo-Avatar: 无需人体姿态从稀疏输入重建可泛化与可动画化身"
authors: "Jing Wen, Alex Schwing, Shenlong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=N2QBQh6HeN"
tags: ["query:talking-head"]
score: 10.0
evidence: 无需人体姿态输入，从稀疏图像重建可动画的3D人体化身
tldr: 针对现有方法需要精确人体姿态输入且噪声敏感的问题，NoPo-Avatar直接从图像重建可动画的3D化身，无需姿态估计。通过去除对姿态的依赖，显著提升了在噪声姿态下的重建质量，在多个基准数据集上验证了其有效性和泛化性，简化了数字人化身创建流程。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1371, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1406, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 541, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 765, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1419, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1440, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2qbqh6hen/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1417, \"height\": 408, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1064, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1086, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1261, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 729, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 574, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 681, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 666, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 880, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2qbqh6hen/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 978, \"height\": 217, \"label\": \"Table\"}]"
motivation: 现有化身重建方法依赖精确的人体姿态，噪声姿态会严重降低结果质量。
method: 仅从图像输入重建化身，不依赖测试时的人体姿态，消除姿态噪声影响。
result: 在THuman2.0等挑战性数据集上，姿态噪声下重建质量显著优于姿态依赖方法。
conclusion: 无姿态输入的化身重建方法更具鲁棒性和实用性，提升了数字人创建的便捷性。
---

## Abstract
We tackle the task of recovering an animatable 3D human avatar from a single or a sparse set of images. For this task, beyond a set of images, many prior state-of-the-art methods use accurate “ground-truth” camera poses and human poses as input to guide reconstruction at test-time. We show that pose‑dependent reconstruction degrades results significantly if pose estimates are noisy.
To overcome this, we introduce NoPo-Avatar, which reconstructs avatars solely from images, without any pose input. 
By removing the dependence of test-time reconstruction on human poses, NoPo-Avatar is not affected by noisy human pose estimates, making it more widely applicable. Experiments on challenging THuman2.0, XHuman, and HuGe100K  data show that NoPo-Avatar outperforms existing baselines in practical settings (without ground‑truth poses) and delivers comparable results in lab settings (with ground‑truth poses).

---

## 论文详细总结（自动生成）

# NoPo-Avatar: 无需人体姿态从稀疏输入重建可泛化与可动画化身

## 1. 论文的核心问题与整体含义
**研究动机：** 当前从单张或稀疏图像重建可动画3D人体化身的方法，大多依赖精确的相机姿态和人体姿态作为输入来指导重建。然而，在真实场景中，姿态估计器通常存在误差，且论文实验表明，输入姿态的噪声会导致渲染质量显著下降（噪声越大，LPIPS和FID恶化越明显）。  
**整体含义：** 该工作旨在消除重建过程对测试阶段人体姿态和相机姿态的依赖，提出一种仅从图像和人体掩膜即可直接重建可动画化身的模型，从而克服姿态噪声的敏感性，使方法在实际应用中更鲁棒、更通用。

## 2. 论文提出的方法论
**核心思想：** 不依赖任何姿态先验，仅利用输入图像及其掩膜，直接在规范T-pose空间重建高斯基元，并通过线性混合蒙皮（LBS）驱动以实现动画。  
**关键技术细节：**
- **双分支重建模块（Recon）：**
  - *模板分支（Template Branch）：* 以可学习的嵌入作为输入（代表平均SMPL-X T-pose模板），输出相对于模板的高斯残差，负责捕捉人体总体结构并补全不可见区域。
  - *图像分支（Image Branches）：* 为每张输入图像建立分支，共享编码器权重，预测每个前景像素对齐的规范空间高斯（Splatter Images），保留输入图像中的精细纹理。
- **编码器-解码器结构：**
  - 编码器：模板分支使用固定的可学习特征图；图像分支使用ViT对图像编码。
  - 解码器：多个ViT块，各分支间通过交叉注意力交换信息，实现无姿态对齐与不可见区域“补绘”。
- **预测头：** 采用DPT头，模板分支预测相对于UV空间模板的高斯残差；图像分支直接预测每个像素对应的高斯参数（位置、尺度、旋转、不透明度、球谐系数、LBS权重），并通过输入掩膜过滤背景。
- **动画与渲染：** 重组模板与图像分支的高斯集合G = GT ∪ GI。通过LBS将规范空间高斯变形到目标姿态（包含形状变换β和姿态旋转θ），再用高斯泼溅渲染。
- **训练损失：** MSE损失、LPIPS损失、Chamfer距离（模板与图像分支高斯间）、投影损失（约束图像分支高斯对应像素及渲染自洽性）、LBS损失（监督与SMPL-X网格的伪LBS权重一致）。

## 3. 实验设计
**数据集及场景：**
- 训练：THuman2.0（426人），THuman2.1（约2500人），HuGe100K（>10万人）。
- 评估：THuman2.0测试集（100人）、XHuman（20个受试者，跨域泛化）、HuGe100K测试集（50人）。
- 任务场景：
  - 稀疏多视图新视角合成（3张输入）
  - 单视图新视角合成及新姿态合成
  - 跨域泛化（XHuman）
  - 零样本下游任务（部件分割、姿态估计）

**Benchmark及对比方法：**
- 稀疏多视图设置：
  - 使用预测姿态（MultiHMR）与真值姿态，对比GHG、LIFe-GoM、GoMAvatar、3DGS-Avatar、iHuman、NHP、NIA等。
  - 测试时姿态优化（摄像机/人体姿态）进一步对比。
- 单视图设置：对比IDOL、LHM（1B参数）。

**评估指标：** PSNR、LPIPS*、FID，重建时间。

## 4. 资源与算力
- **训练过程：** 三阶段逐步提高分辨率（256→512→全分辨率），THuman实验批量大小4，耗时约12天（每阶段4天）。HuGe100K实验批量大小16/8，最后阶段全分辨率训练80K次。
- **GPU类型与数量：** 使用2块NVIDIA L40S训练256分辨率，4块L40S训练512分辨率，4块NVIDIA H200训练全分辨率。
- **推理资源：** 三张1024×1024图像约需24GB显存；单张896×640约需11GB。
- 本研究使用较大量计算资源，但文中详细提供了各部分配置。

## 5. 实验数量与充分性
**实验充分性：**
- 消融实验：分别验证模板分支与图像分支、投影损失、LBS损失的作用，评估不同输入视图数。
- 鲁棒性分析：输入姿态噪声实验（不同标准差高斯噪声及预测姿态），训练噪声鲁棒性，目标姿态噪声影响。
- 数值对比：覆盖多个数据集、多种训练规模（THuman2.0/2.1/+HuGe100K），性能随数据量提升的规律。
- 跨域泛化：在未见过的XHuman上测试新视角合成与新姿态合成。
- 附加分析：零样本下游任务（部件分割、姿态估计）、身份漂移量化。
- 对比方法实现细节清晰，测试时目标姿态优化消除尺度/位姿失配影响，保证比较公平。
- 总体来说，实验设计全面且客观。

## 6. 论文的主要结论与发现
- 不使用任何姿态先验，NoPo-Avatar在姿态估计不准确时性能远超基线，在真值姿态下也可媲美或超越（尤其LPIPS*和FID）。
- 模板分支有助于补绘不可见区域，图像分支保留观察到的细节，双分支组合效果最优。
- 辅助损失（投影损失和LBS损失）对规范空间重建及动画能力至关重要。
- 模型可受益于更大训练数据规模，特别是在跨域泛化任务上。
- 单视图重建速度与IDOL相近（约321ms），快于LHM，且视觉质量更优。
- 展现了零样本部件分割和基于分析综合的姿态估计能力。

## 7. 优点
- **完全无需姿态输入**，从根本上解决了姿态噪声敏感问题，更具实用性。
- **双分支设计**兼顾整体形状补全与局部细节保留，尤其改善面部、衣纹等精细区域。
- **重建速度快**（单张图像约0.32秒，三张图像约1.32秒），有利于实时应用。
- **可动画**规范空间表示，无需后处理即可驱动新姿态。
- **跨域泛化强**，经大规模数据训练后能较好适应新数据域。
- 同时展示了零样本下游任务的潜力，拓宽应用场景。

## 8. 不足与局限
- **面部表情和手部建模不足**：当前不支持表情重定向，手部因分辨率低易模糊。
- **训练数据质量依赖**：合成数据HuGe100K多视角一致性差，会导致半透明区域和模糊渲染；回归式方法难以生成不可见区域的锐利高频细节。
- **身份漂移**：虽优于IDOL，但未配备专门的人脸增强模块，与LHM的微距面部建模相比有差距。
- **泛化限制**：仅用亚洲面孔数据集（THuman）时可能对其他种族表现不佳，需多样性数据提升。
- **清晰度局限**：大范围不可见区域呈模糊补绘，不如生成式方法。

（完）
