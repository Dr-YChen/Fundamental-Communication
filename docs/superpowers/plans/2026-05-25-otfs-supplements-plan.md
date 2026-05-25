# OTFS讲义补充实现计划

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** 创建20个新notebook补充OTFS深入学习内容，并重组现有讲义为13个章节结构

**Architecture:** 分阶段实现，每阶段聚焦1-2个章节，按依赖顺序（先基础后应用）

**Tech Stack:** Python 3, numpy, matplotlib, scipy, jupyter

---

## 第一阶段：核心补充（章节9-12，共12个notebooks）

### Task 9-1: matrix-basics.ipynb
**Files:**
- Create: `9-matrix-coding/1-matrix-basics.ipynb`

**Content:** 矩阵运算、特征值分解、SVD、Toeplitz矩阵

- [ ] Create notebook structure
- [ ] Implement matrix operations section
- [ ] Add eigenvalue/SVD section with Python demos
- [ ] Add Toeplitz matrix section
- [ ] Commit

---

### Task 9-2: kronecker-products.ipynb
**Files:**
- Create: `9-matrix-coding/2-kronecker-products.ipynb`

**Content:** Kronecker积、Khatri-Rao积、Hadamard积、MIMO应用

- [ ] Create notebook structure
- [ ] Implement Kronecker product section
- [ ] Add Khatri-Rao product section
- [ ] Add MIMO channel model application
- [ ] Commit

---

### Task 9-3: ldpc.ipynb
**Files:**
- Create: `9-matrix-coding/3-ldpc.ipynb`

**Content:** LDPC码构造、Sum-Product译码、密度演化、5G NR LDPC

- [ ] Create notebook structure
- [ ] Implement LDPC fundamentals section
- [ ] Add encoding/decoding Python demos
- [ ] Add density evolution visualization
- [ ] Commit

---

### Task 9-4: polar-turbo.ipynb
**Files:**
- Create: `9-matrix-coding/4-polar-turbo.ipynb`

**Content:** Polar码构造（SC/SCL译码）、Turbo码、BICM

- [ ] Create notebook structure
- [ ] Implement Polar code section (construction + SC译码)
- [ ] Add SCL-CRC decoding
- [ ] Add Turbo code and BICM section
- [ ] Commit

---

### Task 10-1: pilot-design.ipynb
**Files:**
- Create: `10-estimation-detection/1-pilot-design.ipynb`

**Content:** 导频类型、导频图案设计、信道估计质量分析

- [ ] Create notebook structure
- [ ] Implement pilot types section
- [ ] Add pilot pattern design Python demos
- [ ] Add MSE analysis
- [ ] Commit

---

### Task 10-2: ls-mmse.ipynb
**Files:**
- Create: `10-estimation-detection/2-ls-mmse.ipynb`

**Content:** LS估计、MMSE估计、低复杂度方法

- [ ] Create notebook structure
- [ ] Implement LS estimation section
- [ ] Add MMSE estimation with Bayesian framework
- [ ] Add low-complexity methods (SVD-MMSE)
- [ ] Commit

---

### Task 10-3: sparse-estimation.ipynb
**Files:**
- Create: `10-estimation-detection/3-sparse-estimation.ipynb`

**Content:** 压缩感知基础、OMP、CoSaMP、SAMP、稀疏信道估计

- [ ] Create notebook structure
- [ ] Implement compressed sensing basics
- [ ] Add OMP algorithm Python demo
- [ ] Add CoSaMP and SAMP algorithms
- [ ] Commit

---

### Task 10-4: detection-theory.ipynb
**Files:**
- Create: `10-estimation-detection/4-detection-theory.ipynb`

**Content:** ML/MAP检测、ZF/MMSE线性检测、消息传递（BP/AMP/GAMP）

- [ ] Create notebook structure
- [ ] Implement ML/MAP detection section
- [ ] Add linear detection (ZF/MMSE) with Python demos
- [ ] Add message passing algorithms (BP, AMP)
- [ ] Commit

---

### Task 11-1: cfo-sync.ipynb
**Files:**
- Create: `11-synchronization/1-cfo-sync.ipynb`

**Content:** CFO估计（导频辅助+数据辅助）、分数/整数频偏、补偿

- [ ] Create notebook structure
- [ ] Implement CFO fundamentals section
- [ ] Add CFO estimation algorithms
- [ ] Add compensation methods
- [ ] Commit

---

### Task 11-2: sto-sync.ipynb
**Files:**
- Create: `11-synchronization/2-sto-sync.ipynb`

**Content:** 符号定时同步、早迟门、Gardner算法、插值滤波器

- [ ] Create notebook structure
- [ ] Implement STO fundamentals
- [ ] Add Early-Late Gate and Gardner algorithm
- [ ] Add interpolation filters
- [ ] Commit

---

### Task 11-3: phase-noise.ipynb
**Files:**
- Create: `11-synchronization/3-phase-noise.ipynb`

**Content:** 相位噪声模型、Wiener过程、对OFDM/OTFS影响、补偿

- [ ] Create notebook structure
- [ ] Implement phase noise fundamentals
- [ ] Add Wiener process model
- [ ] Add compensation methods
- [ ] Commit

---

### Task 12-1: zak-transform.ipynb
**Files:**
- Create: `12-zak-transform/1-zak-transform.ipynb`

**Content:** Zak变换定义、性质、与FFT关系、OTFS应用

- [ ] Create notebook structure
- [ ] Implement Zak transform definition
- [ ] Add properties and proofs
- [ ] Add OTFS application examples
- [ ] Commit

---

## 第二阶段：进阶项目（章节13，共4个notebooks）

### Task 13-1: mimo-otfs.ipynb
**Files:**
- Create: `13-advanced-projects/1-mimo-otfs.ipynb`

**Content:** MIMO-OTFS系统模型、预编码、联合检测

- [ ] Create notebook structure
- [ ] Implement MIMO-OTFS system model
- [ ] Add precoding techniques
- [ ] Add joint detection algorithms
- [ ] Commit

---

### Task 13-2: end-to-end-otfs.ipynb
**Files:**
- Create: `13-advanced-projects/2-end-to-end-otfs.ipynb`

**Content:** 完整OTFS收发机链路、LDPC+OTFS、性能基准

- [ ] Create notebook structure
- [ ] Implement complete transmitter
- [ ] Add multipath channel model
- [ ] Implement complete receiver
- [ ] Add performance benchmarking
- [ ] Commit

---

### Task 13-3: research-frontier.ipynb
**Files:**
- Create: `13-advanced-projects/3-research-frontier.ipynb`

**Content:** OTFS研究前沿（高移动性、URLLC、卫星通信、感知通信）

- [ ] Create notebook structure
- [ ] Research current OTFS literature
- [ ] Document research frontiers
- [ ] Add future directions discussion
- [ ] Commit

---

### Task 13-4: practice-projects.ipynb
**Files:**
- Create: `13-advanced-projects/4-practice-projects.ipynb`

**Content:** 实践项目建议、代码框架、项目评估标准

- [ ] Create notebook structure
- [ ] Add project suggestions
- [ ] Provide code framework templates
- [ ] Add evaluation criteria
- [ ] Commit

---

## 第三阶段：重组现有内容（章节1-8）

### Task Reorg 1: fundamentals/
**Files:**
- Create: `1-fundamentals/1-communication-intro.ipynb`
- Create: `1-fundamentals/2-discrete-signals.ipynb`
- Create: `1-fundamentals/3-fourier-analysis.ipynb`

- [ ] Copy from 0-communication-basics/1-communication-intro.ipynb
- [ ] Copy from 0-communication-basics/2-discrete-signals.ipynb
- [ ] Copy from 0-communication-basics/3-fourier-analysis.ipynb
- [ ] Commit

---

### Task Reorg 2: signals-systems/
**Files:**
- Create: `2-signals-systems/1-lti-systems.ipynb`
- Create: `2-signals-systems/2-filters.ipynb`
- Create: `2-signals-systems/3-system-analysis.ipynb`
- Create: `2-signals-systems/4-sampling-reconstruction.ipynb`

- [ ] Copy from 0-communication-basics/4-lti-systems.ipynb
- [ ] Copy from 0-communication-basics/5-filters.ipynb
- [ ] Create new system analysis notebook
- [ ] Create new sampling reconstruction notebook
- [ ] Commit

---

### Task Reorg 3: modulation-basics/
**Files:**
- Create: `3-modulation-basics/1-analog-modulation.ipynb`
- Create: `3-modulation-basics/2-digital-modulation.ipynb`
- Create: `3-modulation-basics/3-qam-basics.ipynb`
- Create: `3-modulation-basics/4-noise-snr.ipynb`

- [ ] Copy from 0-communication-basics/6-analog-modulation.ipynb
- [ ] Copy from 0-communication-basics/7-digital-modulation.ipynb
- [ ] Copy from 0-communication-basics/8-qam-basics.ipynb
- [ ] Copy from 0-communication-basics/9-noise-and-snr.ipynb
- [ ] Commit

---

### Task Reorg 4: channels-receivers/
**Files:**
- Create: `4-channels-receivers/1-multipath-fading.ipynb`
- Create: `4-channels-receivers/2-rayleigh-rician.ipynb`
- Create: `4-channels-receivers/3-receiver-basics.ipynb`
- Create: `4-channels-receivers/4-communication-systems.ipynb`

- [ ] Copy from 0-communication-basics/10-multipath-fading.ipynb
- [ ] Create Rayleigh/Rician model notebook
- [ ] Copy from 0-communication-basics/11-receiver-basics.ipynb
- [ ] Copy from 0-communication-basics/12-communication-systems.ipynb
- [ ] Commit

---

### Task Reorg 5: chapters 5-8
**Files:**
- Create/Move: `5-signal-representations/` (from existing 1-signal-representations/)
- Create/Move: `6-channel-basics/` (from existing 2-channel-basics/)
- Create/Move: `7-modulation/` (from existing 3-modulation/)
- Create/Move: `8-mimo/` (from existing 4-mimo-basics/)

- [ ] Reorganize chapter 5
- [ ] Reorganize chapter 6
- [ ] Reorganize chapter 7
- [ ] Reorganize chapter 8
- [ ] Commit

---

## 最后：更新README

**Files:**
- Modify: `README.md`

- [ ] Update README with new 13-chapter structure
- [ ] Commit

---

## 实现顺序

```
Phase 1（核心补充，优先）:
  章节9 (matrix-coding) → 章节10 (estimation-detection) → 章节11 (synchronization) → 章节12 (zak-transform)

Phase 2（进阶项目）:
  章节13 (advanced-projects)

Phase 3（重组现有内容）:
  章节1-4 (重组0-communication-basics/) → 章节5-8 (重组现有内容)

最后:
  更新README
```

---

## 质量标准

每个notebook必须满足：
1. 所有代码可独立运行
2. 中文注释清晰
3. 图表使用中文标签
4. 学习目标明确
5. 思考题有深度