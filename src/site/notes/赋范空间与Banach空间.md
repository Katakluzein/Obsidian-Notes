---
{"dg-publish":true,"permalink":"/赋范空间与Banach空间/","tags":["#量子力学数学基础"]}
---

本节中的$\mathsf{X},\mathsf{Y}$均为赋范空间。
> [!definition] 赋范空间{\cite[Def.2.1
> - {Moretti2017}}]
>   设$\mathsf{X}$ 是数域 $\mathbb{K}=\mathbb{C}$ 或 $\mathbb{R}$上的线性映射，映射 $N: \mathsf{X} \rightarrow \mathbb{R}$ 被称为$\mathsf{X}$上的范数 ，$(\mathsf{X}, N)$称为**normed space**，如果
>   N0. $N(u) \geq 0$ 任取 $u \in \mathsf{X}$,
>
>   N1. $N(\lambda u)=|\lambda| N(u)$ 任取$\lambda \in \mathbb{K}$ ， $u \in \mathsf{X}$,
>
>   N2. $N(u+v) \leq N(u)+N(v)$，任取 $u, v \in \mathsf{X}$,
>
>   N3. $N(u)=0 \Rightarrow u=\mathbf{0}$，任取 $u \in \mathsf{X}$.

> [!definition] 常见的算符模(范数)
> - \label{def:operatornorm}
>   称$|A|:=\sqrt{A^{\text{}} A}$为有界算符$A \in B(\mathsf{H})$的**模**。
>   **Schatten $p$-norm**的定义为
>
$$
\|T\|_{p}=\left[\operatorname{tr}\left(|T|^{p}\right)\right]^{1 / p}=\left(\sum_{i=1}^n \sigma_i^p(T)\right)^{\frac{1}{p}}
$$
>   当$p=1$时，称为**trace norm**，是所有奇异值的和，
>
>   当$p=2$时，称为**Hilbert-Schmidt norm**{（[[Moretti2017\|Moretti2017]] Def.4.24）}或**Frobenius norm**{（[[tomamichel2015quantum\|tomamichel2015quantum]] (3.3)）}。
>
>   当$p=\infty$时，称为**operator norm**，省略下标不写都是指这种情况，是算符的最大奇异值。
>
>   设$A\in L(\mathsf{X},\mathsf{Y})$是非零赋范空间$\mathsf{X},\mathsf{Y}$之间的(线性)算子，其算符范数为(operator norm)
>
$$
\begin{array}{l}\|A\|_{\infty}=\inf \{c \geq 0 \quad:\|A v\| \leq c\|v\| \text { for all } v \in V\} \\ =\sup \{\|A v\| \quad:\|v\| \leq 1 \quad \text { and } \quad v \in V\} \\ =\sup \{\|A v\| \quad:\|v\|<1 \quad \text { and } \quad v \in V\} \\ =\sup \{\|A v\| \quad:\|v\| \in\{0,1\} \quad \text { and } \quad v \in V\} \\ =\sup \{\|A v\| \quad:\|v\|=1 \quad \text { and } \quad v \in V\} \\ \text { this equality holds if and only if } V \neq\{0\} \\ =\sup \left\{\frac{\|A v\|}{\|v\|}: v \neq 0 \quad \text { and } \quad v \in V\right\} \\ \text { this equality holds if and only if } V \neq\{0\} \\\end{array}
$$
> [!note]
> - 算符模的一些性质{（[[Moretti2017\|Moretti2017]] Th.2.44）}，由定义可得$\|TSu\|\leqslant \|T \|\|S u\|\leqslant \|T\|\|S\|\|u\|$，进而
>
$$
\|T S\| \leq\|T\|\|S\|, T, S \in B(\mathsf{X})
$$
>
>   $S=(1-T)^{-1}=\sum_{n=0}^{\infty} S_n=\sum_{n=0}^{\infty} T^k$，当$\|T\|<1$时，级数绝对收敛{（[[kato1995PerturbationTheoryLinear\|kato1995PerturbationTheoryLinear]] (4.22)）}。进而推论当$\|1-R\|=\|T\|<1$时，$R$可逆，满足$RS=\mathbb{I}$。
>
>   赋范空间的对偶空间也是赋范空间，两个空间上的模互为对偶。
>
>   算符模的不等式（还有更多的不等式吗）
>
$$
\|A\|_1 \leq \sqrt{\operatorname{rank}(A)}\|A\|_2 .
$$
>
>   容易证明Schatten p-范数关于复共轭、共轭转置和转置都是不变的，这是因为这些操作都不改变奇异值。
>
>   算符模让算符代数成为赋范代数。

> [!definition] 对偶算符
> - \label{def:adjoint}
>   有界算符$T\in B(\mathsf{X},\mathsf{Y})$，则其**对偶**(adjoint)定义$T^{\prime} \in B\left(\mathsf{Y}^{\prime}, \mathsf{X}^{\prime}\right)$为
>
$$
\left(T^{\prime} f\right)(u)=f(T(u))
$$
>   任取 $u \in \mathsf{X}, f \in \mathsf{Y}^{\prime}$.

> [!note]
> - 比较定义\ref{def:hermiteconjugate}。

> [!theorem] 连续等价于有界{} （[[krantz2013guide\|krantz2013guide]] Th.1.4）
> - $T\in L(\mathsf{X},\mathsf{Y})$，则$T$有界等价于$T$连续。

> [!proof]
> - 由于线性性，$T$连续等价于在原点连续。
>
>   设$T$在原点连续，则存在$\delta$，使得当$\|u\|<\delta$时，$\|Tu\|<1$，取固定的$\delta_1<\delta$，任取$v\in \mathsf{X} -\{0\}$，有$u=\delta_1 v/\|v\|$的模小于1，于是$\|Tv\| <\|v\|/\delta_1$，    $T$有界。
>
>   设$T$有界，则$\|Tu\|\leqslant \|T\|\|u\|$意味着连续。

> [!theorem] 算符的逆是连续函数
> - 设$T\in B(\mathsf{X})$是可逆的，则当$S \in B(\mathsf{X})$足够接近$T$时，$S$也是可逆的。因此，可逆算符集是$B(\mathsf{X})$中的 开集。

> [!proof]
> - $S=(1-F)^{-1}=\sum_{n=0}^{\infty} S_n=\sum_{n=0}^{\infty} F^k$，当$\|F\|<1$时，级数绝对收敛，有误差估计式
>
$$
\|S-S_n\|=\left\|\sum_{k=n+1}^{\infty}F^k\right\|\leqslant \sum_{k=n+1}^{\infty}=\frac{\|F\|^{n+1}}{1-\|F\|}
$$
>   当$n=0$时，
>
$$
\left\|(1-F)^{-1}-1\right\| \leqslant\frac{\|F\|}{1-\|F\|}
$$
>   设$A=S-T$，并假设$\|A\|<\frac{1}{\|T^{-1}\|}$，则$\|AT^{-1}\|<1$，因此$\mathbb{I}+AT^{-1}$可逆，
>
$$
\| T^{-1}-S^{-1} \|=\| T^{-1}((1+AT^{-1})^{-1})\|\leqslant \frac{\|A\|\left\|T^{-1}\right\|^2}{1-\|A\|\left\|T^{-1}\right\|}
$$
> [!note]
> - 行列式是连续的而且可逆矩阵的集合是行列式函数在开集$\mathbb{R}-\{0\}$上的原像，连续函数保持开集\footnote{参见：[tricki](https://www.tricki.org/article/Dont_start_from_scratch)}。

> [!theorem] （反向）Hölder不等式{} （[[tomamichel2015quantum\|tomamichel2015quantum]] Lm.3.1）
> - Let $L, R\in \mathcal{L}(\mathsf{H})$, and let $p, q \in \mathbb{R} \cup\{\infty\}$ with the property that $\frac{1}{p}+\frac{1}{q}=1$. If $p, q \geq 1$ then
>
$$
|\operatorname{tr}(L R^\dagger )| \leqslant \|LR^\dagger \|_1 = \operatorname{tr}|L R^\dagger| \leqslant \|L\|_{p} \cdot\|R\|_{q} .
$$
>   The second inequality becomes an equality iff $|L|^p/\|L\|_p^p=|R|^q/\|R\|_q^q$. if $p=1$, the equality holds iff $P_L|R|=|R|P_L=\|R\|P_L$, where $P_L$ is the projcetion onto the range of $L$.
>
>   In reverse, if $0<p<1$ and $q<0$, and if $L, R \geq 0$ with $\operatorname{supp}(L) \subseteq \operatorname{supp}(R)$, then
>
$$
\|LR \|_1 =\operatorname{tr}(L R) \geq\|L\|_{p} \cdot\|R\|_{q} .
$$
> [!proof]
> 

> [!note]
> - Hölder不等式更多讨论\footnote{参见[讲义](https://homepages.cwi.nl/~fehr/QIT2021/Chap7.pdf)，[SE帖](https://math.stackexchange.com/questions/1648542/proving-holders-inequality-for-schatten-norms)，或者本地文档：normChap7.pdf}。
>
>   对任意算符有，$| \mathrm{tr}(A)|\leqslant \|A \|_1$，或等价地，算符的本征值的和的绝对值小于等于奇异值的和，参见[SE帖](https://math.stackexchange.com/questions/381808/sum-of-eigenvalues-and-singular-values)。由于奇异值等于本征值的绝对值等价于矩阵正规，所以等式成立的一个充分条件是$A$正矩阵。
>
>   定理中等号成立的条件需要$L$和$R$的定义域和陪域是相同的。
>
>   一般情况下$\|LR^\dagger\|\neq \|R^\dagger L\|$，因此使用不同的排列方式会得到不同的放缩公式。
>
>   两个不等号的成立条件在一般情况下是不一样的\footnote{详见：算符模和范数Holder不等式成立的条件.nb}。但也有可能同时取得等号{（[[wilde2013quantum\|wilde2013quantum]] (12.6)）}。
>
>   向量和线性泛函版本的Hölder不等式{（[[steele2004CauchySchwarzMasterClass\|steele2004CauchySchwarzMasterClass]] p.135）}{（[[Moretti2017\|Moretti2017]] Ex.2.13）}
>
$$
\sum_{k=1}^{n} a_{k} b_{k} \leq\left(\sum_{k=1}^{n} a_{k}^{p}\right)^{1 / p}\left(\sum_{k=1}^{n} b_{k}^{q}\right)^{1 / q}
$$
>
$$
\int_{X}|f(x) g(x)| d \mu(x) \leq\left(\int_{X}|f(x)|^{p} d \mu(x)\right)^{1 / p}\left(\int_{X}|g(x)|^{q} d \mu(x)\right)^{1 / q}
$$
>   where $p, q>0$ satisfy $1=\frac{1}{p}+\frac{1}{q}, f$ and $g$ are measurable and $\mu$ is a positive measure on $X$.
>
>   Hölder不等式的推论
>
$$
\|L\|_{p}=\max _{\substack{\|K\|_{q} \leq 1}}\left|\operatorname{tr}\left(L^{\dagger} K\right)\right| \quad,\text{任取}\quad \frac{1}{p}+\frac{1}{q}=1, p, q>1,
$$
>   $\|K\|_{q} \leq 1$可以改为$\|K\|_{q} = 1$
>
>   一个变体不等式{（[[tyson2010TwosidedBoundsMinimumerror\|tyson2010TwosidedBoundsMinimumerror]] (43)）}，$A,U:\mathsf{H}\rightarrow \mathsf{K}$，
>
$$
\sup _{\|U\| \leq 1} \operatorname{Re}\left(\operatorname{Tr} A^{\dagger} U\right)=\|A\|_{1}
$$
>   等号成立当且仅当
>
$$
\left.U\right|_{\operatorname{im}\left(A^{\dagger} A\right)}=A\left(A^{\dagger} A\right)^{-1 / 2}
$$
>   按照惯例只在支集上取逆。
>
>
>
>   \begin{figure}[htbp]
>   \centering
>   \includegraphics[width=0.7\textwidth]{image//2024-04-18-19-50-33.png}
>   \caption{ 待整理：等号成立的充分性检验，注意到$|U|=\mathrm{id}$,pjt.p.43 }
>   \label{  }
>   \end{figure}
>   \begin{figure}[htbp]
>   \centering
>   \includegraphics[width=0.5\textwidth]{image//2024-04-18-18-48-35.png}
>   \caption{ 待整理：可以只定义在$\mathrm{im}|A|$上的原因,pjt.p.43 }
>   \label{  }
>   \end{figure}
>   \begin{figure}[htbp]
>   \centering
>   \includegraphics[width=0.3\textwidth]{image//2024-04-18-19-51-44.png}
>   \caption{ 待整理：结论是否成立？ ,pjt.p.43}
>   \label{  }
>   \end{figure}
>   

> [!theorem] Arzelà–Ascoli{} （[[Moretti2017\|Moretti2017]] Th.2.22）
> - 设$\mathsf{K}$是紧的可分空间。假设一族定义在$\mathsf{K}$上的连续函数$\left\{f_n\right\}_{n \in \mathbb{N}} \subset C(\mathrm{~K})$满足等度连续性(equicontinuous)以及有界，即存在实数$C$，使得对任意的$n$，$\left\|f_n\right\|_{\infty}<C$，那么存在一个子列收敛到连续函数$f\in C(\mathsf{K})$，连续是指$f$关于范数$\|f\|_{\infty}:=\sup _{x \in \mathrm{K}}\|f(x)\|$连续。

> [!note]
> - 等度连续要求每个函数都是一致连续的且每个$\delta_n$与$n$无关，所以等度连续可能更强。
>
>   这个命题很像有界数列必有收敛子列，实际上证明中也用到了这个命题。
>
>   Banach–Steinhaus定理{（[[Moretti2017\|Moretti2017]] Cor.2.63）}的推论：一族Banach空间之间的一族有界算符$\left\{T_\alpha\right\}_{\alpha \in A} \subset B(\mathsf{X}, \mathsf{Y})$是一致连续的。

> [!definition] 赋范空间上的弱拓扑
> - 设$X$是赋范空间，则称由$X$上的一族半范数
>
$$
p_{f}(x):=|f(x)|, \quad x \in X,f \in X^\prime
$$
>   诱导的拓扑为$X$的**弱拓扑**。

> [!note]
> - \graytx{（待补充：半范数如何诱导拓扑？）}
>
>   从一族半范数诱导拓扑的定义参见{（[[Moretti2017\|Moretti2017]] Def.2.68）}，一族半范数在线性空间$\mathsf{X}$上诱导$P=\{p_i\}_{i\in I}$的拓扑的拓扑基的元素是用各个半范数的开球的有限交得到的，拓扑基中的元素为
>
$$
x+\left(B_{p_{i_1}, \delta_1} \cap \cdots \cap B_{p_{i_n}, \delta_n}\right)
$$
>   其中$x\in \mathsf{X}$，$i_k\in I$，$n\in \mathbb{N}$，$\delta_i>0$。   实际上这些半范数的所有开球构成一个子拓扑基{（[[xusenlinpointset\|xusenlinpointset]] Def.2.1.1）}。在线性空间上用一族半范数诱导的拓扑空间构成的线性拓扑空间成为**局部凸空间**(locally convex space)。

> [!definition] 算子空间上的强、弱拓扑{\cite[Def.2.72
> - {Moretti2017}}]
>   设空间$\mathsf{X}$和$\mathsf{Y}$是$\mathbb{C}$或者$\mathbb{R}$上的赋范空间。在空间$L(\mathsf{X}, \mathsf{Y})$
>   (以及$B(\mathsf{X}, \mathsf{Y})$)上定义以下几种算符拓扑：
>   \begin{enumerate}
> - 由一族半范数(seminorm)
>
$$
p_{x, f}(T):=|f(T(x))|, \quad T \in L(\mathsf{\mathsf{X}}, \mathsf{\mathsf{Y}})(B(\mathsf{\mathsf{X}}, \mathsf{\mathsf{Y}}))
$$
\index{$B(\mathsf{\mathsf{X}}, \mathsf{\mathsf{Y}})$，有界算符}
>   诱导的拓扑称为$L(\mathsf{X}, \mathsf{Y})$($B(\mathsf{X}, \mathsf{Y})$)上的**弱拓扑**。，其中$x\in \mathsf{X}$和$f\in \mathsf{Y}^\prime$
> - 由一族半范数
$$
p_{x}(T):=\|T(x)\|_{\mathsf{\mathsf{Y}}}, \quad T \in L(\mathsf{\mathsf{X}}, \mathsf{\mathsf{Y}})(B(\mathsf{\mathsf{X}}, \mathsf{\mathsf{Y}}))
$$
>   诱导的拓扑称为$L(\mathsf{X}, \mathsf{Y})$
>   ($B(\mathsf{X}, \mathsf{Y})$)上的**强拓扑**，其中$x\in \mathsf{X}$。
> - 在$B(\mathsf{X}, \mathsf{Y})$上用算符模
>
$$
\|T\|:=\sup _{\|u\| \neq 0} \frac{\|T u\|}{\|u\|}
$$
>   诱导的拓扑称为$B(\mathsf{X}, \mathsf{Y})$上的**一致拓扑**(uniform)。
> - 设$\mathsf{Y}$为$\mathbb{C}$或者$\mathbb{R}$，则$B(\mathsf{X}, \mathsf{Y})=\mathsf{X}^\prime$。$\mathsf{X}^\prime=B(\mathsf{X},\mathsf{Y})$上的一致拓扑(算符模诱导的拓扑)被称为$\mathsf{X}^\prime$上的**对偶强拓扑**。
>   前两种定义方式合二为一， 称为$\mathsf{X}^\prime$上的 **${}^*$-弱拓扑，诱导该拓扑的一族半范数为
>
$$
p_{x}^{*}(f):=|f(x)| ,\quad f \in \mathsf{X}^{\prime}
$$
>
>   \end{enumerate}

> [!note]
> - 实际上，${}^*$-弱拓扑中的星号也是对偶的意思，比较两个定义中的弱拓扑和${}^*$-弱拓扑可知，两者使用的半范数相同，但是他们分别诱导了$X$及其对偶空间上的拓扑。(?)
>
>   前两种定义在$\mathsf{Y}=\mathbb{C}$时合二为一，2和4的等价性显然，1和4的等价性是由于
>
$$
\{p_{x,g}\mid x\in \mathsf{X},g\in \mathsf{Y}^\prime\}=\{p_x^*\mid x\in \mathsf{X}\}
$$
>   设$f\in \mathsf{X}^\prime$，两个范数的定义分别为，$p_{x,g}(f)=|g(f(x))|$，$p^*_x(f)=|f(x)|$。其中的 $g\circ f \in B(\mathsf{X},\mathbb{C})=\mathsf{X}^\prime$，反之，任取$q\in \mathsf{X}^\prime$，也可以将$q$写成$q=g\circ f$的形式，其中$g\in \mathsf{Y}^\prime ,f\in \mathsf{X}^\prime$。
>
>   强拓扑比弱拓扑更细{（[[Moretti2017\|Moretti2017]] p.75）}，因此在强拓扑中收敛蕴含在弱拓扑中收敛。一致拓扑又比强拓扑细。

> [!theorem] 半范数诱导的拓扑中收敛的充要条件
> - 设线性拓扑空间$(\mathsf{X},\mathscr{T})$的拓扑是由一族半范数$\mathscr{P}=\{p_i\}$诱导的，则序列$\{x_n\}\subset X$收敛到$x\in \mathsf{X}$当且仅当
>
$$
p_i\left(x_n-x_0\right) \rightarrow 0,~n\rightarrow \infty
$$
>   对任意的$p_i\in \mathscr{P}$。

> [!note]
> 

赋范空间上，算符模小于1的算符被称为**收缩算符**(contraction)。Sz.-Nagy's dilation定理：可以将contraction扩张成isometry，进而扩张成unitary。

Banach理论中的三个重要的定理：Banach-Steinhaus定理{（[[Moretti2017\|Moretti2017]] Th.2.62）}(又称uniform
boundedness principle)，开映射原理(open mapping principle)以及Hahn-Banach定理。Hahn-Banach定理可以推论$T$及其对偶$T^\prime$有相同的范数。

> [!definition] 闭算子{\cite[def.2.98
> - {Moretti2017}}]
>   称 $T \in L(\mathsf{X}, \mathsf{Y})$ 是**闭**的，如果 $T$的图像(graph)，
>
$$
G(T):=\{(x, T x) \in \mathsf{X} \oplus \mathsf{Y} \mid x \in \mathsf{X}\},
$$
>   在积拓扑中是闭子空间。在更一般的定义中
>
$$
G(T):=\{(x, T x) \in \mathsf{X} \oplus \mathsf{Y} \mid x \in  D(T)\subset \mathsf{X}\},
$$
> [!theorem] 闭图像定理
> - $T \in L(\mathsf{X}, \mathsf{Y})$是闭的当且仅当她是有界的。
