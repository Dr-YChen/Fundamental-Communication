# 通信基础入门讲义 — 设计规范

## 1. 概述

### 1.1 目的

创建一套面向**跨领域工程师转通信**的基础入门讲义，配套Python实验，建立完整通信知识框架，能够平滑过渡到现有高阶讲义（OTFS等）。

### 1.2 目标受众

| 特点 | 描述 |
|------|------|
| 工程背景 | 跨领域工程师，有工科本科数学基础（微积分、线性代数、概率统计） |
| Python水平 | 需要跟着教程学，边学通信概念边学Python |
| 学习方式 | 交替进行：概念→代码演示→深入原理 |
| 最终目标 | 建立通用通信基础，可继续学习OTFS/OFDM等高阶内容 |

### 1.3 项目体量

- **13个notebook**（预计40-60小时学习时间）
- 按信号处理链路组织，辅以系统级概念

---

## 2. 内容结构

### 2.1 三层四模块框架

```
三层：
  世界观 → 基础概念 → 核心原理 → 系统概览

四模块（13个notebook）：
├── 0-通信世界观/
│   └── 1-communication-intro.ipynb
├── 1-信号基础/
│   ├── 2-discrete-signals.ipynb
│   └── 3-fourier-analysis.ipynb
├── 2-系统与滤波/
│   ├── 4-lti-systems.ipynb
│   └── 5-filters.ipynb
├── 3-调制基础/
│   ├── 6-analog-modulation.ipynb
│   ├── 7-digital-modulation.ipynb
│   └── 8-qam-basics.ipynb
├── 4-信道基础/
│   ├── 9-noise-and-snr.ipynb
│   └── 10-multipath-fading.ipynb
├── 5-接收机原理/
│   └── 11-receiver-basics.ipynb
├── 6-系统概览/
│   └── 12-communication-systems.ipynb
└── 7-进阶过渡/
    └── 13-preparing-for-advanced.ipynb
```

### 2.2 详细模块说明

#### 模块0：通信世界观（第1个notebook）

**Notebook**: `1-communication-intro.ipynb`

| 内容 | 说明 |
|------|------|
| 什么是通信 | 通信的定义、历史（从烽火台到5G）、现代通信系统全景图 |
| 为什么重要 | 连接世界的骨架、行业就业方向 |
| 通信系统的组成 | 发射机→信道→接收机的基本架构 |
| 行业全景 | 2G/3G/4G/5G/卫星通信/IoT等应用场景 |

**配套Python**：展示一个简单 radio link 的组成框图

---

#### 模块1：信号基础（第2-3个notebook）

**Notebook 1**: `2-discrete-signals.ipynb`

| 内容 | 说明 |
|------|------|
| 连续信号vs离散信号 | 模拟信号与数字信号的区别 |
| 采样定理（Nyquist） | 采样频率、混叠现象 |
| 量化与编码 | 模拟信号数字化步骤（A/D转换） |
| 离散时间信号表示 | 序列、单位脉冲序列 |

**配套Python**：采样演示、量化误差分析

---

**Notebook 2**: `3-fourier-analysis.ipynb`

| 内容 | 说明 |
|------|------|
| 傅里叶级数 | 周期信号的频域表示 |
| 傅里叶变换 | 非周期信号的频谱分析 |
| 频谱概念 | 幅度谱、相位谱、功率谱密度 |
| 能量与功率 | 信号能量/功率计算 |

**配套Python**：频谱分析、信号合成与分解

---

#### 模块2：系统与滤波（第4-5个notebook）

**Notebook 1**: `4-lti-systems.ipynb`

| 内容 | 说明 |
|------|------|
| LTI系统 | 线性时不变系统的定义与性质 |
| 卷积 | 连续/离散卷积运算 |
| 冲激响应 | 系统对单位脉冲的响应 |
| 频率响应 | 系统的幅频特性与相频特性 |

**配套Python**：卷积运算、系统响应仿真

---

**Notebook 2**: `5-filters.ipynb`

| 内容 | 说明 |
|------|------|
| 滤波器类型 | LPF、HPF、BPF、BSF |
| FIR滤波器 | 有限长冲激响应滤波器设计 |
| IIR滤波器 | 无限长冲激响应滤波器简介 |
| Z变换 | 离散系统分析工具 |

**配套Python**：FIR/IIR滤波器设计与应用

---

#### 模块3：调制基础（第6-8个notebook）

**Notebook 1**: `6-analog-modulation.ipynb`

| 内容 | 说明 |
|------|------|
| 调制的意义 | 为什么需要调制（频谱搬移、天线尺寸） |
| 幅度调制（AM） | DSB-FC、DSB-SC、SSB |
| 频率调制（FM） | 调频原理、频偏与调制指数 |
| 相位调制（PM） | 调相原理、与FM的关系 |

**配套Python**：AM/FM调制解调演示

---

**Notebook 2**: `7-digital-modulation.ipynb`

| 内容 | 说明 |
|------|------|
| 数字调制优势 | 相对于模拟调制的优点 |
| ASK/FSK/PSK | 幅移键控、频移键控、相移键控 |
| 星座图 | 数字调制信号的复平面表示 |
| 格雷码映射 | 相邻星座点的比特分配 |

**配套Python**：星座图绘制、调制解调仿真

---

**Notebook 3**: `8-qam-basics.ipynb`

| 内容 | 说明 |
|------|------|
| QAM原理 | 正交幅度调制，I/Q两路合成 |
| I/Q调制 | 同相与正交分量的合成 |
| 星座图距离 | 欧氏距离与误码率关系 |
| 高阶QAM | 16-QAM、64-QAM、256-QAM |

**配套Python**：16-QAM映射、噪声影响演示

---

#### 模块4：信道基础（第9-10个notebook）

**Notebook 1**: `9-noise-and-snr.ipynb`

| 内容 | 说明 |
|------|------|
| 噪声类型 | 热噪声、白噪声、高斯噪声 |
| AWGN信道 | 加性高斯白噪声信道模型 |
| SNR定义 | 信噪比计算，dB与线性值转换 |
| 误码率理论 | BER与SNR的关系 |

**配套Python**：SNR vs BER关系、噪声添加演示

---

**Notebook 2**: `10-multipath-fading.ipynb`

| 内容 | 说明 |
|------|------|
| 多径效应 | 多径传播的物理机制 |
| 瑞利衰落 | Rayleigh信道模型 |
| 莱斯衰落 | Rician信道模型 |
| 信道相干带宽 | 频率选择性衰落 |

**配套Python**：多径信道仿真、BER性能对比

---

#### 模块5：接收机原理（第11个notebook）

**Notebook**: `11-receiver-basics.ipynb`

| 内容 | 说明 |
|------|------|
| 匹配滤波器 | 最大化SNR的接收滤波器 |
| 同步技术 | 载波同步、符号同步 |
| 基础均衡 | 线性均衡、判决反馈均衡概念 |
| 眼图 | 符号间干扰的可视化分析 |

**配套Python**：眼图、匹配滤波演示

---

#### 模块6：系统概览（第12个notebook）

**Notebook**: `12-communication-systems.ipynb`

| 内容 | 说明 |
|------|------|
| 2G/3G/4G/5G演进 | 各代移动通信的关键技术 |
| 复用与多址 | TDM/FDM/CDMA/OFDMA |
| 通信协议栈 | 物理层→MAC层→网络层概述 |
| 实际系统案例 | LTE 4G系统架构简介 |

**配套Python**：展示OFDM系统框图

---

#### 模块7：进阶过渡（第13个notebook）

**Notebook**: `13-preparing-for-advanced.ipynb`

| 内容 | 说明 |
|------|------|
| 向量信号分析 | 复基带信号的向量表示视角 |
| 采样率转换 | 重采样、 interpolation |
| OFDM预览 | 引入OFDM核心概念 |
| 后续学习路径 | 如何衔接高阶讲义 |

**配套Python**：复基带信号处理

---

## 3. 内容风格规范

### 3.1 每个Notebook的结构

```
1. 学习目标（3-4个要点）
      ↓
2. 概念讲解（图文并茂，公式精简）
      ↓
3. 代码演示（可运行，边学边练）
      ↓
4. 原理解析（深入一点）
      ↓
5. 思考题
```

### 3.2 代码风格规范

- 主要使用库：`numpy`、`matplotlib`、`scipy`
- 每个代码块带详细中文注释
- 代码可独立运行，便于学习者实验
- 图表使用中文标签
- 关键变量命名清晰

### 3.3 公式与文字比例

- **公式**：精简核心公式，避免复杂推导
- **解释**：每个公式配文字说明其物理意义
- **图示**：重要概念配示意图（matplotlib绘制）

---

## 4. 与现有高阶讲义的衔接

### 4.1 衔接点

| 高阶讲义 | 衔接内容 | 对应基础讲义模块 |
|---------|---------|------------------|
| `qam-basics.ipynb` | QAM星座图基础 | 模块3-数字调制 |
| `ofdm-principles.ipynb` | OFDM核心概念 | 模块7-进阶过渡 |
| `delay-doppler.ipynb` | 延迟-多普勒域 | 模块7-进阶过渡 |

### 4.2 学习路径映射

```
基础讲义 → 高阶讲义

模块3(QAM基础) → qam-basics.ipynb（跳过，直接进入高阶）
模块3(数字调制) → ofdm-principles.ipynb
模块7(进阶过渡) → delay-doppler.ipynb → zak-transform.ipynb → otfs-modulation.ipynb
```

---

## 5. 目录结构

```
Fundamental-Communication/
├── docs/
│   └── superpowers/
│       └── specs/
│           └── 2026-05-25-communication-basics-design.md
│
├── 0-communication-basics/              (新增)
│   ├── 1-communication-intro.ipynb
│   ├── 2-discrete-signals.ipynb
│   ├── 3-fourier-analysis.ipynb
│   ├── 4-lti-systems.ipynb
│   ├── 5-filters.ipynb
│   ├── 6-analog-modulation.ipynb
│   ├── 7-digital-modulation.ipynb
│   ├── 8-qam-basics.ipynb
│   ├── 9-noise-and-snr.ipynb
│   ├── 10-multipath-fading.ipynb
│   ├── 11-receiver-basics.ipynb
│   ├── 12-communication-systems.ipynb
│   └── 13-preparing-for-advanced.ipynb
│
├── 1-signal-representations/            (现有高阶)
├── 2-channel-basics/
├── 3-modulation/
├── 4-mimo-basics/
├── 5-zak-transform/
├── 6-otfs-full/
├── README.md
└── CLAUDE.md
```

---

## 6. 实现优先级

### 第一批（核心信号基础）

1. `1-communication-intro.ipynb` — 建立世界观
2. `2-discrete-signals.ipynb` — 采样与离散信号
3. `3-fourier-analysis.ipynb` — 频谱分析基础

### 第二批（系统与调制）

4. `4-lti-systems.ipynb` — LTI系统与卷积
5. `5-filters.ipynb` — 滤波器基础
6. `6-analog-modulation.ipynb` — 模拟调制
7. `7-digital-modulation.ipynb` — 数字调制基础

### 第三批（信道与接收机）

8. `8-qam-basics.ipynb` — QAM基础
9. `9-noise-and-snr.ipynb` — 噪声与SNR
10. `10-multipath-fading.ipynb` — 多径衰落
11. `11-receiver-basics.ipynb` — 接收机原理

### 第四批（系统与过渡）

12. `12-communication-systems.ipynb` — 通信系统概览
13. `13-preparing-for-advanced.ipynb` — 进阶过渡

---

## 7. 成功标准

1. **完整性**：跨领域工程师能通过学习这13个notebook建立完整通信知识框架
2. **可读性**：代码可运行，概念解释清晰，公式有物理意义
3. **衔接性**：学完基础讲义后能顺利进入高阶讲义（OTFS等）
4. **独立性**：每个notebook可单独学习，不依赖其他外部资源