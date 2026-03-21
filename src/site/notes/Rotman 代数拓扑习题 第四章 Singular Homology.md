---
{"dg-publish":true,"permalink":"/Rotman 代数拓扑习题 第四章 Singular Homology/"}
---

## Holes and Green's Theorem

## Free Abelian Groups


### 4.1 自由阿贝尔群基底的拆分性质

**证明过程：**

1. **分量的构造**：已知 $F$ 是以 $B$ 为基底的自由阿贝尔群。由于 $B = \bigcup B_\lambda$ 是不相交并集，对于每个 $\lambda,$ 定义 $F_\lambda$ 为由 $B_\lambda$ 生成的子群。根据定义，$F_\lambda$ 是以 $B_\lambda$ 为基底的自由阿贝尔群。
2. **直和关系的确立**：由于 $B$ 是 $F$ 的基底，每一个元素 $\gamma \in F$ 都可以唯一地表示为 $\gamma = \sum_{b \in B} m_b b,$ 其中 $m_b \in \mathbb{Z}$ 且几乎所有 $m_b$ 为 0。
3. **唯一性结论**：对于每个 $\lambda,$ 设 $\gamma_\lambda = \sum_{b \in B_\lambda} m_b b.$ 显然 $\gamma_\lambda \in F_\lambda,$ 且 $\gamma = \sum \gamma_\lambda$。由于基底 $B$ 的线性组合表示是唯一的，且 $B_\lambda$ 之间两两不相交，因此 $\gamma$ 分解为各个 $\gamma_\lambda$ 之和的方式也是唯一的。同时，因为只有有限个 $m_b \neq 0,$ 所以只有有限个 $\gamma_\lambda \neq 0$。

---

### 4.2 自由阿贝尔群同构与秩的关系

**证明过程：**

1. **必要性 ($\implies$)**：假设 $f: F \to F'$ 是同构映射。若 $B$ 是 $F$ 的一组基底，则其像 $f(B)$ 必然是 $F'$ 的一组基底。由于 $f$ 是双射，基底 $B$ 与 $f(B)$ 的势（Cardinality）相同。根据秩的定义，$\text{rank } F = \text{rank } F'$。
2. **充分性 ($\impliedby$)**：假设 $\text{rank } F = \text{rank } F',$ 这意味着它们各自的基底 $B$ 与 $B'$ 具有相同的势。因此存在一个双射 $\phi: B \to B'$。根据自由阿贝尔群的泛性质，该双射可以唯一地线性扩张为一个群同态 $\Phi: F \to F'$。由于 $\Phi$ 在基底上是双射，它是一个群同构。

---

### 4.3 奇异 0-链与 1-链的边缘算子性质

**证明过程：**

- **(i) 证明 $\partial_1$ 是同态**： 由于 $S_1(X)$ 是以所有路径 $\sigma: I \to X$ 为基底生成的自由阿贝尔群，根据基底映射的线性扩张定理（Theorem 4.1），存在唯一的同态 $\partial_1: S_1(X) \to S_0(X),$ 使得对每个基底元素 $\sigma$ 满足 $\partial_1 \sigma = \sigma(1) - \sigma(0)$。
    
- **(ii) 证明 $x_1 - x_0 \in \text{im } \partial_1 \iff x_0, x_1$ 属于同一路分支**：
    
    - **充分性**：若 $x_0, x_1$ 在同一路分支，则存在连续路径 $\sigma$ 使得 $\sigma(0)=x_0, \sigma(1)=x_1$。此时 $\partial_1 \sigma = x_1 - x_0,$ 故 $x_1 - x_0 \in \text{im } \partial_1$。
    - **必要性**：假设 $x_1 - x_0 \in \text{im } \partial_1.$ 定义映射 $\phi: S_0(X) \to \mathbb{Z},$ 将 $x_0$ 所在路分支内的点映为 1，其余点映为 0。对于任意路径 $\sigma,$ 其端点 $\sigma(0), \sigma(1)$ 必在同一分支，故 $\phi(\sigma(1) - \sigma(0)) = 0,$ 从而 $\phi(\text{im } \partial_1) = 0$。若 $x_1$ 不在 $x_0$ 的分支，则 $\phi(x_1 - x_0) = 0 - 1 = -1 \neq 0,$ 产生矛盾。
- **(iii) 证明 $\text{ker } \partial_1$ 与闭路径的关系及示例**：
    
    - **判定**：对于单一路径 $\sigma \in S_1(X),$ $\partial_1 \sigma = \sigma(1) - \sigma(0) = 0$ 当且仅当 $\sigma(1) = \sigma(0),$ 即 $\sigma$ 是闭路径。
    - **非闭路径的核元素示例**：设 $\sigma$ 是从点 $x$ 到 $y$ 的路径，$\tau$ 是另一条从 $x$ 到 $y$ 的不同路径。考虑 1-链 $\gamma = \sigma - \tau.$ 则 $\partial_1 \gamma = (y - x) - (y - x) = 0,$ 因此 $\gamma \in \text{ker } \partial_1,$ 但 $\gamma$ 作为一个链，其组成部分 $\sigma$ 和 $\tau$ 都不是闭路径。
## The Singular Complex and Homology Functors

## Dimension Axiom and Compact Supports

### 习题 4.4：证明若 $X = \emptyset$，则 $H_n(X) = 0$ 对所有 $n \ge 0$ 成立

**证明过程：**

1. **单形不存在性**：由于没有从标准 $n$-单形 $\Delta^n$ 到空集 $\emptyset$ 的连续映射 $\sigma: \Delta^n \to \emptyset$，因此不存在任何奇异 $n$-单形。
2. **链群的平凡性**：奇异链群 $S_n(X)$ 是以所有奇异 $n$-单形为基底生成的自由阿贝尔群。因为基底为空，所以 $S_n(\emptyset)$ 是平凡群 ${0}$。
3. **同调群结论**：由于所有的 $S_n(\emptyset) = 0$，其闭链群 $Z_n$ 和边缘链群 $B_n$ 显然也均为 $0$。根据定义 $H_n(X) = Z_n/B_n$，得出 **$H_n(\emptyset) = 0$**。

---

### 习题 4.5：证明若 $X$ 是单点空间，则 $H_0(X) \cong \mathbb{Z}$

**证明过程：**

1. **确定链群**：对于单点空间 $X = {x_0}$，在任何维度 $n \ge 0$ 下，都仅有一个奇异 $n$-单形 $\sigma_n$（即常数映射）。因此，每个 $S_n(X)$ 都是由 $\sigma_n$ 生成的无限循环群 $\mathbb{Z}$。
2. **分析边缘算子**：
    - 对于 $n=0$，边缘算子 $\partial_0: S_0(X) \to 0$ 必然是零映射，故 **$\ker \partial_0 = S_0(X) \cong \mathbb{Z}$**。
    - 对于 $n=1$，根据维度公理的证明，$\partial_1 \sigma_1 = \sigma_0 - \sigma_0 = 0$。因此 $B_0(X) = \text{im } \partial_1 = 0$。
3. **计算同调群**： 
4. $$H_0(X) = Z_0(X) / B_0(X) \cong \mathbb{Z} / {0} \cong \mathbb{Z}$$ 由此得证，单点空间的第零同调群与整数加法群同构。

---

### 习题 4.6：证明对于固定的 $n \ge 0$，$S_n: \mathsf{Top} \to \mathsf{Ab}$ 是一个函子

**证明过程：**

1. **对象映射**：函子 $S_n$ 将每个拓扑空间 $X$ 映射为其奇异 $n$-链群 $S_n(X)$，这是一个阿贝尔群。
2. **态射映射**：对于连续映射 $f: X \to Y$，$S_n$ 诱导一个同态 $f_\#: S_n(X) \to S_n(Y)$。其定义为对基底元素 $\sigma$ 满足 $f_\#(\sigma) = f \circ \sigma$，并线性扩张至整个群。
3. **验证函子公理**：
    - **恒等映射**：对于恒等映射 $1_X$，$(1_X)_\#(\sigma) = 1_X \circ \sigma = \sigma$，因此 $(1_X)_\# = 1_{S_n(X)}$，保持恒等态射不变。
    - **复合映射**：若有连续映射 $f: X \to Y$ 和 $g: Y \to Z$，则对于任意 $\sigma \in S_n(X)$： 
    - $$(g \circ f)_\#(\sigma) = (g \circ f) \circ \sigma = g \circ (f \circ \sigma) = g_\#(f_\#(\sigma))$$ 这说明 $(g \circ f)_\# = g_\# \circ f_\#$，满足复合保持性。
4. **结论**：$S_n$ 满足函子的所有定义条件。

### 习题 4.7：计算 $S^0$ 的同调群 $H_n(S^0)$ 对所有 $n \ge 0$

**证明过程：**

1. **确定空间的结构**： $S^0$ 是 0 维球面，由两个离散的点 ${1, -1}$ 组成。这两个点构成了 $S^0$ 的两个不同的路分支。
    
2. **应用路分支分解定理**： 根据定理 4.13，一个空间的奇异同调群等于其所有路分支同调群的直和。因此有： 
3. $$H_n(S^0) \cong H_n({1}) \oplus H_n({-1}) \text{}$$
    
3. **应用维度公理**： 维度公理指出，对于单点空间 ${pt}$，当 $n=0$ 时 $H_0({pt}) \cong \mathbb{Z}$，而当 $n > 0$ 时 $H_n({pt}) = 0$。
    
4. **分情况计算结果**：
    
    - **当 $n = 0$ 时**：$H_0(S^0) \cong \mathbb{Z} \oplus \mathbb{Z}$。
    - **当 $n > 0$ 时**：$H_n(S^0) \cong 0 \oplus 0 = 0$。

**结论：** $H_n(S^0) \cong \mathbb{Z} \oplus \mathbb{Z}$ (若 $n=0$)，且 $H_n(S^0) = 0$ (若 $n > 0$)。

---

### 习题 4.8：计算 Cantor 集 $X$ 的同调群 $H_n(X)$ 对所有 $n \ge 0$

**证明过程：**

1. **确定 Cantor 集的路分支**： Cantor 集是一个完全不连通的空间，其每一个路分支都仅包含一个点。这意味着 Cantor 集可以被视为大量单点路分支的并集。
    
2. **计算第零同调群 $H_0(X)$**： 根据定理 4.14(ii)，$H_0(X)$ 是秩等于路分支数量的自由阿贝尔群。由于 Cantor 集包含不可数个点（在代数拓扑背景下有时简化讨论其由点集生成的自由群结构），其第零同调群为所有单点分支对应的整数群的直和：
 $$H_0(X) \cong \bigoplus_{x \in X} \mathbb{Z}$$
    
3. **计算高阶同调群 $H_n(X)$ ($n > 0$)**： 由于每个路分支 $X_\lambda$ 都是单点空间，根据维度公理，当 $n > 0$ 时 $H_n(X_\lambda) = 0$。应用路分支分解定理，所有这些平凡群的直和仍然是平凡的。
    

**结论：** 对于 Cantor 集 $X$，$H_0(X) \cong \bigoplus_{x \in X} \mathbb{Z}$，而对于所有 $n > 0$，$H_n(X) = 0$。

## The Homotopy Axiom
### 习题 4.9 棱柱的相关公式

针对 Rotman 习题 4.9 及其证明中涉及的符号，以下是按逻辑顺序整理的记号列表及其自完备定义：

#### 空间与基础记号

- **$\Delta^n$ (标准 $n$-单形)**：$\mathbb{R}^{n+1}$ 中由顶点 $e_0, \dots, e_n$ 张成的凸子集，即 $\sum t_i = 1$ 且 $t_i \ge 0$ 的点集。
- **$I$ (单位区间)**：即闭区间 $I$。
- **$a_i, b_i$ (棱柱顶点)**：积空间 $\Delta^n \times I$ 中的特定点。$a_i = (e_i, 0)$ 位于底面，$b_i = (e_i, 1)$ 位于顶面。
- **$[v_0, \dots, v_k]$ (仿射单形)**：表示将标准单形的顶点有序映射到指定点集 ${v_i}$ 的唯一仿射映射。（和凸集的记号重复了，但是恰到好处）

#### 算子与映射

- **$\partial_n$ (边缘算子)**：链群间的同态 $\partial_n: S_n(X) \to S_{n-1}(X)$。对于单形 $\sigma$，$\partial_n \sigma = \sum (-1)^i \sigma \epsilon_i^n$，其中 $\epsilon_i^n$ 是面映射。
- **$f_\#$ (诱导链映射)**：由连续映射 $f: X \to Y$ 诱导的单形复合映射，满足 $f_\#(\sigma) = f \circ \sigma$。
- **$\lambda^i$ (包含映射)**：定义为 $\lambda^i: X \to X \times I, x \mapsto (x, i)$，其中 $i \in {0, 1}$，将空间分别嵌入到积空间的底部或顶部。
- **$P_n$ ([[棱柱\|棱柱]]算子/Prism Operator)**：从 $S_n(X)$ 到 $S_{n+1}(X \times I)$ 的自然变换。它通过将 $n$-单形拉伸为 $(n+1)$-单形的组合，构造同伦公理中的链同伦映射。
	- **$P_n(\sigma)=(\sigma\times 1)_\# \beta_{n+1}$ 
- **$\delta$ (恒等链)**：指 $\Delta^n \to \Delta^n$ 的恒等映射。在证明中，它被视为 $S_n(\Delta^n)$ 的基底元素。
- **$\beta_{n+1}$ (剖分链)**：$S_{n+1}(\Delta^n \times I)$ 中的一个特定链，定义为 $\sum_{i=0}^n (-1)^i [a_0, \dots, a_i, b_i, \dots, b_n]$。它代表了将柱体 $\Delta^n \times I$ 剖分为单形的代数和。


#### 习题 4.9(i)：棱柱算子公式在 $n=0, 1$ 时的验证

**证明过程：**

我们需要验证公式：
$$\partial_{n+1} \beta_{n+1} = (\lambda^1_{\#n} - \lambda^0_{\#n} - P_{n-1} \partial_n)(\delta)$$

#### 1. 当 $n=0$ 时：

- **计算左边 (LHS)**：
    - 根据定义，$\beta_1 = [a_0, b_0]$，这是一个从 $\Delta^1$ 到 $\Delta^0 \times I$ 的映射。
    - $\partial_1 \beta_1 = \beta_1(e_1) - \beta_1(e_0) = b_0 - a_0$。
- **计算右边 (RHS)**：
    - 已知 $P_{-1}$ 是零映射。
    - $\lambda^1_{\#0}(\delta) = \lambda^1(e_0) = (e_0, 1) = b_0$。
    - $\lambda^0_{\#0}(\delta) = \lambda^0(e_0) = (e_0, 0) = a_0$。
    - 因此，$(\lambda^1_{\#0} - \lambda^0_{\#0} - P_{-1} \partial_0)(\delta) = b_0 - a_0$。
- **结论**：LHS = RHS，公式在 $n=0$ 时成立。

---
#### 2. 当 $n=1$ 时：

这是最容易出现“差一个负号”的地方，请重点核对第 (2) 步中的分配律。

- **（1）计算左边 (LHS)**：
    
    - 根据公式 $\beta_{n+1} = \sum_{i=0}^n (-1)^i [a_0, \dots, a_i, b_i, \dots, b_n]$。
    - 对于 $n=1$，$\beta_2 = [a_0, b_0, b_1] - [a_0, a_1, b_1]$。
    - 计算边缘：
        - $\partial_2 [a_0, b_0, b_1] = [b_0, b_1] - [a_0, b_1] + [a_0, b_0]$。
        - $\partial_2 [a_0, a_1, b_1] = [a_1, b_1] - [a_0, b_1] + [a_0, a_1]$。
    - **相减合并**： 
    - $$\partial_2 \beta_2 = ([b_0, b_1] - [a_0, b_1] + [a_0, b_0]) - ([a_1, b_1] - [a_0, b_1] + [a_0, a_1])$$ $$\partial_2 \beta_2 = [b_0, b_1] - [a_0, b_1] + [a_0, b_0] - [a_1, b_1] + [a_0, b_1] - [a_0, a_1]$$ $$LHS = [b_0, b_1] + [a_0, b_0] - [a_1, b_1] - [a_0, a_1]$$
- **（2）计算右边 (RHS)**：
    
    - 公式为 $(\lambda^1_{\#1} - \lambda^0_{\#1} - P_0 \partial_1)(\delta)$。
    - **前两项**：$(\lambda^1_{\#1} - \lambda^0_{\#1})(\delta) = [b_0, b_1] - [a_0, a_1]$。
    - **第三项 $P_0 \partial_1 \delta$**：
        - $\partial_1 \delta = e_1 - e_0$。
        - 由棱柱算子定义，$P_0(e_i) = [a_i, b_i]$。
        - 因此 $P_0 \partial_1 \delta = [a_1, b_1] - [a_0, b_0]$。
    - **合并（关键的负号分配）**： 
    - $$RHS = ([b_0, b_1] - [a_0, a_1]) - ([a_1, b_1] - [a_0, b_0])$$ 注意：减去括号里的项时，$-[a_0, b_0]$ 会变成 **正的** $+ [a_0, b_0]$： 
    - $$RHS = [b_0, b_1] - [a_0, a_1] - [a_1, b_1] + [a_0, b_0]$$
- **结论**： 对比 LHS 和 RHS，每一项的符号现在完全一致： $$[b_0, b_1] + [a_0, b_0] - [a_1, b_1] - [a_0, a_1]$$ 公式在 $n=1$ 时成立。
    
这个单形作用在$\Delta^1$的两个顶点上得到相同的结果，这意味着它是闭链（因为用边缘算子作用上去就意味着计算它在两个顶点处的差）。显然是闭链，因为它是边缘链。
#### 习题 4.9(ii)：给出 $P_1^X(\sigma)$ 的显式公式

根据教材 Rotman《代数拓扑导论》及配套解答，棱柱算子 $P_n^X$ 的核心在于将积空间 $\Delta^n \times I$ 剖分为 $(n+1)$-单形。

**证明过程：**

1. **定义基础结构**： 棱柱算子 $P_n^X: S_n(X) \to S_{n+1}(X \times I)$ 定义为 $P_n^X(\sigma) = (\sigma \times 1)_\# (\beta_{n+1})$。对于 $n=1$，我们需要确定 $\beta_2 \in S_2(\Delta^1 \times I)$ 的表达式。
    
2. **写出 $\beta_2$ 的剖分公式**： 根据公式 $\beta_{n+1} = \sum_{i=0}^n (-1)^i [a_0, \dots, a_i, b_i, \dots, b_n]$，其中 $a_i = (e_i, 0)$ 且 $b_i = (e_i, 1)$ 是 $\Delta^n \times I$ 中的顶点。 对于 $n=1$，$\beta_2$ 由两个 2-单形组成： $$\beta_2 = [a_0, b_0, b_1] - [a_0, a_1, b_1]$$ 这里的方括号表示将 $\Delta^2$ 的顶点有序映射到 $\Delta^1 \times I$ 对应点的仿射映射。
    
3. **计算各分量映射的重心坐标表示**： 设 $(t_0, t_1, t_2)$ 为 $\Delta^2$ 的重心坐标。我们需要分析 $\beta_2$ 如何将这些坐标映射到 $\Delta^1 \times I$ 中：
    
    - **第一项 $[a_0, b_0, b_1]$**：将重心坐标映射为 $t_0 a_0 + t_1 b_0 + t_2 b_1 = ((t_0+t_1)e_0 + t_2 e_1, t_1 + t_2)$。
    - **第二项 $[a_0, a_1, b_1]$**：将重心坐标映射为 $t_0 a_0 + t_1 a_1 + t_2 b_1 = (t_0 e_0 + (t_1+t_2) e_1, t_2)$。
4. **得出 $P_1^X(\sigma)$ 的最终公式**： 将 $\sigma \times 1$ 复合到上述映射上。在 $\Delta^1$ 中，点 $(1-s)e_0 + s e_1$ 通常由参数 $s$ 标识。 因此，对于 1-单形 $\sigma: \Delta^1 \to X$，公式 $P_1^X(\sigma): \Delta^2 \to X \times I$ 为： $$P_1^X(\sigma)(t_0, t_1, t_2) = (\sigma(t_2), t_1 + t_2) - (\sigma(t_1 + t_2), t_2)$$ 其中第一项代表在时间段内“向上”倾斜的单形，第二项代表“向下”倾斜的单形，两者的差值构成了 1-单形在积空间中的“棱柱面”。
    

**结论**： 该显式公式提供了 1-单形通过棱柱算子转化为积空间 2-链的具体几何表达。
### 习题 4.10 证明：棱柱算子 $P_n$ 的自然性

**证明过程：**

设 $j: X \to Y$ 为连续映射，$\sigma: \Delta^n \to X$ 为 $X$ 中的一个奇异 $n$-单形。根据棱柱算子 $P_n$ 的定义 $P_n^X(\sigma) = (\sigma \times 1)_\#(\beta_{n+1})$，我们验证交换图的两个路径：

1. **先作用 $P_n^X$ 再作用 $(j \times 1)_\#$**： 
2. $$(j \times 1)_\# (P_n^X(\sigma)) = (j \times 1)_\# ((\sigma \times 1)_\#(\beta_{n+1}))$$ 根据诱导链映射的复合性质 $(g \circ f)_\# = g_\# \circ f_\#$： 
3. $$= ((j \times 1) \circ (\sigma \times 1))_\# (\beta_{n+1}) = ((j \circ \sigma) \times 1)_\# (\beta_{n+1})$$
    
2. **先作用 $j_\#$ 再作用 $P_n^Y$**： $$P_n^Y (j_\#(\sigma)) = P_n^Y (j \circ \sigma)$$ 代入 $P_n^Y$ 在 $Y$ 上的定义： $$= ((j \circ \sigma) \times 1)_\# (\beta_{n+1})$$
    

**结论**： 由于两组公式完全相等，且 $P_n$ 对链群中单形的线性组合同样成立，因此 $(j \times 1)_\# P_n^X = P_n^Y j_\#$，即 $P_n$ 是一个自然变换。

---

#### 几何直观说明

棱柱算子 $P_n$ 的几何本质是将一个 $n$-单形沿“时间”轴 $I$ 拉伸，构造出积空间中的一个“奇异棱柱”（即一组 $(n+1)$-单形的和）。

**自然性** 的几何意义在于：

- **路径一**：先在空间 $X$ 中把单形 $\sigma$ “拉伸”成棱柱，然后再通过映射 $j$ 把整个棱柱搬移到空间 $Y \times I$ 中。
- **路径二**：先通过映射 $j$ 把单形 $\sigma$ 搬移到空间 $Y$ 中，然后再在 $Y$ 中将其“拉伸”成棱柱。

由于映射 $j$ 只作用于空间坐标而保持时间坐标 $I$ 不变，这两种操作的结果在几何上是完全重合的。这意味着**棱柱构造与空间的连续映射是相容的**。

### 习题 4.11：形变收缩核的同调性质证明

**证明过程：**

1. **同伦等价的确立**：若 $X$ 是 $Y$ 的[[形变收缩核\|形变收缩核]]，根据定义，存在包含映射 $i: X \hookrightarrow Y$ 和连续收缩映射 $r: Y \to X$，满足 $r \circ i = 1_X$ 且 $i \circ r \simeq 1_Y$（即 $i \circ r$ 同伦于 $Y$ 上的恒等映射）。这说明 $X$ 与 $Y$ 具有相同的同伦型。
2. **应用同伦公理**：根据同调论的同伦公理（Theorem 4.23），同伦的连续映射在同调群上诱导相同的同态。
3. **同构的代数推导**：
    - 考虑复合映射 $r \circ i = 1_X$，在同调群上诱导的同态满足：$H_n(r) \circ H_n(i) = H_n(1_X) = id_{H_n(X)}$。
    - 考虑复合映射 $i \circ r \simeq 1_Y$，在同调群上诱导的同态满足：$H_n(i) \circ H_n(r) = H_n(1_Y) = id_{H_n(Y)}$。
4. **结论**：上述两个等式说明 $H_n(i)$ 具有左逆和右逆，因此 $H_n(i): H_n(X) \to H_n(Y)$ 是一个群同构。

---

### 习题 4.12：$\sin(1/x)$ 空间的同调群计算

**证明过程：**

1. **空间的路分支分解**：$\sin(1/x)$ 空间（通常指闭区间内的图象与 y 轴上极限线段的并集）包含两个路分支：
    - 分支 $A$：$y$ 轴上的线段 ${(0, y) : -1 \le y \le 1}$。
    - 分支 $G$：函数图象 ${(x, \sin(1/x)) : 0 < x \le 1/2\pi}$。
2. **验证分支的可缩性**：线段 $A$ 显然是可缩的。图象 $G$ 同胚于半开区间，因此也是可缩的。
3. **应用路分支分解定理**：根据定理 4.13，一个空间的奇异同调群等于其所有路分支同调群的直和：$H_n(X) \cong \bigoplus H_n(X_\lambda)$。
4. **分维度计算**：
    - **当 $n = 0$ 时**：每个路分支的第零同调群都同构于 $\mathbb{Z}$。因此，$H_0(X) \cong H_0(A) \oplus H_0(G) \cong \mathbb{Z} \oplus \mathbb{Z}$。
    - **当 $n > 0$ 时**：根据维度公理，可缩空间的更高阶同调群均为零。因此，$H_n(X) \cong 0 \oplus 0 = 0$。

**最终结论：** $\sin(1/x)$ 空间的同调群为 $H_0(X) \cong \mathbb{Z} \oplus \mathbb{Z}$，且当 $n \ge 1$ 时 $H_n(X) = 0$。

## The Hurewicz Theorem
### 习题 4.13：证明 Hurewicz 映射 $\varphi$ 的自然性

**证明过程：**

1. 取 $\pi_1(X, x_0)$ 中的一个元素 $[f]$。应用 Hurewicz 映射 $\varphi_X$ 得到同调类 $\text{cls}(f \circ \eta)$，其中 $\eta: \Delta^1 \to I$ 是标准参数化。再应用诱导同态 $h_*$，得到 $h_*(\text{cls}(f \circ \eta)) = \text{cls}(h \circ f \circ \eta)$。
2. 先应用 $h_*$ 得到 $[h \circ f] \in \pi_1(Y, y_0)$。接着应用 $\varphi_Y$ 得到 $\text{cls}((h \circ f) \circ \eta)$。
3. **结论**：由于两个复合路径的结果均为 $\text{cls}(h \circ f \circ \eta)$，证明了 $\varphi$ 是一个自然变换。

### 习题 4.14 严谨证明：1-链 $f$ 与 $-f^{-1}$ 同调
对于题目中**不一定是封闭**的路径 $f$，严谨的证明必须先构造出一个闭合结构。以下是基于你提供的逻辑重写的严谨证明：

**证明过程：**

1. **构造闭路径**： 设 $f: I \to X$ 是 $X$ 中的一条路径（不要求起点 $f(0)$ 等于终点 $f(1)$）。 考虑复合路径 $g = f * f^{-1}$。无论 $f$ 是否封闭，$g$ 都是一个以 $x_0 = f(0)$ 为基点的**闭路径（回路）**，因为它从 $x_0$ 出发回到 $x_0$。
    
2. **利用同伦性质**： 根据基本群性质，任何形如 $f * f^{-1}$ 的路径都同伦于常数路径 $c$（即 $[f * f^{-1}] = 1 \in \pi_1(X, x_0)$）。 由于 $g$ 是闭路径，我们可以对其应用 Hurewicz 映射。
    
3. **严谨的 Hurewicz 映射应用**： 考虑闭路径的组合：$g * g^{-1} = (f * f^{-1}) * (f * f^{-1})^{-1}$。 根据路径逆的定义 $(f * f^{-1})^{-1} = (f^{-1})^{-1} * f^{-1} = f * f^{-1}$，因此 $g = g^{-1}$。 由于 $g * g^{-1} \simeq c$ 是零伦的，应用 Hurewicz 同态 $\varphi$： 
4. $$\varphi([g * g]) = \varphi([c]) = 0$$ 由于 $\varphi$ 是群同态，这对应于 1-同调类中的加法： $$\text{cls}(g) + \text{cls}(g) = 2 \text{cls}(g) = 0 \in H_1(X)$$
    
4. **回到 1-链层面**： 在奇异链群 $S_1(X)$ 中，复合路径 $g = f * f^{-1}$ 所代表的 1-链与 $f + f^{-1}$ 是同调的（模仿定理Th.4.27的构造可知）。 由于 $g \simeq c$ 是零伦的，因此它所代表的 1-链必然是一个**边缘链（Boundary）**，即 $f + f^{-1} \in B_1(X)$。
    
5. **结论**： 在 $H_1(X)$ 中，这意味着： 
6. $$\text{cls}(f) + \text{cls}(f^{-1}) = 0 \implies \text{cls}(f) = -\text{cls}(f^{-1})$$ 因此，1-链 $f$ 与 $-f^{-1}$ 同调。
    

**总结**：通过构造 $f * f^{-1}$ 这个闭路径，我们绕过了 $f$ 非封闭的限制，从而能够严谨地利用 Hurewicz 映射和回路的零伦性质来完成证明。





#### 证明过程

1. **构造第一个 2-单形 $\sigma_1$**： 根据定理 4.27 的证明构造方法，对于可复合路径 $\alpha$ 和 $\beta$（即 $\alpha(1) = \beta(0)$），可以定义一个奇异 2-单形 $\sigma_1$，使其边缘满足： 
2. $$\partial \sigma_1 = \beta - (\alpha * \beta) + \alpha$$ 这意味着在 $S_1(X)$ 中，$\alpha * \beta \sim \alpha + \beta$。
    
3. **构造第二个 2-单形 $\sigma_2$**： 同理，考虑路径 $(\alpha * \beta)$ 与 $\gamma$ 的复合。由于 $(\alpha * \beta)(1) = \beta(1) = \gamma(0)$，我们可以构造另一个 2-单形 $\sigma_2$，其边缘为： 
4. $$\partial \sigma_2 = \gamma - (\alpha * \beta * \gamma) + (\alpha * \beta)$$
    
5. **合并边缘算子**： 将上述两个 2-单形相加，考虑 2-链 $\sigma_1 + \sigma_2$ 的边缘： 
6. $$\partial(\sigma_1 + \sigma_2) = (\beta - \alpha * \beta + \alpha) + (\gamma - \alpha * \beta * \gamma + \alpha * \beta)$$ 中间项 $-\alpha * \beta$ 与 $+\alpha * \beta$ 抵消，得到： 
7. $$\partial(\sigma_1 + \sigma_2) = \alpha + \beta + \gamma - (\alpha * \beta * \gamma)$$
    
8. **验证同调类**： 由于 $\alpha * \beta * \gamma$ 是闭路径，其代表一个 1-闭链。同时，因为 $\alpha(0) = \gamma(1)$ 且中间节点首尾相接，1-链 $\alpha + \beta + \gamma$ 的边缘为 0： $$\partial_1(\alpha + \beta + \gamma) = (\alpha(1) - \alpha(0)) + (\beta(1) - \beta(0)) + (\gamma(1) - \gamma(0)) = 0$$ 因此 $\alpha + \beta + \gamma - (\alpha * \beta * \gamma)$ 是一个边缘链（Boundary），即： 
9. $$\text{cls}(\alpha * \beta * \gamma) = \text{cls}(\alpha + \beta + \gamma) \in H_1(X)$$


### 4.16 基于同伦和同调的degree的定义的一致性
要证明连续映射 $f: S^1 \to S^1$ 的同调度（$d(f)$）与基本群度（$\text{deg}(f)$）一致，我们需要建立基本群 $\pi_1$ 与第一同调群 $H_1$ 之间的联系，其核心工具是 **Hurewicz 映射** $\varphi$。

#### 1. 建立交换图表

根据 Hurewicz 映射的**自然性**（Exercise 4.13），对于任何尖空间映射(保持基点的映射) $f: (S^1, 1) \to (S^1, 1)$，以下图表是交换的：
$$\begin{array}{ccc} \pi_1(S^1, 1) & \xrightarrow{f_*} & \pi_1(S^1, 1) \\ \downarrow \varphi & & \downarrow \varphi \\ H_1(S^1) & \xrightarrow{f_*} & H_1(S^1) \end{array}$$

#### 2. 利用群结构的性质

- **同构性**：由于 $S^1$ 是道路连通的，且其基本群 $\pi_1(S^1, 1) \cong \mathbb{Z}$ 是阿贝尔群，根据 **Hurewicz 定理**，映射 $\varphi$ 是一个群同构。
- **生成元**：设 $[u]$ 是 $\pi_1(S^1, 1)$ 的生成元（例如绕圆周一周的路径类）。由于 $\varphi$ 是同构，$\varphi([u])$ 必然是 $H_1(S^1)$ 的生成元，记为 $[z]$。

#### 3. 追逐图表（Diagram Chasing）

我们从左上角的生成元 $[u] \in \pi_1(S^1, 1)$ 出发，沿两条路径观察其在右下角 $H_1(S^1)$ 中的像：

- **路径一（先下后右）**：
    1. 应用 $\varphi$：$[u] \mapsto \varphi([u]) = [z]$。
    2. 应用同调诱导映射 $f_*$：根据题干中**同调度**的定义，$f_*([z]) = d(f)[z]$。
- **路径二（先右后下）**：
    1. 应用基本群诱导映射 $f_*$：根据**基本群度**的定义，$f_*([u]) = \text{deg}(f)[u]$。
    2. 应用 $\varphi$：由于 $\varphi$ 是同态，$\varphi(\text{deg}(f)[u]) = \text{deg}(f) \cdot \varphi([u]) = \text{deg}(f)[z]$。

#### 4. 得出结论

由于图表交换，上述两条路径的结果必须相等： 
$$d(f)[z] = \text{deg}(f)[z]$$ 由于 $H_1(S^1) \cong \mathbb{Z}$ 且 $[z]$ 是其生成元，我们可以消去 $[z]$，得到： 
$$d(f) = \text{deg}(f)$$

**结论**：在圆周 $S^1$ 上，通过基本群（路径旋转次数）定义的度与通过同调（代数倍数）定义的度是完全等价的。

