# Fundamental Communication

OTFS通信原理Python讲义 — 通过Jupyter Notebook系统学习现代无线通信原理。

## 项目概述

本项目提供两套交互式Jupyter Notebook讲义：

1. **通信基础入门（0-communication-basics）** — 面向跨领域工程师的通信基础课程，从零开始建立通信概念框架
2. **高阶通信技术（1-signal-representations → 6-otfs-full）** — 面向OTFS等高阶调制技术的深度学习

## 内容结构

```
.
├── 0-communication-basics/          # 通信基础入门（新手）
│   ├── 1-communication-intro.ipynb    # 通信概论
│   ├── 2-discrete-signals.ipynb     # 离散信号与采样
│   ├── 3-fourier-analysis.ipynb     # 傅里叶分析
│   ├── 4-lti-systems.ipynb         # LTI系统与卷积
│   ├── 5-filters.ipynb             # 滤波器基础
│   ├── 6-analog-modulation.ipynb   # 模拟调制
│   ├── 7-digital-modulation.ipynb   # 数字调制
│   ├── 8-qam-basics.ipynb          # QAM基础
│   ├── 9-noise-and-snr.ipynb      # 噪声与SNR
│   ├── 10-multipath-fading.ipynb   # 多径衰落
│   ├── 11-receiver-basics.ipynb    # 接收机基础
│   ├── 12-communication-systems.ipynb  # 通信系统概览
│   └── 13-preparing-for-advanced.ipynb  # 进阶过渡
│
├── 1-signal-representations/        # 信号表示基础（高阶）
│   ├── time-frequency.ipynb
│   ├── fourier-transform.ipynb
│   └── delay-doppler.ipynb
├── 2-channel-basics/               # 信道特性
│   ├── multipath-channel.ipynb
│   └── doppler-effect.ipynb
├── 3-modulation/                    # 调制技术
│   ├── qam-basics.ipynb             # QAM调制
│   ├── fdm-principles.ipynb          # 频分复用(FDM)原理
│   ├── tdm-principles.ipynb         # 时分复用(TDM)原理
│   └── ofdm-principles.ipynb        # OFDM原理
├── 4-mimo-basics/                   # MIMO基础
│   └── mimo-intro.ipynb
├── 5-zak-transform/                 # Zak变换
│   └── zak-transform.ipynb
├── 6-otfs-full/                     # 完整OTFS系统
│   └── otfs-modulation.ipynb
└── README.md
```

## 学习路径

### 路径一：通信基础入门（新手）

适合跨领域工程师转通信，从零开始：

```
1. 通信概论
   ↓
2. 离散信号与采样
   ↓
3. 傅里叶分析
   ↓
4. LTI系统与卷积
   ↓
5. 滤波器基础
   ↓
6. 模拟调制
   ↓
7. 数字调制
   ↓
8. QAM基础
   ↓
9. 噪声与SNR
   ↓
10. 多径衰落
    ↓
11. 接收机基础
    ↓
12. 通信系统概览
    ↓
13. 进阶过渡
    ↓
    ↓ (进入高阶讲义)
```

### 路径二：高阶通信技术

适合有通信基础后深入学习OTFS：

1. **信号表示基础** — 傅里叶变换、时频域、延迟-多普勒域
2. **信道特性** — 多径衰落、多普勒效应
3. **调制技术** — QAM、FDM、TDM、OFDM原理
4. **MIMO基础** — 空间复用与预编码
5. **Zak变换** — OTFS的数学基础
6. **OTFS系统** — 完整调制解调流程

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