---
title: Low-Rank Head Avatar Personalization with Registers
title_zh: 基于寄存器的低秩头部头像个性化
authors: "Sai Tanmay Reddy Chakkera, Aggelina Chatziagapi, Md Moniruzzaman, Chen-ping Yu, Yi-Hsuan Tsai, Dimitris Samaras"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=mhARf5VzCn"
tags: ["query:talking-head"]
score: 10.0
evidence: 使用寄存器模块进行头部头像生成的低秩个性化
tldr: 针对通用头部头像模型难以合成身份特定细节的问题，本文提出一种寄存器模块增强低秩适配(LoRA)的参数高效个性化方法。该方法应用于预训练模型的中间特征，以少量参数即可捕获高频面部细节。实验证明，其在头部头像生成任务中优于标准LoRA，实现精准身份保持与高效适应性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1224, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 1152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1316, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1437, \"height\": 1353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1436, \"height\": 1639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1434, \"height\": 1626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1429, \"height\": 2133, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1431, \"height\": 2138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1437, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1439, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1441, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1443, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1440, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1441, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mharf5vzcn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1424, \"height\": 896, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 971, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1463, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 727, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 596, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 406, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 570, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mharf5vzcn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 206, \"label\": \"Table\"}]"
motivation: 通用头像模型丢失身份细节，标准LoRA难以捕获高频特征。
method: 设计寄存器模块适配预训练模型中间特征，弥补LoRA不足。
result: 以少量参数实现身份精确的头像个性化，高频细节更佳。
conclusion: 提供高效的头部头像个性化方案，提升数字人脸重建精度。
---

## Abstract
We introduce a novel method for low-rank personalization of a generic model for head avatar generation. Prior work proposes generic models that achieve high-quality face animation by leveraging large-scale datasets of multiple identities. However, such generic models usually fail to synthesize unique identity-specific details, since they learn a general domain prior. To adapt to specific subjects, we find that it is still challenging to capture high-frequency facial details via popular solutions like low-rank adaptation (LoRA). This motivates us to propose a specific architecture, a Register Module, that enhances the performance of LoRA, while requiring only a small number of parameters to adapt to an unseen identity. Our module is applied to intermediate features of a pre-trained model, storing and re-purposing information in a learnable 3D feature space. To demonstrate the efficacy of our personalization method, we collect a dataset of talking videos of individuals with distinctive facial details, such as wrinkles and tattoos. Our approach faithfully captures unseen faces, outperforming existing methods quantitatively and qualitatively.

---

## 论文详细总结（自动生成）

好的，作为一名资深的学术论文分析助手，我将基于您提供的论文内容，为您生成一份结构化、深入且客观的中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景**：通用头部头像生成模型（如GAGAvatar）通过在大规模多身份数据集上训练，能够为新身份生成可动画化的3D头像，但通常只能学习到通用的人脸先验，难以合成特定身份的高频细节，如独特的皱纹、纹身、皮肤质感等。
*   **核心问题**：如何对通用头像模型进行高效的个性化适配，使其在保持泛化能力的同时，能精确捕捉并还原特定身份（尤其是数据集中未见的身份）的精细面部特征。
*   **现有方法的不足**：流行的参数高效微调方法（如LoRA）虽然能减少可训练参数量，但其本身不足以捕获细粒度的高频身份特征。
*   **研究动机与整体含义**：本文旨在解决通用模型在个性化适配中丢失身份特定高频细节的难题。通过提出一种创新的“寄存器模块”来增强LoRA的性能，实现以极少量的参数完成对未见身份的高保真、个性化头像生成。

### 2. 论文提出的方法论

*   **核心思想**：受到视觉变换器（ViT）中寄存器令牌（Register Tokens）的启发，本文提出一种“寄存器模块”，为LoRA的适配过程提供更好的学习信号。该模块在训练时学习一个3D特征空间，用于“存储”和“复用”特定身份的面部细节信息，从而引导模型关注输入特征中的关键区域。
*   **关键技术流程**：
    1.  **基础模型与LoRA适配**：以预训练的通用头像模型GAGAvatar为基础，在其特定层的权重矩阵中引入低秩可分解矩阵（LoRA），公式为 `Wadapt = W + BA`，仅训练增量部分`BA`，适配完成后可与原始权重合并，不增加推理开销。
    2.  **寄存器模块（Register Module）设计**：
        *   **3D特征绑定**：将一组可学习的嵌入向量 `e` 绑定到3D形变模型（3DMM）网格 `M` 的顶点上。
        *   **投影与插值**：根据驱动图像的相机姿态，计算可见顶点`U`，并通过透视投影将它们及其对应的嵌入向量投影到2D特征平面上，形成稀疏特征图。然后，使用多边形轮廓和K近邻反距离加权插值，生成密集的2D特征图 `f_S`。
        *   **特征融合与处理**：该密集特征图经过一个CNN编码器 `E_proc-1` 处理后，与源图像的DINOv2密集特征 `f_src_dense` 相加，再通过另一个CNN编码器 `E_proc-2` 处理，得到最终的寄存器模块输出 `f_reg`。
        *   **训练时注入，推理时剥离**：在训练阶段，`f_reg` 被送入重建分支；而在推理阶段，则直接使用源图像的DINOv2特征，不增加任何推理负担。
    3.  **目标函数**：除基础模型的损失外，还引入了两个监督信号来训练寄存器模块：
        *   **特征对齐损失 `L_feat`**：以驱动图像的DINOv2特征 `f_dri_dense` 为目标，约束 `f_reg` 与其相似的均方误差损失。
        *   **正则化损失 `L_reg`**：惩罚绑定在3DMM顶点上的嵌入向量 `e` 之间的成对余弦相似度，防止它们趋于同质化，确保学习到多样化的细节。

### 3. 实验设计

*   **数据集**：
    1.  **RareFace-50**：本文专门为评估个性化效果而新收集的数据集，包含50位具有独特高频面部细节（如皱纹、纹身）的个体访谈视频，弥补了现有数据集的多样性不足。
    2.  **VFHQ Test Set**：包含50段高质量视频的公开基准测试集。
    3.  **HDTF**：包含362段视频的公开数据集。
*   **评估指标**：
    *   **LPIPS（↓）**：衡量生成图像与源图像在高频细节区域的感知相似度。
    *   **ACD（平均内容距离，↓）**：利用ArcFace计算源图像与生成图像的身份特征余弦距离，用于评估身份保持度。
*   **对比方法**：
    *   **GAGAvatar**：未做适配的通用模型基线。
    *   **LoRA**：标准低秩适配方法。
    *   **MetaPortrait**：在LoRA权重上实现基于Reptile的元学习适配方法。

### 4. 资源与算力

*   **适配阶段**：
    *   **本文方法与标准LoRA**：适配耗时约25–35分钟，使用一张RTX A5000 GPU，显存占用约14.9–23 GB。
    *   **元学习方法（Meta-Learning）**：预训练阶段耗时12天，使用一张Quadro RTX 8000 GPU（45 GB显存）；对新身份的快速适配只需约4分钟。
*   **推理阶段**：所有LoRA类方法在推理时均将适配的权重合并，因此推理速度和资源消耗与基础模型GAGAvatar完全一致。

### 5. 实验数量与充分性

*   **主要对比实验**：在三个数据集（VFHQ、HDTF、RareFace-50）上，与3个基线/对比方法进行定量（LPIPS和ACD）和定性（视觉质量）评估，实验全面。
*   **消融研究**：进行了充分的消融实验以验证模块设计的有效性：
    *   对比了“LoRA + 高斯噪声”、“LoRA + 可学习嵌入”、“LoRA + 高斯噪声顶点嵌入”等变体，证明了3D学习特征空间设计的优越性。
    *   消融了损失函数 `L_feat` 和 `L_reg`，以及正则化权重 `λ_reg`，验证了其必要性。
    *   研究了不同适配视频长度（4秒、2秒、1秒）对性能的影响。
*   **通用性验证**：将寄存器模块与另一种参数高效微调方法DoRA结合，验证了其泛化能力。
*   **用户研究**：进行了主观用户调研，结果显示参与者在身份保持（78.2%）和视觉质量（89.9%）上均更偏好本文方法。
*   **总体评价**：实验设计严谨，对比公平，消融实验充分，从定量、定性和主观评价等多个维度验证了方法的有效性和模块中各部分设计的合理性。

### 6. 论文的主要结论与发现

*   **标准LoRA不足以捕获高频身份细节**，而本文提出的“寄存器模块”能有效增强LoRA，实现对特定身份高频特征的精准捕获。
*   核心创新在于将2D图像“寄存器”的概念成功扩展至**3D面部特征空间**，通过学习一个可复用面部细节的3D特征表示，为适配过程提供了更强的学习信号。
*   该方法**参数高效、推理无损**，在适配阶段仅增加少量参数（约占总参数11%），且在推理时因模块被移除，不增加任何额外开销。
*   在多个数据集上，该方法均能**显著优于**标准LoRA和基于元学习的方法，实现了更优的视觉质量和身份保真度。

### 7. 优点

*   **方法新颖**：将ViT中“寄存器”存储全局信息的思想巧妙地拓展到3D头部头像生成领域，用于存储和复用特定身份的面部细节，构思独特。
*   **性能卓越且高效**：在仅增加少量训练参数和不影响推理速度的前提下，显著提升了通用头像模型的个性化能力，特别是在高频细节保留方面。
*   **实验设计严谨**：
    *   自行构建并提出了**RareFace-50数据集**，专门解决现有数据集在身份细节多样性上的不足，具有重要的社区贡献。
    *   设计了**针对性评估**，如在高频细节区域计算LPIPS，以及适配不同时长视频的消融，增强了结论的说服力。
    *   进行了全面的定量、定性、消融及用户研究，证据链条完整。

### 8. 不足与局限

*   **极端视角表现欠佳**：论文指出，对于在适配视频中极少或从未出现的极端侧脸或背面视角，方法可能产生次优结果。
*   **对3DMM拟合的依赖**：方法流程依赖于视频的3DMM跟踪来获取姿态和网格信息，若跟踪精度不足（如面对极度夸张表情），其误差会传递至最终生成的头像，影响效果。
*   **光照与服饰建模缺失**：该方法沿用了光照无关的建模方式，会将源图像的光影“烘焙”进头像纹理。同时，它不专门处理服饰细节。
*   **应用风险**：如同其他高保真生成技术，该技术存在被滥用于制作深度伪造（Deepfakes）的风险，需要相应的检测技术和使用许可来规避。

（完）
