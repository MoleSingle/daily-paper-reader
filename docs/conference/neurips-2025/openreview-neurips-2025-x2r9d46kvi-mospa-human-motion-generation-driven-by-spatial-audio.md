---
title: "🎧MOSPA: Human Motion Generation Driven by Spatial Audio"
title_zh: "MOSPA: 空间音频驱动的人体运动生成"
authors: "Shuyang Xu, Zhiyang Dou, Mingyi Shi, Liang Pan, Leo Ho, Jingbo Wang, Yuan Liu, Cheng Lin, Yuexin Ma, Wenping Wang, Taku Komura"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=X2r9D46kvI"
tags: ["query:talking-head"]
score: 4.0
evidence: 空间音频驱动人体运动数据集用于数字人动画
tldr: 现有音频驱动运动生成多基于语音或音乐，忽略空间音频特征。本文构建首个空间音频驱动人体运动数据集SAM，包含多样空间音频与高质量运动数据，并提出对应生成方法。实验显示该方法能利用空间信息生成更自然逼真的人体动作，为数字人动画提供了新基准和数据支撑。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 770, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1268, \"height\": 159, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1298, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1246, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1257, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1257, \"height\": 189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 626, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 782, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 204, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 823, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1338, \"height\": 1212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 657, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1165, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1343, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1209, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1350, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 954, \"height\": 227, \"label\": \"Table\"}]"
motivation: 缺少考虑空间音频特征的人体运动数据集与模型，制约虚拟人真实感响应。
method: 构建SAM数据集并设计音频驱动人体运动生成网络，融合空间音频编码。
result: 生成的运动在真实感和多样性上优于现有音频驱动方法。
conclusion: 空间音频驱动运动生成开启了数字人动画新方向，并贡献了基准数据集。
---

## Abstract
Enabling virtual humans to dynamically and realistically respond to diverse auditory stimuli remains a key challenge in character animation, demanding the integration of perceptual modeling and motion synthesis. Despite its significance, this task remains largely unexplored. Most previous works have primarily focused on mapping modalities like speech, audio, and music to generate human motion. As of yet, these models typically overlook the impact of spatial features encoded in spatial audio signals on human motion. To bridge this gap and enable high-quality modeling of human movements in response to spatial audio, we introduce the first comprehensive "Spatial Audio-Driven Human Motion" (SAM) dataset, which contains diverse and high-quality spatial audio and motion data. For benchmarking, we develop a simple yet effective diffusion-based generative framework for human "MOtion generation driven by SPatial Audio," termed MOSPA, which faithfully captures the relationship between body motion and spatial audio through an effective fusion mechanism. Once trained, MOSPA can generate diverse realistic human motions conditioned on varying spatial audio inputs. We perform a thorough investigation of the proposed dataset and conduct extensive experiments for benchmarking, where our method achieves state-of-the-art performance on this task. Our code and model are publicly available at https://github.com/xsy27/Mospa-Acoustic-driven-Motion-Generation.git

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
本论文《MOSPA: 基于空间音频的人体运动生成》聚焦于一个尚未被充分探索的虚拟人动画难题：**如何让虚拟角色对包含空间方位信息的环境声音（如枪声、虫鸣从特定方向传来）做出动态、逼真的物理反应**。
*   **研究背景**：现有音频驱动的运动生成工作主要集中在**音乐**（Music-to-Motion）和**语音**（Speech-to-Motion）上，它们处理的是纯语义/节律信息，完全忽略了**空间音频**中编码的方向、距离和强度等空间特征对人体运动的关键影响。
*   **研究动机**：让虚拟人在听到左侧爆炸时本能向右闪避，听到后方喊叫时转身逃跑，是高沉浸感虚拟现实、人机交互等应用的核心需求。
*   **整体贡献**：本文不仅定义了“空间音频驱动运动生成”这一新任务，还构建了首个大规模基准数据集**SAM**，并提出了专门的生成框架**MOSPA**，填补了这一领域的数据和方法空白。

### 2. 论文提出的方法论
本文提出了一个名为 **MOSPA** 的扩散概率模型，其核心思想是通过有效融合**空间音频特征**、**声源位置**和**运动风格**来生成精确的人体动作。

*   **音频特征提取**：
    *   使用 `librosa` 提取双耳音频的**梅尔频率倒谱系数 (MFCC)**、**Tempogram**、**RMS能量**等特征。
    *   通过对双耳特征进行拼接，形成维度为2272的联合音频向量 **a**，以同时捕捉时间动态、空间特性和强度变化。

*   **运动表征**：
    *   采用 SMPL-X 模型（去掉手指关节）的25个体关节。
    *   运动向量 **x** 由**关节全局位置**、**局部6D旋转**和**关节速度**拼接而成，总维度为300，兼顾精确的姿态和动态变化。

*   **生成框架**：
    *   **扩散过程**：遵循标准的马尔可夫链加噪公式 \( q(x_t|x_{t-1}) = \mathcal{N}(\sqrt{\alpha_t}x_{t-1}, (1-\alpha_t)I) \)。
    *   **反向去噪**：采用一个**纯编码器Transformer**，直接预测干净样本 \( \hat{x}_0 \)。其输入为噪声运动向量 \( x_t \)、时间步 \( t \)、音频特征 \( a \)、声源位置 \( s \) 和运动类型 \( g \) 拼接而成的token序列。
    *   **损失函数**：结合了预测运动与真实运动的**均方误差 (MSE)**、逐帧变化率平滑损失、**几何损失**（前向运动学FK的位置和速度损失）、**脚部接触损失**、轨迹及旋转特定损失，以多维度约束生成质量。

### 3. 实验设计
*   **数据集**：
    *   **SAM 数据集**：自建数据集，包含超过 **9小时**（34K+秒）的3D人体运动及对应的**双耳空间音频**。
    *   **覆盖度**：涵盖27种常见日常空间音频场景（如枪声、虫鸣、电话铃声），超过70个音频片段，20种/49种反应类型（包含运动风格），由12名动捕演员录制。
    *   **划分**：按 **8:1:1** 划分训练集、验证集和测试集。

*   **Benchmark与基线方法**：
    *   将该任务评估为一项生成任务，评价指标包括：
        *   **R-Precision (Top-1/2/3)**：评估生成动作与音频条件的一致性。
        *   **FID**：衡量生成动作与真实动作分布的距离（越低越好）。
        *   **Diversity & APD**：衡量生成动作的多样性。
    *   对比了四种主流的音频/音乐驱动运动生成方法：**EDGE**、**POPDG**、**LODGE** 和 **Bailando**，将它们原有的音频输入替换为本文的空间音频特征。

### 4. 资源与算力
*   **训练硬件**：单个 **Nvidia RTX 4090 GPU**。
*   **训练时间**：在 batch size 为 128 的设置下，整个训练过程耗时约 **18小时** (6,000个epochs)。

### 5. 实验数量与充分性
论文设计了较为充分的定量和定性实验来验证模型有效性：
1.  **主要基线对比**：与4个现有方法在全部4个指标上进行对比，证明了MOSPA的SOTA性能。
2.  **消融实验**：对扩散模型的**潜在维度 (512 vs. 256)**、**注意力头数 (8 vs. 4)**、**扩散步数 (1000 vs. 100 vs. 4)**、**运动风格遮蔽**以及**关键音频特征 (MFCC/Tempogram)** 的使用进行了6组以上的消融实验。
3.  **用户调研**：25名参与者从意图对齐、运动质量、真值相似度三个维度对生成结果进行盲评，提供了主观评估证据。
4.  **鲁棒性测试**：展示了模型在**分布外音频配置**上的生成效果，验证了泛化能力。
5.  **跨领域应用验证**：展示了生成运动用于驱动物理仿真人形机器人的能力。

### 6. 论文的主要结论与发现
*   **新任务定义**：成功定义并探索了空间音频驱动运动生成这一全新任务。
*   **数据贡献**：贡献了首个大规模、高质量的空间音频-运动配对数据集SAM。
*   **方法有效性**：MOSPA框架通过融合MFCC、Tempogram、RMS等多种空间音频特征，能有效捕捉声音的语义、空间和强度变化，生成高质量动作。
*   **性能领先**：MOSPA在多个定量指标、定性展示和用户研究中均大幅超越现有基线，在FID上达到7.981，显著低于其他方法，证明了空间感知对运动生成的重要性。

### 7. 优点
*   **问题新颖性**：创新性地提出了空间音频条件控制下的运动生成任务，拓宽了现有研究视野。
*   **数据集价值**：SAM数据集的场景/反应多样性、包含声源位置标注、使用双耳录音等设计，为该领域后续研究提供了扎实基准。
*   **基线设计合理**：MOSPA简单有效的扩散-Transformer框架以及专门设计的损失函数，提供了强大的任务基线。
*   **多维度验证**：实验不仅包含数值对比，还结合了用户主观评估和机器人仿真，增强了说服力。

### 8. 不足与局限
*   **物理正确性**：生成运动缺乏物理约束，可能违反力学规律（如脚部滑动）。
*   **身体建模不完整**：仅驱动身体动作，忽略了SMPL-X支持的手部动作和面部表情，无法生成全身体验。
*   **缺乏场景感知**：模型未考虑环境几何结构，无法生成与场景物体交互（如躲避障碍物）的运动。
*   **动捕环境局限**：数据采集在特定室内环境，模型可能对极端的真实世界声学环境泛化受限。

（完）
