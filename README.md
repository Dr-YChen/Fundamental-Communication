# Fundamental Communication

OTFS通信原理Python讲义 — 通过Jupyter Notebook系统学习现代无线通信原理。

## 项目概述

本项目提供一套交互式Jupyter Notebook讲义，帮助理解OTFS（正交时频空）调制的数学基础与通信原理。OTFS是一种新型多载波调制技术，在高移动性场景下相比传统OFDM具有显著优势。

## 内容结构

```
.
├── 1-signal-representations/    # 信号表示基础
│   ├── time-frequency.ipynb      # 时域与频域
│   ├── fourier-transform.ipynb   # 傅里叶变换
│   └── delay-doppler.ipynb      # 延迟-多普勒域
├── 2-channel-basics/            # 信道特性
│   ├── multipath-channel.ipynb   # 多径效应
│   └── doppler-effect.ipynb      # 多普勒效应
├── 3-modulation/                 # 调制解调
│   ├── qam-basics.ipynb          # QAM调制
│   └── ofdm-principles.ipynb     # OFDM原理
├── 4-mimo-basics/                # MIMO基础
│   └── mimo-intro.ipynb
├── 5-zak-transform/              # Zak变换
│   └── zak-transform.ipynb
├── 6-otfs-full/                  # 完整OTFS系统
│   └── otfs-modulation.ipynb
└── README.md
```

## 学习路径

按依赖顺序学习：

1. **信号表示基础** — 傅里叶变换、时频域、延迟-多普勒域
2. **信道特性** — 多径衰落、多普勒效应
3. **调制技术** — QAM、OFDM原理
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