---
{"dg-publish":true,"permalink":"/Rotman 代数拓扑习题 第五章 Long Exact Sequences/","tags":["代数"]}
---

## The Category Comp
### 5.1 正合列的性质

- **(i) 证明 $f$ 是单射**：根据在 $A$ 处的正合性定义，有 $\text{im}(0 \to A) = \ker f$。由于从零群出发的唯一映射其像必为 ${0}$，故 $\ker f = {0}$，这意味着 $f$ 是单射。
- **(ii) 证明 $g$ 是满射**：根据在 $C$ 处的正合性定义，有 $\text{im} g = \ker(C \to 0)$。由于映射到零群的唯一同态其核是整个群 $C$，故 $\text{im} g = C$，这意味着 $g$ 是满射。
- **(iii) 证明 $f$ 是同构**：由前两小题可知，$f$ 既是单射又是满射。作为一个双射同态，$f$ 必然是同构。
- **(iv) 证明 $A = 0$**：由 (i) 可知映射 $0 \to A$ 是单射，由 (ii) 可知映射 $A \to 0$ 是满射，这暗示 $A$ 既是零群的像又是零群的核，因此 $A \cong 0$，即 $A = 0$。

### 5.2 正合性与映射性质的等价

根据正合序列 $A \xrightarrow{f} B \xrightarrow{g} C \xrightarrow{h} D$ 的定义：

- 在 $B$ 处正合意味着 $\text{im } f = \ker g$。
- 在 $C$ 处正合意味着 $\text{im } g = \ker h$。

**证明过程：**

1. **必要性 ($\implies$)**：若 $f$ 是满射，则 $\text{im } f = B$。根据正合性，$\ker g = B$，这意味着 $g$ 将 $B$ 中的所有元素映为 $0$，即 $g$ 是零映射。因此 $\text{im } g = {0}$。再次根据正合性，$\ker h = {0}$，这证明了 **$h$ 是单射**。
2. **充分性 ($\impliedby$)**：若 $h$ 是单射，则 $\ker h = {0}$。根据正合性，$\text{im } g = {0}$，这意味着 $g$ 是零映射。因此，$\ker g = B$。再次根据正合性，$\text{im } f = B$，这证明了 **$f$ 是满射**。

### 5.3 短正合序列的同构性质证明

**证明过程：**
假设他们都是阿贝尔群
1. **证明 $i(A) \cong A$**： 根据在 $A$ 处的正合性，$0 \to A \xrightarrow{i} B$ 意味着 $\ker i = \text{im}(0 \to A) = {0}$。因此，$i$ 是一个单射同态。由于任何映射到其像集的单射都是双射，所以 $i$ 诱导了原群 $A$ 与其像集 $i(A)$ 之间的同构，即 $i(A) \cong A$。
    
2. **证明 $B/i(A) \cong C$**：
    
    - **像集关系**：根据在 $B$ 处的正合性，有 $\ker p = \text{im } i = i(A)$。
    - **满射性**：根据在 $C$ 处的正合性，$B \xrightarrow{p} C \to 0$ 意味着 $\text{im } p = \ker(C \to 0) = C$，因此 $p$ 是一个满射。
    - **同构定理**：根据群同态第一同构定理，对于满射 $p: B \to C$，存在同构 $B/\ker p \cong \text{im } p$。将上述关系代入得： 
    - $$B/i(A) \cong C$$ 该同构映射由 $b + i(A) \mapsto p(b)$ 给出。


### 5.4 证明：夹在同构映射间的项为零

考虑长正合序列中的片段： 
$$\dots \to A_n \xrightarrow{h_n} B_n \xrightarrow{f_n} C_n \xrightarrow{g_n} A_{n-1} \xrightarrow{h_{n-1}} B_{n-1} \to \dots$$

**证明过程：**
要证明 $C_n = 0$，只需证明从 $C_n$ 出发的映射 $g_n$ 的核 ($\ker g_n$) 和像 ($\text{im } g_n$) 均为零。

1. **证明 $g_n$ 的核为零**：
    - 因为 $h_n: A_n \to B_n$ 是同构，所以它是满射，即 $\text{im } h_n = B_n$。
    - 根据 $B_n$ 处的正合性，$\ker f_n = \text{im } h_n = B_n$。
    - 这意味着 $f_n$ 是零映射（它把 $B_n$ 中所有元素映为 $0$），因此 $\text{im } f_n = 0$。
    - 根据 $C_n$ 处的正合性，$\ker g_n = \text{im } f_n = 0$，即 $g_n$ 是单射。
2. **证明 $g_n$ 的像为零**：
    
    - 因为 $h_{n-1}: A_{n-1} \to B_{n-1}$ 是同构，所以它是单射，即 $\ker h_{n-1} = 0$。
    - 根据 $A_{n-1}$ 处的正合性，$\text{im } g_n = \ker h_{n-1} = 0$。
3. **结论**：
    
    - 由于 $g_n: C_n \to A_{n-1}$ 是一个单射，且其像集为零映射的像（即 ${0}$），这意味着其定义域 $C_n$ 必须只有零元素。
    - 因此，$C_n = 0$ 对所有 $n$ 成立。

这一结论在代数拓扑中极具威力，例如当你证明了包含映射诱导了 $H_n(A) \cong H_n(X)$ 的同构时，可以立即断定相对同调群 $H_n(X, A) = 0$。

### 5.5：阿贝尔群正合列与秩的关系证明

#### (i) 证明：若 $0 \to A \xrightarrow{f} B \xrightarrow{g} C \to 0$ 正合，则 $\operatorname{rank} B = \operatorname{rank} A + \operatorname{rank} C$
参考 [[1 Stories of Bizzo's Life/1 数学/5 代数拓扑#^bkpo2o\|5 代数拓扑#^bkpo2o]] 
**证明过程（基于你的图片构造）：**

1. **选取 $A$ 的基**：设 ${a_i}$ 是 $A$ 的极大线性无关组，则 $\operatorname{rank} A = |{a_i}|$。
2. **在 $B$ 中构造无关组**：由于 $f$ 是单射，$f({a_i})$ 是 $f(A) \subseteq B$ 的极大线性无关组。将其扩充为 $B$ 的极大线性无关组 $S = {f(a_i)} \cup {b_j}$，则 $\operatorname{rank} B = |{a_i}| + |{b_j}|$。
3. **验证 ${g(b_j)}$ 是 $C$ 的基**：
    - **线性无关性**：若 $\sum m_j g(b_j) = 0$，则 $g(\sum m_j b_j) = 0$。根据正合性，$\sum m_j b_j \in \ker g = \operatorname{im} f$，故 $\sum m_j b_j = \sum n_i f(a_i)$。由于 $S$ 是线性无关组，所有系数 $m_j, n_i$ 均为 0。
    - **极大性（生成能力）**：对任意 $c \in C$，由 $g$ 的满射性存在 $b \in B$ 使 $g(b) = c$。$b$ 可（在模掉挠元素意义下）表示为 $\sum n_i f(a_i) + \sum m_j b_j$。则 $c = g(b) = \sum m_j g(b_j)$（因为 $g \circ f = 0$）。
4. **结论**：$\operatorname{rank} C = |{b_j}|$。因此 $\operatorname{rank} B = \operatorname{rank} A + \operatorname{rank} C$。
==不需要群是自由的== 

---

#### (ii) 证明：若 $0 \to A_n \xrightarrow{f_n} A_{n-1} \to \dots \to A_1 \xrightarrow{f_1} A_0 \to 0$ 正合，则 $\sum_{i=0}^{n}(-1)^{i} \operatorname{rank} A_{i} = 0$

**1. 证明递推关系：** 对每一段 $0 \to \ker f_i \to A_i \xrightarrow{f_i} \operatorname{im} f_i \to 0$，根据 (i) 的结论有： 
$$\operatorname{rank} A_i = \operatorname{rank} \ker f_i + \operatorname{rank} \operatorname{im} f_i$$ 由于序列正合，$\operatorname{im} f_i = \ker f_{i-1}$，代入得： 
$$\operatorname{rank} A_i - \operatorname{rank} \ker f_i = \operatorname{rank} \ker f_{i-1}$$

**2. 利用交错和求值：** 考虑总和 $S = \sum_{i=0}^{n}(-1)^{i} \operatorname{rank} A_{i}$：

- 在首项 $A_n$，由 $0 \to A_n$ 可知 $f_n$ 是单射，故 $\ker f_n = 0$。
- 在末项 $A_0$，由 $A_0 \to 0$ 可知 $f_0$ 是零映射，故 $\ker f_0 = A_0$。
- 代入递推式： 
- $$S = \operatorname{rank} A_n - \operatorname{rank} A_{n-1} + \operatorname{rank} A_{n-2} - \dots + (-1)^n \operatorname{rank} A_0$$
- $$S = (\operatorname{rank} \ker f_n + \operatorname{rank} \ker f_{n-1}) - (\operatorname{rank} \ker f_{n-1} + \operatorname{rank} \ker f_{n-2}) + \dots + (-1)^n \operatorname{rank} \ker f_0$$
- 这是一个**消去和（Telescoping sum）**，中间项全部抵消，且已知 $\ker f_n = 0$，最终项与首项相抵，结果为 $0$。


### 5.6 零边缘算子复形的同调

**解答：** 根据复形同调群的定义，对于复形 $(\mathcal{S}_*, \partial)$，其第 $n$ 个同调群定义为： 
$$H_n(\mathcal{S}_*) = \text{ker } \partial_n / \text{im } \partial_{n+1}$$。 已知对于每一个 $n \in \mathbb{Z}$，边缘算子 $\partial_n = 0$。

1. **确定核（Kernel）**：由于 $\partial_n$ 是零映射，其核 $\text{ker } \partial_n$ 包含 $\mathcal{S}_n$ 中的所有元素，即 $\text{ker } \partial_n = \mathcal{S}_n$。
2. **确定像（Image）**：由于 $\partial_{n+1}$ 是零映射，其像 $\text{im } \partial_{n+1}$ 仅包含零元素，即 $\text{im } \partial_{n+1} = {0}$。
3. **计算同调群**： 
4. $$H_n(\mathcal{S}_*) = \mathcal{S}_n / {0} \cong \mathcal{S}_n$$。 由此得证，对于边缘算子全为零的复形，其同调群就等于其对应的链群。

### 5.7 链映射作为 Comp 中的等价

**解答：** 在 `Comp` 范畴中，链映射 $f: \mathcal{S}'_* \to \mathcal{S}_*$ 是等价（即同构）的充要条件是每一个分量 $f_n$ 都是阿贝尔群的同构。

- **必要性 ($\implies$)**：若 $f = {f_n}$ 是 `Comp` 中的等价，则存在链映射 $g = {g_n}: \mathcal{S}_* \to \mathcal{S}'_*$ 使得 $gf = 1_{\mathcal{S}'_*}$ 且 $fg = 1_{\mathcal{S}_*}$。根据 `Comp` 中复合映射的定义，这意味着对于每个 $n$，有 $g_n f_n = 1_{S'_n}$ 且 $f_n g_n = 1_{S_n}$。因此，$f_n$ 是具有逆映射 $g_n$ 的双射同态，即 $f_n$ 是同构。
- **充分性 ($\impliedby$)**：若每个 $f_n: S'_n \to S_n$ 都是同构，令 $g_n = f_n^{-1}$。我们需要证明 $g = {g_n}$ 是一个链映射。已知 $f$ 是链映射，满足 $\partial_n f_n = f_{n-1} \partial'_n$。在此等式两边左乘 $f_{n-1}^{-1}$，右乘 $f_n^{-1}$，得到： 
- $$f_{n-1}^{-1} \partial_n f_n f_n^{-1} = f_{n-1}^{-1} f_{n-1} \partial'_n f_n^{-1} \implies g_{n-1} \partial_n = \partial'_n g_n$$ 这证明了 $g$ 满足链映射的**交换**图表条件。因为 $g_n$ 是 $f_n$ 的逆，所以在 `Comp` 中 $g$ 是 $f$ 的逆映射。

### 5.8 Comp 与 Ab 中正合性的关系

**解答：** 序列 $\mathcal{S}'_* \xrightarrow{f} \mathcal{S}_* \xrightarrow{g} \mathcal{S}''_*$ 在 `Comp` 中正合的定义是：$\text{im } f = \text{ker } g$。

1. **链复形的相等**：两个子复形相等，当且仅当它们在每一个维度 $n$ 上的项（组）都相等。
2. **分量定义**：
    - $\text{im } f$ 是 $\mathcal{S}_*$ 的子复形，其第 $n$ 项为 $\text{im } f_n$。
    - $\text{ker } g$ 是 $\mathcal{S}_*$ 的子复形，其第 $n$ 项为 $\text{ker } g_n$。
3. **等价推导**： $\text{im } f = \text{ker } g \iff \forall n \in \mathbb{Z}, \text{im } f_n = \text{ker } g_n$。 而 $\text{im } f_n = \text{ker } g_n$ 正是序列 $S'_n \xrightarrow{f_n} S_n \xrightarrow{g_n} S''_n$ 在 `Ab` 中正合的定义。

### 5.9 自然映射与第一同构定理

**解答：** (i) 证明 $\nu$ 是链映射且其核为 $\mathcal{S}'_*$

- **链映射**：需证明 $\bar{\partial}_n \nu_n = \nu_{n-1} \partial_n$，其中 $\bar{\partial}_n$ 是商复形的边缘算子。对于 $s_n \in S_n$，有： $\nu_{n-1}(\partial_n s_n) = \partial_n s_n + S'_{n-1}$。 根据商复形边缘算子的定义：$\bar{\partial}_n(s_n + S'_n) = \partial_n s_n + S'_{n-1}$。 由于 $\nu_n(s_n) = s_n + S'_n$，显然有 $\bar{\partial}_n \nu_n(s_n) = \nu_{n-1} \partial_n(s_n)$，故 $\nu$ 是链映射。
- **核**：$\text{ker } \nu$ 作为一个复形，其第 $n$ 项为 $\text{ker } \nu_n = S'_n$。由于 $\mathcal{S}'_*$ 是子复形，其边缘算子是 $\partial_n$ 的限制，这与 $\text{ker } \nu$ 的结构完全一致，因此 $\text{ker } \nu = \mathcal{S}'_*$。

**(ii) 证明第一同构定理在 Comp 中成立**

- **构造同构**：已知 $f: \mathcal{S}_* \to \mathcal{S}''_*$ 是链映射。在每一个维度 $n$，根据 `Ab` 中的第一同构定理，存在唯一的同构 $\bar{\theta}_n: S_n / \text{ker } f_n \xrightarrow{\cong} \text{im } f_n$，满足 $\bar{\theta}_n \nu_n = f_n$。
- **证明链映射**：我们要证明 $\theta = {\bar{\theta}_n}$ 满足链映射的交换图。考虑图表： 
- $$\text{im } f_n \xrightarrow{\bar{\partial}_n} \text{im } f_{n-1}$$ $$\bar{\theta}_n \uparrow \quad \quad \uparrow \bar{\theta}_{n-1}$$ $$S_n / \text{ker } f_n \xrightarrow{\partial'_n} S_{n-1} / \text{ker } f_{n-1}$$ 利用 $\nu$ 是满射链映射且 $f$ 是链映射的性质： $\bar{\theta}_{n-1} \partial'_n \nu_n = \bar{\theta}_{n-1} \nu_{n-1} \partial_n = f_{n-1} \partial_n = \partial_n f_n = \partial_n \bar{\theta}_n \nu_n$。 由于 $\nu_n$ 是满射，可消去得到 $\bar{\theta}_{n-1} \partial'_n = \partial_n \bar{\theta}_n$，证明了 $\theta$ 是链映射。
- **结论**：因为每个 $\bar{\theta}_n$ 都是同构，根据习题 5.7，$\theta$ 是 `Comp` 中的等价（同构）。
### 5.10 链复形范畴中的第二同构定理

**证明：** 为了证明链复形的第二同构定理 $S'_* / (S'_* \cap S''^*) \cong (S'_* + S''^*) / S''^*$，我们遵循群论中利用第一同构定理进行推导的逻辑，并将其推广至 `Comp` 范畴。

**1. 构造链映射 $\psi$** 考虑包含映射 $i: S'_* \hookrightarrow S'_* + S''_*$ 以及自然商映射 $\pi: S'_* + S''^* \to (S'_* + S''^*) / S''^*$。 根据链映射复合的定义，定义 $\psi = \pi \circ i: S'_* \to (S'_* + S''^*) / S''^*$。 对于每一个维度 $n$，分量映射 $\psi_n: S'_n \to (S'_n + S''_n) / S''_n$ 的定义为： 
$$\psi_n(s'_n) = s'_n + S''_n \quad (\forall s'_n \in S'_n)$$

**2. 证明 $\psi$ 是满链映射**

- **链映射性质**：由于 $i$ 和 $\pi$ 都是链映射（根据子复形和商复形的定义），它们的复合映射 $\psi$ 也是链映射。
- **满射性**：在阿贝尔群范畴 `Ab` 中，根据群同构第二定理的证明逻辑，任取 $(S'_n + S''_n) / S''_n$ 中的元素 $y = (s'_n + s''_n) + S''_n$，由于 $s''_n \in S''_n$，该元素可简化为 $s'_n + S''_n$。显然存在 $s'_n \in S'_n$ 使得 $\psi_n(s'_n) = y$。因此每个分量 $\psi_n$ 都是满射。
- 在 `Comp` 中，若链映射的每个分量都是满射，则该链映射是满射。

**3. 确定核复形 $\text{ker } \psi$** $\text{ker } \psi$ 是 $S'_*$ 的一个子复形，其第 $n$ 项由下式给定： 
$$\text{ker } \psi_n = {s'_n \in S'_n : \psi_n(s'_n) = 0} = {s'_n \in S'_n : s'_n \in S''_n} = S'_n \cap S''_n$$ 因此，作为链复形，$\text{ker } \psi = S'_* \cap S''_*$。

**4. 应用链复形的第一同构定理** 根据习题 5.9(ii) 已证的结论：若 $f: \mathcal{S}_* \to \mathcal{T}_*$ 是链映射，则存在链同构 $\theta: \mathcal{S}_* / \text{ker } f \cong \text{im } f$。 将 $\psi$ 代入该定理：

- $\text{ker } \psi = S'_* \cap S''^*$
- 由于 $\psi$ 是满射，$\text{im } \psi = (S'_* + S''^*) / S''^*$

由此得到链同构： $$S'_* / (S'_* \cap S''^*) \cong (S'_* + S''^*) / S''^*$$ 证明完毕。该同构在每一个维度 $n$ 上都对应于阿贝尔群的第二同构定理。

### 5.11 链复形范畴中的第三同构定理

**证明：** 为了证明在 `Comp` 范畴中存在短正合序列 $0 \to T_*/U_* \xrightarrow{i} S_*/U_* \xrightarrow{p} S_*/T_* \to 0$，我们需要验证该映射是链映射，并且该序列在每一个维度 $n$ 上作为阿贝尔群序列都是正合的。

**1. 定义映射及其分量** 根据题意，$U_* \subset T_* \subset S_*$ 是子复形。对于每一个 $n \in \mathbb{Z}$，序列的分量映射定义如下：

- **包含映射** $i_n: T_n/U_n \to S_n/U_n$，定义为 $i_n(t_n + U_n) = t_n + U_n$。由于 $T_n \subset S_n$，该映射在阿贝尔群商群之间是良定义的。
- **自然商映射** $p_n: S_n/U_n \to S_n/T_n$，定义为 $p_n(s_n + U_n) = s_n + T_n$。由于 $U_n \subset T_n$，该映射是良定义的：若 $s_n + U_n = s'_n + U_n$，则 $s_n - s'_n \in U_n \subset T_n$，从而 $s_n + T_n = s'_n + T_n$。

**2. 验证 $i$ 和 $p$ 是链映射** 我们需要证明这些分量映射与边缘算子 $\partial$ 交换：

- **对于 $i$**：需验证 $\bar{\partial}_{S/U} i_n = i_{n-1} \bar{\partial}_{T/U}$。对于任意 $t_n + U_n \in T_n/U_n$： $\bar{\partial}_{S/U} i_n(t_n + U_n) = \bar{\partial}_{S/U}(t_n + U_n) = \partial t_n + U_{n-1}$。 $i_{n-1} \bar{\partial}_{T/U}(t_n + U_n) = i_{n-1}(\partial t_n + U_{n-1}) = \partial t_n + U_{n-1}$。
- **对于 $p$**：需验证 $\bar{\partial}_{S/T} p_n = p_{n-1} \bar{\partial}_{S/U}$。对于任意 $s_n + U_n \in S_n/U_n$： $\bar{\partial}_{S/T} p_n(s_n + U_n) = \bar{\partial}_{S/T}(s_n + T_n) = \partial s_n + T_{n-1}$。 $p_{n-1} \bar{\partial}_{S/U}(s_n + U_n) = p_{n-1}(\partial s_n + U_{n-1}) = \partial s_n + T_{n-1}$。 因此，$i = {i_n}$ 和 $p = {p_n}$ 确实是 `Comp` 中的链映射。

**3. 在 Ab 中验证每一维度的正合性** 对于每一个固定的 $n$，根据阿贝尔群的第三同构定理（由于阿贝尔群的所有子群皆为正规子群，该定理直接适用），序列 $0 \to T_n/U_n \xrightarrow{i_n} S_n/U_n \xrightarrow{p_n} S_n/T_n \to 0$ 是 `Ab` 中的短正合序列：

- **$i_n$ 是单射**：若 $i_n(t_n + U_n) = 0$，则 $t_n \in U_n$，故在 $T_n/U_n$ 中 $t_n + U_n = 0$。
- **$p_n$ 是满射**：对于任意 $s_n + T_n \in S_n/T_n$，取 $s_n + U_n \in S_n/U_n$ 即可满足 $p_n(s_n + U_n) = s_n + T_n$。
- **核心正合性** ($\text{im } i_n = \text{ker } p_n$)：
    - $\text{im } i_n = \{t_n + U_n \in S_n/U_n \mid t_n \in T_n\}$。
    - $\text{ker } p_n = \{s_n + U_n \in S_n/U_n \mid s_n + T_n = 0\} = \{s_n + U_n \mid s_n \in T_n\}$。 显然两者相等。

**4. 结论** 根据习题 5.8，链复形序列在 `Comp` 中正合，当且仅当它在每一个维度 $n$ 上作为阿贝尔群序列在 `Ab` 中都正合。 由于上述序列在所有维度 $n \in \mathbb{Z}$ 上均满足短正合性，故在 `Comp` 中：
$$0 \to T_*/U_* \xrightarrow{i} S_*/U_* \xrightarrow{p} S_*/T_* \to 0$$ 是短正合序列。证明完毕。

以下是关于 Rotman 习题 5.12 的解答，以及对你提出的疑问的分析：
## Exact Homology Sequences
### 5.12 复形直和的同调

**证明：** 设 $\mathcal{S}_*$ 是复形家族 ${(\mathcal{S}_*^\lambda, \partial^\lambda)}_{\lambda \in \Lambda}$ 的直和，记为 $\mathcal{S}_* = \sum_\lambda \mathcal{S}_*^\lambda$。根据复形直和的定义，其第 $n$ 级链群为 $S_n = \sum_\lambda S_n^\lambda$，边缘算子为 $\partial_n = \sum_\lambda \partial_n^\lambda$。

1. **确定闭链群（Kernel）**： 一个元素 $\gamma \in S_n$ 可以唯一表示为有限和 $\gamma = \sum \gamma_\lambda$，其中 $\gamma_\lambda \in S_n^\lambda$。根据边缘算子的定义，$\partial_n \gamma = \sum_\lambda \partial_n^\lambda \gamma_\lambda$。由于直和中各分量线性无关，$\partial_n \gamma = 0$ 当且仅当对所有的 $\lambda$，都有 $\partial_n^\lambda \gamma_\lambda = 0$。 因此，$Z_n(\mathcal{S}_*) \cong \sum_\lambda Z_n(\mathcal{S}_*^\lambda)$。
    
2. **确定边缘链群（Image）**： 同理，元素 $\beta$ 在 $\text{im } \partial_{n+1}$ 中，当且仅当存在 $\alpha = \sum \alpha_\lambda$ 使得 $\beta = \partial_{n+1} \alpha = \sum \partial_{n+1}^\lambda \alpha_\lambda$。这意味着每个分量 $\beta_\lambda$ 都必须在对应复形的像 $\text{im } \partial_{n+1}^\lambda$ 中。 因此，$B_n(\mathcal{S}_*) \cong \sum_\lambda B_n(\mathcal{S}_*^\lambda)$。
    
3. **计算同调群**： 利用商群与直和的交换律（即 $(\sum A_\lambda) / (\sum B_\lambda) \cong \sum (A_\lambda / B_\lambda)$）： 
4. $$H_n(\mathcal{S}_*) = \frac{Z_n(\mathcal{S}_*)}{B_n(\mathcal{S}_*)} \cong \frac{\sum_\lambda Z_n(\mathcal{S}_*^\lambda)}{\sum_\lambda B_n(\mathcal{S}_*^\lambda)} \cong \sum_\lambda \frac{Z_n(\mathcal{S}_*^\lambda)}{B_n(\mathcal{S}_*^\lambda)} = \sum_\lambda H_n(\mathcal{S}_*^\lambda)$$ 证明完毕。

#### 为什么与定理 4.13 有关？

之所以提到 **定理 4.13**，是因为该定理是这个代数结论在拓扑学中的第一个重要应用实例。

- **定理 4.13 的内容**：它证明了若 $X$ 的路分支为 ${X_\lambda}$，则 $H_n(X) \cong \sum H_n(X_\lambda)$。
- **联系点**：定理 4.13 的证明逻辑是先展示 **整个奇异复形 $S_*(X)$ 可以分解为各路分支复形 $S_*(X_\lambda)$ 的直和**（因为每一个奇异单形的像必定落在一个唯一的路分支内）。一旦确立了这种复形层面的直和关系，后续关于同调群可以拆分为直和的代数推导，与习题 5.12 完全一致。

简单来说，**定理 4.13 负责完成从拓扑到代数直和的转化，而习题 5.12 则是对这种直和关系的纯代数性质总结**。你在证明 5.12 时所用的关于 $\text{ker}$ 和 $\text{im}$ 的加和说明，正是定理 4.13 证明中隐含的核心步骤。


### 5.13 相对链群的基底证明

1. **定义基底及其划分**： 根据定义，$S_n(X)$ 是以所有奇异 $n$-单形 $\sigma: \Delta^n \to X$ 为基底的自由阿贝尔群。令此基底为 $B$。我们可以将 $B$ 划分为两个不相交的集合：
    - $B_A = \{ \sigma \in B \mid \text{im } \sigma \subseteq A \}$，它恰好是 $S_n(A)$ 的基底。
    - $B_{X \setminus A} = \{ \sigma \in B \mid \text{im } \sigma \not\subset A \}$，即所有像不完全在 $A$ 中的单形。
2. **构造同态**： 利用自由阿贝尔群的泛性质，我们可以定义唯一的群同态 $\varphi: S_n(X) \to \mathbb{Z}^{\oplus B_{X \setminus A}}$。该同态在基底 $B$ 上的作用定义为： 
$$\varphi(\sigma) = \begin{cases} \sigma, & \text{若 } \sigma \in B_{X \setminus A} \\ 0, & \text{若 } \sigma \in B_A \end{cases}$$
3. **应用同构定理**：
    
    - **满射性**：由于 $\varphi$ 的像集包含基底 $B_{X \setminus A}$ 的所有生成元，因此 $\varphi$ 是满射。
    - **核的确定**：由定义可知，$\ker \varphi$ 正是由 $B_A$ 生成的自由阿贝尔群，即 $\ker \varphi = S_n(A)$。
    - **同构关系**：根据群同态第一同构定理，存在同构： 
    - $$S_n(X) / S_n(A) \cong \text{im } \varphi = \mathbb{Z}^{\oplus B_{X \setminus A}}$$
4. **结论**： 由于 $\mathbb{Z}^{\oplus B_{X \setminus A}}$ 是以 $B_{X \setminus A}$ 为基底的自由阿贝尔群，因此商群 $S_n(X) / S_n(A)$ 也是自由阿贝尔群，其基底由所有满足 $\text{im } \sigma \not\subset A$ 的单形的陪集 $\sigma + S_n(A)$ 构成。
    
这一构造清晰地展示了 $S_n(X, A)$ 实际上是由那些“不在 $A$ 里面”的单形线性组合而成的。

### 5.14 收缩核与同调群
#### 5.14 (i) 构造短正合序列

**题目：** 考虑阿贝尔群的正合序列 $\dots \to C_{n+1} \xrightarrow{f_n} A_n \xrightarrow{i_n} B_n \xrightarrow{p_n} C_n \xrightarrow{f_{n-1}} A_{n-1} \to \dots$，其中每隔两个映射的映射 $i_n$ 都是单射。证明序列 $0 \to A_n \xrightarrow{i_n} B_n \xrightarrow{p_n} C_n \to 0$ 对所有 $n$ 都是正合的。

**证明：**

1. **验证 $i_n$ 的正合性**：根据已知条件，$i_n: A_n \to B_n$ 是单射，因此 $\text{ker } i_n = 0$。根据原序列在 $A_n$ 处正合的定义，有 $\text{im } f_n = \text{ker } i_n = 0$。
2. **验证 $p_n$ 的满射性**：由于 $\text{im } f_n = 0$，映射 $f_n$ 是零映射，其核 $\text{ker } f_n = C_{n+1}$。根据原序列在 $C_{n+1}$ 处正合的定义，有 $\text{im } p_{n+1} = \text{ker } f_n = C_{n+1}$，这证明了对于所有的 $n$，$p_n$ 都是满射。
3. **结论**：在原正合序列中，已经保证了 $\text{im } i_n = \text{ker } p_n$。结合 $i_n$ 是单射且 $p_n$ 是满射的结论，序列 $0 \to A_n \xrightarrow{i_n} B_n \xrightarrow{p_n} C_n \to 0$ 符合短正合序列的定义。

#### 5.14 (ii) 形变收缩核与直和分解

**题目：** 若 $A$ 是 $X$ 的形变收缩核（retract），证明对于所有 $n \ge 0$，$H_n(X) \cong H_n(A) \oplus H_n(X, A)$。

**证明：**

1. **利用形变收缩性质**：若 $A$ 是 $X$ 的形变收缩核，则存在包含映射 $i: A \hookrightarrow X$ 和收缩映射 $r: X \to A$，使得 $r \circ i = 1_A$。
2. **诱导同态的性质**：根据同调函子的性质，$H_n(r) \circ H_n(i) = H_n(r \circ i) = H_n(1_A) = 1_{H_n(A)}$。这表明 $H_n(i)$ 具有左逆映射，因此 $H_n(i)$ 是单射。
3. **长正合序列的简化**：考虑空间对 $(X, A)$ 的同调长正合序列：$\dots \to H_n(A) \xrightarrow{i_*} H_n(X) \xrightarrow{j_*} H_n(X, A) \xrightarrow{d} H_{n-1}(A) \to \dots$。由于 $i_* = H_n(i)$ 对所有 $n$ 都是单射，连接同态 $d$ 的图像 $\text{im } d = \text{ker } i_* = 0$，故 $d$ 是零映射。
4. **应用分裂引理**：根据[[Davis, Kirk Lemma 1.24 模的正合列的可裂性\|Davis, Kirk Lemma 1.24 模的正合列的可裂性]]，$i_*$可裂等价于$j_*$可裂。因此，我们得到一系列分裂短正合序列 $0 \to H_n(A) \xrightarrow{i_*} H_n(X) \xrightarrow{j_*} H_n(X, A) \to 0$。根据分裂短正合序列的性质，中间项等于两端项的直和：$H_n(X) \cong H_n(A) \oplus H_n(X, A)$。

#### 5.14 (iii) 强形变收缩核的相对同调

**题目：** 若 $A$ 是 $X$ 的强形变收缩核（deformation retract），则对于所有 $n \ge 0$，$H_n(X, A) = 0$。

**证明：**

1. **同伦等价性**：若 $A$ 是 $X$ 的强形变收缩核，则包含映射 $i: A \hookrightarrow X$ 是一个同伦等价。
2. **同调群同构**：根据同伦公理，同伦等价映射在每一维同调群上都诱导同构，即 $i_*: H_n(A) \xrightarrow{\cong} H_n(X)$ 是同构。
3. **长正合序列分析**：再次考查空间对 $(X, A)$ 的长正合序列。由于 $i_*$ 是同构：
    - 它是满射，由正合性可知 $\text{ker } j_* = \text{im } i_* = H_n(X)$，这意味着 $j_*$ 必须是零映射。
    - 它也是单射，由正合性可知 $\text{im } d = \text{ker } i_* = 0$，这意味着 $d$ 必须是零映射。
4. **结论**：在序列 $\dots \xrightarrow{i_*} H_n(X) \xrightarrow{j_*} H_n(X, A) \xrightarrow{d} H_{n-1}(A) \to \dots$ 中，由于 $j_* = 0$ 且 $d = 0$，根据正合性 $\text{im } j_* = \text{ker } d = H_n(X, A)$，可推得 $H_n(X, A) = 0$。


### 5.15 链复形零调性的传递性证明

**已知条件：**

1. 存在链复形的短正合序列：$0 \to S'_* \xrightarrow{i} S_* \xrightarrow{p} S''_* \to 0$。
2. 复形“零调（Acyclic）”意味着其所有同调群均为零，即对于所有 $n$，有 $H_n = 0$。

**证明过程：** 根据定理 5.6（Exact Triangle），该短正合序列诱导如下同调群的长正合序列： 
$$\dots \to H_n(S'_*) \xrightarrow{i_*} H_n(S_*) \xrightarrow{p_*} H_n(S''_*) \xrightarrow{d_n} H_{n-1}(S'_*) \to \dots$$
我们分三种情况讨论（任选两个复形为零调）：

1. 情况一：若 $S'_*$ 和 $S_*$ 是零调的
    
    - 对于所有的 $n$，有 $H_n(S'_*) = 0$ 且 $H_n(S_*) = 0$。
    - 观察长正合序列中的一段
    - $$H_n(S_*) \to H_n(S''_*) \to H_{n-1}(S'_*)$$
    - 代入已知值得到：$0 \to H_n(S''_*) \to 0$。
    - 根据正合性的定义（$\text{im } f = \text{ker } g$），映射 $0 \to H_n(S''_*)$ 是单射且 $H_n(S''_*) \to 0$ 是满射，故 $H_n(S''_*) = 0$。
    - 因此，$S''_*$ 也是零调的。
2. 情况二：若 $S_*$ 和 $S''_*$ 是零调的
    
    - 对于所有的 $n$，有 $H_n(S_*) = 0$ 且 $H_n(S''_*) = 0$。
    - 观察长正合序列中的一段： 
    - $$H_{n+1}(S''_*) \xrightarrow{d_{n+1}} H_n(S'_*) \to H_n(S_*)$$
    - 代入已知值得到：$0 \to H_n(S'_*) \to 0$。
    - 同理，这迫使 $H_n(S'_*) = 0$。因此 $S'_*$ 是零调的。
3. 情况三：若 $S'_*$ 和 $S''_*$ 是零调的
    
    - 对于所有的 $n$，有 $H_n(S'_*) = 0$ 且 $H_n(S''_*) = 0$。
    - 观察长正合序列中的一段： 
$$H_n(S'_*) \to H_n(S_*) \to H_n(S''_*)$$
    - 代入已知值得到：$0 \to H_n(S_*) \to 0$。
    - 这迫使 $H_n(S_*) = 0$。因此 $S_*$ 是零调的。

**结论：** 在链复形的短正合序列中，只要其中两个复形是零调的，根据同调长正合序列的夹逼作用，第三个复形必然也是零调的。这种方法比直接进行元素级别的“图追逐”证明（如 中所示）要高效得多。


### 5.16 相对链群的之间的映射
#### 1. 关键引理：$f_\#(S_n(A)) \subseteq S_n(A')$ 的证明

**已知条件**：$f: (X, A) \to (X', A')$ 是一个空间对映射。根据定义，这意味着 $f: X \to X'$ 是连续映射，且满足 **$f(A) \subseteq A'$**。

**证明过程**：

1. **取基底元素**：设 $\sigma$ 是 $S_n(A)$ 中的一个生成元，即一个奇异 $n$-单形 $\sigma: \Delta^n \to A$。
2. **复合映射**：由诱导链映射的定义，$f_\#(\sigma) = f \circ \sigma$。
3. **像的包含关系**：由于 $\sigma$ 的值域在 $A$ 内，即 $\sigma(\Delta^n) \subseteq A$，那么复合映射的像满足： 
$$(f \circ \sigma)(\Delta^n) = f(\sigma(\Delta^n)) \subseteq f(A)$$
4. **利用空间对定义**：因为 $f(A) \subseteq A'$，所以 $(f \circ \sigma)(\Delta^n) \subseteq A'$。
5. **结论**：这说明 $f \circ \sigma$ 是一个从 $\Delta^n$ 到 $A'$ 的连续映射，即 $f_\#(\sigma) \in S_n(A')$。由于 $S_n(A)$ 是由这些单形生成的自由阿贝尔群，通过线性扩张可知： **$f_\#(S_n(A)) \subseteq S_n(A')$**。

---

#### 2. 证明 $f_\#(Z_n(X, A)) \subseteq Z_n(X', A')$

**定义**：相对 $n$-闭链群定义为 $Z_n(X, A) = { \gamma \in S_n(X) : \partial_n \gamma \in S_{n-1}(A) }$。

**证明过程**：

1. 设 $\gamma \in Z_n(X, A)$。我们需要证明 $f_\# \gamma$ 满足相对 $n$-闭链的条件。
2. **边缘运算**：考虑 $f_\# \gamma$ 的边缘。根据链映射的性质，边缘算子 $\partial$ 与 $f_\#$ 交换：
$$\partial'_n (f_\# \gamma) = f_\# (\partial_n \gamma)$$
3. **包含判定**：由已知条件 $\partial_n \gamma \in S_{n-1}(A)$。
4. **应用关键引理**：根据第1部分证得的结论，$f_\#(S_{n-1}(A)) \subseteq S_{n-1}(A')$。因此： 
$$f_\# (\partial_n \gamma) \in S_{n-1}(A')$$
5. **结论**：既然 $\partial'_n (f_\# \gamma) \in S_{n-1}(A')$，则根据定义 **$f_\# \gamma \in Z_n(X', A')$**。

---

#### 3. 证明 $f_\#(B_n(X, A)) \subseteq B_n(X', A')$

**定义**：相对 $n$-边缘链群定义为 $B_n(X, A) = B_n(X) + S_n(A)$。

**证明过程**：

1. 设 $\gamma \in B_n(X, A)$。根据定义，可以将其写为 $\gamma = \beta + \alpha$，其中 $\beta \in B_n(X)$ 且 $\alpha \in S_n(A)$。
2. **作用诱导映射**：$f_\# \gamma = f_\# \beta + f_\# \alpha$。
3. **处理第一项 ($B_n$ 部分)**：
    - 因为 $\beta \in B_n(X)$，存在 $\zeta \in S_{n+1}(X)$ 使得 $\beta = \partial \zeta$。
    - 则 $f_\# \beta = f_\# (\partial \zeta) = \partial' (f_\# \zeta)$。
    - 因为 $f_\# \zeta \in S_{n+1}(X')$，所以 $f_\# \beta \in B_n(X')$。
4. **处理第二项 ($S_n$ 部分)**：
    - 由第1部分结论，$f_\# \alpha \in S_n(A')$。
5. **合并结论**：
$$f_\# \gamma \in B_n(X') + S_n(A') = B_n(X', A')$$ 证得 **$f_\#(B_n(X, A)) \subseteq B_n(X', A')$**。

**总结**：这一结论保证了空间对映射 $f$ 能够诱导商复形之间的链映射，进而诱导相对同调群之间的同态 $f_*: H_n(X, A) \to H_n(X', A')$。


### 5.17 用相对闭链群和相对边缘群刻画相对同调诱导映射

习题 5.17 要求证明 $f_*(\text{cls } \gamma) = \text{cls } f_\# \gamma$，这里的 $\gamma \in Z_n(X, A)$。利用 5.16 的结论，我们可以证明他是良定义的（我们并没有证明两种定义是等价的），证明步骤如下：

1. **利用同构关系**：根据定理 5.11，通过第三同构定理，相对同调群可以表示为相对闭链群对相对边缘链群的商：
$$H_n(X, A) \cong Z_n(X, A) / B_n(X, A)$$
2. **验证算子良定性（利用 5.16）**：
    - **相对闭链的保持**：由 5.16 已知 $f_\#(Z_n(X, A)) \subseteq Z_n(X', A')$。这保证了如果 $\gamma$ 是一个相对闭链，那么 $f_\# \gamma$ 也是 $X'$ 中相对于 $A'$ 的闭链，因此 $\text{cls } f_\# \gamma$ 有意义。
    - **相对边缘链的保持**：由 5.16 已知 $f_\#(B_n(X, A)) \subseteq B_n(X', A')$。这保证了如果两个相对闭链在 $H_n(X, A)$ 中同调（即它们的差是相对边缘链），那么它们的像在 $H_n(X', A')$ 中也同调。这说明该映射在同调类上是**良定义**的。
3. **结论**：通过 5.16 确定的包含关系，直接证明了在以相对闭链代表同调类时，映射形式确实为 $\text{cls } \gamma \mapsto \text{cls } f_\# \gamma$。

#### 原定义的补充说明：商复形之间的链映射诱导相对同调同态

在 Rotman 的教材框架中，习题 5.17 提到的 _*诱导映射 $f_*$ 的“原始定义”（original definition）_* 是基于_*商复形之间的链映射_*所诱导的同态。
具体整理如下：

1. 相对同调群的原始定义
根据教材定义，相对同调群 $H_n(X, A)$ 被定义为**商复形 $S_*(X)/S_*(A)$ 的第 $n$ 个同调群**： 
$$H_n(X, A) := H_n(S_*(X)/S_*(A))$$
 2. 诱导映射 $f_*$ 的原始构造
对于空间对的映射 $f: (X, A) \to (X', A')$，其诱导映射 $f_*$ 是通过以下步骤定义的：
- **链映射的限制**：连续映射 $f$ 诱导了奇异链复形之间的链映射 $f_\#: S_*(X) \to S_*(X')$。由于 $f(A) \subset A'$，该链映射满足 $f_\#(S_*(A)) \subset S_*(A')$。
- **商链映射的导出**：基于上述包含关系，$f_\#$ 诱导了一个**商复形之间的链映射**（通常也记作 $f_\#$ 或 $S_*(f)$）： $$f_\#: S_*(X)/S_*(A) \to S_*(X')/S_*(A')$$ 其具体作用于商空间的元素（即余集）上：$\gamma_n + S_n(A) \mapsto f_\#(\gamma_n) + S_n(A')$。
- **同调诱导**：由于 $H_n$ 是从链复形范畴 $\mathsf{Comp}$ 到阿贝尔群范畴 $\mathsf{Ab}$ 的函子，这个商复形之间的链映射自然地诱导了同调群之间的同态： 
$$f_* : H_n(S_*(X)/S_*(A)) \to H_n(S_*(X')/S_*(A'))$$

### 5.18 相对闭链群的等价刻画

相对 $n$-闭链群 **$Z_n(X, A)$** 的定义为所有满足其边缘（boundary）落在 $S_{n-1}(A)$ 中的 $n$-链组成的集合，即 $Z_n(X, A) = { \gamma \in S_n(X) : \partial_n \gamma \in S_{n-1}(A) }$。

对于奇异 $n$-单形 $\sigma: \Delta^n \to X$，其边缘 $\partial_n \sigma=\sum_{i=0}^n (-1)^i \sigma \epsilon_i$。根据已知条件，$\sigma$ 的每一个面 $\sigma \epsilon_i$ 的值都落在 $A \subset X$ 中。由于每个面映射 $\sigma \epsilon_i$ 都是从标准 $(n-1)$-单形到 $A$ 的连续映射，因此每一个 $\sigma \epsilon_i$ 本身都是 $A$ 中的一个奇异 $(n-1)$-单形。

这意味着对于所有的 $i$，$\sigma \epsilon_i$ 均属于奇异链群 **$S_{n-1}(A)$**。因为 $\partial_n \sigma$ 是由这些属于 $S_{n-1}(A)$ 的单形通过线性组合构成的，所以其边缘结果 **$\partial_n \sigma$ 必然属于 $S_{n-1}(A)$**。根据相对闭链的定义， $\sigma\in Z_n(X, A)$。

## Reduced Homology

### 5.19 约化同调的长正合序列


> [!proposition] Ex.5.19 rotman2013alto
>   If $A \subset X$, then there is an exact sequence
> $$\cdots \rightarrow \tilde{H}_{n}(A) \rightarrow \tilde{H}_{n}(X) \rightarrow H_{n}(X, A) \rightarrow \tilde{H}_{n-1}(A) \rightarrow \cdots,$$
>   which ends
> $$\cdots \rightarrow \tilde{H}_{0}(A) \rightarrow \tilde{H}_{0}(X) \rightarrow H_{0}(X, A) \rightarrow 0 .$$
>   $\left(\operatorname{Hint}: \widetilde{S}_{*}(X) / \widetilde{S}_{*}(A)=S_{*}(X) / S_{*}(A).\right)$

#### 1. 证明提示：$\tilde{S}_*(X)/\tilde{S}_*(A) = S_*(X)/S_*(A)$

增广奇异复形 $\tilde{S}_*(X)$ 的定义是在原有的奇异复形末尾添加了一个 $\mathbb{Z}$ 项和增广映射 $\tilde{\partial}_0$。

- **对于 $n \ge 0$**：$\tilde{S}_n(X)$ 与 $S_n(X)$ 完全相同，子复形亦然，因此其商群 $\tilde{S}_n(X)/\tilde{S}_n(A) = S_n(X)/S_n(A)$。
- **对于 $n = -1$**：根据定义，$\tilde{S}_{-1}(X) \cong \mathbb{Z}$ 且 $\tilde{S}_{-1}(A) \cong \mathbb{Z}$。包含映射 $i: A \to X$ 在这一维诱导的是恒等映射，因此商群为 $\mathbb{Z}/\mathbb{Z} = 0$。
- **结论**：由于标准相对链复形 $S_n(X, A)$ 在 $n < 0$ 时本身就定义为 $0$，因此这两个复形在所有阶数上都相等，即 $\tilde{S}_*(X)/\tilde{S}_*(A) = S_*(X, A)$。

#### 2. 利用 Theorem 5.6 证明长正合序列

根据 **Theorem 5.6 (正合三角)**，复形的任何短正合列都会诱导一个同调群的长正合序列。

考虑增广复形的短正合列（显然是正合列）： 
$$0 \to \tilde{S}_*(A) \xrightarrow{i} \tilde{S}_*(X) \xrightarrow{p} \tilde{S}_*(X)/\tilde{S}_*(A) \to 0$$

1. $H_n(\tilde{S}_*(A))$ 即为约化同调群 $\tilde{H}_n(A)$。
2. $H_n(\tilde{S}_*(X))$ 即为约化同调群 $\tilde{H}_n(X)$。
3. $H_n(\tilde{S}_*(X)/\tilde{S}_*(A))$ 根据提示等价于 $H_n(S_*(X, A))$，即相对同调群 $H_n(X, A)$。

将上述项代入 Theorem 5.6 的长正合列公式中，立即得到： 
$$\dots \to \tilde{H}_n(A) \to \tilde{H}_n(X) \to H_n(X, A) \xrightarrow{d} \tilde{H}_{n-1}(A) \to \dots$$

#### 3. 序列的末尾分析

序列在低维处的表现如下： 
$$\dots \to \tilde{H}_0(A) \to \tilde{H}_0(X) \to H_0(X, A) \to \tilde{H}_{-1}(A)$$ 对于任何非空空间 $A$，其增广映射 $\tilde{\partial}_0$ 是满射，因此其 $-1$ 阶约化同调群 $\tilde{H}_{-1}(A) = 0$。这保证了序列在 $H_0(X, A)$ 处以 $\to 0$ 结束，从而证明了正合性在末尾也得到保持。

约化同调序列在计算悬挂空间（Suspension）时非常高效。你想了解它是如何简化球面同调群 $H_n(S^k)$ 的归纳证明的吗？


#### 4.另一种解法：利用三元组 $(X, A, {x_0})$

除了通过增广复形的短正合列直接推导，习题 5.19 还有一个更具几何直观的解法，即利用**三元组（Triple）的长正合序列**。
如果你已经证明了**定理 5.9**（三元组长正合序列）以及**定理 5.17**（约化同调与相对同调的关系），那么可以通过以下步骤快速证明：

1. **构造三元组序列**：选取基点 $x_0 \in A \subset X$。根据三元组 $(X, A, {x_0})$ 的长正合序列： 
$$\dots \to H_n(A, {x_0}) \to H_n(X, {x_0}) \to H_n(X, A) \xrightarrow{\partial} H_{n-1}(A, {x_0}) \to \dots$$
2. **应用约化同调的识别定理**：根据定理 5.17，对于任何基点 $x_0$ 和所有 $n \ge 0$，存在同构 $H_n(X, {x_0}) \cong \tilde{H}_n(X)$。
3. **代换同构项**：将上述同构代入三元组序列：
    - 将 $H_n(A, {x_0})$ 替换为 $\tilde{H}_n(A)$。
    - 将 $H_n(X, {x_0})$ 替换为 $\tilde{H}_n(X)$。
    - 将 $H_{n-1}(A, {x_0})$ 替换为 $\tilde{H}_{n-1}(A)$。
4. **得出结论**：代换后直接得到： 
$$\dots \to \tilde{H}_n(A) \to \tilde{H}_n(X) \to H_n(X, A) \to \tilde{H}_{n-1}(A) \to \dots$$
 这种解法的好处：

- **避开了增广算子的代数细节**：它直接利用了“相对一点的同调就是约化同调”这一几何直观。
- **自动处理序列末端**：由于 $H_0(x_0, x_0) = 0$，序列末端的 $H_0(X, A) \to 0$ 会自然出现。
你的直觉非常敏锐，这正是 **相对同调群** 的几何本质。在 $(D^2, S^1)$ 这个空间对中，证明 $H_1(D^2, S^1) = 0$ 最严谨且简洁的方法是利用 **空间对的长正合序列**。

### 5.20 $H_1(D^2, S^1) = 0$

**证明过程：**

1. **写出空间对的长正合序列**： 根据定理 5.8，对于空间对 $(D^2, S^1)$，存在以下同调群的长正合序列： 
$$\dots \to H_1(D^2) \xrightarrow{j_*} H_1(D^2, S^1) \xrightarrow{d} H_0(S^1) \xrightarrow{i_*} H_0(D^2) \to \dots$$
    
2. **确定已知的绝对同调群**：
    
    - **$H_1(D^2) = 0$**：因为圆盘 $D^2$ 是凸集，所以是可缩的。根据推论 4.25，可缩空间的高维同调群为 $0$。
    - **$H_0(S^1) \cong \mathbb{Z}$ 且 $H_0(D^2) \cong \mathbb{Z}$**：因为 $S^1$ 和 $D^2$ 都是路径连通的，所以它们的 $0$ 阶同调群都同构于整数群 $\mathbb{Z}$。
3. 分析包含映射诱导的 $i_*$： 包含映射 $i: S^1 \hookrightarrow D^2$ 诱导的 $i_*: H_0(S^1) \to H_0(D^2)$ 是一个同构。这是因为在路径连通空间中，任意一点生成的同调类都是 $H_0$ 的生成元，$i$ 将 $S^1$ 的生成元映为了 $D^2$ 的生成元。
    
4. **利用正合性推导**： 将上述结果代入正合序列的末端： 
5. $$0 \to H_1(D^2, S^1) \xrightarrow{d} \mathbb{Z} \xrightarrow{\cong} \mathbb{Z}$$
    
    - 根据 $H_0(S^1)$ 处的正合性，$\text{im } d = \ker i_*$。
    - 由于 $i_*$ 是同构，其核 $\ker i_* = 0$，因此 $\text{im } d = 0$。
    - 根据 $H_1(D^2, S^1)$ 处的正合性，$d$ 的核 $\ker d = \text{im } (0 \to H_1(D^2, S^1)) = 0$。
    - 一个核为 $0$ 且像为 $0$ 的同态 $d$，其定义域 $H_1(D^2, S^1)$ 必然为 **$0$**。

#### 另一个证明：约化同调长正合列
使用习题 5.19 中的**约化同调长正合序列**，证明 $H_1(D^2, S^1) = 0$ 的过程会更加简洁，因为它能直接消掉 $n=0$ 处的平凡项。
**证明过程：**
1. **写出约化同调长正合序列**： 根据习题 5.19，对于空间对 $(D^2, S^1)$，存在以下正合序列： 
2. $$\dots \to \tilde{H}_1(D^2) \to H_1(D^2, S^1) \to \tilde{H}_0(S^1) \to \tilde{H}_0(D^2) \to \dots$$
3. **利用可缩性与连通性简化各项**：
    - **$\tilde{H}_n(D^2) = 0$**：由于圆盘 $D^2$ 是凸集，它是可缩的。对于任何可缩空间，所有维度的约化同调群均为 $0$。因此 $\tilde{H}_1(D^2) = 0$ 且 $\tilde{H}_0(D^2) = 0$。
    - **$\tilde{H}_0(S^1) = 0$**：球面 $S^1$ 是**道路连通**的。根据约化同调的性质，非空道路连通空间的 $0$ 阶约化同调群为 $0$。
4. **代入序列得出结论**： 将上述零项代入正合序列中，我们得到： $$0 \to H_1(D^2, S^1) \to 0$$ 根据正合性，夹在两个零群中间的群必然为零。 因此，**$H_1(D^2, S^1) = 0$**。
    
#### 直观解释
直觉“将任何一条边界在 $S^1$ 上的 $D^2$ 内部线段表示成一个完整的圈减去这段圆弧”在代数上对应于：

- **相对闭链**：一条两端在 $S^1$ 上的线段 $\gamma$ 满足 $\partial \gamma \in S_0(S^1)$。
- **闭合操作**：你在 $S^1$ 中找一段圆弧 $\beta$ 使得 $\partial \beta = \partial \gamma$。于是 $\gamma - \beta$ 就成了一个绝对闭链（完整的圈）。
- **平凡化**：由于 $D^2$ 内部没有洞（$H_1(D^2)=0$），这个“圈” $\gamma - \beta$ 必然是某个 2 维区域的边界（即 $\gamma - \beta \in B_1(D^2)$）。
- **结论**：这意味着 $\gamma$ 在模掉 $S^1$ 中的链 $\beta$ 后，变成了绝对边界。因此 $\gamma \in B_1(D^2, S^1)$，即**每一个相对闭链都是相对边界**，所以商群 $H_1 = 0$。
这种利用“圆盘没有洞”来填满“开口圈”的想法，正是相对同调的核心。



### 5.21 锥相对于底的1阶同调群

1. **建立长正合序列**： 对于空间对 $(CX, X)$，考虑其约化同调序列： 
2. $$\dots \to \tilde{H}_1(CX) \to H_1(CX, X) \xrightarrow{d} \tilde{H}_0(X) \to \tilde{H}_0(CX) \to \dots$$
    
2. **确定各项群结构**：
    
    - **$\tilde{H}_n(CX) = 0$**：由于锥空间 $CX$ 总是可缩的，其所有阶数的约化同调群均为 0。
    - **$\tilde{H}_0(X) \cong \mathbb{Z}^4$**：已知 $X$ 有 5 个路径连通分支，其第零维同调群 $H_0(X) \cong \mathbb{Z}^5$。根据约化同调与绝对同调的关系，$\tilde{H}_0(X)$ 的秩比 $H_0(X)$ 少 1，故 $\tilde{H}_0(X) \cong \mathbb{Z}^4$。
3. **利用正合性推导**： 将上述结果代入序列： 
4. $$0 \to H_1(CX, X) \xrightarrow{d} \mathbb{Z}^4 \to 0$$ 由于序列在 $H_1(CX, X)$ 处是正合的，连接同态 $d$ 必须是一个**同构**。
    

**$H_1(CX, X) \cong \mathbb{Z}^4$**。


### 5.22 **$H_1(S^1, S^0) \cong \mathbb{Z} \oplus \mathbb{Z}$**。

我们可以利用空间对 $(S^1, S^0)$ 的**约化同调长正合序列**（参见习题 5.19 的结论）来进行证明：

1. **写出长正合序列片段**： $$\tilde{H}_1(S^0) \to \tilde{H}_1(S^1) \xrightarrow{j_*} H_1(S^1, S^0) \xrightarrow{\partial} \tilde{H}_0(S^0) \to \tilde{H}_0(S^1)$$
    
2. **确定各项的具体群结构**：
    
    - **$\tilde{H}_1(S^0) = 0$**：因为 $S^0$ 是零维离散点集，其一维（及以上）同调群均为 0。
    - **$\tilde{H}_1(S^1) \cong \mathbb{Z}$**：一维球面的约化同调群为 $\mathbb{Z}$。
    - **$\tilde{H}_0(S^0) \cong \mathbb{Z}$**：$S^0$ 由 2 个路径连通分支组成，根据 $\text{rank}(\tilde{H}_0) = \text{card}(\Lambda) - 1$，其秩为 $2 - 1 = 1$。
    - **$\tilde{H}_0(S^1) = 0$**：由于 $S^1$ 是路径连通空间，其零阶约化同调群为 0。
3. **代入序列得出结论**： 将上述结果代入正合序列，得到一个短正合列： $$0 \to \mathbb{Z} \xrightarrow{j_*} H_1(S^1, S^0) \xrightarrow{\partial} \mathbb{Z} \to 0$$ 由于右侧的 $\mathbb{Z}$ 是**自由阿贝尔群**，该短正合列必定分裂（Split）[[Davis, Kirk Lemma 1.24 模的正合列的可裂性\|Davis, Kirk Lemma 1.24 模的正合列的可裂性]]。 因此： $$H_1(S^1, S^0) \cong \mathbb{Z} \oplus \mathbb{Z}$$
    

**几何直观**： $H_1(S^1, S^0)$ 衡量的是在圆周 $S^1$ 中，相对于两个端点 $S^0$ 而言的“回路”。这包含了一个完整的圆周回路（对应 $\tilde{H}_1(S^1)$）以及一条连接 $S^0$ 中两个不同点的路径（在相对意义下它也是一个“循环”）。将圆周捏成一个8字，所以存在两个非平凡的群，两个1维洞。

### 5.23 $H_n(X, X) = 0$

根据相对同调群的定义，我们可以从链群和循环群/边缘群两个角度给出证明：

**方法一：基于相对链复形定义**

1. 根据定义，第 $n$ 相对链群 $S_n(X, A)$ 被定义为商复形 $S_n(X)/S_n(A)$,。
2. 当子空间 $A = X$ 时，对于所有的 $n \ge 0$，相对链群 $S_n(X, X) = S_n(X)/S_n(X) \cong 0$,。
3. 由于整个相对链复形中的每一项都是零群，其对应的同调群（核模去像）自然也为零,。
4. 因此，对于所有 $n \ge 0$，$H_n(X, X) = 0$,。

**方法二：基于相对循环与相对边缘定义**

1. 根据定义，模 $X$ 的第 $n$ 相对循环群为 $Z_n(X, X) = {\gamma \in S_n(X) : \partial_n \gamma \in S_{n-1}(X)}$,。
2. 由于任何 $n$ 阶链 $\gamma$ 的边缘 $\partial_n \gamma$ 显然都属于 $S_{n-1}(X)$，因此每一个 $n$ 阶链都是相对循环，即 $Z_n(X, X) = S_n(X)$,。
3. 模 $X$ 的第 $n$ 相对边缘链群定义为 $B_n(X, X) = B_n(X) + S_n(X)$,。
4. 因为绝对边缘链群 $B_n(X)$ 本身就是 $S_n(X)$ 的子群，所以 $B_n(X) + S_n(X) = S_n(X)$,。
5. 利用相对同调群的等价定义 $H_n(X, X) \cong Z_n(X, X) / B_n(X, X)$，可得 $H_n(X, X) \cong S_n(X) / S_n(X) \cong 0$,。

这个结论在几何上非常直观：当你把空间 $X$ 中的所有部分都“模掉”（视为零或边界）时，空间中就不再剩下任何非平凡的特征了。

**方法三：利用约化同调长正合序列**

根据习题 5.19，对于任何空间对 $(X, A)$，存在约化同调的长正合序列。令 $A = X$，证明如下：

**1. 写出约化同调长正合序列** 对于空间对 $(X, X)$，考虑其约化同调序列片段： $$\dots \to \tilde{H}_n(X) \xrightarrow{i_*} \tilde{H}_n(X) \xrightarrow{j_*} H_n(X, X) \xrightarrow{d} \tilde{H}_{n-1}(X) \xrightarrow{i_*} \tilde{H}_{n-1}(X) \to \dots$$

_*2. 分析诱导同态 $i_*$_* 在此序列中，$i: X \hookrightarrow X$ 是包含映射，即恒等映射 $1_X$。 根据同调函子的性质，$i_* = H_n(1_X)$ 是 $\tilde{H}_n(X)$ 上的**恒等同构**。

**3. 利用正合性推导**

- 因为 $i_*$ 是满射，根据正合性，下一个映射 $j_*$ 的像 $\text{im } j_* = \ker i_*$。由于 $i_*$ 是同构，其核为 $0$，故 $\text{im } j_* = 0$。
- 因为 $i_*$ 是单射，根据正合性，上一个映射 $j_*$ 的核 $\ker j_* = \text{im } i_*$。由于 $i_*$ 是满射，$\text{im } i_*$ 是整个 $\tilde{H}_n(X)$，故 $\ker j_* = \tilde{H}_n(X)$。
- 综合上述两点，映射 $j_*: \tilde{H}_n(X) \to H_n(X, X)$ 既是零映射又是满射。

**4. 结论** 一个定义域为 $\tilde{H}_n(X)$ 且值为 $0$ 的满射，其陪域（Target）必然为零群。 因此，对于所有 $n \ge 0$，**$H_n(X, X) = 0$**。
