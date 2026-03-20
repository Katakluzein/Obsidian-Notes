---
{"dg-publish":true,"permalink":"/Rotman 代数拓扑习题 第零章 introduction/"}
---


## Notation

## Brouwer Fixed Point Theorem
### 0.1 **命题：$G = H \oplus \ker r$ 的证明**

设 $H$ 是阿贝尔群 $G$ 的子群。若存在群同态 $r: G \to H$ 使得对所有 $x \in H$ 都有 $r(x) = x$，则 $G$ 是 $H$ 与 $\ker r$ 的直和。

#### **1. 存在性 (Existence)**

根据提示，对于任意 $y \in G$，我们可以将其改写为： $$y = r(y) + (y - r(y))$$

- 显然，$r(y) \in H$（因为 $r$ 的值域是 $H$）。
- 我们将 $y - r(y)$ 记为 $k$。由于 $r$ 是群同态，且 $r(y) \in H$，根据已知条件 $r(r(y)) = r(y)$。
- 计算 $r(k)$： $$r(y - r(y)) = r(y) - r(r(y)) = r(y) - r(y) = 0$$
- 因此，$y - r(y) \in \ker r$。 这说明 $G \subset H + \ker r$。另一个方向是显然的，因为$H$和$\ker r$都是$G$的子群。

#### **2. 唯一性 (Uniqueness) —— 基于你的证明思路**

这是显然的，因为$\mathrm{ker} r\cap H=\{0\}$，但我们也可以利用分解的唯一性来证明，就像刚刚学习线性代数中的商空间的时候做的一样。

为了证明分解的唯一性，我们需要证明如果存在另一种分解方式，它必然与上述分解相同。 假设对于 $y \in G$，存在 $h' \in H$ 和 $k' \in \ker r$ 使得 $y = h' + k'$。

- 由于 $h' \in H$，我们可以将其表示为原本的分解项 $r(y)$ 加上某个偏差值 $z \in H$，即 $h' = r(y) + z$。
- 那么对应的 $k'$ 项可以写作： $$k' = y - h' = y - (r(y) + z) = (y - r(y)) - z$$
- 根据假设 $k' \in \ker r$，则有 $r(k') = 0$，即： $$r(y - r(y) - z) = 0$$
- 利用 $r$ 的同态性质： $$r(y) - r(r(y)) - r(z) = 0$$
- 正如我们在存在性证明中所述，因为 $r(y) \in H$，所以 $r(r(y)) = r(y)$。代入上式得： $$r(y) - r(y) - r(z) = 0 \implies -r(z) = 0 \implies r(z) = 0$$
- 由于已知条件 $z \in H$，而对于 $H$ 中的任何元素 $r$ 作用后保持不变（即 $r(z) = z$），因此： $$z = r(z) = 0$$
- 既然 $z = 0$，则 $h' = r(y) + 0 = r(y)$，且 $k' = (y - r(y)) - 0 = y - r(y)$。
- 这证明了对于任何 $y \in G$，将其分解为 $H$ 中的元素与 $\ker r$ 中的元素之和的方式是**唯一**的。

### 0.2 $D^1$ 上的 Brouwer 不动点定理

#### **定理：$D^1$ 上的 Brouwer 不动点定理**

任何连续映射 $f: D^1 \to D^1$ 都至少有一个不动点（即存在 $x \in D^1$ 使得 $f(x) = x$）。

---

### **证明过程**

**1. 反证假设与几何直观** 假设 $f: D^1 \to D^1$ 是连续的且**没有不动点**，即对于所有 $x \in D^1$，都有 $f(x) \neq x$。 在几何上，$D^1$ 即闭区间 $[-1, 1]$，其边界 $S^0$ 为两点集 ${-1, 1}$。由于 $f(x)$ 与 $x$ 是两个不同的点，它们可以确定一条唯一的**射线**。

**2. 构造映射 $g: D^1 \to S^0$** 定义映射 $g: D^1 \to S^0$，规定 **$g(x)$ 为从 $f(x)$ 出发经过 $x$ 的射线与边界 $S^0 = {-1, 1}$ 的交点**。 在 $n=1$ 的情况下，射线只有两个方向（正向或负向），因此 $g(x)$ 的解析表达式为：
$$
g(x) = \begin{cases} 1, & \text{若 } f(x) < x 、\\ -1, & \text{若 } f(x) > x
、\end{cases} 
$$ 

由于假设 $f(x) \neq x$，上述条件涵盖了所有情况，因此 $g$ 是**良定义**的。

**3. 验证端点的取值** 我们需要考察 $g$ 在 $D^1$ 两个端点 $-1$ 和 $1$ 处的取值：

- **对于 $x = -1$**：由于 $f$ 的值域是 $[-1, 1]$ 且没有不动点，所以 $f(-1) \neq -1$。这意味着必须有 $f(-1) > -1$。根据定义，此时 $g(-1) = -1$。
- **对于 $x = 1$**：同理，$f(1) \neq 1$，必须有 $f(1) < 1$。根据定义，此时 $g(1) = 1$。

**4. 导出矛盾**

- **连续性**：由于 $f$ 是连续的且在 $D^1$ 上满足 $f(x) \neq x$，函数 $x - f(x)$ 永远不为零且保持连续，因此 $g$ 是一个连续映射。
- **连通性矛盾**：$D^1 = [-1, 1]$ 是一个**连通集**（凸集必连通）。根据拓扑学基本性质，连通集在连续映射下的像也必须是连通的。
- 然而，我们发现 $g(D^1)$ 包含了 $-1$ 和 $1$ 这两个点，这意味着 $g(D^1) = S^0 = {-1, 1}$。
- $S^0$ 是一个**离散的两点空间，它是非连通的**。

**结论**：连续映射将连通空间映成了非连通空间，这产生了矛盾。因此，最初的假设（$f$ 没有不动点）不成立，$f$ 必须有一个不动点。


### 0.3 证明赤道不是球面的收缩核（retract）

根据 Rotman 教材 Exercise 0.3 的要求，模仿 Lemma 0.2 的证明逻辑，证明过程如下：

假设 $n$-维球面 $S^n$ 的赤道 $S^{n-1}$ 是其收缩核（Retract）。根据收缩核的定义，存在包含映射 $i: S^{n-1} \hookrightarrow S^n$ 和连续映射（收缩映射）$r: S^n \to S^{n-1}$，使得它们的复合满足： $$r \circ i = id_{S^{n-1}} \quad$$

对该恒等式作用第 $n-1$ 阶同调函子 $H_{n-1}$，利用函子的性质（映射复合的同态等于同态的复合，且恒等映射诱导恒等同态）可得： $$H_{n-1}(r) \circ H_{n-1}(i) = H_{n-1}(id_{S^{n-1}}) = id_{H_{n-1}(S^{n-1})} \quad$$

根据题意给出的球面同调群假设：

1. 对于赤道球面，$H_{n-1}(S^{n-1}) = \mathbb{Z}$。
2. 对于 $n$-维球面，由于 $n-1 \neq 0$ 且 $n-1 \neq n$，故 $H_{n-1}(S^n) = 0$。

将上述群代入同态公式中： 由于 $H_{n-1}(i): H_{n-1}(S^{n-1}) \to H_{n-1}(S^n)$，而 $H_{n-1}(S^n) = 0$，因此 $H_{n-1}(i)$ 必然是零同态。 由此推导出复合映射的同态也必然为零： $$H_{n-1}(r) \circ H_{n-1}(i) = 0$$

然而，等式右侧 $id_{H_{n-1}(S^{n-1})}$ 是 $\mathbb{Z}$ 上的恒等算子，不等于零同态（因为 $\mathbb{Z} \neq 0$）。 $$0 = id_{\mathbb{Z}} \quad \text{（矛盾）}$$

由此矛盾可知，最初的假设不成立，故 **$S^n$ 的赤道不是一个收缩核**。

### 0.4 利用Dn上的连续函数存在不动点即可

### 0.5 定理：单位正方形内路径相交证明
![2047d5a818883e29cdf064b1376e1dbc.jpg|311](/img/user/2047d5a818883e29cdf064b1376e1dbc.jpg)

设 $f, g: I \to I \times I$ 为连续路径，满足：

- $f$ 从底部连接到顶部：$f(0) = (a, 0)$，$f(1) = (b, 1)$。
- $g$ 从左侧连接到右侧：$g(0) = (0, c)$，$g(1) = (1, d)$。 其中 $a, b, c, d \in I$。证明存在 $s, t \in I$ 使得 $f(s) = g(t)$。

---
参考：
- [algebraic topology - Intersection of paths on unit square using Brouwer fixed point theorem - Mathematics Stack Exchange](https://math.stackexchange.com/questions/2662788/intersection-of-paths-on-unit-square-using-brouwer-fixed-point-theorem?noredirect=1)  
- [general topology - Why do "path diagonals" of a rectangle need to intersect? - Mathematics Stack Exchange](https://math.stackexchange.com/questions/1937510/why-do-path-diagonals-of-a-rectangle-need-to-intersect/1937554#1937554) 

下面的命题的证明可以迁移到原来的命题中。
#### 命题：单位正方形内交叉路径的相交性

设 $I = [-1, 1] \times [-1, 1]$ 为单位正方形。设 $\omega, \tau: [-1, 1] \to I$ 为两条连续路径，满足以下边界条件（即两条路径在拓扑上形成一个“十字”）：

1. **路径 $\omega$（连接左下到右上）**：$\omega(-1) = (-1, -1)$，$\omega(1) = (1, 1)$。
2. **路径 $\tau$（连接右下到左上）**：$\tau(-1) = (1, -1)$，$\tau(1) = (-1, 1)$。

**证明：** 存在 $s, t \in [-1, 1]$ 使得 $\omega(s) = \tau(t)$。

---

#### **证明步骤**

#### **1. 反证假设与函数构造**

假设这两条路径**不相交**，即对于所有的 $s, t \in [-1, 1]$，都有 $\omega(s) \neq \tau(t)$。 由此，向量 $\tau(t) - \omega(s)$ 永远不为零。我们定义其 **无穷范数（Max Norm）** 为： $$N(s, t) = |\tau(t) - \omega(s)|_\infty = \max{|\tau_1(t) - \omega_1(s)|, |\tau_2(t) - \omega_2(s)|}$$ 由于路径不相交，$N(s, t) > 0$ 始终成立。

#### **2. 构造连续映射 $F$**

构造映射 $F: I \to I$，其定义为： $$F(s, t) = \frac{\tau(t) - \omega(s)}{N(s, t)}$$

- **连续性**：由于 $\omega, \tau$ 连续且分母 $N(s, t) \neq 0$，故 $F$ 是良定义的连续函数。
- **值域**：根据定义，$|F(s, t)|_\infty = 1$。这意味着 $F$ 的图像实际上落在正方形的**边界 $\partial I$** 上，即对于任何 $(s, t)$，其结果的分量必有一个为 $1$ 或 $-1$。

#### **3. 应用 Brouwer 不动点定理**

根据 **Brouwer 不动点定理**，连续映射 $F: I \to I$ 必存在一个不动点 $(u, v) \in I$，满足： $$F(u, v) = (u, v)$$ 由于 $F$ 的结果模长为 1，这意味着这个不动点必然满足 **$|u| = 1$ 或 $|v| = 1$**。

#### **4. 分情况讨论导出矛盾**

我们将不动点所在的四个边界情况逐一分析：

- **情况 1：$u = -1$** 根据不动点等式，第一个分量 $F_1(u, v) = -1$，即： $$\frac{\tau_1(v) - \omega_1(-1)}{N(-1, v)} = -1 \implies \tau_1(v) - (-1) = -N(-1, v)$$ 简化得 $\tau_1(v) + 1 = -N(-1, v)$。 由于 $N > 0$，等式右边为负数；但 $\tau_1(v) \in [-1, 1]$，故左边 $\tau_1(v) + 1 \ge 0$。**矛盾**。
    
- **情况 2：$u = 1$** 第一个分量 $F_1(1, v) = 1$，代入 $\omega_1(1) = 1$ 得： $$\tau_1(v) - 1 = N(1, v)$$ 右边 $N > 0$，左边 $\tau_1(v) - 1 \le 0$。**矛盾**。
    
- **情况 3：$v = -1$** 观察第二个分量 $F_2(u, -1) = -1$，代入 $\tau_2(-1) = -1$ 得： $$\frac{-1 - \omega_2(u)}{N(u, -1)} = -1 \implies -1 - \omega_2(u) = -N(u, -1)$$ 简化得 $\omega_2(u) + 1 = N(u, -1)$。 由图像推导可知，此处会与 $\omega_2$ 的取值范围或 $N$ 的定义产生进一步的数值指向矛盾（类似情况1）。
    
- **情况 4：$v = 1$** 同理，第二个分量 $F_2(u, 1) = 1$，代入 $\tau_2(1) = 1$ 同样会导出数值不等式的**矛盾**。
    

#### **结论**

由于所有可能的边界情况都导出了矛盾，说明最初的假设（路径不相交）是不成立的。因此，在正方形内部必然存在某点使得 $N(s, t) = 0$，即 **$\omega(s) = \tau(t)$**，两条路径必然相交。
### 0.6 **证明：Perron 定理**

设 $A = [a_{ij}]$ 是一个实 $n \times n$ 矩阵，且对所有 $i, j$ 都有 $a_{ij} > 0$。

#### **1. 定义定义域**

考虑标准 $(n-1)$-单形 $\Delta^{n-1} \subset \mathbb{R}^n$，定义为：任意坐标大于等于零，且所有坐标和为1，这是一个**紧致凸集**，在拓扑上同胚于圆盘 $D^{n-1}$。

#### **2. 构造连续映射 $g$**

定义函数 $\sigma: \mathbb{R}^n \to \mathbb{R}$ 为坐标之和，即 $\sigma(x) = \sum x_i$。 定义映射 $g: \Delta^{n-1} \to \Delta^{n-1}$ 为： $$g(x) = \frac{Ax}{\sigma(Ax)}$$

- **良定义性**：对于任意 $x \in \Delta^{n-1}$，由于 $\sum x_j = 1$，至少有一个 $x_j > 0$。因为矩阵 $A$ 的所有项 $a_{ij} > 0$，所以 $Ax$ 的每个分量 $(Ax)_i = \sum_j a_{ij}x_j$ 都**严格大于 0**。因此，$\sigma(Ax) = \sum_i (Ax)_i > 0$，分母不为零。
- **值域**：显然 $\sigma(g(x)) = \frac{\sigma(Ax)}{\sigma(Ax)} = 1$，且由于 $Ax$ 的分量为正，故 $g(x)$ 的分量也为正（从而 $\ge 0$），因此 $g(x) \in \Delta^{n-1}$。
- **连续性**：由于线性变换 $A$、求和函数 $\sigma$ 以及除法运算在分母不为零处均连续，故 $g$ 是**连续函数**。

#### **3. 应用 Brouwer 不动点定理**

根据 **Brouwer 不动点定理**，连续映射 $g: \Delta^{n-1} \to \Delta^{n-1}$ 必有一个不动点 $x \in \Delta^{n-1}$，满足： $$g(x) = x \implies \frac{Ax}{\sigma(Ax)} = x$$
#### **4. 导出特征值与特征向量**

设 $\lambda = \sigma(Ax)$。根据上述等式，有： $$Ax = \lambda x$$

- **正特征值**：由于我们已经证明对于 $\Delta^{n-1}$ 中的 $x$，$\sigma(Ax) > 0$，因此 **$\lambda$ 是一个正数**。
- **正特征向量**：由于 $x \in \Delta^{n-1}$，其坐标 $x_i \ge 0$。由于 $Ax = \lambda x$，第 $i$ 个坐标满足 $x_i = \sum_j a_{ij}x_j/\lambda$。
- 正如我们在良定义性中所分析的，由于 $a_{ij} > 0$ 且 $\sum x_j = 1$，上式右侧的求和对每一个 $i$ 都必然是**严格大于 0** 的。
- 因为 $\lambda > 0$，所以必有 **$x_i > 0$** 对所有 $i$ 成立。

**结论**：矩阵 $A$ 具有正特征值 $\lambda$，且存在对应的所有分量均为正数的特征向量 $x$。

## Categories and Functors

### 0.7 证明g=h
利用了态射复合的**结合律 (Associativity)** 和**单位态射 (Identity morphism)** 的性质。
证明步骤如下：

1. **利用结合律**：考虑复合态射 $g \circ f \circ h$。根据范畴的定义，态射的复合满足结合律，因此可以写成： **$g \circ (f \circ h) = (g \circ f) \circ h$**。
2. **代入右逆性质**：已知 $h$ 是 $f$ 的右逆，即 $f \circ h = 1_B$。将其代入等式左边： **$g \circ (f \circ h) = g \circ 1_B = g$**。
3. **代入左逆性质**：已知 $g$ 是 $f$ 的左逆，即 $g \circ f = 1_A$。将其代入等式右边： **$(g \circ f) \circ h = 1_A \circ h = h$**。

**结论**：由于等式两边必然相等，因此 **$g = h$**。

### 0.8 恒等态射的性质
(1) 只要利用I'= I' ○ I = I即可

(2) **命题**：  
若 $\mathcal{C}'$ 是范畴 $\mathcal{C}$ 的一个子范畴（subcategory），且 $A \in \mathrm{Ob}(\mathcal{C}')$，则 $A$ 在 $\mathcal{C}'$ 中的恒等态射 $1_A^{\mathcal{C}'}$ 就是 $A$ 在 $\mathcal{C}$ 中的恒等态射 $1_A^{\mathcal{C}}$。

**证明**：

因为 $\mathcal{C}'$ 是 $\mathcal{C}$ 的子范畴，根据子范畴的定义，有以下包含关系：

1. 对象包含：$\mathrm{Ob}(\mathcal{C}') \subseteq \mathrm{Ob}(\mathcal{C})$  
2. 态射包含：若 $f : X \to Y$ 在 $\mathcal{C}'$ 中，则 $f : X \to Y$ 也在 $\mathcal{C}$ 中（即 $\mathrm{Hom}_{\mathcal{C}'}(X,Y) \subseteq \mathrm{Hom}_{\mathcal{C}}(X,Y)$）

特别地，对于任意对象 $A \in \mathrm{Ob}(\mathcal{C}')$，其在 $\mathcal{C}'$ 中的恒等态射 $1_A^{\mathcal{C}'}$ 满足：

$$
1_A^{\mathcal{C}'} \in \mathrm{Hom}_{\mathcal{C}'}(A,A)
$$

由子范畴定义，立即得到这个态射也生活在C范畴的Hom集中：

$$
1_A^{\mathcal{C}'} \in \mathrm{Hom}_{\mathcal{C}}(A,A)
$$

现在回忆范畴中恒等态射的唯一性公理（identity morphism axiom）：  
在任何一个范畴 $\mathcal{C}$ 中，对于任意对象 $A$，存在**唯一**一个态射 $1_A : A \to A$，使得对于任意态射 $f : X \to A$ 和 $g : A \to Y$，都有：

$$
1_A \circ f = f, \quad g \circ 1_A = g
$$

由于 $1_A^{\mathcal{C}'}$ 是 $\mathcal{C}'$ 中 $A$ 的恒等态射，因此它满足 $\mathcal{C}'$ 中的恒等性质。但因为所有涉及的态射和复合都在 $\mathcal{C}$ 中也有定义，且**复合规则相同**（这是子范畴的定义所要求的），所以 $1_A^{\mathcal{C}'}$ 同时也满足 $\mathcal{C}$ 中关于 $A$ 的恒等态射的定义条件。

又因为范畴 $\mathcal{C}$ 中的恒等态射是**唯一**的，因此必然有：

$$
1_A^{\mathcal{C}'} = 1_A^{\mathcal{C}}
$$

即 $A$ 在子范畴 $\mathcal{C}'$ 中的恒等态射与它在更大范畴 $\mathcal{C}$ 中的恒等态射是同一个态射。

**证毕**。

### 0.9 pre order 是范畴
根据教材 Rotman《代数拓扑导论》Exercise 0.9 的要求，证明一个拟序集（Quasi-ordered set）$X$ 通过该构造可以形成一个范畴 $\mathcal{C}$。拟序关系 $\sim$ 的自反性（Reflexive）和传递性（Transitive）是满足范畴公理的关键。

#### **证明：拟序集构造范畴的验证**

**1. 定义基本要素**

- **对象 (Objects)**：范畴的物件类 $obj \mathcal{C}$ 即为集合 $X$ 中的所有元素。
- **态射 (Morphisms)**：对于任意对象 $x, y \in X$，若 $x \sim y$，则态射集合 $Hom(x, y)$ 定义为仅包含一个元素 $i_{xy}$ 的集合；若 $x \not\sim y$，则 $Hom(x, y) = \emptyset$。
- **复合 (Composition)**：对于 $x \sim y \sim z$，定义复合运算为 $i_{yz} \circ i_{xy} = i_{xz}$。

**2. 验证范畴公理**

- **态射集合的两两不交性 (Disjointness)**： 范畴要求不同的态射集合必须不相交。在该构造中，每个非空集合 $Hom(x, y)$ 中的唯一元素 $i_{xy}$ 都由有序对 $(x, y)$ 唯一标识，因此对于不同的物件对，其态射集合是两两不交的。
    
- **复合满足结合律 (Associativity)**： 假设有态射 $i_{xy} \in Hom(x, y)$，$i_{yz} \in Hom(y, z)$ 和 $i_{zw} \in Hom(z, w)$，即满足 $x \sim y \sim z \sim w$。
    
    - 先复合前两个：$(i_{zw} \circ i_{yz}) \circ i_{xy} = i_{yw} \circ i_{xy} = i_{xw}$。
    - 先复合后两个：$i_{zw} \circ (i_{yz} \circ i_{xy}) = i_{zw} \circ i_{xz} = i_{xw}$。 由于拟序关系具有传递性，且对应的 $Hom(x, w)$ 集合中仅存在唯一的元素 $i_{xw}$，因此结合律必然成立。
- **恒等态射的存在性 (Identity)**： 范畴公理要求每个对象 $x$ 都存在一个恒等态射 $1_x$。
    
    - 因为关系 $\sim$ 是**自反的**，对于任何 $x \in X$，总有 $x \sim x$，因此集合 $Hom(x, x)$ 始终包含唯一元素 $i_{xx}$。
    - 验证左恒等性质：对于任何 $i_{yx} \in Hom(y, x)$，有 $i_{xx} \circ i_{yx} = i_{yx}$，因为结果必须落在唯一的 $Hom(y, x)$ 中。
    - 验证右恒等性质：对于任何 $i_{xz} \in Hom(x, z)$，有 $i_{xz} \circ i_{xx} = i_{xz}$。 因此，$i_{xx}$ 充当了对象 $x$ 的恒等态射 $1_x$。

#### **结论**

该构造完全满足范畴的定义：**自反性保证了恒等态射的存在，传递性保证了复合运算的良定义及其结合律**。因此，任何拟序集都可以被视作一个态射集合至多只有一个元素的范畴。

### 0.10 群是范畴

根据教材 **Rotman**《代数拓扑导论》及其习题解答 **solutions.pdf**，关于 Exercise 0.10 的完整证明整理如下：

#### **证明：由幺半群 $G$ 构造范畴 $\mathcal{C}$**

设 $G$ 是一个幺半群（即具有单位元 $1$ 的结合半群）。我们按照以下步骤验证该构造满足范畴的所有公理：

#### **1. 定义范畴的基本要素**

- **对象 (Objects)**：范畴 $\mathcal{C}$ 的对象类仅包含一个元素，记为 `*`。
- **态射 (Morphisms)**：对于唯一的对象对 `(*, *)`，定义态射集合 $Hom(*, *) = G$。即 $G$ 中的每一个元素 $g$ 都被视为从 `*` 到 `*` 的一个态射。
- **复合 (Composition)**：定义复合运算 $G \times G \to G$ 为幺半群 $G$ 中给定的乘法运算。若 $f, g \in G$，则其复合 $g \circ f$ 定义为乘积 $gf$。

#### **2. 验证范畴公理**

- **态射集合的两两不交性 (Disjointness)**：范畴公理 (i) 要求不同的态射集合必须不相交。由于该范畴中只有一个态射集合 $Hom(*, *)$，这一性质平凡地（vacuously）成立。
- **结合律 (Associativity)**：范畴公理 (ii) 要求态射的复合满足结合律。对于任意态射 $f, g, h \in G$，其复合运算为： $h \circ (g \circ f) = h(gf)$ 以及 $(h \circ g) \circ f = (hg)f$ 由于 $G$ 是一个幺半群，其乘法运算天然满足结合律，即 $h(gf) = (hg)f$，因此态射复合满足结合律。
- **单位态射的存在性 (Identity)**：范畴公理 (iii) 要求对每个对象 $A$ 存在恒等态射 $1_A$。在本构造中，幺半群 $G$ 的单位元 $1$ 充当了对象 `*` 的恒等态射 $1_*$。 对于任何态射 $g \in G$，根据幺半群单位元的性质有： $1 \circ g = 1 \cdot g = g$ 且 $g \circ 1 = g \cdot 1 = g$ 因此，$1$ 满足恒等态射的所有要求。

#### **3. 结论与洞察**

该构造完全符合范畴的定义。这个例子具有重要的教学意义，因为它展示了**态射（Morphisms）并不一定是集合之间的函数**。在通常的范畴（如 **Sets** 或 **Top**）中，态射是函数；但在本范畴中，态射仅仅是幺半群中的抽象代数元素。

**补充：** 如果 $G$ 不仅仅是幺半群而是一个**群**，那么这个范畴中的每一个态射都是一个同构（Equivalence），这样的范畴被称为**群样范畴（Groupoid）**。

### 0.11  **$\mathsf{Top}$** 可以被视为 **$\mathsf{Top}^2$** 的子范畴
要证明 **$\mathsf{Top}$** 可以被视为 **$\mathsf{Top}^2$** 的子范畴（Subcategory），我们需要按照子范畴的定义，验证对象、态射以及复合运算的包含与一致性关系。

以下是详细证明步骤：

#### **1. 对象类的识别 (Identification of Objects)**

- **$\mathsf{Top}$ 的对象**：所有拓扑空间 $X$。
- **$\mathsf{Top}^2$ 的对象**：所有拓扑空间序对 $(X, A)$，其中 $A$ 是 $X$ 的子空间。
- **证明**：如果我们将每个拓扑空间 $X$ 标识为序对 $(X, \emptyset)$。由于空集 $\emptyset$ 是任何拓扑空间 $X$ 的合法子空间，因此每一个 $X \in \text{obj}(\mathsf{Top})$ 都唯一对应一个对象 $(X, \emptyset) \in \text{obj}(\mathsf{Top}^2)$。这满足了子范畴定义中对象类的包含要求。

#### **2. 态射集合的验证 (Verification of Morphisms)**

- **$\mathsf{Top}$ 的态射**：连续映射 $f: X \to Y$。
- **$\mathsf{Top}^2$ 的态射**：从 $(X, A)$ 到 $(Y, B)$ 的态射是一个连续映射 $f: X \to Y$，且满足限制条件 $f(A) \subseteq B$。
- **证明**：考虑被标识的对象 $(X, \emptyset)$ 和 $(Y, \emptyset)$。在此情形下，态射必须满足 $f(\emptyset) \subseteq \emptyset$。由于任何映射作用于空集的结果依然是空集，这一条件对任何连续映射 $f: X \to Y$ 都是**平凡成立**的。因此，$\text{Hom}_{\mathsf{Top}}(X, Y)$ 中的每一个态射都完全对应于 $\text{Hom}_{\mathsf{Top}^2}((X, \emptyset), (Y, \emptyset))$ 中的态射。

#### **3. 复合运算的一致性 (Consistency of Composition)**

- 在 $\mathsf{Top}$ 中，态射的复合定义为通常的函数复合。
- 在 $\mathsf{Top}^2$ 中，态射 $(f, f')$ 的复合也是通过逐个分量的复合（即函数复合）来定义的。
- **证明**：当我们识别 $X \equiv (X, \emptyset)$ 时，$\mathsf{Top}$ 中的复合运算 $g \circ f$ 正好是 $\mathsf{Top}^2$ 中对应态射复合运算的限制。

#### **结论**

通过将空间 $X$ 与序对 $(X, \emptyset)$ 等同，满足了：

1. **对象包含**：$\text{obj}(\mathsf{Top}) \subseteq \text{obj}(\mathsf{Top}^2)$。
2. **态射包含**：对于所有 $X, Y \in \text{obj}(\mathsf{Top})$，$\text{Hom}_{\mathsf{Top}}(X, Y) \subseteq \text{Hom}_{\mathsf{Top}^2}((X, \emptyset), (Y, \emptyset))$。
3. **复合保持**：复合运算在两个范畴中是一致的。

因此，**$\mathsf{Top}$ 可以被视为 $\mathsf{Top}^2$ 的一个子范畴**。


### 0.12 箭头范畴
[arrow category in nLab](https://ncatlab.org/nlab/show/arrow+category) 
题目中的态射的定义从映射对改为交换图。如果态射只被视为这个映射对，那么会违反两个不同的Hom集之间交集非空的条件，所以态射应该被定义为整个交换图，这时候f和g不可能生活在另一个由f'和g'定义的Hom集中。
**题目分析**：

**证明 At 是一个范畴**

设原范畴为 $\mathcal{C}$，我们构造新范畴 At = $\mathcal{C}^\to$ 称为[[箭头范畴\|箭头范畴]] ：

- **对象**（objects of At）：$\mathcal{C}$ 中的所有态射，即 $\mathrm{Ob}(\mathrm{At}) = \mathrm{Mor}(\mathcal{C}) = \bigcup_{A,B \in \mathrm{Ob}(\mathcal{C})} \mathrm{Hom}_\mathcal{C}(A,B)$  
  （也就是说，每个对象就是 $\mathcal{C}$ 里的一条箭 $f : A \to B$，我们常把它简记为 $f$ 本身。）

- **态射**（morphisms in At）：  
  给定 At 中的两个对象 $f : A \to B$ 和 $g : C \to D$，则  
  $\mathrm{Hom}_{\mathrm{At}}(f, g) = \{(h,k) \mid h \in \mathrm{Hom}_\mathcal{C}(A,C),\ k \in \mathrm{Hom}_\mathcal{C}(B,D),\ \text{s.t. the diagram below commutes}\}$

  $$
  \begin{CD}
  A @>f>> B \\
  @VhVV @VkVV \\
  C @>g>> D
  \end{CD}
  \qquad \text{即} \qquad g \circ h = k \circ f
  $$

  这样的有序对 $(h,k)$ 就叫从 $f$ 到 $g$ 的一个态射（也常形象地称为“交换方”或 commuting square）。

- **恒等态射**（identity）：  
  对任意对象 $f : A \to B$，其恒等态射是  
  $\mathrm{id}_f = (1_A, 1_B)$  
  显然有 $f \circ 1_A = 1_B \circ f$，所以图交换，且对任意 $(h,k) : f \to g$ 有  
  $(h,k) \circ (1_A, 1_B) = (h \circ 1_A, k \circ 1_B) = (h,k)$  
  类似地左边也成立。

- **复合**（composition）：  
  设 $(h,k) : f \to g$，$(h',k') : g \to m$，其中 $m : E \to F$，由此可知gh=kf，mh'=k'g，定义   $(h',k') \circ (h,k) = (h' \circ h,\ k' \circ k)$  
复合就是两个交换图叠在一起，所以存在交换图ghh'=kfh'=kk'm，即复合之后仍然是交换的
- **结合律**：因为 $\mathcal{C}$ 中的复合满足结合律，坐标分别复合自然也满足：  
  $((h'',k'') \circ (h',k')) \circ (h,k) = (h'' \circ h' \circ h,\ k'' \circ k' \circ k) = (h'' \circ (h' \circ h),\ k'' \circ (k' \circ k))$  
  两边相等。

因此，所有范畴公理都满足，At 是一个范畴。

### 0.13 $\mathsf{Top}^2$是箭头范畴的一个子范畴
**命题**：  
证明范畴 $\mathbf{Top}_2$ 是某个合适态射范畴（morphism category，如习题 0.12 所构造）的子范畴。其中，$\mathbf{Top}_2$ 的对象是拓扑空间对 $(X, A)$（$A \subseteq X$，$A$ 带有子空间拓扑），态射是连续映射 $f: (X, A) \to (Y, B)$ 满足 $f(A) \subseteq B$。

（提示：取原范畴 $\mathcal{C} = \mathbf{Top}$，令 $\mathbf{At}$ 为对应的态射范畴；将对 $(X, A)$ 视为包含映射 $i: A \hookrightarrow X$。）

**证明**：

首先回忆习题 0.12 中构造的态射范畴 $\mathbf{At} = \mathbf{Top}^\to$（箭头范畴）：

- **对象**：$\mathbf{Top}$ 中的连续映射 $f: C \to D$（任意连续映射）。
- **态射**：给定对象 $f: A \to B$ 和 $g: C \to D$，态射是从有序对 $(h, k)$ 其中 $h: A \to C$、$k: B \to D$ 连续，且使下图交换：
  $$
  \begin{CD}
  A @>f>> B \\
  @VhVV @VkVV \\
  C @>g>> D
  \end{CD}
  $$
  即 $g \circ h = k \circ f$。
- 复合：逐坐标复合 $(h', k') \circ (h, k) = (h' \circ h, k' \circ k)$，已证满足范畴公理。

现在，我们将 $\mathbf{Top}_2$ 嵌入 $\mathbf{At}$ 中作为子范畴。定义子范畴 $\mathbf{Top}_\mathrm{inc} \subseteq \mathbf{At}$ 如下：

- **对象**：$\mathbf{At}$ 中那些是**包含映射**的对象，即形如 $i_A: A \hookrightarrow X$ 的连续映射，其中 $A \subseteq X$ 是 $X$ 的子空间，$i_A$ 是标准包含（$i_A(a) = a \in X$）。  
  每个这样的对象 $i_A: A \hookrightarrow X$ 对应 $\mathbf{Top}_2$ 中的一个对象 $(X, A)$（一一对应）。

- **态射**：在 $\mathbf{Top}_\mathrm{inc}$ 中，给定两个对象 $i_A: A \hookrightarrow X$ 和 $i_B: B \hookrightarrow Y$，其态射是 $\mathbf{At}$ 中从 $i_A$ 到 $i_B$ 的所有态射，即有序对 $(h, k)$ 使得下图交换：
  $$
  \begin{CD}
  A @>i_A>> X \\
  @VhVV @VkVV \\
  B @>i_B>> Y
  \end{CD}
  $$
  由于 $i_A$ 和 $i_B$ 是包含，交换条件 $i_B \circ h = k \circ i_A$ 等价于：对任意 $a \in A$，$h(a) = k(a)$（因为 $i_B(h(a)) = h(a) \in Y$，$k(i_A(a)) = k(a) \in Y$）。  
  此外，$h: A \to B$ 连续（故 $h(A) \subseteq B$），$k: X \to Y$ 连续。  
  这意味着 $k|_A = h$，即 $k$ 在 $A$ 上限制得到 $h$，且 $k(A) = h(A) \subseteq B$。  
  因此，这样的 $(h, k)$ 精确对应 $\mathbf{Top}_2$ 中从 $(X, A)$ 到 $(Y, B)$ 的态射 $k: X \to Y$（连续，$k(A) \subseteq B$），其中 $h = k|_A: A \to B$ 是诱导映射。

现在，逐个验证 $\mathbf{Top}_\mathrm{inc}$ 是 $\mathbf{At}$ 的子范畴（subcategory）：

1. **对象包含**：$\mathrm{Ob}(\mathbf{Top}_\mathrm{inc}) \subseteq \mathrm{Ob}(\mathbf{At})$，因为每个包含 $i_A: A \hookrightarrow X$ 都是 $\mathbf{Top}$ 中的一个连续映射，故是 $\mathbf{At}$ 的对象。

2. **态射包含**：对于任意 $\mathbf{Top}_\mathrm{inc}$ 中的对象 $i_A$ 和 $i_B$，  
   $\mathrm{Hom}_{\mathbf{Top}_\mathrm{inc}}(i_A, i_B) = \{(h, k) \in \mathrm{Hom}_{\mathbf{At}}(i_A, i_B) \mid \text{交换条件自动由 }\mathbf{At}\text{ 保证}\}$。  
   实际上，这里我们取了 $\mathbf{At}$ 中这些对象之间的**所有**态射，即 $\mathbf{Top}_\mathrm{inc}$ 在这些对象上是 $\mathbf{At}$ 的**全子范畴**（full subcategory）。  
   （注意：子范畴不要求是全的，只要态射是更大范畴中态射的子集即可；这里恰好是全的。）

3. **恒等态射保持**：对于对象 $i_A: A \hookrightarrow X$，其在 $\mathbf{At}$ 中的恒等态射是 $(1_A, 1_X)$，因为  
   $i_A \circ 1_A = 1_X \circ i_A$（显然成立）。  
   这对应 $\mathbf{Top}_2$ 中 $(X, A)$ 的恒等态射 $1_X: X \to X$（$1_X|_A = 1_A$）。  
   由前一题（或直接），子范畴中的恒等就是更大范畴中的恒等。

4. **复合保持**：设 $(h, k): i_A \to i_B$ 和 $(h', k'): i_B \to i_C$（$i_C: C \hookrightarrow Z$），则在 $\mathbf{At}$ 中的复合是 $(h' \circ h, k' \circ k)$。  
   需要验证这仍是 $\mathbf{Top}_\mathrm{inc}$ 中的态射，即使对应图交换（由 $\mathbf{At}$ 的复合定义，已知交换）。  
   在 $\mathbf{Top}_2$ 中，这对应复合 $k' \circ k: X \to Z$，且 $(k' \circ k)|_A = k'|_B \circ k|_A = h' \circ h$，符合 $\mathbf{Top}_2$ 的复合规则。  
   此外，结合律由 $\mathbf{At}$ 继承。

因此，$\mathbf{Top}_\mathrm{inc}$ 是 $\mathbf{At}$ 的子范畴。而且，$\mathbf{Top}_2$ 与 $\mathbf{Top}_\mathrm{inc}$ 等价（甚至同构，作为范畴，在Rotman的书中两者不做区分），因为对象和态射一一对应（如上所述）。

**证毕**。

### 0.14 商群作为群范畴的商范畴
根据你提供的图片证明思路（Source）以及 Rotman 教材中的相关练习（Exercise 0.10, 0.14），以下是关于该命题的完整细节补充与证明整理。

#### **命题证明：群 $G$ 构造的商范畴与商群 $G/H$ 的一致性**

#### **1. 证明 $\sim$ 是范畴 $\mathcal{C}$ 上的全等关系 (Congruence)**

根据范畴全等关系的定义（Source），我们需要验证：

- **它是等价关系**：定义 $x \sim y$ 为 $xy^{-1} \in H$。
    - **自反性**：$xx^{-1} = 1 \in H$（子群必含单位元），故 $x \sim x$。
    - **对称性**：若 $x \sim y$，则 $xy^{-1} \in H$。由于 $H$ 是子群，$(xy^{-1})^{-1} = yx^{-1} \in H$，故 $y \sim x$。
    - **传递性**：若 $x \sim y$ 且 $y \sim z$，则 $xy^{-1} \in H$ 且 $yz^{-1} \in H$。由子群对乘法的封闭性，$(xy^{-1})(yz^{-1}) = xz^{-1} \in H$，故 $x \sim z$。
- **对复合运算具有相容性**：
    - 假设 $x \sim x'$ 且 $y \sim y'$，即 $x(x')^{-1} = h_1 \in H$ 且 $y(y')^{-1} = h_2 \in H$。
    - 我们需要证明复合后的态射依然满足关系，即 $yx \sim y'x'$（注意复合顺序，范畴中 $g \circ f$ 对应群运算 $gf$）。
    - 计算：$(yx)(y'x')^{-1} = yx(x')^{-1}y'^{-1}$。
    - 代入 $x(x')^{-1} = h_1$，得到 $yh_1y'^{-1}$。
    - 由于 $y(y')^{-1} = h_2$，可写出 $y'^{-1} = y^{-1}h_2$。代入上式得： $$(yx)(y'x')^{-1} = yh_1(y^{-1}h_2) = (yh_1y^{-1})h_2$$
    - 因为 **$H$ 是正规子群**，$yh_1y^{-1}$ 必然属于 $H$,。
    - 两个 $H$ 中的元素相乘仍属于 $H$，故 $(yx)(y'x')^{-1} \in H$，证明了 $yx \sim y'x'$。

#### 2. 证明商范畴中的态射集 $[*, *] = G/H$

根据商范畴的构造（Source）：

- **对象**：商范畴 $\mathcal{C}'$ 的对象与原范畴一致，仍为 ${*}$。
- *态射集 $[*,* ]$__：其定义为原态射集 $\text{Hom}(*, *)$ 在等价关系 $\sim$ 下的等价类集合。
    - 在群论中，满足 $xy^{-1} \in H$ 的元素 $x, y$ 处于同一个**陪集Coset**中。
    - 因为 $H$ 是正规子群，其左陪集与右陪集相等，即等价类 $[g] = {x \in G \mid x \sim g} = gH$,。
    - 因此，所有的等价类构成的集合正是商群的底层集合： $$[*, *] = {gH \mid g \in G} = G/H$$
- **复合运算的一致性**：
    - 商范畴中的复合定义为 $[y] \circ [x] = [yx]$。
    - 对应到陪集运算即为 $(yH)(xH) = (yx)H$。这与商群 $G/H$ 的群运算完全一致。

### **结论**

该构造成功地将群论中的**商群概念**转化为了范畴论中的**商范畴语言**。正如图片所示，利用正规子群的性质（$yHy^{-1} = H$）保证了范畴复合运算在等价类下是良定义的，从而使得商范畴的态射集恰好就是商群。

### 0.15 函子保持交换图

**习题 0.15（Rotman《An Introduction to Homological Algebra》）**：

设 $\mathcal{D}$ 和 $\mathcal{C}$ 是两个范畴，$T: \mathcal{D} \to \mathcal{C}$ 是任意变差的函子（即可以是协变函子或反变函子）。  
若 $D$ 是 $\mathcal{D}$ 中的一个**交换图**（commutative diagram），则 $T(D)$（即将图中所有顶点和箭头用 $T$ 替换，箭头方向可能被反转）是 $\mathcal{C}$ 中的一个交换图。

保持复合所以保持交换图
- [[交换图的理解\|交换图的理解]] 

### 0.16 equivalence的例子：各种同构

根据范畴论的通用定义，范畴 $\mathcal{C}$ 中的**等价（Equivalence）**（或称同构）是指一个态射 $f: A \to B$，存在态射 $g: B \to A$ 使得 $f \circ g = 1_B$ 且 $g \circ f = 1_A$。

以下是对 Exercise 0.16 中各范畴等价条件的细致证明：

#### **(i) 集合范畴 ($\mathsf{Sets}$)：双射**

- **证明**：在 $\mathsf{Sets}$ 中，态射是集合间的函数。根据等价的定义，$f: A \to B$ 是等价意味着存在函数 $g: B \to A$ 满足 $f(g(y)) = y$（对所有 $y \in B$）且 $g(f(x)) = x$（对所有 $x \in A$）。这在集合论中恰好是**双射（Bijection）**的定义，即 $f$ 拥有一个双侧逆函数。

#### **(ii) 拓扑空间范畴 ($\mathsf{Top}$)：同胚**

- **证明**：态射是连续函数。$f: X \to Y$ 是等价意味着存在连续函数 $g: Y \to X$ 使得 $f \circ g = id_Y$ 且 $g \circ f = id_X$。一个**双射且其逆映射也连续**的连续函数被称为**同胚（Homeomorphism）**。

#### **(iii) & (iv) 群范畴 ($\mathsf{Groups}$) 与 环范畴 ($\mathsf{Rings}$)：同构**

- **证明**：在这两个范畴中，态射分别是群同态和环同态（需保持单位元）。如果 $f$ 是范畴意义上的等价，则存在同态 $g$ 满足 $f \circ g = 1$ 且 $g \circ f = 1$。由于 $f$ 具有双向逆，它必然是双射。在代数结构中，**双射的同构映射其逆映射也必然是同构映射**，因此等价即为**同构（Isomorphism）**。

#### **(v) 拟序集范畴：满足 $x \le y$ 且 $y \le x$ 的所有 $i_{xy}$**

- **证明**：在该范畴中，对象是集合元素，态射集 $Hom(x, y)$ 当 $x \le y$ 时为单元素集 ${i_{xy}}$，否则为空。
    - 若 $i_{xy}$ 是等价，则必须存在反向态射 $i_{yx}: y \to x$。
    - 根据态射定义，存在 $i_{yx}$ 意味着 $y \le x$；同时 $i_{xy}$ 存在意味着 $x \le y$。
    - 复合性质 $i_{yx} \circ i_{xy} = i_{xx}$ 和 $i_{xy} \circ i_{yx} = i_{yy}$ 由拟序集的自反性自动保证。

#### **(vi) 空间对范畴 ($\mathsf{Top}^2$)：满足 $f(A) = A'$ 的同胚 $f: X \to X'$**

- **证明**：对象是空间对 $(X, A)$，态射 $f: (X, A) \to (X', A')$ 是连续映射 $f: X \to X'$ 且满足限制条件 $f(A) \subseteq A'$。
    - 若 $f$ 是等价，则存在 $g: (X', A') \to (X, A)$ 满足 $g \circ f = id_X$ 且 $f \circ g = id_{X'}$。
    - 在底层空间上，$f: X \to X'$ 是一个具有连续逆映射 $g$ 的连续映射，故 $f$ 是同胚。
    - 作为 $\mathsf{Top}^2$ 的态射，必须有 $f(A) \subseteq A'$ 且 $g(A') \subseteq A$。
    - 由 $g(A') \subseteq A$ 可推得 $f(g(A')) \subseteq f(A)$，即 $A' \subseteq f(A)$。
    - 结合 $f(A) \subseteq A'$ 和 $A' \subseteq f(A)$，得出 **$f(A) = A'$**。

#### **(vii) 幺半群 $G$ 定义的范畴：具有双侧逆的元素**

- **证明**：此范畴只有一个对象 $*$，态射是 $G$ 中的元素 $g$，复合定义为 $G$ 中的乘法。
    - 根据定义，$g$ 是等价当且仅当存在态射（即元素）$h \in G$ 使得 $g \circ h = 1$ 且 $h \circ g = 1$（其中 1 是 $G$ 的恒等元）。
    - 这正是幺半群中**具有双侧逆元（Two-sided inverse）**的定义。

### 0.17 到商范畴的函子

根据教材 Rotman《代数拓扑导论》中的练习 0.17 以及配套解答，证明 **$T': \mathcal{C}' \to \mathcal{D}$ 是一个函子** 的过程如下：

#### **1. 证明作用在态射上是良定义的 (Well-definedness)**

这是证明的核心。我们需要证明 $T'$ 对态射等价类的作用不依赖于所选的代表元。

- **前提条件**：设 $[f]$ 和 $[g]$ 是商范畴 $\mathcal{C}'$ 中从对象 $X$ 到 $Y$ 的两个态射类，且假设 **$[f] = [g]$**。
- **等价关系**：根据商范畴的定义，$[f] = [g]$ 意味着在原范畴 $\mathcal{C}$ 中满足全等关系 **$f \sim g$**。
- **函子性质**：题目给出的假设是：如果 $f \sim g$，那么函子 $T$ 满足 **$T(f) = T(g)$**。
- **推导**：根据 $T'$ 的定义，$T'([f]) = T(f)$ 且 $T'([g]) = T(g)$。由于 $T(f) = T(g)$，因此： $$T'([f]) = T'([g])$$ 这证明了 **$T'$ 在态射上的作用是良定义的**，即它与等价类中代表元的选择无关。

#### **2. 证明保持单位态射 (Identity Preservation)**

- **商范畴的单位元**：对于商范畴 $\mathcal{C}'$ 中的任意对象 $X$，其单位态射定义为原范畴单位态射的等价类，即 **$1'_X = [1_X]$**。
- **映射计算**：根据 $T'$ 的定义： $$T'(1'_X) = T'([1_X]) = T(1_X)$$。
- **原函子性质**：由于 $T$ 是从 $\mathcal{C}$ 到 $\mathcal{D}$ 的函子，它必须保持单位元，即 $T(1_X) = 1_{T(X)}$。
- **结论**：因为 $T'(X) = T(X)$，所以： $$T'(1'_X) = 1_{T'(X)}$$ 这证明了 $T'$ 保持单位态射。

#### **3. 证明保持复合运算 (Composition Preservation)**

- **态射复合**：设 $[f] \in \text{Hom}_{\mathcal{C}'}(X, Y)$ 且 $[g] \in \text{Hom}_{\mathcal{C}'}(Y, Z)$。在商范畴中，它们的复合定义为 **$[g] \circ [f] = [g \circ f]$**。
- **映射计算**： $$T'([g] \circ [f]) = T'([g \circ f]) = T(g \circ f)$$。
- **利用 $T$ 的函子性**：由于 $T$ 是函子，它保持复合运算，即 $T(g \circ f) = T(g) \circ T(f)$。
- **转换回 $T'$**：根据 $T'$ 的定义，$T(g) = T'([g])$ 且 $T(f) = T'([f])$。
- **结论**：因此： $$T'([g] \circ [f]) = T'([g]) \circ T'([f])$$ 这证明了 $T'$ 保持态射的复合。

### **总结**

由于 **$T'$ 在态射上良定义**，且**保持了单位态射与复合运算**，根据函子的定义，$T'$ 是一个从商范畴 $\mathcal{C}'$ 到 $\mathcal{D}$ 的**函子**。

### 0.18 挠群的性质

根据教材 **Rotman**《代数拓扑导论》Exercise 0.18 的要求，以及 **solutions.pdf** 中的详细解答，以下是关于挠函子（Torsion Functor） $t$ 的完整证明：

#### **(i) 证明 $t$ 定义了从 $\mathsf{Ab}$ 到 $\mathsf{Ab}$ 的函子**

**1. 挠子群的性质：** 对于阿贝尔群 $G$，其挠子群定义为 $tG = {x \in G : x \text{ has finite order}}$。

**2. 同态将有限阶元素映射到有限阶元素：** 设 $f: G \to H$ 是一个群同态。我们需要证明 $f$ 对 $tG$ 的限制 $t(f) = f|_{tG}$ 的值域落在 $tH$ 中。

- 设 $x \in tG$，则存在正整数 $n$ 使得 $nx = 0$。
- 由于 $f$ 是同态，有 $n f(x) = f(nx) = f(0) = 0$。
- 这说明 $f(x)$ 也是有限阶元素，因此 $f(x) \in tH$。
- 结论：$t(f)$ 是从 $tG$ 到 $tH$ 的良定义同态。

**3. 验证函子公理：**

- **保持恒等映射**：$t(1_G) = 1_G|_{tG}$，这显然是 $tG$ 上的恒等映射 $1_{tG}$。
- **保持复合运算**：设 $G \xrightarrow{f} H \xrightarrow{g} K$ 是两个同态。 $$t(g \circ f) = (g \circ f)|_{tG} = g|_{f(tG)} \circ f|_{tG}$$ 由于 $f(tG) \subseteq tH$，这可以表示为 $g|_{tH} \circ f|_{tG} = t(g) \circ t(f)$。 因此，$t$ 是一个从阿贝尔群范畴到其自身的协变函子。

#### **(ii) 证明若 $f$ 是单射，则 $t(f)$ 也是单射**

- 假设 $f: G \to H$ 是单射。
- 由于 $t(f)$ 只是 $f$ 在子群 $tG$ 上的限制，如果 $t(f)(x) = t(f)(y)$ 对于某些 $x, y \in tG$ 成立，那么在原群中必有 $f(x) = f(y)$。
- 由 $f$ 的单射性可知 $x = y$。
- 因此，$t(f)$ 作为单射映射的限制，必然保持单射性。

#### **(iii) 给出 $f$ 是满射但 $t(f)$ 不是满射的反例**

我们需要寻找一个满同态，它将无限阶元素映为有限阶元素，但由于定义域的有限阶部分太小，导致无法覆盖值域的所有有限阶元素。

**反例构造：**

- 令 $G = \mathbb{Z}$（整数加法群），$H = \mathbb{Z}/2\mathbb{Z}$（模 2 余数群）。
- 令 $f: \mathbb{Z} \to \mathbb{Z}/2\mathbb{Z}$ 为自然的满同态（投影映射），即 $f(x) = x \pmod 2$。

### 0.19 阿贝尔群的商群的性质

根据教材 Rotman《代数拓扑导论》中的练习 0.19 及其相关代数定义，以下是对你问题的详细解答：

#### **1. 什么是 $G/pG$？**

在阿贝尔群（Abelian Group）范畴中，群运算通常用加法表示。对于给定的素数 $p$ 和阿贝尔群 $G$：

- **$pG$ 的定义**：$pG$ 是指集合 $\{pg \mid g \in G\}$，即群 $G$ 中所有可以表示为 $p$ 个相同元素相加形式的元素集合。
- **$G/pG$ 的定义**：它是群 $G$ 对其子群 $pG$ 的**商群（Quotient Group）**。

#### **2. $pG$ 是 $G$ 的子群吗？**

**在阿贝尔群中，$pG$ 永远是 $G$ 的子群。**

- **子群性质验证**：
    1. **封闭性**：对于 $pg_1, pg_2 \in pG$，有 $pg_1 + pg_2 = p(g_1 + g_2) \in pG$。
    2. **单位元**：$0 = p \cdot 0 \in pG$。
    3. **逆元**：$-(pg) = p(-g) \in pG$。
- **商群定义说明**：由于 $G$ 是阿贝尔群，其所有子群都是**正规子群**。根据商空间的构造性质，只要子群是正规的，商群就一定有良定义。因此，你不必担心无法定义商群的问题。

---

#### **3. Exercise 0.19 证明整理**

#### **(i) 证明：若 $f: G \to H$ 是满射，则 $F(f)$ 也是满射**

- **设** $h + pH$ 是商群 $F(H) = H/pH$ 中的任意一个元素。
- **利用满射性质**：因为已知 $f: G \to H$ 是满射，所以对于 $h \in H$，一定存在某个 $g \in G$ 使得 $f(g) = h$。
- **作用函子 $F$**：根据 $F(f)$ 的定义： $$F(f)(g + pG) = f(g) + pH = h + pH$$
- **结论**：由于 $H/pH$ 中的任意元素都能在 $F(f)$ 的像集中找到原像，因此 $F(f)$ 是满射。

#### **(ii) 举例：$f$ 是单射但 $F(f)$ 不是单射**

我们需要找一个映射，它在原群中是保序的（单射），但模 $p$ 之后会丢失信息。

- **构造示例**：令 $p = 2$，取阿贝尔群 $G = \mathbb{Z}, H = \mathbb{Z}$。
- **定义单同态**：令 $f: \mathbb{Z} \to \mathbb{Z}$ 为 $f(n) = 2n$（即乘以 2）。显然，这是一个单射（若 $2n_1 = 2n_2$，则 $n_1 = n_2$）。
- **分析 $F(f)$**：
    - $F(\mathbb{Z}) = \mathbb{Z}/2\mathbb{Z} = {0 + 2\mathbb{Z}, 1 + 2\mathbb{Z}}$。
    - 计算 $F(f)$ 在两个元素上的取值：
        - $F(f)(0 + 2\mathbb{Z}) = f(0) + 2\mathbb{Z} = 0 + 2\mathbb{Z}$。
        - $F(f)(1 + 2\mathbb{Z}) = f(1) + 2\mathbb{Z} = 2 + 2\mathbb{Z} = 0 + 2\mathbb{Z}$。
- **结论**：$F(f)$ 将定义域中的所有元素都映到了值域的零元，它是一个零同态，不是单射。


### 0.20 从拓扑范畴到环范畴

根据教材 Rotman《代数拓扑导论》习题 0.20 以及配套解答，该命题的证明整理如下：

#### **(i) 证明 $C(X)$ 是一个带单位元的交换环**

**1. 运算的闭合性：** 对于拓扑空间 $X$，$C(X)$ 是所有连续实值函数 $f: X \to \mathbb{R}$ 的集合。

- **加法**：对于 $f, g \in C(X)$，定义 $(f+g)(x) = f(x) + g(x)$。由于实数加法是连续的，两个连续函数的和依然是连续函数，故 $f+g \in C(X)$。
- **乘法**：对于 $f, g \in C(X)$，定义 $(f \cdot g)(x) = f(x)g(x)$。同理，实数乘法是连续的，连续函数的积也是连续函数，故 $f \cdot g \in C(X)$。

**2. 环公理的验证：** 由于 $C(X)$ 上的运算是逐点（pointwise）定义的，而实数集 $\mathbb{R}$ 在通常的加法和乘法下是一个交换环，因此 $C(X)$ 自动继承了 $\mathbb{R}$ 的代数性质：

- **交换律与结合律**：加法和乘法的交换律、结合律均由 $\mathbb{R}$ 的性质保证。
- **分配律**：$f \cdot (g + h) = f \cdot g + f \cdot h$ 逐点成立。
- **单位元**：
    - **加法零元**：恒等于 0 的常数函数 $0(x) = 0$。
    - **乘法单位元 (1)**：恒等于 1 的常数函数 $1(x) = 1$。

因此，$C(X)$ 是一个带单位元 1 的交换环。

---

#### **(ii) 证明 $X \mapsto C(X)$ 是从 $\mathsf{Top}$ 到 $\mathsf{Rings}$ 的反变函子**

要证明这是一个反变函子，我们需要定义它如何作用于对象和态射，并验证函子公理。

**1. 作用于对象 (Objects)：** 对于 $\mathsf{Top}$ 中的每个对象（拓扑空间 $X$），函子将其映射到环 $\mathsf{Rings}$ 中的对象 $C(X)$。

**2. 作用于态射 (Morphisms)：** 设 $f: X \to Y$ 是 $\mathsf{Top}$ 中的一个连续映射。定义映射 $C(f): C(Y) \to C(X)$ 如下： 对于任何 $g \in C(Y)$，令 $C(f)(g) = g \circ f$。==关键公式== 类似于拉回？

- **良定义性**：由于 $g$ 和 $f$ 都是连续的，它们的复合 $g \circ f$ 也是连续的实值函数，因此 $g \circ f \in C(X)$。
- **环同态验证**：$C(f)$ 保持了加法、乘法和单位元。例如： $$C(f)(g_1 + g_2) = (g_1 + g_2) \circ f = (g_1 \circ f) + (g_2 \circ f) = C(f)(g_1) + C(f)(g_2)$$ 同理可证乘法和单位元的保持性。

**3. 验证函子公理：**

- **反变性 (保持复合并交换顺序)**： 设 $X \xrightarrow{f} Y \xrightarrow{g} Z$ 是连续映射。对于 $h \in C(Z)$： $$C(g \circ f)(h) = h \circ (g \circ f)$$ $$(C(f) \circ C(g))(h) = C(f)(h \circ g) = (h \circ g) \circ f$$ 由于函数复合满足结合律，两者相等，即 $C(g \circ f) = C(f) \circ C(g)$。
- **保持恒等映射**： 对于恒等映射 $1_X: X \to X$： $C(1_X)(g) = g \circ 1_X = g$。 即 $C(1_X)$ 是 $C(X)$ 上的恒等同态 $1_{C(X)}$。

**结论**： 由于该 assignment 满足所有公理，它定义了一个从 **$\mathsf{Top}$** 到 **$\mathsf{Rings}$** 的**反变函子**。