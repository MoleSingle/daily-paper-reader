---
title: "HumanCrafter: Synergizing Generalizable Human Reconstruction and Semantic 3D Segmentation"
title_zh: "HumanCrafter: 协同泛化人体重建与语义三维分割"
authors: "Panwang Pan, Tingting Shen, Chenxin Li, Yunlong Lin, Kairun Wen, Jingjing Zhao, Yixuan Yuan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=EakfENFVPT"
tags: ["query:talking-head"]
score: 7.0
evidence: 单幅图像三维人体重建用于数字化身创建
tldr: 现有三维人体重建方法在特定任务（如人体分割）应用中受限，且标注数据集稀缺。本文提出HumanCrafter统一框架，以前馈方式从单张图像联合建模外观与人体部位语义，集成人体几何先验和自监督语义先验。为解决数据不足，开发交互式标注流程生成高质量数据-标签对。实验表明多任务协同提升了重建与分割性能，为创建数字人体化身提供了高效基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1393, \"height\": 812, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1277, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1286, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1199, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1195, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1220, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 582, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1371, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 711, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 710, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 835, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 958, \"height\": 163, \"label\": \"Table\"}]"
motivation: 现有三维人体重建高保真但局限于特定任务，缺乏联合建模外观与语义的能力。
method: 提出统一框架，结合几何先验重建与自监督语义分割，通过像素对齐实现跨任务协同。
result: 联合训练提高了重建精度与部位分割质量，并开源了新的标注数据集。
conclusion: 多任务三维人体建模方案有效推进了数字人化身创建技术。
---

## Abstract
Recent advances in generative models have achieved high-fidelity in 3D human reconstruction, yet their utility for specific tasks (e.g., human 3D segmentation) remains constrained. We propose HumanCrafter, a unified framework that enables the joint modeling of appearance and human-part semantics from a single image in a feed-forward manner. Specifically, we integrate human geometric priors in the reconstruction stage and self-supervised semantic priors in the segmentation stage. To address labeled 3D human datasets scarcity, we further develop an interactive annotation procedure for generating high-quality data-label pairs. Our pixel-aligned aggregation enables cross-task synergy, while the multi-task objective simultaneously optimizes texture modeling fidelity and semantic consistency. Extensive experiments demonstrate that HumanCrafter surpasses existing state-of-the-art methods in both 3D human-part segmentation and 3D human reconstruction **from a single image**.

---

## 论文详细总结（自动生成）

## 1. 论文核心问题与研究背景

- 现有 3D 人体重建方法虽已达到高保真外观重建，但通常仅关注纹理与几何，难以直接支持下游任务（如人体部位语义分割），且重建与分割任务往往割裂进行。
- 多阶段流水线（先重建再执行 2D 分割或提取语义）存在三维不一致、计算开销大、工程复杂等问题。
- 三维人体语义标注数据稀缺，进一步制约了联合学习的发展。
- **核心目标**：提出统一的前馈式框架 `HumanCrafter`，从单张图像同时实现高质量 **3D 人体重建**与**人体部位语义分割**，并使两项任务相互促进。

## 2. 方法论

### 2.1 整体架构
- 输入单张 RGB 图像，通过一个**扩散模型（SV3D）**生成多视角潜在特征，并将 **SMPL 人体参数模型**作为几何先验，渲染侧面法线图与 Plücker 光线嵌入拼接后送入 Transformer。
- 基于像素对齐的 **3D Gaussian Splatting** 表示，将多视角特征聚合，预测每个像素对应的 3D 高斯参数（位置、颜色、不透明度、尺度、旋转等），进而通过可微光栅化渲染新视角。
- 为支持语义分割，在 3D 高斯上附加**可学习的语义特征嵌入**，形成“VersatileSplats”，通过混合渲染同时输出颜色和语义特征图。

### 2.2 关键技术细节
- **特征聚合 Transformer（Sec. 3.1）**：利用交叉视图注意力融合多视角几何与外观信息，并预测深度图与 3D 位置偏移，将 2D 特征映射到 3D 空间。
- **像素对齐聚合与语义先验（Sec. 3.2）**：冻结预训练的 DINOv2‑ViT‑small/registers 作为 2D 语义编码器，通过前一 Transformer 的注意力权重对 DINOv2 特征进行加权融合，进而解码出每个像素对应的语义 3D 高斯。该过程使得重建任务学到的几何对应关系直接指导语义特征的对齐，无需额外跨视图匹配。
- **可微渲染**：扩展 3DGS 光栅化以支持 feature 渲染，使语义特征可微分训练。
- **多任务损失函数**：综合**重建损失**（MSE + LPIPS + mask loss）、**特征蒸馏损失**（预测特征与 DINOv2 在 ground truth 新视图上特征的 cosine 相似度）以及**少量标注视点的交叉熵分割损失**进行端到端联合优化。

### 2.3 公式简洁描述
- 颜色渲染: \( c = \sum_{i=1}^N c_i \sigma_i \prod_{j=1}^{i-1} (1-\sigma_j) \)
- 特征渲染: \( \mathbf{f} = \sum_{i=1}^N \tilde{\mathbf{f}}_i \sigma_i \prod_{j=1}^{i-1} (1-\sigma_j) \)
- 总损失: \(\mathcal{L}(\Theta) = \mathbb{E}_{i\in\{1,\dots,k_v\}} \left[ \mathcal{L}_{\text{render}} + \lambda_{\text{dist}} \mathcal{L}_{\text{dist}}(\mathbf{f}_i,\hat{\mathbf{f}}_i) \right] + \lambda_{\text{seg}} \mathbb{E}_{j\in\{1,\dots,k_s\}} \left[ \mathcal{L}_{\text{CE}}(\mathbf{S}_j,\hat{\mathbf{S}}_j) \right]\)

## 3. 实验设计

### 3.1 数据集与评价指标
- **训练集**：THuman2.1（2300 扫描）、2K2K（1500 扫描）、Human MVImageNet（约 4000 身份，8000 装束）。
- **自建语义标注数据集**：从训练集中选取 500 扫描，每扫描人工标注 8 个语义分割图，利用 SAM 辅助加速。
- **测试集**：上述数据集的剩余扫描，以及由网络图像构建的 In‑the‑wild 测试集。
- **评价指标**：
  - 重建质量：PSNR、SSIM、LPIPS、多视图一致性（COLMAP 重建点数）。
  - 分割精度：mIoU、平均像素准确率（mAcc）。
  - 推理效率：重建与分割的耗时。

### 3.2 对比方法
- **单图像重建**：LGM†、GRM†、InstantMesh、LaRa、SiFU、PSHuman、Human3Diffusion。
- **人体语义分割**：LSM*（由论文在两视图输入下重新训练）、Sapiens（2D 人体分割 SOTA）。
- **组合基线**：Human3Diffusion 重建 + Sapiens 做 2D 分割，以对比统一框架下的联合效果。

## 4. 资源与算力
- 训练硬件：8 块 NVIDIA A800 GPU。
- 训练时长：约 7 天。
- 训练策略：首先 80K 迭代训练 256×256 分辨率，再 20K 迭代微调至 512×512。
- 加速技术：Flash‑Attention‑v2、梯度检查点、BF16 混合精度。
- 单次推理耗时：扩散模型生成多视图特征约 6 秒，重建阶段约 0.2 秒；整体前向时间约 6.24 秒。

## 5. 实验数量与充分性
- **主要对比实验**：
  - 表 1、2：在两个数据集上对比重建和分割，覆盖 10 余种 SOTA 方法，展示了显著优势。
  - 定性结果（图 3、4 等）：多种复杂姿态、宽松衣物、极端视角下的视觉对比。
- **消融实验**：
  - 人体几何先验的作用（有无 SMPL、使用法线/坐标/深度对比）。
  - 模型组件（Plücker 嵌入、DINOv2 vs ViT‑s、像素对齐聚合模块）。
  - 损失函数（无 LPIPS、无蒸馏损失 \(L_\text{dist}\)、无分割损失 \(L_\text{CE}\)）。
  - 微调 DINOv2 编码器的影响、双 Transformer 架构的必要性。
- 实验设计充分、消融系统，对比公平（部分基线在相同数据上重训练），能有效支撑核心结论。

## 6. 主要结论与发现
- **统一框架有效性**：HumanCrafter 首次在单次前馈推理中同时解决 3D 人体重建与部位分割，且两项任务通过像素对齐聚合和多任务损失相互受益。
- **性能大幅提升**：在重建质量（PSNR、SSIM、LPIPS）和分割精度（mIoU）上均大幅超越现有方法，同时保持实时渲染（分割 126 ms）。
- **几何先验关键**：SMPL 法线图作为条件显著提升单视图重建精度，缓解深度歧义。
- **语义先验与对齐**：冻结 DINOv2 并通过注意力聚合赋予 3DGS 语义，既避免了大规模标注需求，又保障了 3D 一致性。
- **应用潜力**：支持文本到 3D 人体生成、3D 一致性编辑、VR 沉浸式体验等。

## 7. 方法亮点
- **多任务统一**：在 3DGS 中嵌入语义特征，通过共享渲染管线实现联合学习，避免了常见的两阶段不一致问题。
- **高效的数据构建**：利用 SAM 辅助交互式标注，快速获得高质量 3D 语义标签，为训练分割任务奠定数据基础。
- **设计精妙的特征对齐**：利用重建 Transformer 的注意力权重直接引导语义特征的跨视图聚合，无需额外配准或特征匹配，实现真正的端到端协同。
- **推理速度快**：虽然包含扩散先验，但整体处理时间仅 6 秒左右，非常适合下游交互应用。

## 8. 不足与局限
- **依赖外部先验模型**：需使用 SV3D 扩散模型和 DINOv2，整体管线较重；扩散模型的偏见可能被传入重建结果，带来隐私或公平性风险。
- **动态场景未覆盖**：当前仅支持静态单帧输入，未扩展到动态 4D 场景（如视频）。
- **标注规模有限**：尽管开发了标注流程，但分割训练仍依赖手工标注的 500 扫描、每扫描 8 视角，若想覆盖更多类别或更精细部位，成本可能上升。
- **泛化性验证**：虽然在 In‑the‑wild 图像上展示了一些结果，但大规模开放场景下的鲁棒性尚未充分量化。
- **潜在滥用风险**：能生成高度逼真的 3D 数字人，可能被用于深度伪造或非法传播，需配套数字水印等防范措施。

（完）
