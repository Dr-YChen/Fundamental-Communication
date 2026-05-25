# OTFS讲义补充设计规范

> 为研究生OTFS学习补充核心内容

## 1. 概述

### 1.1 目标

为已有通信基础（完成0-communication-basics/）的研究生补充OTFS深入学习所需的**数学基础、信道编码、信道估计、检测理论、同步技术**。

### 1.2 设计原则

- **理论与实践平衡**：既有公式推导也有Python实现
- **按学科分类**：内容组织清晰，便于深入学习
- **可独立学习**：每个notebook可单独使用
- **与现有内容衔接**：补充内容最终服务于OTFS系统

### 1.3 目标受众

- 完成0-communication-basics/的研究生
- 具备基础数学（微积分、线性代数、概率统计）
- 需要OTFS深入学习的研究者

---

## 2. 内容结构

### 2.1 总体目录

```
7-matrix-theory/                    矩阵论基础
├── 1-matrix-basics.ipynb          矩阵运算、特征值分解、SVD
├── 2-toeplitz-circulant.ipynb     Toeplitz矩阵与循环矩阵
└── 3-kronecker-khatri-rao.ipynb  Kronecker积与Khatri-Rao积

8-channel-coding/                   信道编码理论
├── 1-capacity-basics.ipynb        Shannon容量与信道编码定理
├── 2-ldpc.ipynb                   LDPC码（构造、译码、密度演化）
├── 3-polar.ipynb                  Polar码（构造、SC/SCL译码）
└── 4-turbo-bicm.ipynb             Turbo码与BICM编码调制

9-channel-estimation/               信道估计
├── 1-pilot-design.ipynb           导频设计原则
├── 2-ls-mmse.ipynb               LS与MMSE信道估计
├── 3-sparse-estimation.ipynb      稀疏信道估计（OMP、CoSaMP）
└── 4-otfs-channel-estimation.ipynb OTFS专用信道估计

10-detection-theory/               检测理论
├── 1-ml-map.ipynb                 ML与MAP检测
├── 2-linear-detection.ipynb       ZF、MMSE线性检测
├── 3-sic-detection.ipynb          SIC检测（V-BLAST）
└── 4-message-passing.ipynb         消息传递算法（BP、AMP、GAMP）

11-synchronization/                同步技术
├── 1-cfo-sync.ipynb               载波频率同步
├── 2-sto-sync.ipynb               符号定时同步
└── 3-phase-noise.ipynb            相位噪声补偿

12-advanced-projects/              进阶项目
├── 1-mimo-otfs.ipynb              MIMO-OTFS系统设计
└── 2-end-to-end-otfs.ipynb        完整OTFS收发机项目
```

**总计：20个notebook**

---

## 3. 各模块详细说明

### 3.1 模块7：矩阵论基础（3个notebook）

#### Notebook 7-1: matrix-basics.ipynb

| 内容 | 说明 |
|------|------|
| 矩阵运算 | 加减乘除、转置、共轭、迹 |
| 范数 | Frobenius范数、谱范数、向量范数 |
| 特征值分解 | 特征值、特征向量、对角化 |
| SVD奇异值分解 | SVD与矩阵性质、最佳近似 |
| 矩阵求逆 | 伪逆Moore-Penrose、Woodbury恒等式 |

**Python实验**：矩阵分解可视化、SVD图像压缩

---

#### Notebook 7-2: toeplitz-circulant.ipynb

| 内容 | 说明 |
|------|------|
| Toeplitz矩阵 | 定义、多项式表示、与线性时不变系统关系 |
| 循环矩阵 | 定义、与FFT的关系、循环卷积 |
| 循环Toeplitz | OTFS信道矩阵结构 |
| 快速算法 | 利用FFT加速矩阵-向量乘法 |

**Python实验**：Toeplitz矩阵构造、循环卷积FFT实现

---

#### Notebook 7-3: kronecker-khatri-rao.ipynb

| 内容 | 说明 |
|------|------|
| Kronecker积 | 定义、性质、矩阵运算中的角色 |
| Khatri-Rao积 | 列Kronecker积、空间相关矩阵 |
| Hadamard积 | element-wise乘积的性质 |
| 应用 | MIMO系统模型、 Kronecker积信道模型 |

**Python实验**：MIMO信道Kronecker模型

---

### 3.2 模块8：信道编码理论（4个notebook）

#### Notebook 8-1: capacity-basics.ipynb

| 内容 | 说明 |
|------|------|
| Shannon容量 | 信道容量定义、C=Elog(1+SNR) |
| 信道编码定理 | 可靠传输的条件、渐近容量 |
| 加性高斯信道 | AWGN信道容量推导 |
| 离散信道容量 | BSC、删除信道的容量 |
| 编码增益 | 编码增益 vs 频谱效率 |

**Python实验**：容量曲线绘制、SNR vs 容量关系

---

#### Notebook 8-2: ldpc.ipynb

| 内容 | 说明 |
|------|------|
| LDPC码基础 | Tanner图、校验矩阵构造 |
| 规则LDPC vs 不规则LDPC | 度分布设计 |
| 译码算法 | Sum-Product（BP）算法、置信传播 |
| 密度演化 | 收敛性分析、阈值计算 |
| 5G NR LDPC | 5G标准中的LDPC结构 |

**Python实验**：LDPC编码/译码实现、BP算法可视化

---

#### Notebook 8-3: polar.ipynb

| 内容 | 说明 |
|------|------|
| 信道极化 | 极化现象、 Bhattacharyya参数 |
| 极化码构造 | 巴氏参数构造、密度进化构造 |
| SC译码 | 串行抵消译码 |
| SCL译码 | SCL-CRC联合译码、性能提升 |
| 5G NR Polar | 5G标准中的Polar码结构 |

**Python实验**：Polar码构造与译码、AWGN信道性能

---

#### Notebook 8-4: turbo-bicm.ipynb

| 内容 | 说明 |
|------|------|
| Turbo码 | 并行级联卷积码、PCCC结构 |
| Turbo译码 | MAP算法、迭代译码原理 |
| BICM | 比特交织编码调制原理 |
| 编码调制联合设计 | BICM-ID（迭代检测译码） |
| EXIT图 | 译码收敛性分析 |

**Python实验**：Turbo迭代译码可视化、BICM容量分析

---

### 3.3 模块9：信道估计（4个notebook）

#### Notebook 9-1: pilot-design.ipynb

| 内容 | 说明 |
|------|------|
| 导频类型 | 块状导频、梳状导频、离散导频 |
| 导频图案 | 时频资源映射、导频密度设计 |
| 正交性 | 导频与数据的正交设计 |
| 信道估计质量 | 均方误差、MSE与CRB |
| 导频污染 | 多小区场景下的导频污染问题 |

**Python实验**：不同导频图案对比、MSE性能比较

---

#### Notebook 9-2: ls-mmse.ipynb

| 内容 | 说明 |
|------|------|
| LS估计 | 最小二乘估计原理、实现 |
| MMSE估计 | 最小均方误差估计、贝叶斯框架 |
| 时变信道估计 | 滑动窗口估计、滤波 |
| 低复杂度方法 | SVD-MMSE、时域逼近 |
| OTFS中的估计 | 延迟-多普勒域导频放置 |

**Python实验**：不同估计算法性能对比、OTFS信道估计

---

#### Notebook 9-3: sparse-estimation.ipynb

| 内容 | 说明 |
|------|------|
| 压缩感知基础 | 稀疏性、RIP条件、恢复保证 |
| OMP算法 | 正交匹配追踪原理与实现 |
| CoSaMP算法 | 压缩采样匹配追踪 |
| 稀疏度自适应 | SAMP算法 |
| 分布式压缩感知 | 多观测向量情形 |

**Python实验**：稀疏信道估计实现、不同算法对比

---

#### Notebook 9-4: otfs-channel-estimation.ipynb

| 内容 | 说明 |
|------|------|
| OTFS信道特点 | 延迟-多普勒域稀疏性 |
| OTFS导频设计 | 分散导频vs集中导频 |
| 信道估计策略 | 块状估计、逐符号估计 |
| 时变信道处理 | Doppler扩展的信道跟踪 |
| 克拉美-罗界 | 信道估计精度极限 |

**Python实验**：OTFS信道估计完整流程、导频优化

---

### 3.4 模块10：检测理论（4个notebook）

#### Notebook 10-1: ml-map.ipynb

| 内容 | 说明 |
|------|------|
| 检测基本问题 | 假设检验、检测器设计准则 |
| ML检测 | 最大似然检测原理 |
| MAP检测 | 最大后验概率检测 |
| 错误概率 | 成对错误概率、联合边界 |
| 最优检测复杂度 | 穷举搜索的复杂度问题 |

**Python实验**：ML/MAP检测实现、错误概率曲线

---

#### Notebook 10-2: linear-detection.ipynb

| 内容 | 说明 |
|------|------|
| ZF检测 | 迫零检测原理与实现 |
| MMSE检测 | 最小均方误差检测 |
| 正则化MMSE | 噪声增强与正则化参数选择 |
| 近似MMSE | 低复杂度近似方法 |
| 性能分析 | SNR、MIMO信道条件数的影响 |

**Python实验**：ZF/MMSE检测实现、性能对比

---

#### Notebook 10-3: sic-detection.ipynb

| 内容 | 说明 |
|------|------|
| 串行干扰抵消 | SIC原理、逐次抵消 |
| V-BLAST结构 | 垂直分层空时码 |
| 检测顺序优化 | 基于SNR、基于信道条件数的排序 |
| 复杂度分析 | 检测延迟、硬件实现考虑 |
| 与线性检测结合 | SIC前预处理、混合检测 |

**Python实验**：V-BLAST检测实现、不同排序策略对比

---

#### Notebook 10-4: message-passing.ipynb

| 内容 | 说明 |
|------|------|
| 因子图基础 | 和积算法、变量节点、因子节点 |
| BP算法 | 置信传播原理与实现 |
| AMP算法 | 近似消息传递、状态演化 |
| GAMP算法 | 高斯AMP、扩展到一般线性模型 |
| OTFS中的应用 | 稀疏信道估计+检测联合优化 |

**Python实验**：MP算法实现、AMP状态演化可视化

---

### 3.5 模块11：同步技术（3个notebook）

#### Notebook 11-1: cfo-sync.ipynb

| 内容 | 说明 |
|------|------|
| 载波频率偏移 | CFO来源、对系统的影响 |
| CFO估计 | 基于导频、基于数据辅助 |
| 分数频偏估计 | 小数频偏估计原理 |
| 整数频偏估计 | 大范围搜索方法 |
| CFO补偿 | 频域/时域补偿方法 |

**Python实验**：CFO估计仿真、性能分析

---

#### Notebook 11-2: sto-sync.ipynb

| 内容 | 说明 |
|------|------|
| 符号定时偏移 | STO来源、对采样点的影响 |
| 早迟门检测 | Early-Late Gate原理 |
| Gardner算法 | 定时误差检测器 |
| 插值滤波器 | 分数延迟滤波、拉格朗日插值 |
| 定时恢复环路 | PLL、DPLL结构 |

**Python实验**：定时同步环路仿真、眼图分析

---

#### Notebook 11-3: phase-noise.ipynb

| 内容 | 说明 |
|------|------|
| 相位噪声来源 | 振荡器相位噪声特性 |
| 相位噪声模型 | Wiener过程、克拉美-罗界 |
| 对OFDM/OTFS影响 | ICI、 constellation rotation |
| 相位噪声补偿 | DFT域补偿、判决辅助 |
| 相位追踪 | 导频辅助相位估计 |

**Python实验**：相位噪声对系统影响、补偿方法对比

---

### 3.6 模块12：进阶项目（2个notebook）

#### Notebook 12-1: mimo-otfs.ipynb

| 内容 | 说明 |
|------|------|
| MIMO-OTFS系统模型 | 延迟-多普勒域MIMO模型 |
| 发送预编码 | 线性预编码、TH预编码 |
| 接收检测 | MIMO-OTFS联合检测 |
| 信道估计 | MIMO导频设计 |
| 性能分析 | 频谱效率、误码率 |

**Python实验**：MIMO-OTFS完整链路仿真

---

#### Notebook 12-2: end-to-end-otfs.ipynb

| 内容 | 说明 |
|------|------|
| 完整系统框架 | 发送机、信道、接收机全链路 |
| 参数配置 | 子载波数、符号数、CP长度 |
| LDPC+OTFS | 编码调制一体化设计 |
| 同步+检测 | 联合同步与检测算法 |
| 性能基准 | 与OFDM系统对比 |

**Python实验**：完整OTFS系统仿真、性能评估

---

## 4. 内容风格规范

### 4.1 每个Notebook结构

```
1. 学习目标（3-4个要点）
      ↓
2. 概念讲解（理论推导 + 物理意义）
      ↓
3. Python演示（代码实现 + 结果分析）
      ↓
4. 原理解析（深入理论）
      ↓
5. 思考题与扩展
```

### 4.2 公式与代码比例

- **理论部分**：40%（公式推导为主）
- **代码部分**：40%（可运行仿真）
- **分析部分**：20%（结果分析与讨论）

### 4.3 与现有内容的衔接

| 补充内容 | 衔接现有内容 |
|---------|-------------|
| 矩阵论基础 | Zak变换、OTFS信道矩阵 |
| 信道编码 | OTFS系统设计 |
| 信道估计 | delay-doppler.ipynb |
| 检测理论 | otfs-modulation.ipynb |
| 同步技术 | ofdm-principles.ipynb |

---

## 5. 学习路径建议

```
研一新生学习顺序：

第一学期（基础）：
  7-matrix-theory/ → 矩阵论基础
  8-channel-coding/ → 信道编码理论

第二学期（核心）：
  9-channel-estimation/ → 信道估计
  10-detection-theory/ → 检测理论
  11-synchronization/ → 同步技术

第三学期（应用）：
  12-advanced-projects/ → 进阶项目
  → 开始OTFS研究
```

---

## 6. 成功标准

1. **完整性**：补充内容覆盖OTFS深入学习的主要方面
2. **可读性**：理论与代码比例适当，研究生可自学
3. **可运行**：所有代码经过验证可独立运行
4. **衔接性**：与现有notebook形成完整学习路径