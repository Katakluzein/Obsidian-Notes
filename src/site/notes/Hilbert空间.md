---
{"dg-publish":true,"permalink":"/Hilbert空间/","tags":["#量子力学数学基础"]}
---


> [!definition] 内积空间
> - 设 $\mathsf{X}$ 是复线性空间,映射$\langle\cdot , \cdot \rangle: \mathsf{X} \times \mathsf{X} \rightarrow \mathbb{C}$ 称为**内积**,   $(\mathsf{X}, S)$称为**内积空间** ,如果
>
> - (正性)~ $\langle u, u\rangle  \geq 0$ 任取 $u  \in \mathsf{X}$
> - (第二分量线性)~$\langle u, \alpha v+\beta w\rangle =\alpha \langle u, v\rangle +\beta \langle u, w\rangle$ 任取 $\alpha, \beta \in \mathbb{C}$ 和 $u ,v ,w  \in \mathsf{X}$;
> - (第一分量共轭线性)~$\langle u,v\rangle =\overline{\langle v, u\rangle }$任取 $u , v \in \mathsf{X}$;
> - (正定性)~$\langle u , u \rangle =0 \Rightarrow u =\mathbf{0}$, 任取 $u  \in \mathsf{X}$.

> [!note]
> - 这里的braket是内积的符号，用法与量子力学中不同，因此中间用逗号而非竖线分割以示区分。内积应视为定义在$\mathsf{X}\times \mathsf{X}$上，而不是$\mathsf{X^\prime }\times \mathsf{X}$上。
>
>   在微分几何中，流形的切空间是实线性空间，切空间上的内积被称为度规张量。

线性空间只要维度相同就同构，而希尔伯特空间与其对偶空间之间可以定义一个反线性的双射，因此$\mathsf{H}$与$\mathsf{H}^*$之间是反同构的{（[[Moretti2017\|Moretti2017]] p.117）}，是否可以定义真正的同构(幺正变换)？

> [!definition] 等距映射(Isometry)和{偏等距映射}(Partial Isometry){\cite[Def.3.72
> - {Moretti2017}}]
>   设 $\left(\mathsf{X}, S_{\mathsf{X}}\right),\left(\mathsf{Y}, S_{\mathsf{Y}}\right)$ 是内积空间. 线性映射 $L: \mathsf{X} \rightarrow$ $\mathsf{Y}$ 称为**等距映射**(isometry)如果
>
$$
S_{\mathsf{Y}}(L(x), L(y))=S_{\mathsf{X}}(x, y) \text { for any } x, y \in \mathsf{X} .
$$
>   如果等距映射 $L: \mathsf{X} \rightarrow \mathsf{Y}$ 是满射，称其为内积空间的**同构**。
>
>   设$U$是$\mathsf{H}$上的有界算符，如果$\|U x\|=\|x\|, \quad$ 任取 $x \in[\operatorname{ker}(U)]^{\perp}$，那么称$U$为$\mathsf{H}$上的**偏等距映射**(partial isometry)

> [!note]
> - 根据内积的定性，$x=y\implies L(x)=L(y)$，因此等距映射是单射，等距映射满射时可逆。
>
>
>
>  - 等距映射可以在更一般的度量空间中定义。在Riemann流形上，有两种定义isometry的方式。第一种，将Riemann流形视为一般的度量空间，然后根据度量空间上的等距映射来定义Riemann流形上的等距映射；第二种，设$f$是两个Riemann流形$(R,g),~(R^\prime,g^\prime)$之间的微分同胚，如果$g=f^{*} g^{\prime}$，那么称$f$为**isometry**。
>
>  - $C^*$-代数中的元素被称为偏等距若$u^{*} u$是投影算符。被称为等距若$uu^*=\mathbb{I}$。
>  - $T \in L\left(\mathsf{H}, \mathsf{H}_{1}\right)$ 是等距算符，当且仅当$T$是有界的且$T^{*} T=I_{\mathsf{H}}$
>
> -  偏等距算符的例子：比特翻转码中一个看上去像是逻辑$X$的算符$U=|000\rangle\langle 111|+|111\rangle\langle 000|.$

> [!definition] Hilbert空间与幺正变换
> - 如果内积空间$\mathsf{H}$上的内积诱导的模使其成为Banach空间，那么称$\mathsf{H}$为**Hilbert空间**。两个Hilbert空间之间的同构称为**幺正变换**(unitary)。

> [!note]
> - 在希尔伯特空间中，完备性是指柯西列一定收敛，闭是指空间包含了所有的点列极限点。对于子空间来说，我们也可以讨论它是否完备，因为把范数限制到子空间上就得到了一个赋范空间，同样可以讨论子空间是否是闭的，实际上，完备子空间一定是闭的，因为收敛序列一定是柯西列，但闭不一定完备，例如考虑有理数$\mathbb{Q}$上的单位区间$[0,1]$，它在$\mathbb{Q}$中是闭集，但却不完备。

 
> [!theorem] Riesz{} （[[Moretti2017\|Moretti2017]] Th.3.16）
> - 设 $(\mathsf{H} ,\langle \mid\rangle )$ 是Hilbert空间。对任意的连续线性泛函 $f: \mathsf{H} \rightarrow \mathbb{C}$ 存在唯一的元素 $y_{f} \in \mathsf{H}$ 满足
>
$$
f(x)=\left\langle y_{f}, x\right\rangle  \quad \forall x \in \mathsf{H} .
$$
>   映射 $\mathsf{H}^{\prime} \ni f \mapsto y_{f} \in \mathsf{H}$ 是双射。

> [!proposition] Hermite共轭{\cite[(3.35)
> - {Moretti2017}}]\label{def:hermiteconjugate}
>   设$\mathsf{H}_1$和$\mathsf{H}_2$是希尔伯特空间，$T\in B(\mathsf{H}_1,\mathsf{H}_2)$，那么唯一存在一个线性算符$T^\dagger :\mathsf{H}_2\rightarrow \mathsf{H}_1$
>
$$
\langle u ,T v\rangle_{2}=\left\langle T^{\text{}} u ,v\right\rangle _{1}
$$
>   任取$u\in \mathsf{H}_2$，$v\in \mathsf{H}_1$，$T^\dagger$是$T$的**厄米共轭**。

> [!proof]
> - 映射$\mathsf{H}_1 \ni v \mapsto(u \mid T v)_2 \in \mathbb{C}$是线性，有界的，因此根据Riesz定理，存在唯一元素$\mathsf{H}_1 \ni v \mapsto(u \mid T v)_2 \in \mathbb{C}$，使得$(u \mid T v)_2=\left(w_{T, u} \mid v\right)_1$，另外，映射$u \mapsto w_{T, u}$是线性映射，这就是要找的$T^\dagger$。

> [!note]
> - 比较对偶算符的定义\ref{def:adjoint}。
>
>   $B(\mathsf{H})$上的$\dagger$使其成为一个$C^*$-代数{（[[Moretti2017\|Moretti2017]] Th.3.49）}。

从定义中可以看出，Hermite共轭是与基底无关的，从另一角度看，厄米共轭是矩阵的共轭转置，而共轭转置和基变换是交换的，
$$
(UAU^\dagger)^\dagger=UA^\dagger U^\dagger
$$
```tikz
        \usepackage{amsmath}
        \usepackage{tikz-cd}
        \begin{document}
        \begin{tikzcd}[sep=2.25em]
	{M_n(\mathbb{C})} & {M_n(\mathbb{C})} \\
	{M_n(\mathbb{C})} & {M_n(\mathbb{C})}
	\arrow["{(\cdot)^\dagger}", from=1-1, to=1-2]
	\arrow["{U(\cdot)U^\dagger }"', from=1-1, to=2-1]
	\arrow["{(\cdot)^\dagger}"', from=2-1, to=2-2]
	\arrow["{U(\cdot)U^\dagger }", from=1-2, to=2-2]
\end{tikzcd}
        \end{document}
        ```

而单独的共轭与转置都不与基变换操作交换，只有确定了基底以后，这两个操作才是良定义的。如果要获得与基底无关的共轭以及转置的定义[[tyson2010TwosidedBoundsMinimumerror\|tyson2010TwosidedBoundsMinimumerror]]，需要有交换图

```tikz
        \usepackage{amsmath}
        \usepackage{tikz-cd}
        \begin{document}
        \begin{tikzcd}
	{B(\mathsf{H},\mathsf{K})} && {B(\mathsf{H}^*,\mathsf{K}^*)} & {\overline{A}} \\
	\\
	{B(\mathsf{H},\mathsf{K})} && {B(\mathsf{H}^*,\mathsf{K}^*)} & {\overline{V^\dagger A U} }
	\arrow["{\overline{(\cdot)}}", from=1-1, to=1-3]
	\arrow["{\overline{V^\dagger}(\cdot)\overline{U}}", from=1-3, to=3-3]
	\arrow["{\overline{(\cdot)}}"', from=3-1, to=3-3]
	\arrow["{V^\dagger(\cdot)U}"', from=1-1, to=3-1]
	\arrow[maps to, from=1-4, to=3-4]
	\end{tikzcd}
        \end{document}
        ```

$$
\begin{aligned} \left(e_{1}^{\prime}, \cdots, e_{n}^{\prime}\right)&=\left(e_{1}, \cdots, e_{n}\right) U \\ \left(e_{1}^{*^{\prime}}, \cdots, e_{n}^{*^{\prime}}\right)&=\left(e_{1}^{*}, \cdots, e_{n}^{*}\right) \bar{U} \\ A\left(e_{1}, \cdots, e_{n}\right)&=\left(f_{1}, \ldots, f_{m}\right) A \\ A\left(e_{1}^{\prime}, \cdots, e_{n}^{\prime}\right)&=\left(f_{1}^{\prime}, \ldots, f_{m}^{\prime}\right) V^{\dagger } A U\end{aligned}
$$
定义$\bar{A}: \mathsf{H}^{*} \longrightarrow \mathsf{K}^{*}$，$A^{\top}: \mathsf{K}^{*} \longrightarrow \mathsf{H}^{*}$,$|A\rangle\rangle_{\mathsf{KH}^{*}} \in \mathsf{K} \otimes \mathsf{H}^{*}$满足
$$
\bar{A}_{\mathsf{H}^{*} \rightarrow \mathsf{K}^{*}}=\sum \bar{A}_{i j}|\bar{i}\rangle_{\mathsf{K}^{*}}\left\langle\left.\bar{j}\right|_{\mathsf{H}^{*}}\right.
$$
$$
A_{\mathsf{K}^{*} \rightarrow \mathsf{H}^{*}}^{\mathrm{tr}}= .\sum A_{i j}|\bar{j}\rangle_{\mathsf{H}^{*}} \overline{\langle i}|_{\mathsf{K}^{*}}
$$
eq-eq-transpose
$$
|A\rangle\rangle_{\mathsf{K} \mathsf{H}^{*}}=\sum A_{i j}|i\rangle_{\mathsf{K}}|\bar{j}\rangle_{\mathsf{H}^{*}}
$$
eq-eq-bivector

> [!definition] 正性
> - 对于希尔伯特空间$\mathsf{H}$，线性映射$T \in L(\mathsf{H})$ 是正的，记作 $T \geq 0$, 如果 $(u \mid T u) \geq 0$ 任取 $u \in \mathsf{H}$

> [!note]
> 

Hilbert空间的**可分性**：存在可数稠密子集。Hilbert空间可分的充要条件：维度有限或者存在可数Hilbert基\footnote{位置本征态是过完备的？}。可分希尔伯特空间同构于$\ell^2(\mathbb{N})$或者$\mathbb{C}^n${（[[Moretti2017\|Moretti2017]] Th.3.30）}。

有限维Hilbert空间上的正规变换的定义如下
> [!definition] 正规变换
> - 设 $\mathscr{A}: V \longrightarrow V$ 是Hilbert空间 $V$ 上的线性变换, 如果 $\mathscr{A}$ 有伴随变换, 且 $\mathscr{A}{\mathscr{A}^{\text{}}}=$ $\mathscr{A}^{\text{}} \mathscr{A}$, 则称 $\mathscr{A}$ 是**正规变换**;
>
>   设矩阵 $A \in \mathbb{F}^{n \times n}$, 如果有 $A A^{\text{}}=A^{\text{}} A$, 则称矩阵 $A$ 是**正规方阵** .

> [!note]
> - 正规变换有很多好性质，例如：不同本征值的本征向量相互正交、正规变换的最小多项式是两两互不相同的首一不可约多项式，因此正规方阵幺正相似于对角阵{（[[李忠华线代\|李忠华线代]] Th.9.30）}。

> [!theorem] 极分解
> - 设 $\mathsf{H}$ 是Hilbert空间 $A \in B(\mathsf{H})$.
>
> - 唯一存在 $P, U \in B(\mathsf{H})$\ 满足
>   \begin{itemize}
> - $A$有极分解
>   $A=U P$
> - $P$ 是正算符,
> - $U$ 是 $\operatorname{Ran}(P)$上的等距算符,
> - $U$ 是$\operatorname{ker}(P)$上的零算符。
> - $P=|A|:=\sqrt{A^{\text{}} A}$,因此$\operatorname{ker}(U)=\operatorname{ker}(A)=\operatorname{Ker}(P)=[\operatorname{Ran}(P)]^{\perp}$.
> - 若 $A$ 是双射，则 $U = A|A|^{-1}$，极分解写为$A=(A|A|^{-1})|A|$
>   \end{itemize}

## C star 代数
- [[C star代数\|C star代数]] 