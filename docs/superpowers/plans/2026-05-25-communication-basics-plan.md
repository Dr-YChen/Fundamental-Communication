# 通信基础入门讲义 — 实现计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 创建13个面向跨领域工程师的通信基础入门notebook，配套Python实验，建立完整通信知识框架，能够过渡到现有高阶讲义。

**Architecture:** 按信号处理链路组织（世界观→信号基础→系统与滤波→调制→信道→接收机→系统概览→进阶过渡），每个notebook包含：学习目标、概念讲解、代码演示、原理解析、思考题。

**Tech Stack:** Python 3, numpy, matplotlib, scipy, jupyter

---

## 文件结构

```
0-communication-basics/
├── 1-communication-intro.ipynb
├── 2-discrete-signals.ipynb
├── 3-fourier-analysis.ipynb
├── 4-lti-systems.ipynb
├── 5-filters.ipynb
├── 6-analog-modulation.ipynb
├── 7-digital-modulation.ipynb
├── 8-qam-basics.ipynb
├── 9-noise-and-snr.ipynb
├── 10-multipath-fading.ipynb
├── 11-receiver-basics.ipynb
├── 12-communication-systems.ipynb
└── 13-preparing-for-advanced.ipynb
```

---

## 实现顺序与任务分解

### 第一批：通信世界观 + 信号基础（3个notebook）

#### Task 1: 通信世界观 introduction

**Files:**
- Create: `0-communication-basics/1-communication-intro.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解通信的基本定义和重要性
- 了解通信系统的基本组成（发射机→信道→接收机）
- 了解通信行业发展历程和主要应用场景

# 2. 概念讲解
- 什么是通信（从烽火台到5G的历史）
- 通信系统的基本架构图
- 现代通信应用场景（移动通信、卫星、IoT等）

# 3. Python演示
- 绘制简单radio link框图
- 展示信号从发射到接收的流程

# 4. 原理解析
- 通信系统的资源约束（带宽、功率）
- 基本的性能指标（SNR、BBER）

# 5. 思考题
- 为什么无线通信需要调制？
- 5G相比4G的核心改进是什么？
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写通信世界观内容**
- [ ] **Step 3: 添加Python演示代码**
- [ ] **Step 4: 添加思考题**
- [ ] **Step 5: 测试运行代码**
- [ ] **Step 6: Commit**

---

#### Task 2: 离散信号与采样

**Files:**
- Create: `0-communication-basics/2-discrete-signals.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解连续信号与离散信号的区别
- 掌握采样定理（Nyquist采样率）
- 理解混叠现象及如何避免
- 了解A/D转换的完整流程（采样→量化→编码）

# 2. 概念讲解
- 连续时间信号 vs 离散时间信号
- 采样过程：x[n] = x_c(nT)
- Nyquist采样定理：f_s ≥ 2f_max
- 混叠（Aliasing）现象
- 量化与编码（均匀量化、非均匀量化）

# 3. Python演示
- 连续正弦波的采样演示
- 不同采样率下的信号重建对比
- 量化误差分析

# 4. 原理解析
- 采样信号的频谱复制
- 抗混叠滤波器的作用

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写采样定理内容**
- [ ] **Step 3: 添加采样和量化Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

#### Task 3: 傅里叶分析基础

**Files:**
- Create: `0-communication-basics/3-fourier-analysis.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解傅里叶级数与傅里叶变换的区别
- 掌握频谱的概念（幅度谱、相位谱）
- 理解功率谱密度
- 能够用Python进行频谱分析

# 2. 概念讲解
- 傅里叶级数：周期信号的频域表示
- 傅里叶变换：非周期信号的频谱
- 幅度谱 vs 相位谱
- 能量信号 vs 功率信号
- 帕塞瓦尔定理

# 3. Python演示
- 周期信号的傅里叶级数分解
- 非周期信号的频谱分析
- 多个频率成分的信号合成

# 4. 原理解析
- 时频对偶性
- 快速傅里叶变换（FFT）简介

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写傅里叶分析内容**
- [ ] **Step 3: 添加频谱分析Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

### 第二批：系统与滤波（2个notebook）

#### Task 4: LTI系统与卷积

**Files:**
- Create: `0-communication-basics/4-lti-systems.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解LTI系统的定义和性质
- 掌握连续/离散卷积运算
- 理解冲激响应与系统特性的关系
- 理解频率响应的物理意义

# 2. 概念讲解
- 线性时不变（LTI）系统定义
- 连续卷积：y(t) = x(t)*h(t)
- 离散卷积：y[n] = x[n]*h[n]
- 冲激响应h(t)的含义
- 频率响应H(jω) = |H(jω)|e^(j∠H(jω))

# 3. Python演示
- 卷积运算的直观演示
- 不同系统对同一输入的响应对比
- 频率响应可视化

# 4. 原理解析
- 卷积定理：时域卷积↔频域乘积

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写LTI系统内容**
- [ ] **Step 3: 添加卷积Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

#### Task 5: 滤波器基础

**Files:**
- Create: `0-communication-basics/5-filters.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解四种滤波器类型（LPF/HPF/BPF/BSF）
- 掌握FIR滤波器的设计方法
- 理解IIR滤波器的基本概念
- 能够用Python设计和应用滤波器

# 2. 概念讲解
- 滤波器类型及其频率特性
- FIR滤波器：有限长冲激响应
- IIR滤波器：无限长冲激响应
- Z变换简介

# 3. Python演示
- 不同类型滤波器的频率响应
- FIR滤波器设计（窗函数法）
- 滤波器的实际应用示例

# 4. 原理解析
- 滤波器设计的关键参数（截止频率、过渡带宽度）

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写滤波器内容**
- [ ] **Step 3: 添加滤波器设计Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

### 第三批：调制基础（3个notebook）

#### Task 6: 模拟调制

**Files:**
- Create: `0-communication-basics/6-analog-modulation.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解调制的意义（频谱搬移、天线尺寸）
- 掌握幅度调制（AM/DSB/SSB）原理
- 掌握频率调制（FM）原理
- 理解相位调制（PM）与FM的关系

# 2. 概念讲解
- 为什么要调制：频谱效率、天线尺寸
- 幅度调制：s(t) = [1+m·x(t)]·cos(2πf_c t)
- DSB-SC、SSB调制方式
- 调频原理：瞬时频率与调制指数
- 调相原理：与FM的关系

# 3. Python演示
- AM调制解调演示
- FM调制解调演示
- 不同调制方式的频谱对比

# 4. 原理解析
- 卡森法则（Carson's rule）

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写模拟调制内容**
- [ ] **Step 3: 添加AM/FM Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

#### Task 7: 数字调制基础

**Files:**
- Create: `0-communication-basics/7-digital-modulation.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解数字调制相比模拟调制的优势
- 掌握ASK/FSK/PSK的原理
- 理解星座图的概念
- 掌握格雷码映射的原理

# 2. 概念讲解
- 数字调制的优势（抗噪声、易处理）
- 幅移键控（ASK）
- 频移键控（FSK）
- 相移键控（BPSK、QPSK）
- 星座图表示
- 格雷码映射原理

# 3. Python演示
- 星座图绘制（ASK/BPSK/QPSK）
- 调制解调仿真
- 不同调制方式的误码性能对比

# 4. 原理解析
- 欧氏距离与误码率关系

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写数字调制内容**
- [ ] **Step 3: 添加星座图Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

#### Task 8: QAM基础

**Files:**
- Create: `0-communication-basics/8-qam-basics.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解QAM的正交幅度调制原理
- 掌握I/Q调制的概念
- 理解星座图距离与误码率的关系
- 了解高阶QAM（16/64/256-QAM）

# 2. 概念讲解
- QAM原理：两路正交载波合成
- I/Q表示：s(t) = I·cos(2πf_c t) - Q·sin(2πf_c t)
- 16-QAM星座图
- 高阶QAM的频谱效率与抗噪声性能权衡

# 3. Python演示
- 16-QAM星座图绘制
- QAM调制解调流程
- 噪声对QAM的影响

# 4. 原理解析
- 格雷码在高阶QAM中的应用

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写QAM基础内容**
- [ ] **Step 3: 添加QAM Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

### 第四批：信道基础（2个notebook）

#### Task 9: 噪声与SNR

**Files:**
- Create: `0-communication-basics/9-noise-and-snr.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解AWGN信道模型
- 掌握SNR的定义和计算
- 理解dB与线性值的转换
- 理解噪声对系统性能的影响

# 2. 概念讲解
- 噪声类型：热噪声、白噪声、高斯噪声
- AWGN信道模型
- SNR定义：SNR = P_signal / P_noise
- dB定义：10·log10(P1/P2)
- 噪声功率谱密度N0

# 3. Python演示
- 添加AWGN到信号
- SNR vs BER关系演示
- dB转换计算器

# 4. 原理解析
- 理论误码率公式

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写噪声与SNR内容**
- [ ] **Step 3: 添加SNR Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

#### Task 10: 多径衰落

**Files:**
- Create: `0-communication-basics/10-multipath-fading.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解多径效应的物理机制
- 理解Rayleigh衰落和Rician衰落
- 理解信道相干带宽的概念
- 理解频率选择性衰落

# 2. 概念讲解
- 多径传播机制
- 瑞利衰落（Rayleigh fading）
- 莱斯衰落（Rician fading）
- 相干带宽与符号周期的关系
- 平坦衰落 vs 频率选择性衰落

# 3. Python演示
- 多径信道仿真
- Rayleigh衰落生成
- 不同信道条件下的BER对比

# 4. 原理解析
- 多径信道的时变特性

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写多径衰落内容**
- [ ] **Step 3: 添加多径信道Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

### 第五批：接收机原理（1个notebook）

#### Task 11: 接收机基础

**Files:**
- Create: `0-communication-basics/11-receiver-basics.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 理解匹配滤波器的原理
- 理解载波同步和符号同步
- 理解基本的均衡概念
- 理解眼图的作用

# 2. 概念讲解
- 匹配滤波器：最大化SNR
- 载波同步：Costas环
- 符号同步：Early-Late门
- 线性均衡器
- 判决反馈均衡器
- 眼图与符号间干扰

# 3. Python演示
- 匹配滤波器设计
- 眼图生成
- 不同均衡器的性能对比

# 4. 原理解析
- 同步误差对系统性能的影响

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写接收机内容**
- [ ] **Step 3: 添加匹配滤波和眼图Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

### 第六批：系统概览 + 进阶过渡（2个notebook）

#### Task 12: 通信系统概览

**Files:**
- Create: `0-communication-basics/12-communication-systems.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 了解2G/3G/4G/5G的演进
- 理解TDM/FDM/CDMA/OFDMA多址技术
- 了解通信协议栈的基本结构
- 理解LTE系统的基本架构

# 2. 概念讲解
- 2G：TDMA/FDMA
- 3G：CDMA
- 4G：OFDMA
- 5G：NR与毫米波
- 通信协议栈：物理层→MAC层→网络层
- LTE系统架构简介

# 3. Python演示
- OFDM系统框图
- 多址技术对比

# 4. 原理解析
- 为什么从CDMA演进到OFDMA

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写通信系统概览内容**
- [ ] **Step 3: 添加系统架构Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

#### Task 13: 进阶过渡

**Files:**
- Create: `0-communication-basics/13-preparing-for-advanced.ipynb`

**Content Structure:**
```markdown
# 1. 学习目标
- 建立向量信号分析视角
- 理解复基带信号表示
- 理解采样率转换概念
- 明确后续学习路径

# 2. 概念讲解
- 向量信号分析：I/Q作为向量
- 复基带表示的优势
- 采样率转换：重采样、插值
- 与高阶讲义的衔接点

# 3. Python演示
- 复基带信号处理
- 向量信号在星座图上的表示
- 预览OFDM系统框架

# 4. 原理解析
- 如何衔接到OFDM原理（现有高阶讲义）
- 学习路径建议

# 5. 思考题
```

- [ ] **Step 1: 创建notebook基本结构**
- [ ] **Step 2: 编写进阶过渡内容**
- [ ] **Step 3: 添加复基带处理Python演示**
- [ ] **Step 4: 测试运行代码**
- [ ] **Step 5: Commit**

---

## 最后：更新主README

**Files:**
- Modify: `README.md`

- [ ] **Step 1: 更新README添加基础讲义部分**
- [ ] **Step 2: 更新学习路径说明**
- [ ] **Step 3: Commit**

---

## 实现顺序

```
批次1（Task 1-3）：通信世界观 + 信号基础
批次2（Task 4-5）：系统与滤波
批次3（Task 6-8）：调制基础
批次4（Task 9-10）：信道基础
批次5（Task 11）：接收机原理
批次6（Task 12-13）：系统概览 + 进阶过渡
最后：更新README
```

---

## 质量标准

每个notebook必须满足：
1. 所有代码可独立运行
2. 中文注释清晰
3. 图表使用中文标签
4. 学习目标明确
5. 思考题有深度