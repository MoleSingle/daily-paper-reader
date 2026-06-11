---
title: "MimicMotion: High-Quality Human Motion Video Generation with Confidence-aware Pose Guidance"
title_zh: MimicMotion：基于置信度感知姿态引导的高质量人体运动视频生成
authors: "Yuang Zhang, Jiaxi Gu, Li-Wen Wang, Han Wang, JunqiCheng, Yuefeng Zhu, FangYuan Zou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0YXxh8WALf"
tags: ["query:talking-head"]
score: 6.0
evidence: 利用姿态引导生成高质量人体运动视频，可用于数字人化身创建
tldr: MimicMotion针对视频生成在可控性、长度和细节质量方面的挑战，提出了一种基于置信度感知姿态引导的高质量人体运动视频生成框架。该框架通过姿态置信度加权的区域损失放大和渐进式潜在融合策略，生成长而平滑的视频。实验证明该方法能有效生成任意长度的高质量人体视频，为数字人化身和视频合成提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 660, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 863, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1241, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1732, \"height\": 1802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0yxxh8walf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1728, \"height\": 1790, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0yxxh8walf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 847, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0yxxh8walf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 848, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0yxxh8walf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 837, \"height\": 749, \"label\": \"Table\"}]"
motivation: 现有视频生成方法在可控性、生成视频长度和细节质量上仍存在不足。
method: 提出置信度感知姿态引导、基于姿态置信度的区域损失放大和渐进式潜在融合策略。
result: 实验证明可生成任意长度的高质量平滑人体运动视频。
conclusion: 该方法显著提升了人体运动视频的生成质量与可控性。
---

## Abstract
In recent years, while generative AI has advanced significantly in image generation, video generation continues to face challenges in controllability, length, and detail quality, which hinder its application. We present MimicMotion, a framework for generating high-quality human videos of arbitrary length using motion guidance. Our approach has several highlights. Firstly, we introduce confidence-aware pose guidance that ensures high frame quality and temporal smoothness. Secondly, we introduce regional loss amplification based on pose confidence, which reduces image distortion in key regions. Lastly, we propose a progressive latent fusion strategy to generate long and smooth videos. Experiments demonstrate the effectiveness of our approach in producing high-quality human motion videos. Videos and comparisons are available at [https://tencent.github.io/MimicMotion](https://tencent.github.io/MimicMotion).

---

## 论文详细总结（自动生成）

## 1. 论文核心问题与整体含义
该论文聚焦于**姿态引导的人体运动视频生成**，即在给定单张参考图像和一段目标姿态序列的情况下，生成一段高画质、长时序、且与参考身份一致的人体视频。当前视频生成虽然在图像生成的基础上有所发展，但仍面临**可控性不足、生成视频长度受限、以及细节区域（尤其是手部）易畸变、时序不平滑**等关键挑战。此外，现有方法在训练和推理中常因姿态估计不准（如自遮挡、运动模糊导致的关键点错误）而引入噪声，进而造成生成质量下降。因此，本文旨在提出一种能够有效处理姿态不确定性、提升生成质量、并支持生成任意长度高质量人体运动视频的框架。

## 2. 方法论
### 2.1 总体框架
MimicMotion 以预训练的 Stable Video Diffusion（SVD）为基础，将其扩展为可接受**参考图像**和**姿态序列**条件的视频扩散模型。主要模块包括：
- 一个冻结的 VAE 编码器/解码器（含时序层），用于将视频帧压至潜空间并重建。
- 一个可训练的 PoseNet（由若干卷积层构成），从姿态序列提取特征，并将其以逐元素相加的方式注入 U-Net 的第一层卷积输出。
- 参考图像经 CLIP 图像编码器提取特征，通过交叉注意力注入 U-Net；同时其 VAE 潜表示沿时间复制并与输入视频帧潜特征在通道维度拼接。

### 2.2 置信度感知姿态引导 (Confidence-aware Pose Guidance)
针对姿态估计的不准确性，论文提出：
- **利用姿态估计模型（DWPose）输出的每个关键点的置信度分数**，将其乘以关键点及肢干的绘制颜色，使置信度高的关键点更显眼，低置信度的则减轻影响，不仅过滤噪声，还将不确定性信息传递给模型。
- 在训练阶段，基于关键点置信度阈值生成**手部区域的置信度掩码**。仅对关键点置信度均高于阈值的手部区域进行**损失权重放大**（手部区域损失权重设为10，其余为1），从而迫使模型重点关注高质量手部区域的学习，有效减轻手部畸变。

### 2.3 渐进式潜在融合 (Progressive Latent Fusion) 生成长视频
为生成任意长度视频，将完整姿态序列切分成固定帧数 _N_ 的片段，相邻片段间有一定重叠帧数 _C_。在每个去噪时间步 _t_：
1. 各片段独立进行反向扩散预测。
2. 对重叠区域的潜特征，按照帧在片段中的相对位置进行**加权融合**：越靠近片段内部，其融合权重越高；越靠近边界，则平滑过渡。预定义融合尺度 _λ_fusion = 1/(C+1)。通过这种位置相关的渐进权重，避免了简单平均带来的时序不连续和闪烁。

最后，将所有片段的非重叠部分拼接，经 VAE 时序解码器重建出长视频。

## 3. 实验设计
### 3.1 数据集与场景
- **训练集**：从互联网收集的 4,436 个舞蹈视频，平均时长 20.1 秒，无特殊人工标注。
- **测试集**：TikTok 数据集中序列 335–340 用于定量/定性评估，并进行了中央裁剪以保证各方法输入比例公平。
- **额外测试**：展示了卡通角色和动物视频的跨域生成能力（零样本泛化）。

### 3.2 基准与对比方法
- 对比了同期SOTA方法：MagicAnimate、MagicPose、Moore-AnimateAnyone、MuseV。
- 采用视频级别指标 FID‑VID、FVD，以及帧级别指标 PSNR、SSIM。
- 开展用户调研（36人，每人评估6组视频对），主观评价图像质量和时序平滑度。

### 3.3 消融实验
通过去除手部区域增强、置信度感知引导、渐进式潜在融合，分别验证各模块贡献，指标为 FID‑VID、FVD、SSIM、PSNR。

## 4. 资源与算力
- 训练使用 **8 块 NVIDIA A100 GPU**，batch size 为 8，每段视频 16 帧。
- 共训练 **20 个 epoch**，学习率 10^-5，带 500 次迭代的线性预热。
- 预训练模型 SVD 的参数作为初始化，PoseNet 从头训练，U-Net 和 PoseNet 的所有参数可训。论文未明确给出单次训练的总时长或能耗的具体数值。

## 5. 实验数量与充分性
实验设计较为充分，包括：
- **定量对比**：与 4 种基线方法在 TikTok 测试片段上完整评估 4 项指标。
- **定性对比**：展示生成帧的细节优势（如手部质量、姿态跟随）和时序差异（帧差图）。
- **用户调研**：收集 36 人偏好，提供主观佐证。
- **消融实验**：逐项剥离三个关键模块，分析对全部指标的影响。
- **案例分析**：通过可视化展示置信度引导对错误姿态的纠正、手部增强效果、以及渐进式融合对片段边界平滑性的改善。
- **跨域测试**：另在卡通、动物视频上展示泛化能力。
整体评估客观、公平，对比时采用统一的中央裁剪处理，消融实验控制变量清晰。但用户调研样本量（36人）相对较小，且未在更多样化数据集上测试。

## 6. 主要结论与发现
- 置信度感知姿态引导能有效缓解姿态估计噪声的负面影响，使生成结果在保持时序平滑的同时，更准确地跟随姿态，并减少手部及肢体畸变。
- 手部区域损失增强显著改善了扩散模型常见的手部生成质量问题。
- 渐进式潜在融合解决了长视频生成中片段拼接处的闪烁和突变问题，生成了任意长度且平滑的视频。
- 整体方法在 FID‑VID、FVD、SSIM、PSNR 及用户偏好上全面超越已有 SOTA 方法。

## 7. 优点
- **创新性地将姿态置信度引入引导与损失设计**，利用不确定性信息而非简单过滤，使模型对姿态噪声更加鲁棒。
- **手部增强策略贴近人类感知偏好**，通过加权损失有效减少了模型对手部生成的偏见。
- **渐进式融合机制设计简单有效**，无需重新训练即可提升长视频拼接处的平滑度。
- 模型具有较强的泛化能力，能零样本生成卡通和动物运动视频。
- 实验对比全面，结合定量、定性、用户调研及消融分析，论证充分。

## 8. 不足与局限
- 训练数据仅为特定风格的舞蹈视频，对日常动作或复杂场景的覆盖有限，可能影响泛化鲁棒性。
- 无训练总时长或计算开销的具体报告，难以直接评估实际训练成本。
- 用户调研样本量偏小（36人），可能不足以完全反映主观偏好。
- 手部区域增强依赖于高置信度关键点，在极端遮挡或严重模糊场景下可能仍存在失真。
- 未探讨生成视频的内容一致性问题（如服饰、背景在长时间内的保持），以及可能被滥用于深度伪造的伦理风险虽提及但未提供具体缓解技术。
- 对比方法中未涉及一些基于3D人体先验的密集引导方法（如SMPL），未能展示密集引导与稀疏姿态引导的优劣权衡。

（完）
