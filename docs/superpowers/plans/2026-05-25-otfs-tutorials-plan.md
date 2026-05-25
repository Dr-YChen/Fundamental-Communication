# OTFS通信原理Python讲义 - 实现计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 创建一套Jupyter Notebook讲义，帮助用户基于OTFS论文需求，系统学习通信原理基础

**Architecture:** 采用轻量级Notebook系列方案，每个知识点独立为单个.ipynb文件，按依赖关系组织，支持碎片化学习

**Tech Stack:** Python 3, numpy, matplotlib, scipy, jupyter

---

## 文件结构

```
Theory-OTFS/
├── docs/superpowers/plans/           # 计划文档
│   └── 2026-05-25-otfs-tutorials-plan.md
├── 1-signal-representations/         # 信号表示基础
│   ├── time-frequency.ipynb
│   ├── fourier-transform.ipynb
│   └── delay-doppler.ipynb
├── 2-channel-basics/                # 信道特性
│   ├── multipath-channel.ipynb
│   └── doppler-effect.ipynb
├── 3-modulation/                    # 调制解调
│   ├── qam-basics.ipynb
│   └── ofdm-principles.ipynb
├── 4-mimo-basics/                   # MIMO基础
│   └── mimo-intro.ipynb
├── 5-zak-transform/                 # Zak变换
│   └── zak-transform.ipynb
├── 6-otfs-full/                     # 完整OTFS
│   ├── otfs-modulation.ipynb
│   ├── otfs-equalization.ipynb
│   └── otfs-precoding.ipynb
└── README.md
```

---

## 优先级与任务分解

### 第一批Notebook（最直接支撑OTFS论文）

#### Task 1: fourier-transform.ipynb
**Files:**
- Create: `1-signal-representations/fourier-transform.ipynb`

- [ ] **Step 1: 创建Notebook框架**
  创建包含以下section的Notebook：
  - 标题与目标说明
  - 1. 傅里叶变换直观理解
  - 2. 代码演示：连续傅里叶变换
  - 3. 代码演示：离散傅里叶变换（DFT）
  - 4. 可视化：时域↔频域转换
  - 5. 快速傅里叶变换（FFT）简介
  - 6. 关联OTFS：傅里叶变换在OTFS中的应用
  - 7. 思考题

- [ ] **Step 2: 编写"傅里叶变换直观理解"**
  用2-3段话解释：
  - 傅里叶变换核心思想：任何信号可以分解为正弦波的叠加
  - 时域与频域的互补关系
  - 海森堡不确定性原理

- [ ] **Step 3: 编写"代码演示：连续傅里叶变换"**
  ```python
  import numpy as np
  import matplotlib.pyplot as plt
  from scipy.integrate import quad

  # 定义被积函数：x(t) * exp(-j*2*pi*f*t)
  def continuous_ft(x, t, f):
      return x(t) * np.exp(-1j * 2 * np.pi * f * t)

  # 示例：矩形脉冲的傅里叶变换
  def rect_pulse(t, tau=1):
      return np.where(np.abs(t) <= tau/2, 1, 0)

  # 计算并绘图
  # ... 完整代码见Notebook
  ```

- [ ] **Step 4: 编写"代码演示：离散傅里叶变换（DFT）"**
  展示N点DFT的计算，展示频率轴的刻度

- [ ] **Step 5: 编写"可视化：时域↔频域转换"**
  用matplotlib创建对比图：
  - 显示原始信号（时域）
  - 显示傅里叶变换结果（频域 magnitude）
  - 交互式滑块（可选）调整信号参数

- [ ] **Step 6: 编写"FFT简介"**
  简要说明FFT是DFT的高效算法，提到Cooley-Tukey

- [ ] **Step 7: 编写"关联OTFS"**
  说明：
  - OFDM使用IFFT/FFT
  - OTFS使用Zak变换（傅里叶变换的扩展）
  - 时频域转换是OTFS调制解调的基础

- [ ] **Step 8: 编写"思考题"**
  包含3-5道巩固性选择题/简答题

---

#### Task 2: time-frequency.ipynb
**Files:**
- Create: `1-signal-representations/time-frequency.ipynb`

- [ ] **Step 1: 创建Notebook框架**
  - 1. 时域与频域的核心概念
  - 2. 短时傅里叶变换（STFT）简介
  - 3. 代码演示：信号在时域和频域的表示
  - 4. 可视化理解：时频 duality
  - 5. 关联OTFS：时频域在OTFS中的角色
  - 6. 思考题

- [ ] **Step 2-7: 实现Notebook内容**
  参考Task 1的结构，创建完整的讲解、代码、可视化内容

---

#### Task 3: delay-doppler.ipynb
**Files:**
- Create: `1-signal-representations/delay-doppler.ipynb`

- [ ] **Step 1: 创建Notebook框架**
  - 1. 延迟-多普勒域直观理解
  - 2. 延迟（Delay）和多普勒（Doppler）的物理意义
  - 3. 代码演示：创建延迟-多普勒信道响应
  - 4. 可视化：延迟-多普勒图像
  - 5. 关联OTFS：OTFS的核心创新
  - 6. 思考题

- [ ] **Step 2: 编写"延迟-多普勒域直观理解"**
  用雷达测距测速类比：
  - 延迟对应目标距离（信号往返时间）
  - 多普勒对应目标速度（频率偏移）

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 创建延迟-多普勒信道响应示例
  # 模拟两个反射点：一个静止，一个移动
  tau = np.array([0, 1e-6])  # 延迟（秒）
  nu = np.array([0, 500])    # 多普勒（Hz）

  # 可视化成2D图像
  ```

- [ ] **Step 4: 关联OTFS**
  重点说明：
  - OTFS将信息符号放在延迟-多普勒域
  - 信道响应在延迟-多普勒域变为卷积
  - 所有QAM符号经历相同的信道（不变性）

---

#### Task 4: multipath-channel.ipynb
**Files:**
- Create: `2-channel-basics/multipath-channel.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. 多径效应直观理解
  - 2. 代码演示：多径信道仿真
  - 3. 码间干扰（ISI）与均衡
  - 4. 关联OTFS：延迟扩展的处理

- [ ] **Step 2: 编写"多径效应直观理解"**
  用图示说明：
  - 信号通过不同路径到达接收机
  - 每条路径有不同的延迟和衰减
  - 叠加造成频率选择性衰落

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 模拟多径信道
  # 3条路径：直射径 + 2个反射径
  h = [1.0, 0.5*np.exp(-1j*np.pi/4), 0.3*np.exp(-1j*np.pi/3)]
  tau = [0, 1e-6, 2e-6]  # 微秒级延迟
  ```

- [ ] **Step 4: 关联OTFS**
  - OTFS在延迟-多普勒域分离各径
  - 每径独立处理，避免衰落叠加

---

#### Task 5: doppler-effect.ipynb
**Files:**
- Create: `2-channel-basics/doppler-effect.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. 多普勒效应直观理解
  - 2. 代码演示：多普勒频移仿真
  - 3. 信道的时间选择性
  - 4. 关联OTFS：高移动性场景

- [ ] **Step 2: 编写"多普勒效应直观理解"**
  - 相对运动造成频率偏移
  - f_d = v * f_c / c （简单估算）
  - 时速120km/h时约400Hz偏移（4GHz载波）

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 模拟多普勒频移
  v = 30 * 1000 / 3600  # 30 km/h 转换为 m/s
  f_c = 4e9  # 4 GHz载波
  c = 3e8   # 光速
  f_d = v * f_c / c
  ```

- [ ] **Step 4: 关联OTFS**
  - OFDM对多普勒敏感（小数倍载波间隔就出问题）
  - OTFS将多普勒变为额外维度的多样性

---

#### Task 6: qam-basics.ipynb
**Files:**
- Create: `3-modulation/qam-basics.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. QAM直观理解
  - 2. 代码演示：QAM映射与星座图
  - 3. 噪声对QAM的影响
  - 4. 关联OTFS：QAM符号是OTFS传输的信息载体

- [ ] **Step 2: 编写"QAM直观理解"**
  - I/Q两路正交调制
  - 16-QAM、64-QAM、256-QAM的星座点分布
  - 格雷码映射

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 创建16-QAM星座图
  qam16 = np.array([...])  # 16个复数星座点
  plt.scatter(qam16.real, qam16.imag)
  ```

- [ ] **Step 4: 关联OTFS**
  - OTFS将QAM符号放置在延迟-多普勒网格上
  - 每个QAM符号携带log2(M)比特信息

---

#### Task 7: ofdm-principles.ipynb
**Files:**
- Create: `3-modulation/ofdm-principles.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. OFDM直观理解
  - 2. 代码演示：OFDM调制解调流程
  - 3. 循环前缀（CP）的作用
  - 4. OFDM的优缺点
  - 5. 关联OTFS：OTFS与OFDM的对比

- [ ] **Step 2: 编写"OFDM直观理解"**
  - 多载波调制的核心思想
  - 子载波正交性
  - IFFT/FFT实现

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 简化的OFDM系统
  # 1. QAM映射
  # 2. IFFT调制
  # 3. 添加CP
  # 4. 通过多径信道
  # 5. 移除CP + FFT解调
  # 6. QAM解映射
  ```

- [ ] **Step 4: 关联OTFS**
  - OTFS可以看作OFDM的泛化
  - OTFS用Zak变换代替IFFT/FFT
  - OTFS在延迟-多普勒域工作 vs OFDM在时频域工作

---

#### Task 8: mimo-intro.ipynb
**Files:**
- Create: `4-mimo-basics/mimo-intro.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. MIMO直观理解
  - 2. 代码演示：MIMO信道容量
  - 3. 预编码与均衡基础
  - 4. 关联OTFS：OTFS的MU-MIMO优势

- [ ] **Step 2: 编写"MIMO直观理解"**
  - 空间复用原理
  - 多用户MIMO（MU-MIMO）
  - 大规模MIMO（Massive MIMO）

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 简化的2x2 MIMO信道
  H = np.random.randn(2, 2) + 1j * np.random.randn(2, 2)
  # 计算信道容量
  capacity = np.log2(np.det(np.eye(2) + SNR/2 * H @ H.conj().T))
  ```

- [ ] **Step 4: 关联OTFS**
  - OTFS在延迟-多普勒域处理MIMO
  - 条件数更好，均衡复杂度更低

---

#### Task 9: zak-transform.ipynb
**Files:**
- Create: `5-zak-transform/zak-transform.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. Zak变换直观理解
  - 2. 代码演示：Zak变换计算
  - 3. Zak变换的性质
  - 4. 关联OTFS：Zak变换是OTFS的数学基础

- [ ] **Step 2: 编写"Zak变换直观理解"**
  - Zak变换是时域和延迟-多普勒域之间的变换
  - 公式：Z{φ}(τ, ν) = ∫ φ(t) exp(-j*2π*ν*t) dt （沿多普勒周期积分）
  - 与傅里叶变换的关系

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 数值计算Zak变换
  # 对信号沿多普勒维度积分
  def zak_transform(x, tau_r, nu_r, N, M):
      # 离散化延迟-多普勒网格
      # 计算Zak变换
      return Z
  ```

- [ ] **Step 4: 关联OTFS**
  - OTFS使用SFFT（有限对称有限傅里叶变换）
  - SFFT等价于先FFT再IFFT（列方向）
  - 信息符号在延迟-多普勒域，经SFFT变到时频域

---

#### Task 10: otfs-modulation.ipynb
**Files:**
- Create: `6-otfs-full/otfs-modulation.ipynb`

- [ ] **Step 1: 创建Notebook**
  - 1. OTFS调制原理
  - 2. 代码演示：OTFS调制解调全流程
  - 3. 时频域网格与延迟-多普勒域网格
  - 4. 关联OTFS论文：第2-3节的内容

- [ ] **Step 2: 编写"OTFS调制原理"**
  - OTFS将QAM符号放置在N×M延迟-多普勒网格
  - 通过SFFT变到时频域
  - 通过OFDM调制变到时域发送

- [ ] **Step 3: 编写"代码演示"**
  ```python
  # 简化的OTFS系统
  # 1. 在延迟-多普勒域放置QAM符号
  # 2. SFFT变换到时频域
  # 3. IFFT+OFDM调制
  # 4. 通过信道
  # 5. OFDM解调 + FFT
  # 6. SFFT逆变换
  # 7. 均衡 + QAM解映射
  ```

- [ ] **Step 4: 关联OTFS论文**
  - 对应论文第2.4-2.7节
  - 对应论文第3节（均衡与预编码）

---

### 后续扩展Notebook

#### Task 11: otfs-equalization.ipynb
**Files:**
- Create: `6-otfs-full/otfs-equalization.ipynb`

内容：OTFS均衡原理，与论文第3.1节对应

#### Task 12: otfs-precoding.ipynb
**Files:**
- Create: `6-otfs-full/otfs-precoding.ipynb`

内容：OTFS预编码（ZF THP），与论文第3.2节对应

#### Task 13: complex-numbers.ipynb（可选）
**Files:**
- Create: `0-prerequisites/complex-numbers.ipynb`

内容：复数基础复习，为Zak变换等做铺垫

---

## 实现顺序

1. fourier-transform.ipynb
2. time-frequency.ipynb
3. delay-doppler.ipynb
4. multipath-channel.ipynb
5. doppler-effect.ipynb
6. qam-basics.ipynb
7. ofdm-principles.ipynb
8. mimo-intro.ipynb
9. zak-transform.ipynb
10. otfs-modulation.ipynb

后续可扩展：otfs-equalization.ipynb, otfs-precoding.ipynb, complex-numbers.ipynb

---

## 执行选择

**Plan完成并保存到 `docs/superpowers/plans/2026-05-25-otfs-tutorials-plan.md`**

两种执行方式：

**1. Subagent-Driven (推荐)**
- 每个Notebook由子代理完成
- 两个阶段的审查确保质量

**2. Inline Execution**
- 在本会话中依次执行
- 使用检查点进行阶段性审查

选择哪种方式？