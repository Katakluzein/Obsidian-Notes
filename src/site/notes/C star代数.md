---
{"dg-publish":true,"permalink":"/C star代数/","tags":["量子力学数学基础"]}
---


> [!definition] ${}^*$-代数、$C^*$-代数{（[[Moretti2017\|Moretti2017]] Def.2.24）}}\label{def:staralgebrahom}
>   设$\mathfrak{A}$是数域$\mathbb{C}$上的(交换，Banach，含幺)代数，称映射${ }^{*}: \mathfrak{A} \rightarrow \mathfrak{A}$为**内卷**(involution)，若它满足
>
> - (antilinearity) $(\alpha x+\beta y)^{*}=\bar{\alpha} x^{*}+\bar{\beta} y^{*}$ for any $x, y \in \mathfrak{A}, \alpha, \beta \in \mathbb{C}$
> - (involutivity) $\left(x^{*}\right)^{*}=x$ for any $x \in \mathfrak{A}$
> - $(x y)^{*}=y^{*} x^{*}$ for any $x, y \in \mathfrak{A}$,
>   相应的结构$(\mathfrak{A},^*)$称为(交换，Banach，含幺)**$^*$-代数**。若对Banach  (含幺)$^*$-代数(模长记为$||\cdot||$)，进一步有
$$
\left\|x^{*} x\right\|=\|x\|^{2}
$$
称其为(含幺)**$C^*$-代数**。
>
>   设$x\in (\mathfrak{A},^*)$，称$x$
>
> - **正规** (normal) ，若 $x x^{*}=x^{*} x$,
> - **厄米**(Hemitian)或自伴随，若 $x^{*}=x$,
> - **等距**(isometric)，若 $x^{*} x=\mathbb{I}$,
> - **偏等距**(partial isometric)，若$x=xx^*x$
> - **幺正**(unitary)，若 $x^{*} x=x x^{*}=\mathbb{I}$.
> - **正**(positive)，若存在$a\in \mathfrak{A}$，使得$x=a^*a$。
>   保持$*$和单位元的两个$*$-代数之间的映射称为**$*$-同态**，如果还是双射则称为**$*$-同构**。

> [!note]
> - 共轭转置${}^\text{}$就是矩阵代数中的${}^*$。
>
>   为什么${}^*$被称为内卷呢？因为卷两次等于没有在卷，可以想象无论多卷，都几乎是在原地踏步，这暗示了内卷的本质。
>
>   在无穷维空间中存在等距但不幺正的算符，在有限维空间中不存在{（[[Moretti2017\|Moretti2017]] p.141）}。
