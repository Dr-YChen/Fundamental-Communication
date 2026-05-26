# Fundamental Communication

OTFS通信原理Python讲义 — 通过Jupyter Notebook系统学习现代无线通信原理。

## 项目概述

本项目提供一套完整的交互式Jupyter Notebook讲义，共13个章节，覆盖从通信基础到OTFS高阶技术的全部内容。

## 内容结构（13章节）

```
.
├── 1-fundamentals/                     # 第1章：通信基础
│   ├── 1-communication-intro.ipynb     # 通信概论
│   ├── 2-discrete-signals.ipynb        # 离散信号与采样
│   └── 3-fourier-analysis.ipynb       # 傅里叶分析
│
├── 2-signals-systems/                 # 第2章：信号与系统
│   ├── 1-lti-systems.ipynb            # LTI系统与卷积
│   ├── 2-filters.ipynb                # 滤波器基础
│   ├── 3-system-analysis.ipynb        # 系统分析
│   └── 4-sampling-reconstruction.ipynb # 采样与重构
│
├── 3-modulation-basics/               # 第3章：调制基础
│   ├── 1-analog-modulation.ipynb      # 模拟调制
│   ├── 2-digital-modulation.ipynb     # 数字调制
│   ├── 3-qam-basics.ipynb             # QAM基础
│   └── 4-noise-snr.ipynb              # 噪声与SNR
│
├── 4-channels-receivers/              # 第4章：信道与接收机
│   ├── 1-multipath-fading.ipynb       # 多径衰落
│   ├── 2-rayleigh-rician.ipynb        # 瑞利/莱斯衰落
│   ├── 3-receiver-basics.ipynb        # 接收机基础
│   └── 4-communication-systems.ipynb  # 通信系统概览
│
├── 5-signal-representations/          # 第5章：信号表示
│   ├── time-frequency.ipynb           # 时频分析
│   ├── fourier-transform.ipynb        # 傅里叶变换
│   └── delay-doppler.ipynb            # 延迟-多普勒域
│
├── 6-channel-basics/                  # 第6章：信道基础
│   ├── multipath-channel.ipynb        # 多径信道
│   └── doppler-effect.ipynb           # 多普勒效应
│
├── 7-modulation/                       # 第7章：调制技术
│   ├── qam-basics.ipynb               # QAM调制
│   ├── fdm-principles.ipynb           # 频分复用
│   ├── tdm-principles.ipynb           # 时分复用
│   └── ofdm-principles.ipynb          # OFDM原理
│
├── 8-mimo/                             # 第8章：MIMO基础
│   └── mimo-intro.ipynb               # MIMO系统基础
│
├── 9-matrix-coding/                   # 第9章：矩阵编码（OTFS核心）
│   ├── 1-matrix-basics.ipynb          # 矩阵基础
│   ├── 2-kronecker-products.ipynb     # Kronecker积
│   ├── 3-ldpc.ipynb                   # LDPC码
│   └── 4-polar-turbo.ipynb             # Polar/Turbo码
│
├── 10-estimation-detection/           # 第10章：估计与检测
│   ├── 1-pilot-design.ipynb           # 导频设计
│   ├── 2-ls-mmse.ipynb                # LS/MMSE估计
│   ├── 3-sparse-estimation.ipynb       # 稀疏估计
│   └── 4-detection-theory.ipynb       # 检测理论
│
├── 11-synchronization/                 # 第11章：同步技术
│   ├── 1-cfo-sync.ipynb               # 载波频率同步
│   ├── 2-sto-sync.ipynb               # 符号定时同步
│   └── 3-phase-noise.ipynb            # 相位噪声
│
├── 12-zak-transform/                  # 第12章：Zak变换
│   └── 1-zak-transform.ipynb          # Zak变换与OTFS
│
└── 13-advanced-projects/               # 第13章：进阶项目
    ├── 1-mimo-otfs.ipynb              # MIMO-OTFS系统
    ├── 2-end-to-end-otfs.ipynb         # 端到端OTFS
    ├── 3-research-frontier.ipynb       # 研究前沿
    └── 4-practice-projects.ipynb      # 实践项目
```

## 学习路径

### 推荐顺序：按章节顺序学习

```text
第1章 通信基础 → 第2章 信号与系统 → 第3章 调制基础 → 第4章 信道与接收机
    ↓                ↓                    ↓                  ↓
第5章 信号表示  → 第6章 信道基础   → 第7章 调制技术  → 第8章 MIMO基础
    ↓                ↓                    ↓                  ↓
第9章 矩阵编码  → 第10章 估计与检测 → 第11章 同步技术 → 第12章 Zak变换
    ↓
第13章 进阶项目
```

### 路径说明

- **第1-4章**：通信基础，奠定概念基础
- **第5-8章**：信号表示与调制技术，建立系统框架
- **第9-12章**：OTFS核心技术，深入数学原理
- **第13章**：综合应用与实践

## 环境配置

```bash
# 使用uv创建虚拟环境
uv venv
source .venv/bin/activate  # Linux/Mac
# 或 .venv\Scripts\activate  # Windows

# 安装依赖
uv pip install numpy matplotlib scipy jupyter
```

## 运行Notebook

```bash
jupyter lab
# 或
jupyter notebook
```

## 核心概念

### 时域 vs 频域
信号可在时域（随时间变化）或频域（频率成分）表示，傅里叶变换连接两者。

### 延迟-多普勒域
延迟反映信号路径长度（对应多径），多普勒反映相对运动速度（对应移动性）。OTFS将信息符号放置在此域。

### Zak变换
Zak变换是傅里叶变换的二维扩展，是OTFS调制的核心数学工具。

## 参考资料

- Hadani et al., "Orthogonal Time Frequency Space Modulation"
- 本系列Notebook中的引用

## License

MIT