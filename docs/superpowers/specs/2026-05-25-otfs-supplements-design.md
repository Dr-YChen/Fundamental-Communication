# OTFS讲义完整结构设计规范

> 为研究生OTFS学习补充核心内容

## 1. 概述

### 1.1 目标

为已有通信基础的研究生补充OTFS深入学习所需的**数学基础、信道编码、信道估计、检测理论、同步技术**，并重组现有讲义结构。

### 1.2 设计原则

- **每个章节≤4个notebook**：保持内容精炼
- **序号连续**：无字母后缀
- **理论与实践平衡**：既有公式推导也有Python实现
- **可独立学习**：每个notebook可单独使用

---

## 2. 完整目录结构

### 第一部分：通信基础（4个章节）

| 序号 | 目录 | 主题 | Notebook数量 |
|------|------|------|-------------|
| **1** | fundamentals/ | 通信概论 | 3 |
| **2** | signals-systems/ | 信号与系统 | 4 |
| **3** | modulation-basics/ | 调制基础 | 4 |
| **4** | channels-receivers/ | 信道与接收机 | 4 |

### 第二部分：高阶内容（10个章节）

| 序号 | 目录 | 主题 | Notebook数量 |
|------|------|------|-------------|
| **5** | signal-representations/ | 信号表示 | 3 |
| **6** | channel-basics/ | 信道特性 | 2 |
| **7** | modulation/ | 调制技术 | 4 |
| **8** | mimo/ | MIMO基础 | 1 |
| **9** | matrix-coding/ | 矩阵论+信道编码 | 4 |
| **10** | estimation-detection/ | 信道估计+检测 | 4 |
| **11** | synchronization/ | 同步技术 | 3 |
| **12** | zak-transform/ | Zak变换 | 1 |
| **13** | advanced-projects/ | 进阶项目 | 4 |

---

## 3. 各章节详细内容

### 章节1：fundamentals/（3个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-communication-intro.ipynb | 通信概论、系统架构、历史 |
| 2-discrete-signals.ipynb | 离散信号与采样定理 |
| 3-fourier-analysis.ipynb | 傅里叶分析基础 |

---

### 章节2：signals-systems/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-lti-systems.ipynb | LTI系统与卷积 |
| 2-filters.ipynb | 滤波器基础（FIR/IIR） |
| 3-system-analysis.ipynb | 系统频率响应与分析 |
| 4-sampling-reconstruction.ipynb | 采样与信号重建 |

---

### 章节3：modulation-basics/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-analog-modulation.ipynb | 模拟调制（AM/FM/PM） |
| 2-digital-modulation.ipynb | 数字调制（ASK/FSK/PSK） |
| 3-qam-basics.ipynb | QAM基础 |
| 4-noise-snr.ipynb | 噪声与SNR |

---

### 章节4：channels-receivers/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-multipath-fading.ipynb | 多径衰落 |
| 2-rayleigh-rician.ipynb | Rayleigh/Rician衰落模型 |
| 3-receiver-basics.ipynb | 接收机基础 |
| 4-communication-systems.ipynb | 通信系统概览 |

---

### 章节5：signal-representations/（3个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-time-frequency.ipynb | 时域与频域 |
| 2-fourier-transform.ipynb | 傅里叶变换 |
| 3-delay-doppler.ipynb | 延迟-多普勒域 |

---

### 章节6：channel-basics/（2个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-multipath-channel.ipynb | 多径信道建模 |
| 2-doppler-effect.ipynb | 多普勒效应 |

---

### 章节7：modulation/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-fdm-principles.ipynb | 频分复用原理 |
| 2-tdm-principles.ipynb | 时分复用原理 |
| 3-ofdm-principles.ipynb | OFDM原理 |
| 4-qam-advanced.ipynb | QAM深入（与现有3-modulation/qam-basics合并） |

---

### 章节8：mimo/（1个notebook）

| Notebook | 内容 |
|----------|------|
| 1-mimo-intro.ipynb | MIMO基础 |

---

### 章节9：matrix-coding/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-matrix-basics.ipynb | 矩阵论基础（特征值、SVD、Toeplitz） |
| 2-kronecker-products.ipynb | Kronecker积与 Khatri-Rao积 |
| 3-ldpc.ipynb | LDPC码（构造、译码） |
| 4-polar-turbo.ipynb | Polar码与Turbo码 |

---

### 章节10：estimation-detection/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-pilot-design.ipynb | 导频设计 |
| 2-ls-mmse.ipynb | LS与MMSE信道估计 |
| 3-sparse-estimation.ipynb | 稀疏信道估计（OMP、CoSaMP） |
| 4-detection-theory.ipynb | 检测理论（ML/MAP、线性检测、MP） |

---

### 章节11：synchronization/（3个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-cfo-sync.ipynb | 载波频率同步 |
| 2-sto-sync.ipynb | 符号定时同步 |
| 3-phase-noise.ipynb | 相位噪声补偿 |

---

### 章节12：zak-transform/（1个notebook）

| Notebook | 内容 |
|----------|------|
| 1-zak-transform.ipynb | Zak变换（OTFS核心数学工具） |

---

### 章节13：advanced-projects/（4个notebooks）

| Notebook | 内容 |
|----------|------|
| 1-mimo-otfs.ipynb | MIMO-OTFS系统设计 |
| 2-end-to-end-otfs.ipynb | 完整OTFS收发机 |
| 3-research-frontier.ipynb | OTFS研究前沿 |
| 4-practice-projects.ipynb | 实践项目 |

---

## 4. 实现优先级

### 第一批（核心基础，优先实现）

1. 章节9：matrix-coding/（OTFS数学基础）
2. 章节10：estimation-detection/（信道估计+检测）
3. 章节11：synchronization/（同步技术）
4. 章节13：advanced-projects/（进阶项目）

### 第二批（补充完善）

5. 章节5：signal-representations/（信号表示）
6. 章节6：channel-basics/（信道特性）
7. 章节7：modulation/（调制技术）
8. 章节8：mimo/（MIMO基础）

### 第三批（重组优化）

9. 章节1-4：重组0-communication-basics/为4个新章节
10. 章节12：zak-transform/（Zak变换）

---

## 5. 重组现有文件

### 重组0-communication-basics/（13个→4个章节）

```
原: 0-communication-basics/ (13 notebooks)
拆分为: 1-fundamentals/, 2-signals-systems/, 3-modulation-basics/, 4-channels-receivers/
```

### 合并重复内容

```
3-modulation/qam-basics.ipynb → 合并到 章节7：modulation/ → 4-qam-advanced.ipynb
3-modulation/ofdm-principles.ipynb → 章节7：modulation/ → 3-ofdm-principles.ipynb
```

---

## 6. 成功标准

1. **完整性**：覆盖OTFS深入学习的主要方面
2. **结构性**：每个章节≤4个notebook，序号连续
3. **可读性**：理论与代码比例适当，可自学
4. **可运行**：所有代码可独立运行
5. **衔接性**：形成完整学习路径