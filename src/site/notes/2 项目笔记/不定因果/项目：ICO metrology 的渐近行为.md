---
{"dg-publish":true,"permalink":"/2 项目笔记/不定因果/项目：ICO metrology 的渐近行为/","tags":["不定因果与因果结构","量子精密测量"]}
---

# 背景介绍与问题引入
我们旨在寻找一个参数化[[1 Stories of Bizzo's Life/5 量子科学和量子技术/量子信道\|量子信道]]族 $\{\mathcal{E}_g\}_{g \in \mathbb{R}}$，使得在该信道下，不定因果序（ICO）策略相较于并联（Para）策略的[[1 Stories of Bizzo's Life/5 量子科学和量子技术/32 量子测量\|量子测量]]优势（用[[1 Stories of Bizzo's Life/5 量子科学和量子技术/32 量子测量#Quantum Fisher Information\|量子Fisher信息量]]衡量）最大化。

## 相关领域
- [[1 Stories of Bizzo's Life/5 量子科学和量子技术/19 量子力学 泛函分析\|量子力学]]
- [[1 Stories of Bizzo's Life/5 量子科学和量子技术/32 量子测量\|量子测量]]
- [[1 Stories of Bizzo's Life/5 量子科学和量子技术/33 量子因果结构\|不定因果序]]
一个简短的从量子力学、不定因果序到精密测量的概要参见：
- [[不定因果×量子精密测量的数学概要\|不定因果×量子精密测量的数学概要]]

## 关键概念

**1. 量子费雪信息 (Quantum Fisher Information, QFI)**
   - **定义**: 量子参数估计精度的核心度量。对于依赖参数 $g$ 的量子态 $\rho_g$，QFI ($\mathcal{F}$) 量化了 $\rho_g$ 对参数变化的敏感度。
   - **物理意义**: 根据 **量子 Cramér-Rao 界 (QCRB)**，参数估计的方差下界由 QFI 的倒数给出：$\mathrm{Var}(\hat{g}) \ge \frac{1}{\nu \mathcal{F}}$（$\nu$ 为实验重复次数）。
   - **本文用法**: 我们通过最大化 $\mathcal{F}$ 来寻找最优策略。$\mathcal{F}$ 越大，测量精度越高。

**2. 标准量子极限 (Standard Quantum Limit, SQL)**
   - **定义**: 在经典统计或无纠缠量子资源下，参数估计精度的极限。
   - **标度律**: 对于 $N$ 个探针（或信道使用次数），QFI 随 $N$ 线性增长，即 $\mathcal{F} \propto N$（对应测量精度 $\Delta g \propto 1/\sqrt{N}$）。这是并联策略在大多数噪声信道下的渐近行为。

**3. 海森堡极限 (Heisenberg Limit, HL)**
   - **定义**: 量子力学允许的参数估计的最终极限，通常需要利用量子纠缠等资源才能达到。
   - **标度律**: QFI 随 $N$ 的平方增长，即 $\mathcal{F} \propto N^2$（对应测量精度 $\Delta g \propto 1/N$）。
   - **本文核心**: 我们探讨 ICO 策略是否不仅能达到 HL，还能在 $N^2$ 前的系数上超越传统的并联策略。

**4. Choi-Jamiołkowski 同构 (CJI) 与 Choi 矩阵**
   - **定义**: 建立在量子信道（CPTP 映射）与量子态（算符）之间的一一对应关系。
   - **数学表示**: 对于信道 $\mathcal{E}: L(\mathcal{H}_A) \to L(\mathcal{H}_B)$，其 Choi 矩阵 $\mathsf{E} := (\mathcal{I} \otimes \mathcal{E})(|\Omega\rangle\langle\Omega|)$ 是一个作用在 $\mathcal{H}_A \otimes \mathcal{H}_B$ 上的半正定算符（其中 $|\Omega\rangle$ 是未归一化最大纠缠态）。
   - **作用**: 将“寻找最优信道演化”的动力学问题转化为“优化 Choi 矩阵”的静态几何问题。

**5. 施廷斯普林扩张 (Stinespring Dilation)**
   - **定义**: 任何非幺正的量子信道（开放系统演化）都可以看作是系统与环境相互作用后的约化动力学。
   - **数学表示**: 对于信道 $\mathcal{E}(\rho)$，存在辅助环境系统 $E$ 和一个**等距算符 (Isometry)** $V$，使得 $\mathcal{E}(\rho) = \mathrm{tr}_E [V \rho V^\dagger]$。如果 $V$ 是幺正算符（Unitary），则称为幺正扩张。
   - **本文用法**: 用于证明 HL 的普适性上界。我们将非幺正信道“纯化”为幺正信道，利用幺正信道的性质导出界限。

**6. 过程矩阵 (Process Matrix) 与不定因果序 (ICO)**
   - **定义**: 描述量子操作之间因果关系的最一般数学框架。
   - **物理意义**: 标准量子力学假设事件以固定的时间顺序发生（如 A 在 B 之前）。过程矩阵允许因果顺序的**量子叠加**（例如“A 在 B 前”和“B 在 A 前”的叠加）。满足特定线性约束（$S \succeq 0, \mathcal{Q}_{\mathsf{ICO}}(S)=0$）的过程矩阵即代表 ICO 策略。

**7. Karush-Kuhn-Tucker (KKT) 条件**
   - **定义**: 非线性规划中判断最优解的**一阶必要条件**。对于满足Slater条件的凸优化问题（如本文中的 QFI 最大化），它也是充分条件。
   - **组成**: 包含平稳性条件（梯度为零）、原始可行性、对偶可行性以及**互补松弛条件 (Complementary Slackness)**。
   - **本文用法**: 我们通过构造满足 KKT 条件的对偶变量，严格证明某些策略（如完全混合策略）是全局最优解。

## 符号约定

*   **希尔伯特空间**: 对于 $N$ 次信道使用，输入和输出空间分别为 $T_{\text{tot}}^\mathrm{i} = \bigotimes_{k=1}^N T_k^\mathrm{i}$ 和 $T_{\text{tot}}^\mathrm{o} = \bigotimes_{k=1}^N T_k^\mathrm{o}$。
*   **信道**: 一个由单参数 $g$ 描述的量子信道 $\mathcal{E}_g$。其 Choi 矩阵记为 $\mathsf{E}_g$。
*   **信道表示**: 信道由其 Choi 矩阵的系综分解表示。对于 $N$ 个信道，总 Choi 矩阵 $\mathsf{E}_{\text{tot}}(g) = \mathsf{E}_g^{\otimes N}$ 分解为 $\mathsf{E}_{\text{tot}}(g) = \mathbf{C}_g^0 (\mathbf{C}_g^0)^\dagger$，其中 $\mathbf{C}_g^0$ 是线性算符。其关于参数 $g$ 的导数记为 $\dot{\mathbf{C}}_g^0$。
*   **性能算符**: 给定厄米矩阵 $h \in \mathbb{H}_q$，性能算符定义为 $\Omega_g(h) = 4 [ (\dot{\mathbf{C}}_g^0 - i \mathbf{C}_g^0 h) (\dot{\mathbf{C}}_g^0 - i \mathbf{C}_g^0 h)^\dagger ]^\top$。
*   **策略集**（可行域）:
    *   $\mathsf{ICO} = \{ S \succeq 0 \mid \mathrm{tr}(S)=d^N, \mathcal{Q}_{\mathsf{ICO}}(S)=0 \}$。其中投影超算符定义为 $\mathcal{Q}_{\mathsf{ICO}} =  \bigotimes_{k=1}^N ( \mathcal{I} - \mathcal{D}_{T_k^\mathrm{o}} + \mathcal{D}_{T_k^\mathrm{i} T_k^\mathrm{o}} )  - \mathcal{D}_{T_{\text{tot}}^\mathrm{i} T_{\text{tot}}^\mathrm{o}}=  \bigotimes_{k=1}^N ( \mathcal{I} - \mathcal{D}_{T_k^\mathrm{o}} + \mathcal{D}_{T_k^\mathrm{i} T_k^\mathrm{o}} )  - \bigotimes_{k=1}^N \mathcal{D}_{T_{k}^\mathrm{i} T_{k}^\mathrm{o}}$，这里 $\mathcal{D}_X$ 是子系统 $X$ 上的完全退极化信道。
    *   $\mathsf{Para} = \{ S = \rho \otimes \mathbb{I}_{T_{\text{tot}}^\mathrm{o}} \mid \rho \succeq 0, \mathrm{tr}(\rho)=1 \}$。

## 最优化问题

最大化 QFI 比值 $R(\mathcal{E}_g) = \mathcal{F}^{\mathsf{ICO}}_N(\mathcal{E}_g) / \mathcal{F}^{\mathsf{Para}}_N(\mathcal{E}_g)$ 的问题可表述为：

$$
\begin{aligned}
& \underset{\mathbf{C}_g^0, \dot{\mathbf{C}}_g^0}{\text{maximize}} 
& & R(\mathcal{E}_g)=\frac{\mathcal{F}^{\mathsf{ICO}}_N(\mathcal{E}_g) }{ \mathcal{F}^{\mathsf{Para}}_N(\mathcal{E}_g)} = \frac{\max_{S \in \mathsf{ICO}} \min_{h \in \mathbb{H}_q} \operatorname{tr}\left(\Omega_g(h) S\right)}{\max_{S' \in \mathsf{Para}} \min_{h' \in \mathbb{H}_q} \operatorname{tr}\left(\Omega_g(h') S'\right)} \\
& \text{subject to} 
& & \text{1. CPTP Condition:} \\
& & & \quad \mathrm{tr}_{T_{\text{tot}}^\mathrm{o}}\left( \mathbf{C}_g^0 (\mathbf{C}_g^0)^\dagger \right) = \mathbb{I}_{T_{\text{tot}}^\mathrm{i}} \\
& & & \text{2. Parameter Consistency:} \\
& & & \quad \mathrm{tr}_{T_{\text{tot}}^\mathrm{o}}\left( \dot{\mathbf{C}}_g^0 (\mathbf{C}_g^0)^\dagger + \mathbf{C}_g^0 (\dot{\mathbf{C}}_g^0)^\dagger \right) = 0 \\
& & & \text{3. Product Structure:} \\
& & & \quad \mathbf{C}_g^0 (\mathbf{C}_g^0)^\dagger = (\mathsf{E}_g)^{\otimes N} \quad \text{for some single-channel Choi matrix } \mathsf{E}_g.
\end{aligned}
$$

其中，优化变量 $(\mathbf{C}_g^0, \dot{\mathbf{C}}_g^0)$ 唯一确定了信道及其**局域**几何性质，进而通过 $\Omega_g(h)$ 决定了 QFI。约束条件确保了所描述的物理过程是合法的保迹量子信道及其在参数 $g$ 处的有效变化。

# 核心问题：ICO在量子计量学中的渐近优势边界

最大化QFI比值的问题是高度复杂、层层嵌套的最优化问题，对于有限的$N$执行数值最优化是非常困难的，但是在精密测量问题中，**我们往往只关心QFI关于$N$的增长速率**，且我们不需要从头开始，关于最优并联策略的渐近行为已经有相当多的分析了，我们可以从这些问题出发寻找ICO策略上界。

## 并联策略的渐近行为
一个著名且可达到的QFI上界在 [[Asymptotic Theory of Quantum Channel Estimation\|Asymptotic Theory of Quantum Channel Estimation]] (S. Zhou and L. Jiang, PRX Quantum 2, 010343) 等文献中有详细阐述：
$$
\mathcal{F}_N^{\mathsf{Para}}(\mathsf{E}_g) \le 4 \min_h \left[ N\|\alpha_h\| + N(N-1)\|\beta_h\|^2 \right]  \tag{B1}
$$
其中 $\alpha_h$ 和 $\beta_h$ 是通过对单个信道 $\mathcal{E}_g$ 的Kraus算符进行 $h$-参数化变换后得到的算符 $\alpha = \sum_i \dot{K}_i^\dagger \dot{K}_i$ 和 $\beta = \sum_i \dot{K}_i^\dagger K_i$  。这个界限揭示了两种不同的渐近标度行为：
1.  **海森堡标度 (HL)**: 如果对于所有的Kraus表示（即所有的 $h$），都有 $\|\beta_h\| \neq 0$，那么QFI的渐近标度为 $O(N^2)$，其主导项为 $4N^2 \min_h \|\beta_h\|^2$。
2.  **标准量子极限标度 (SQL)**: 如果存在一个 $h$ 使得 $\|\beta_h\| = 0$，那么QFI的渐近标度为 $O(N)$，其上界为：
    $$
    \mathcal{F}_N^{\mathsf{Para}}(\mathsf{E}_g) \le 4 N \min_{h: \|\beta_h\|=0} \|\alpha_h\|  \tag{B2}
    $$
这篇文章分别在HL情形和SQL情形中制作了一个**完美纠错码**和一个**近似纠错码**来达到这些上界。其中一个证明ICO没有渐近优势的方法就是利用他们制作的最优初态在这两种情况下分别近似满足ICO问题的KKT条件。

 **命题 (HNKS Condition Equivalence)**
设量子信道 $\mathcal{E}_g$ 由 Kraus 算符集 $\{K_i\}$ 描述。定义该信道的 **Kraus 张成空间 (Kraus Span)** $\mathcal{S}$ 为由所有 $K_i^\dagger K_j$ 线性组合生成的厄米算符空间：$\mathcal{S} := \mathrm{span}_{\mathbb{H}} \left\{ K_i^\dagger K_j \mid \forall i, j \right\}.$ 同时定义信道的 **有效哈密顿量 (Effective Hamiltonian)** $H$ 为：$H := i \sum_k K_k^\dagger \dot{K}_k$。

则以下两个条件是等价的：
1.  **无渐近参数依赖条件**: 对于任意可能的 Kraus 表示变换矩阵 $h$（对应于 $\beta(h) = \sum_k \dot{\tilde{K}}_k^\dagger \tilde{K}_k = 0$），总是存在某种表示使得 $\beta$ 消失。
2.  **哈密顿量不在 Kraus 张成空间内 (Hamiltonian-not-in-Kraus-span, HNKS)**:    $H \notin \mathcal{S}.$ 

**注记**:
*   如果 $H \in \mathcal{S}$，则信道受制于标准量子极限（SQL），即 $\mathcal{F} \sim O(N)$。
*   如果 $H \notin \mathcal{S}$，则信道在并在适当的量子纠错或控制下，能恢复出海森堡极限缩放 $\mathcal{F} \sim O(N^2)$。
*   显然蔡氏矩阵的秩等于Kraus算符用复数张成的线性空间的维度，但是$\mathcal{S}$的维度是如何确定的呢？
	* 对于非平凡的[[泡利信道\|泡利信道]]（例如完全退极化信道）来说，$\mathcal{S}$ 能够张成全空间，只能达到SQL。

## 渐近分析第一步：构建海森堡($N^2$)极限

本节阐明了海森堡极限（HL）在量子计量学中的普适性地位，证明了即使引入不定因果序（ICO）策略，量子参数估计的精度依然受到 $N^2$ 标度律的根本限制。核心结论及讨论如下：

1.  **HL 的普适性定理**：
    我们证明了对于任意 $N$ 次使用的量子信道 $\mathcal{E}_g$，其在任意 ICO 策略下的最大量子费雪信息（QFI） $\mathcal{F}_N^{\mathsf{Gen}}$ 均被该信道 Stinespring 扩张 $\mathcal{V}_g$ 的海森堡极限所约束，即 $\mathcal{F}_N^{\mathsf{Gen}}(\mathcal{E}_g) \le N^2 \mathcal{F}_1(\mathcal{V}_g)$。
    *   **幺正信道特例**：对于幺正信道，该上界是紧致且可饱和的。我们通过构造性的 KKT 证明指出，此时 ICO 策略并不优于最优并联策略，两者均严格达到 HL。

2.  **普适性证明逻辑**：
    *   **幺正情形**：基于凸优化和递归 KKT 条件，证明并联策略在 ICO 集合中的全局最优性。
    *   **普适情形**：利用 Stinespring 扩张定理将一般信道映射为更高维度的等距信道，并利用数据处理不等式将问题约化为幺正情形，从而确立 HL 的普适约束。

3.  **ICO 优势的边界分析**：
    通过对比我们的 **普适 ICO 上界** ($4N^2 \min \|\alpha\|$) 与现有的 **固定因果序上界** ($4N\|\alpha\| + 4N(N-1)\min \|\beta\|^2$)，我们量化了 ICO 策略的潜在优势空间。
    *   数学上，由于 $\|\beta\|^2 \le \|\alpha\|$，固定因果序上界始终小于等于 ICO 上界。
    *   两者间的差距（主导项为 $4N^2 (\|\alpha\| - \|\beta\|^2)$）界定了 ICO 策略在非幺正信道中可能超越固定顺序策略的最大渐近增益。

4.  **开放问题**：
    虽然 HL 确立了 $N^2$ 的硬性天花板，但在非幺正信道（噪声环境）下，ICO 策略是否能通过利用 $\|\alpha\| > \|\beta\|^2$ 的空间来实现 **渐近优势**（即获得比固定顺序策略更大的 $N^2$ 前系数），仍是一个极具价值的开放问题，有待通过寻找更紧致的单字母界来解决。

详见：[[Universality of the Heisenberg Limit in Quantum Metrology Across All Causal Structures#不定因果序（ICO）计量学的海森堡极限（HL）普适性\|Universality of the Heisenberg Limit in Quantum Metrology Across All Causal Structures#不定因果序（ICO）计量学的海森堡极限（HL）普适性]]

## HL上界不渐近紧：泡利信道无ICO优势且满足SQL

本节简要概述了关于广义泡利信道（Generalized Pauli Channels）在不定因果序（ICO）框架下计量精度的严格证明。我们证实，对于此类信道，ICO 策略所能达到的最大量子费雪信息（QFI）严格等同于最优并联策略，即 $\mathcal{F}_N^{\mathsf{ICO}} = \mathcal{F}_N^{\mathsf{Para}} = \frac{N}{\vartheta(1-\vartheta)}$。这表明在该模型下，ICO 资源无法提供海森堡极限的渐近优势，且我们提出的上界不是渐近紧的，存在一个仅$N$ scaling的例子。

证明主要基于凸优化框架下的 **Karush-Kuhn-Tucker (KKT) 条件**，核心逻辑如下：

1.  **候选解的构造**：基于 N-Choi 电路的物理直觉，我们构造了完全混合策略 $S^\star = \mathbb{I}/d^N$ 配合辅助参数 $h^\star=0$ 作为优化问题的候选鞍点。
2.  **互补松弛条件的利用**：利用 $S^\star$ 的严格正定性（满秩），结合 KKT 的互补松弛条件，我们在数学上推导出对偶变量 $Y$ 必须恒为零。这一关键洞察将复杂的半正定性验证问题简化为等式验证问题。
3.  **几何约束的代数验证**：证明最终归结为验证构造的对偶变量 $E$ 是否满足 ICO 的因果结构约束（即 $E$ 是否为投影算符 $\mathcal{Q}_{\mathsf{ICO}}$ 的不动点）。利用泡利信道 Choi 矩阵及其导数在偏迹操作下的特殊对称性，我们确认了这一几何条件成立，从而证明了候选解的全局最优性。

详见：[[泡利信道无ICO优势且满足SQL证明详情\|泡利信道无ICO优势且满足SQL证明详情]] 
## HL上界可以被非幺正的信道达到
- z轴旋转+比特翻转噪声(见下一节)满足$\|\beta\|^2=\|\alpha\|$，因此HL可以被达到，因此这种问题的Para最优就是ICO最优。这也符合数值试验的结果。

## ICO无渐近优势的证明思路

当前数值分析和物理直觉都表明实际上ICO没有任何渐近优势，即$R_N(\mathsf{E}_g) = \frac{\mathcal{F}^{\mathsf{ICO}}_N(\mathsf{E}_g)}{\mathcal{F}^{\mathsf{Para}}_N(\mathsf{E}_g)}\to 1~(N\to\infty)$，下面考虑其证明  
### 证明思路1：渐近KKT条件

*   **核心思想**: 尽管我们不知道最优并行策略 $S^*_{\text{Para}}$ 的确切形式，但 **Zhou and Jiang** 的工作告诉我们它的**结构性质**（即，它是在逻辑层面上的GHZ态或自旋压缩态的物理实现）。我们可以利用这些已知的结构性质，尝试为 $S^*_{\text{Para}}$ 构造一组“渐近满足”ICO问题KKT条件的对偶变量。为了分析比值 $R_N(\mathsf{E}_g) = \frac{\mathcal{F}^{\mathsf{ICO}}_N(\mathsf{E}_g)}{\mathcal{F}^{\mathsf{Para}}_N(\mathsf{E}_g)}$ 在 $N \to \infty$ 时的行为，我们需要为分子（ICO策略的QFI）建立一个有效的渐近上界，并与分母（并行策略的QFI）的已知渐近行为进行比较。对于作为分母的并行策略，其渐近行为已有深入研究（上一节）。

*   **关键步骤**:
    1.  写出适用于一般非幺正信道的、完整的**ICO问题KKT（鞍点）条件**。KKT条件详见tex文档章节 ：对 min-max 问题直接构建最优 ICO 策略的 KKT（鞍点）条件
    2.  将由 Zhou and Jiang 构造的最优并行策略（作为候选解）代入，最优初态分成HL和SQL两种情况。
    3.  利用该候选解的结构性质（如纯态、叠加态性质、算符期望值的渐近标度等）来简化KKT条件。
    4.  核心是证明**渐近互补松弛性**，即证明 $\lim_{N\to\infty} \frac{\operatorname{tr}(Y_N S^*_{\text{Para}})}{\mathcal{F}^{\mathsf{Para}}_N} = 0$。

为了能将这个思路推广到最一般的情形中，先对简单的例子来试验一下，已知噪声优先垂直退相干，即先做比特翻转错误再做z轴旋转能达到海森堡极限（[[噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界\|噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界]]）。

### 证明思路2：通过构造对偶上界来约束ICO的QFI（当前最优希望的路径）

我们的总体策略是为ICO策略下的最大QFI（$\mathcal{F}_N^{\text{ICO}}$）建立一个普适的**上界**，并证明这个上界在 $N\to\infty$ 的极限下，其主导项与已知的、可达到的并行策略QFI（这是一个**下界**）相吻合。
从最简单的能够达到海森堡极限的**噪声优先的垂直退相干**模型开始，这个模型的渐近最优初态不需要加入辅助系统，且最优初态是GHZ态，希望对这个模型的理解最终推广到一般的信道（以逻辑GHZ态为最优初态）中。

这个思路中碰到的一些过度缩放导致的失败参见 [[噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界\|噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界]] 。
#### 利用对偶性建立普适上界

1.  **问题的原始形式**: ICO的QFI是一个min-max问题：
    $$
    \mathcal{F}_N^{\text{ICO}}(\mathcal{E}_g) = \min_{h} \max_{S \in \text{ICO}} \text{tr}(\Omega(h)S)
    $$
2.  **对偶形式与上界**: 根据强对偶性，这个问题等价于其对偶问题。这为我们提供了一个关键的工具：对于**任何**特定的厄米矩阵 $h$ 和**任何**对偶变量 $E$，我们都能得到一个严格的上界：
    $$
    \mathcal{F}_N^{\text{ICO}}(\mathcal{E}_g) \le d_{\text{out}} ~ \left(  \|\Omega(h) - \mathcal{Q}_{\text{ICO}}^\dagger(E)\|_{\infty} \right)
    $$
3.  **选择Ansatz**: 为了使上界尽可能紧，我们选择一个物理意义明确的 $h$，即并行策略下的最优解 $h_{Para}^*$。对于垂直退相干模型，已经严格证明（[[噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界\|噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界]]） $h_{Para}^*=0$。因此，上界简化为：
    $$
    \mathcal{F}_N^{\text{ICO}}(\mathcal{E}_g) \le d_{\text{out}}^N \cdot \left( \min_{E} \|\Omega(0) - \mathcal{Q}_{\text{ICO}}(E)\|_{\infty} \right)
    $$

#### 两条失败的路径

这是整个证明的核心困难，我们排除了几种看似可行但实际无效的路径。

1.  **路径一：简单取 $E=0$ (不可行)**
    *   如果直接令 $E=0$，我们需要计算 $\|\Omega(0)\|_{\infty}$。
    *   **问题**: $\|\Omega(0)\|_{\infty}$ 是在整个算符空间上计算的范数，其最大本征态很可能不满足因果约束。这导致的上界过于松散，会随 $N$ **指数增长**，失去了作为物理界限的意义。
    * [[ICO策略下不同QFI的比较.nb\|ICO策略下不同QFI的比较.nb]]
	    * 取E=0来放大，指数增长

2.  **路径二：利用2-范数放缩 (不可行)**
    *   **思路**: 利用范数不等式 $\|\cdot\|_{\infty} \le \|\cdot\|_{F}$，并将关于 $E$ 的最小化问题转化为在2-范数下的最佳逼近问题，即计算 $\| \mathcal{P}_{\text{ICO}}(\Omega(0)) \|_{F}$。
    *   **问题**: 经过显式计算和阶数分析（如您在“2范数放缩垂直退相干ICO-QFI的粗略估计”中所做），我们发现 $\| \mathcal{P}_{\text{ICO}}(\Omega(0)) \|_{F}$ 的主导行为是 $O(N d^{N/2})$。这导致最终的QFI上界依然是**指数增长**的。
    *   **根本原因**: 2-范数（Frobenius范数）对算符的所有奇异值都敏感，而算符范数（$\|\cdot\|_{\infty}$）只关心最大的那一个。对于 $\Omega(0)$ 这样具有大量非零本征值的算符，两个范数之间存在指数级的差距。
    *   [[ICO策略下不同QFI的比较.nb\|ICO策略下不同QFI的比较.nb]]
	    * 用2-范数给出了一个上界，指数增长

#### 仍然可能可行的证明路径

排除了上述两种方法后，我们认识到必须**直接处理算符范数**以及对偶变量 $E$ 的作用。

1.  **核心表达式的几何意义**:
    $$
    \min_{E} \|\Omega(0) - \mathcal{Q}_{\text{ICO}}^\dagger(E)\|_{\infty}
    $$
    这个表达式的精确几何意义是：**算符 $\Omega(0)$ 到由 $\mathcal{Q}_{\text{ICO}}^\dagger$ 的像空间（即“非法”因果结构所张成的子空间）的距离**，该距离由算符范数度量。

2.  **最终猜想与待证明的环节**:
    结合下界和上界，我们强烈地推断出：
    $$
    \min_{E} \|\Omega(0) - \mathcal{Q}_{\text{ICO}}^\dagger(E)\|_{\infty} \leq \frac{(1-2p)^2 N^2}{d_{out}^N}
    $$
    **待证明的关键一步是**：证明通过选择一个足够好的非零对偶变量 $E_{opt}$，我们无法将上界 $\|\Omega(0) - \mathcal{Q}_{\text{ICO}}^\dagger(E_{opt})\|_{\infty}$ 的 $N^2$ 系数减小到 $(1-2p)^2$ 以下。物理直觉是，$\Omega(0)$ 的最大本征态（GHZ态）已经是一个合法的因果态，因此任何用于“惩罚”非法因果性的 $E$ 在这个方向上都无能为力。将这个物理直觉转化为严格的数学证明是完成此路径的最后一步。


### 证明思路 3：QFI的完整迭代公式（得到了能区分HL和SQL但不紧的界）

**核心思想**:
不再依赖于数值上的范数迭代放缩（如 Kurdziałek 等人针对定因果序策略的方法，这是更紧但是更难用的方法，有机会获得终极渐近界），而是利用 **$N$ 体性能算符 $\Omega^{(N)}$ 的精确代数结构** 与 **ICO 策略空间 $\mathcal{S}$ 的因果几何约束** 之间的相互作用。我们证明了，那些可能导致超海森堡标度（Super-Heisenberg scaling）或破坏标准量子极限（SQL）条件的项，会被 ICO 的因果结构“**结构性归零 (Structurally Nullified)**”。

**技术路线与主要结果**:

1.  **性能算符的闭合形式解**:
    通过求解关于信道数 $N$ 的线性递归关系，我们获得了 $N$ 体 ICO 系统总性能算符 $\Omega^{(N)}$ 的显式闭合表达式。其由局域项和非局域干涉项组成：
    $$
    \Omega^{(N)} = \underbrace{\sum \dots \Omega^{(1)} \dots}_{\text{Local } O(N)} + \underbrace{\frac{1}{4} \sum_{j<k} \left( \dots \Lambda_j \otimes \Lambda_k^\dagger \dots + \text{h.c.} \right)}_{\text{Non-local } O(N^2)}
    $$
    这一形式将复杂的 $N$ 体问题转化为对单信道干涉算符 $\Lambda$ 性质的分析。

2.  **正交分解与结构性归零 (Structural Nullification)**:
    这是证明中最关键的一步。我们将干涉算符分解为 $\Lambda = \Lambda^\parallel$（与并联策略相关的 $\beta$ 部分）和 $\Lambda^\perp$（在输出端无迹的正交部分）。利用 Oreshkov 等人关于过程矩阵的刻画定理（特别是两体过程矩阵 $W^{A_1 A_2 B_1 B_2}$ 中不存在同时激活 $B_1$ 和 $B_2$ 的非平凡项），我们证明了如下**结构性恒等式**：
    $$
    \operatorname{tr}\left[ (\Lambda_j^{\perp} \otimes \Lambda_k^{\perp \dagger}) S_{jk}^{\text{red}} \right] \equiv 0 \quad \forall S \in \mathsf{ICO}
    $$
    这意味着，看似可能导致松散界限的“纯噪声干涉项”在物理上是被 ICO 的因果结构严格禁止的。

3.  **上界**:
    结合上述两条，我们推导出了一个新的、物理意义明确的 QFI 上界：
    $$
    \mathcal{F}_{\mathsf{ICO}}^{(N)*} \le \min_{h} \left[ 4N \|\alpha_h\|_\infty + N(N-1) \left( 4 \|\beta_h\|_\infty^2 + 2d \|\beta_h\|_\infty \|\Lambda_h^\perp\|_\infty \right) \right]
    $$
    其中 $d$ 是希尔伯特空间维度。

**结论与意义**:

*   **渐近标度律的等价性**:
    *   **SQL 判据**: 当信道满足 $\beta_h=0$ (Hamiltonian-in-Kraus-span) 时，上式中 $O(N^2)$ 项的系数**严格为零**（因为每一项都包含 $\|\beta_h\|$ 因子）。这证明了 ICO 策略无法使 SQL 信道达到海森堡极限。
    *   **HL 判据**: 只有当 $\beta_h \neq 0$ 时，上界才允许 $O(N^2)$ 增长。这证明了 ICO 策略达到海森堡极限的充要条件与并联策略完全一致（HNKS 条件）。

*   **系数优势的物理来源**:
    尽管渐近标度相同，ICO 策略仍然可能通过第二项 $2d \|\beta\| \|\Lambda^\perp\|$ 获得常数倍的系数优势。这解释了为何在特定信道（如 $\Lambda^\perp$ 很大的信道）中 ICO 能表现出优于并联策略的性能——它利用不定因果序提取了 $\Lambda^\perp$ 中的相干性并将其与 $\beta$ 耦合。

2. **当前工具的局限性**： 对于最普适的 ICO (Gen) 策略，我们目前拥有的 **广义柯西-施瓦茨不等式** 及其在性能算符上的应用（如 Bound 2 的推导中所示）还不足以在不对称的交叉项上提供足够紧致的约束。Bound 2 的推导虽然在代数上消除了纯噪声项 ($\Lambda^\perp \otimes \Lambda^{\perp\dagger}$)，但 **未能消除信号-噪声交叉项** ($\Lambda^\parallel \otimes \Lambda^{\perp\dagger}$)，导致 $C_{\text{cross}}$ 最终保留下来。

3. **定因果序（AD/CS）的成功经验**： Kurdziałek 等人在 2023 年的工作中，正是采用了 **单步迭代** 的方法，成功地证明了在定因果序（AD/CS）策略下，QFI 的增长满足更紧的界限： $$a^{(i+1)} \le a^{(i)} + |\alpha| + 2|\beta|\sqrt{a^{(i)}}$$ 该迭代不等式的解（$a^{(N)} \le N^2 |\beta|^2$ 加上次导项）**自动压制了** $N^2$ 交叉项的出现，从而在不依赖于对 $C_{\text{cross}}$ 进行复杂代数分析的情况下，证明了 AD/CS 策略的渐近等价性,。
    


此证明很大程度上解决了关于 ICO 渐近优势的猜想，并给出了比 Kurdziałek 迭代界限更精细的结构性解释。详细推导见附件 [[通过迭代法找ICO-QFI上界\|通过迭代法找ICO-QFI上界]]。

#### 用完整迭代依然能够得到HL的界

- [[用性能算符的完整迭代得到HL界\|用性能算符的完整迭代得到HL界]] 

### 证明思路4：QFI的单步迭代公式与ICO策略的渐近行为

**核心思想**: 证明对于最一般的ICO策略，其QFI的单步增长也受到一个普适的迭代不等式约束，并且该不等式的解在渐近极限下与已知的所有定因果序策略（并行、自适应、因果叠加）的界限一致，从而确立它们的渐近等价性。

#### 1. 背景：定因果序策略的迭代界限

2023年的一项重要工作 (S. Kurdziałek et al., PRL 131, 090801) [[Using adaptiveness and causal superpositions against noise in quantum metrology\|Using adaptiveness and causal superpositions against noise in quantum metrology]] 证明，对于广义的自适应策略和因果叠加（CS）策略，其QFI的上界 $\mathcal{F}_N$ 满足如下的单步迭代不等式：
$$
a^{(i+1)} \le a^{(i)} + \|\alpha\| + 2\|\beta\| \sqrt{a^{(i)}}
$$
其中 $a^{(i)}$ 是 $i$ 次调用后的QFI上界（$\mathcal{F}_i/4$）。这个不等式的解给出了一个渐近紧致的界，其形式为 $4 \min_h \left[ N\|\alpha_h\| + N(N-1)\|\beta_h\|^2 \right]$。这意味着，在 $N \to \infty$ 的极限下，这些更复杂的定因果序策略相比并行策略**不存在渐近优势**。

#### 2. 将迭代方法推广至一般ICO策略

我们的核心任务是证明，对于由最一般的过程矩阵 $W$ 所描述的ICO策略，其QFI的渐近上界也遵循相似的结构。基于我们最新的推导结果 [[通过迭代法找ICO-QFI上界\|通过迭代法找ICO-QFI上界]]，我们已经为一般ICO策略下的QFI建立了一个精确的单步迭代公式。

首先，总的 $N$-通道性能算符 $\Omega^{(N)}$ 满足递推关系：
$$
\Omega^{(N)} = \Omega^{(N-1)} \otimes \mathsf{E}^\top + \mathsf{E}^{\otimes (N-1)\top} \otimes \Omega^{(1)} + \frac{1}{4}\left( \Lambda^{(N-1)} \otimes \Lambda^{(1)\dagger} + \text{h.c.} \right)
$$
对于任意策略 $S$，其QFI $\mathcal{F}^{(N)}(S) = \mathrm{tr}(S\Omega^{(N)})$ 相应地满足：
$$
\mathcal{F}^{(N)}(S) = \mathsf{H}_N(S) + \mathsf{L}_N(S) + \mathcal{F}_{\text{int}}(S)
$$
其中 $\mathsf{H}_N(S)$ 和 $\mathsf{L}_N(S)$ 分别是历史项和局域项，$\mathcal{F}_{\text{int}}(S)$ 是干涉项。

**关键步骤**: 我们通过广义算符柯西-施瓦茨不等式严格证明了干涉项被历史项和局域项的几何平均值所约束：
$$
|\mathcal{F}_{\text{int}}(S)| \le \frac{1}{2} \sqrt{\mathsf{H}_N(S) \cdot \mathsf{L}_N(S)}
$$
这直接导出了一个对**任意**半正定算符 $S$（包括非物理策略）都成立的普适迭代不等式：
$$
\mathcal{F}^{(N)}(S) \le \left( \sqrt{\mathsf{H}_N(S)} + \sqrt{\mathsf{L}_N(S)} \right)^2
$$

#### 3. 施加因果约束并求解上界

当我们将优化范围限制在物理上合法的ICO策略集 $\mathsf{Gen}$ 内时，因果约束保证了约化过程的物理性，从而有：
$$
\max_{S \in \mathsf{Gen}} \min_h \mathsf{H}_N(S) \le \mathcal{F}_{N-1}^{\mathsf{Gen}} \quad \text{and} \quad \max_{S \in \mathsf{Gen}} \min_h \mathsf{L}_N(S) \le \mathcal{F}_1^{\mathsf{Gen}}
$$
这最终导出了ICO策略最大QFI所必须服从的迭代不等式：
$$
\mathcal{F}_N^{\mathsf{Gen}} \le \left( \sqrt{\mathcal{F}_{N-1}^{\mathsf{Gen}}} + \sqrt{\mathcal{F}_1^{\mathsf{Gen}}} \right)^2
$$
该不等式的闭合形式解为 $\mathcal{F}_N^{\mathsf{Gen}} \le N^2 \mathcal{F}_1^{\mathsf{Gen}} = 4N^2 \min_h \|\alpha_h\|$，这正是我们在论文中提出的**界1 (Bound 1)**。

这个结果虽然已经证明了海森堡极限的普适性，但它在结构上比 Kurdziałek 等人的界更松，因为它没有显式地分离出由 $\beta$ 主导的渐近系数。

#### 4. 迈向更紧的界与渐近等价性

尽管数值试验 [[ICO策略下不同QFI的比较.nb\|ICO策略下不同QFI的比较.nb]] 发现ICO策略的QFI有时能够超过并行策略的上界，但我们的**界2 (Bound 2)**
$$
\mathcal{F}_N^{\mathsf{Gen}}(\mathcal{E}_g) \le \min_{\{K_i\}} \left[ 4N \|\alpha\| + N(N-1) \left( 4 \|\beta\|^2 + 2d \|\beta\| \|\Lambda^\perp\| \right) \right]
$$
已经通过对 `Λ` 算符的正交分解和利用ICO的“结构性归零”性质，在代数上证明了ICO策略的 $O(N^2)$ 项系数**必然**与 $\|\beta\|^2$ 和 $\|\beta\|\|\Lambda^\perp\|$ 有关。

**核心论点**: 当一个信道是SQL信道时（即存在一种Kraus分解使得 $\beta=0$），界2的 $O(N^2)$ 项严格为零。这证明了ICO策略无法将一个SQL信道提升为HL信道，确立了与并行/自适应策略相同的SQL/HL划分标准。

对于HL信道（$\min\|\beta\| \ne 0$），界2的 $N^2$ 系数 $4\|\beta\|^2 + 2d\|\beta\|\|\Lambda^\perp\|$ 与并行策略的系数 $4\|\beta\|^2$ 相比，多出了一项 $2d\|\beta\|\|\Lambda^\perp\|$。尽管数值上已经观察到对于某些信道，ICO策略可以在有限$N$时略微超越定序策略的界限，但这些证据表明这种超越可能是一个不依赖于$N$的常数，并不会改变 $O(N^2)$ 项的系数。一个合理的猜想是，ICO策略的渐近优势（即 $N \to \infty$ 时QFI的比值）为零。证明这一猜想是当前该领域的一个核心**开放问题**，其关键可能在于证明在最优策略下，信号-噪声交叉项的贡献是渐近次阶的，或者在KKT条件框架与大$N$极限下的代数和Kurdzialek中的迭代方法相结合。

- [[整理前的ICO-QFI单步迭代证明思路4\|整理前的ICO-QFI单步迭代证明思路4]] 


### 证明思路5：建立ICO策略与并联策略的关系
结合了证明思路2，但是基本失败了，参见[[噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界\|噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界]]

## 如果ICO能够提供渐近优势？
由于这是开放问题，我们不排除ICO提供渐近优势的可能，它可能在以下两种意义下提供渐近优势
- 式(B1)的结构保持不变，其中的标度的系数更大
- 式(B1)从根本上就是错误地 ，存在一些串并联联策略下无法达到海森堡极限，但是ICO能够达到海森堡极限的信道，这将是最令人以外的
如果ICO确实存在渐近优势，那么最有可能出现这种情况的信道，应该是那些**因果结构和噪声动力学高度耦合**的信道。例如，可以从已知的、在有限N下ICO优势最显著的信道（如旋转+幅值阻尼）出发
**两种优势**: 即使渐近等价性成立，ICO在有限N下的的优势仍然是巨大且有价值的。因此，另一个重要的研究方向是：**对于给定的噪声模型和资源限制**，如何系统性地找到最优的ICO策略，并量化其相比并行策略的具体优势大小？ 这正是 kurdzialek2024 (Tensor Network) 这篇文章试图解决的问题。

## 信道的QFI渐近行为与ICO优势汇总
当前的方法==只有能力证明ICO无优势==，因为我总是在验证解是否满足KKT条件。
- [[四种典型噪声：平行、垂直；退相干、振幅衰减\|四种典型噪声：平行、垂直；退相干、振幅衰减]] 这四种典型的噪声都被我进行了分类，见下。
### HL
 在并联策略下能够达到HL，即满足HNKS的信道，例如下面的：
#### ICO有优势
- 通过随机数值试验确认了满足条件的信道存在
	- 参见：[[ICO策略下不同QFI的比较.nb\|ICO策略下不同QFI的比较.nb]] 
		- 接收系综及其导数的QFI计算：存在ICO有优势且满足HL的信道
			- 根据随机系综判断是否满足HNKS 
			- 生成一个满足NHKS条件的随机系综
-  先经历垂直退相干噪声再经历z轴旋转，N=2没有出现优势，N=3才出现
	- [[噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界\|噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界]] 
	- [[ICO策略下不同QFI的比较.nb\|ICO策略下不同QFI的比较.nb]] 
		- 噪声先作用：模型 (a): 垂直退相干 (Perpendicular Dephasing)（比较ICO和FO）
### ICO无优势
 - 先z轴旋转+再经历比特翻转噪声（垂直退相干的另一个版本），可以完全纠正掉，得到最好的QFI，这种情况下应该不可能通过ICO获得更高的QFI，而且这是一种我们的上界得到饱和的例子也即$\|\beta\|^2=\|\alpha\|$
	 - [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		 - z轴旋转+比特翻转没有任何优势，达到海森堡极限的噪声信道。
		 - 信号先作用：模型 (a): 垂直退相干 (Perpendicular Dephasing)。→只有数值验证，没有严格证明
 - 绕着z轴和x轴的对角线旋转+比特翻转没有任何优势，达到海森堡极限的噪声信道。
### SQL
在并联策略不能达到HL的信道
#### ICO有优势
- 先作用退相干噪声再作用z轴旋转
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]]
		- 噪声先作用（更容易出现优势）：平行、垂直退相干；平行、垂直幅值衰减（比较ICO和FO）
			- 噪声先作用：模型 (b) : 平行退相干 (Parallel Dephasing)（比较ICO和FO）
- 广义[[幅值衰减\|幅值衰减]]+z旋转信道
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- z轴旋转+广义幅值阻尼 已知有优势 - 下面也是GAD信道，画更多的图
- 先AD噪声再z轴旋转
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- 噪声先作用：模型 (c): 垂直幅值阻尼 (Perpendicular Amplitude Damping)（比较ICO和FO）
- 先x轴的AD噪声再z轴旋转
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- 噪声先作用：模型 (d): 平行幅值阻尼 (Parallel Amplitude Damping)（比较ICO和FO）
- [[擦除信道\|擦除信道]]+z旋转
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- Erasure，有优势 N增长	
- [[AD复合比特翻转\|AD复合比特翻转]]+z旋转信道
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- Gemini：幅值-比特翻转信道 (Amplitude-Bit-Flip Channel, ABFC)
- 先z轴旋转+再退相干，测量z轴转角有优势，测量退相干强度没有优势，N=2没有，N=3才出现优势
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- 旋转+退相干 dephasing  或比特翻转 ，特定情况（sandwich，噪声+旋转+噪声）有优势
#### ICO无优势
- 泡利信道测量保持不变的概率，已经严格证明ICO无优势，在某些特殊的参数下无法达到HL（大概率是任何参数都不行）
	- [[new avai SPD data generation simCmdC0.nb\|new avai SPD data generation simCmdC0.nb]] 
		- 泡利信道：Mothe：专注于没有SQL的例子（我就需要一个例子来说明我们的界是松的）
## 其他可能有帮助的推导
### 性能算符的纯化表达式

本节的核心目标是为量子计量学中的[[性能算符\|性能算符]] $\Omega(h)$提供一个全新的、基于纯化的物理解释和数学表达式。

推导从量子信息的基本原理出发：一个混合末态 $\rho_\theta$ 的量子费雪信息（QFI）等于其所有可能纯化 $|\psi\rangle$ 的 QFI 的最小值。我们通过信道的施廷斯普林扩张（Stinespring Dilation）构造了末态的一个一般纯化 $|\psi\rangle = |V\rangle \star |w\rangle$，其中 $|V\rangle$ 是信道 Choi 矩阵的纯化，而 $|w\rangle$ 是策略 $W$ 的纯化。

推导的关键在于证明，遍历所有可能的信道纯化（这等价于在扩张的辅助空间 $A$ 上应用任意幺正变换 $U_A$）在数学上完全等价于遍历所有厄米矩阵 $h$（其中 $ih_A = U_A^\dagger \dot{U}_A$）。

最终，我们得到了性能算符的等价表达式：
$$
\Omega(h) \coloneqq 4 \left( \mathrm{tr}_A \left[ |\dot{V}(h)\rangle\langle\dot{V}(h)| \right] \right)^T
$$
其中 $|\dot{V}(h)\rangle \equiv |\dot{V}\rangle + (i\mathbb{I}_{T^\mathrm{io}} \otimes h_A)|V\rangle\in \mathcal{H}^{T^\mathrm{io}A}$ 是在特定纯化选择（由 $h$ 参数化）下的“有效导数”纯态。

这个表达式的意义在于，它将用于半定规划（SDP）的抽象代数对象 $\Omega(h)$ 与一个清晰的物理图像联系起来：**性能算符本质上是在最不利的纯化选择下，信道纯化态对参数变化的响应速度（速度模方）在系统空间上的投影。**

进一步利用$|V\rangle = \sum_{j=1}^q |K_j^\top \rangle \otimes |j\rangle_A$可以得到Kraus算符表述的性能算符
$$
\Omega(h) =4\sum_i \left(|\dot{K}_i^\top\rangle - i\sum_j h_{ji}|K_j^\top\rangle\right) \left(\langle\dot{K}_i^\top| + i\sum_k h_{ki}\langle K_k^\top|\right)= 4 \left( \sum_i | \dot{\tilde{K}}_i(h)^\top \rangle\rangle \langle\langle \dot{\tilde{K}}_i(h)^\top | \right)^\top= 4 \sum_i | \dot{\tilde{K}}_i(h)^\dagger\rangle\rangle \langle\langle \dot{\tilde{K}}_i(h)^\dagger | 
$$
其中$\dot{\tilde{K}}_i(h) = \dot{K}_i + i \sum_j h_{ij} K_j$ 。

具体推导参见： [[遍历Stinespring等距得到信道的QFI的证明#QFI纯化公式推导1：性能算符的另一种表达式\|遍历Stinespring等距得到信道的QFI的证明#QFI纯化公式推导1：性能算符的另一种表达式]] 

前面的公式都是$N$信道的，而单信道的Choi矩阵记为$\mathsf{E} \coloneqq \mathrm{tr}_A \left[ |V\rangle\langle V| \right] = \sum_m |K_m^\top \rangle\langle K_m^\top |$，满足$\mathrm{tr}_{out}\mathsf{E}=\mathbb{I}_{in}$
最好能够用到符号$$\alpha_h := \mathrm{tr}_{out}\left( \sum_i |\dot{\tilde{K}}_i^\top(h)\rangle \langle \dot{\tilde{K}}_i^\top(h)| \right)= \sum \dot{\tilde{K}}_i^\dagger(h)\dot{\tilde{K}}_i(h)$$
$$\beta_h=\mathrm{tr}_{out}\left( \sum_i |K_i^\top(h)\rangle \langle \dot{\tilde{K}}_i^\top(h)|\right)= \sum K_i^\dagger(h)\dot{\tilde{K}}_i(h)$$
偏迹不一定增加或者减小算符模，没有一般规律。考虑例子：$\mathrm{tr}_A:X\otimes I_A\mapsto d_A X$ 导致本征值放大以及将Bell态约化到最大混态导致本征值减小。
- [[通过迭代法找ICO-QFI上界\|通过迭代法找ICO-QFI上界]] 
## 关联材料和推导
- [[性能算符的迭代\|性能算符的迭代]] 
- [[最优化问题关于内部的考虑\|最优化问题关于内部的考虑]] 
- [[噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界\|噪声优先垂直退相干：Para-QFI、利用对偶性求ICO-QFI的上界]]
	- [[Detour：将ICO的投影超算符作用到性能算符上\|Detour：将ICO的投影超算符作用到性能算符上]] 
- [[张量网络凸优化与QFI数值程序\|张量网络凸优化与QFI数值程序]] 
- [[ICO无渐近优势的证明思路的进一步分析\|ICO无渐近优势的证明思路的进一步分析]] 

### 文章
来自 
- [[2 项目笔记/不定因果/Necessity of non-unitarity for metrological advantage of indefinite causal order\|Necessity of non-unitarity for metrological advantage of indefinite causal order]]
- [[Universality of the Heisenberg Limit in Quantum Metrology Across All Causal Structures\|Universality of the Heisenberg Limit in Quantum Metrology Across All Causal Structures]] 
### 其他
- [[Gemini\|Gemini]] https://aistudio.google.com/prompts/19hJ2mxIA_Tz_xF_BRdlPAZ3ghQ0YWIow 
- [[并联策略最优初态的分析\|并联策略最优初态的分析]] 
	- [[The elusive Heisenberg limit in quantum-enhanced metrology\|The elusive Heisenberg limit in quantum-enhanced metrology]] 
	-  [[Asymptotic Theory of Quantum Channel Estimation\|Asymptotic Theory of Quantum Channel Estimation]] (Zhou and Jiang): 奠基性工作。提出了**HNKS条件**作为判断信道能否达到海森堡极限的充要条件，并为HL和SQL两种情况分别构造了**可达的**QEC协议，证明了并行策略上界是渐近紧的。
	-  [[General framework for estimating the ultimate precision limit in noisy quantum-enhanced metrology\|General framework for estimating the ultimate precision limit in noisy quantum-enhanced metrology]] (Escher et al.): 早期的奠基性工作，通过“环境纯化”方法，将对初态的优化转化为对Kraus算符表示的优化，为后续的QFI界限研究奠定了基础。
- [[2 项目笔记/不定因果/Necessity of non-unitarity for metrological advantage of indefinite causal order\|Necessity of non-unitarity for metrological advantage of indefinite causal order]]: 您的核心工作，严格证明了在**幺正信道**估计中，ICO策略相比并行策略没有优势。其核心方法是为最优并行策略构造了一组满足ICO问题KKT条件的对偶变量。
- [[0 fleeting/论文阅读笔记/Reassessing the advantage of indefinite causal orders for quantum metrology\|Reassessing the advantage of indefinite causal orders for quantum metrology]] (Mothe et al.): 通过SDP数值方法，系统性地比较了不同策略类别（包括QC-CC, QC-QC）在有限$N$下的性能。首次清晰地区分了哪些信道（如退偏振）ICO无优势，哪些信道（如旋转+幅值阻尼）ICO有优势。
- [[Optimal Strategies of Quantum Metrology with a Strict Hierarchy\|Optimal Strategies of Quantum Metrology with a Strict Hierarchy]] (Liu et al.): 提供了将不同策略（并行、串行、因果叠加、通用ICO）下的QFI优化问题转化为SDP的统一框架，并能数值地重构出最优策略。他们的数值结果证实了策略间的严格层级关系。
- [[Using adaptiveness and causal superpositions against noise in quantum metrology\|Using adaptiveness and causal superpositions against noise in quantum metrology]] (Kurdziałek et al.)： 解决了“并行策略 vs. 自适应/因果叠加策略”的渐近等价性猜想。核心工具是**迭代QFI界限**，证明了对于`CS`策略，其渐近性能与并行策略相同。
- Kimi的分析材料：解决思路：证明ICO策略相比并行策略没有渐近优势.pdf
- [[Variational Analysis\|Variational Analysis]] 
# 松散的内容
- [[项目：ICO metrology 的渐近行为松散的内容\|项目：ICO metrology 的渐近行为松散的内容]] 
- [[ICO metrology项目提示词\|ICO metrology项目提示词]] 

