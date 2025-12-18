---
{"dg-publish":true,"permalink":"/QC-QC/"}
---

主条目:[[1 Stories of Bizzo's Life/5 量子科学和量子技术/33 量子因果结构\|33 量子因果结构]]

# 基本定义
参考{（[[wechs2021QuantumCircuitsClassical\|wechs2021QuantumCircuitsClassical]] Sec.V.B）,（[[salzger2024MappingIndefiniteCausal\|salzger2024MappingIndefiniteCausal]] Apdx.B）}。$N$个外部(相对量子梳而言)信道$\{\mathcal{A}_k:B(\mathsf{H}^{A_{k}^I}) \rightarrow B(\mathsf{H}^{A_{k}^O}),k=1,2,\ldots,n\}$，由一个QC-QC过程控制其作用顺序。不失一般性，设每个信道的蔡氏秩是1，将所有的输入空间视同，记为$\mathsf{H}^{\tilde{A}_{k_n}^I}$，将输出空间也视同，记为$\mathsf{H}^{\tilde{A}_{k_n}^I}$。显式地引入控制系统$C_n,~n=1,\ldots,N$，基底设为
$$
\left|\mathcal{K}_{n - 1}, k_n\right\rangle^{C_n}=\left|\left\{k_1, \ldots, k_{n - 1}\right\}, k_n\right\rangle^{C_n}
$$
空间维度为
$$
\mathrm{dim~}C_n= C_N^{n-1}C_{N-n+1}^1=\frac{N!}{(N-n)!(n-1)!}
$$
这个控制基底记录了上一次以及在这之前作用的信道，上一次作用了$\mathcal{A}_{k_n}$，而再前面作用的信道为$\mathcal{A}_{k_1},\cdots ,\mathcal{A}_{k_{n- 1}}$，它们的作用顺序没有被记录下来。这个改动是实现动态相干的关键？
将外部信道嵌入到$n$个更大的信道中，设在第$n$个时间步上(滥用记号$\tilde{A}_n$)，外部信道和控制系统上的映射为
$$
\begin{aligned}
\tilde{A}_n: & =\sum_{\mathcal{K}_{n-1}, k_n} \tilde{A}_{k_n} \otimes\left|\mathcal{K}_{n-1}, k_n\right\rangle^{C_n^{\prime}}\left\langle\mathcal{K}_{n-1},\left.k_n\right|^{C_n}:\right.  \mathsf{H}^{\tilde{A}_n^I C_n} \rightarrow \mathsf{H}^{\tilde{A}_n^O C_n^{\prime}},
\end{aligned}
$$
其蔡氏向量为
$$
\begin{aligned}
   |\tilde{A}_n  \rangle= &   \sum_{\mathcal{K}_{n-1}, k_n} |\tilde{A}_{k_n}  \rangle \otimes |\mathcal{K}_{n-1}, k_n \rangle^{C_n} \otimes |\mathcal{K}_{n-1}, k_n \rangle^{C_n^{\prime}}  \in \mathsf{H}^{\tilde{A}_n^{\prime} C_n A_n C_n^{\prime}}  
\end{aligned}
$$
内部控制会根据控制系统的状态决定作用的幺正变换，内部控制的蔡氏向量的一般形式为
$$
\begin{aligned}
   |\tilde{V}_1  \rangle= &   \sum_{k_1} |\tilde{V}_{\emptyset, \emptyset}^{ \rightarrow k_1}  \rangle \otimes |\emptyset, k_1 \rangle^{C_1} \in \mathsf{H}^{P \tilde{A}_1^I \alpha_1 C_1}, \\
   |\tilde{V}_{n+1}  \rangle= & \sum_{\substack{\mathcal{K}_{n-1}, k_n, k_{n+1}}} |\tilde{V}_{\mathcal{K}_{n-1}, k_n}^{\rightarrow k_{n+1}} \rangle \otimes |\mathcal{K}_{n-1}, k_n \rangle^{C_n^{\prime}}  \otimes |\mathcal{K}_{n-1} \cup k_n, k_{n+1} \rangle^{C_{n+1}}  \in \mathsf{H}^{\tilde{A}_n^o \alpha_n C_n^{\prime} \tilde{A}_{n+1}^I \alpha_{n+1} C_{n+1}}, \\
   |\tilde{V}_{N+1}  \rangle= & \sum_{k_N} |\tilde{V}_{\mathcal{\mathcal { N }} \backslash k_N, k_N}^{ \rightarrow F} \rangle \otimes |\mathcal{N} \backslash k_N, k_N \rangle^{C_N^{\prime}}  \in \tilde{\mathsf{H}}^{\tilde{A}_N^O \alpha_N C_N^{\prime} F \alpha_F}  
\end{aligned}
$$
eq-eq-internalisometry

需要注意指标满足条件$k_n\notin \mathcal{K}_{n-1},k_{n+1}\notin \mathcal{K}_{n-1}\cup k_{n}$。不必在意tilde以及指标重复的问题，这是原作者为了区分$\mathsf{H}^{A_{k_i}}$与$\mathsf{H}^{A_{i}}$而引入的记号，带tilde的符号表示出现在某个特定时刻的Hilbert空间那些不带tilde的空间都与之同构( $|\tilde{V}_{\mathcal{K}_{n-1}, k_n}^{\rightarrow k_{n+1}} \rangle$ 具有两重身份)。上面的蔡氏向量满足特定的保迹(归一化)条件，
$$
\sum_{k_1} \operatorname{Tr}_{A_{k_1}^I \alpha_1}\left|w_{\left(\emptyset, k_1\right)}\right\rangle\left\langle w_{\left(\emptyset, k_1\right)}\right|= \mathbb{I}^P
$$
$$
\begin{aligned}
\forall n & =1, \ldots, N-1, \forall \mathcal{K}_n, \\
&   \sum_{k_{n+1} \notin \mathcal{K}_n} \operatorname{Tr}_{A_{k_{n+1}}^I \alpha_{n+1}} \mid w_{ (\mathcal{K}_n, k_{n+1} )} \rangle \langle w_{ (\mathcal{K}_n, k_{n+1} )} | =  \sum_{k_n \in \mathcal{K}_n} \operatorname{Tr}_{\alpha_n} |w_{ (\mathcal{K}_n \backslash k_n, k_n )} \rangle \langle w_{ (\mathcal{K}_n \backslash k_n, k_n )} | \otimes  \mathbb{I}^{A_{k_n}^O},
\end{aligned}
$$
eq-eq-qcqctpcond
$$
\begin{aligned}
& \operatorname{Tr}_{F \alpha_F} |w_{(\mathcal{N}, F)} \rangle \langle w_{(\mathcal{N}, F)} |    \quad=\sum_{k_N \in \mathcal{N}} \operatorname{Tr}_{\alpha_N} \mid w_{ (\mathcal{N} \backslash k_N, k_N )} \rangle \langle w_{ (\mathcal{N} \backslash k_N, k_N )} | \otimes  \mathbb{I}^{A_{k_N}^O}
\end{aligned}
$$
归一化条件中出现的向量的定义为
$$
\left|w_{\left(\emptyset, k_1\right)}\right\rangle=\left.\left|w_{\left(k_1\right)}\right\rangle=\left|V_{\emptyset, \emptyset}^{\rightarrow k_1}\right\rangle\right\rangle
$$
$$
\left|w_{\left(\mathcal{K}_{n-1}, k_n\right)}\right\rangle\equiv \sum_{\substack{\left(k_1, \ldots, k_{n}\right): \\\left\{k_1, \ldots, k_{n-1}\right\}=\mathcal{K}_{n-1}}}\left|w_{\left(k_1, \ldots, k_{n}\right)}\right\rangle =  \sum_{k_{n-1} \in \mathcal{K}_{n-1}}\left|w_{\left(\mathcal{K}_{n-1} \backslash k_{n-1}, k_{n-1}\right)}\right\rangle *\left|V_{\mathcal{K}_{n-1} \backslash k_{n-1}, k_{n-1}}^{\rightarrow k_{n}}\right\rangle \in \mathsf{H}^{P A_{\mathcal{K}_{n-1}}^{I O} A_{k_n}^I \alpha_n}
$$
$$
\begin{aligned}
& \left.\left.\left|w_{\left(k_1, \ldots, k_n\right)}\right\rangle\equiv \left|V_{\emptyset, \emptyset}^{k_1}\right\rangle\right\rangle *\left|V_{\emptyset, k_1}^{k_2}\right\rangle * \cdots *\left|V_{\left\{k_1, \ldots, k_{n-2}\right\}, k_{n-1}}^{k_{n}}\right\rangle\right\rangle = |w_{(k_1,\cdots,k_{n-1})}\rangle \star |V^{\rightarrow k_n}_{\{ k_1,\ldots ,k_{n-2}\},k_{n-1}} \rangle \in \mathsf{H}^{P A_{\left\{k_1, \ldots, k_{n-1} \right\}}^{I O} A_{k_n}^I \alpha_n},
\end{aligned}
$$
$$
\left|w_{(\mathcal{N}, F)}\right\rangle  \equiv \sum_{\left(k_1, \ldots, k_N\right)} \left|w_{\left(k_1, \ldots, k_N\right)}\right\rangle \star \left|V_{\left\{k_1, \ldots, k_{N-1}\right\}, k_N}^{\rightarrow F}\right\rangle =  \sum_{\left(k_1, \ldots, k_N\right)}\left|w_{\left(k_1, \ldots, k_N, F\right)}\right\rangle
$$
eq-eq-qcqcprocessvec
$$
\begin{aligned}
\left|w_{\left(k_1, \ldots, k_N, F\right)}\right\rangle\equiv  & \left.\left.\left.\left|V_{\emptyset, \emptyset}^{\rightarrow k_1}\right\rangle\right\rangle *\left|V_{\emptyset, k_1}^{\rightarrow k_2}\right\rangle\right\rangle *\left|V_{\left\{k_1\right\}, k_2}^{\rightarrow k_3}\right\rangle\right\rangle  \left.* \cdots *\left|V_{\left\{k_1, \ldots, k_{N-2}\right\}, k_{N-1}}^{k_N}\right\rangle\right\rangle  *\left|V_{\left\{k_1, \ldots, k_{N-1}\right\}, k_N}^{\rightarrow F}\right\rangle \in \mathsf{H}^{P A_{\mathcal{N}}^{I O} F \alpha_F} .
\end{aligned}
$$
如果辅助系统$\alpha_i$是平凡的，那么与其有关的两个操作之间的链积可以改为张量积，即
$$
\left|V_{\{k_1,\cdots,k_{i-2}\},k_{i-1}}^{\rightarrow k_i}\right\rangle  *\left|V_{{\{k_1,\cdots,k_{i-1}\},k_{i}}}^{\rightarrow k_{i+1}}\right\rangle =\left|V_{\{k_1,\cdots,k_{i-2}\},k_{i-1}}^{\rightarrow k_i}\right\rangle  \otimes \left|V_{{\{k_1,\cdots,k_{i-1}\},k_{i}}}^{\rightarrow k_{i+1}}\right\rangle
$$
将蔡氏向量的定义代入到归一化条件式\eqref{eq:qcqctpcond}可得
\begin{figure}[htbp]
 \centering
 \includegraphics[width=0.7\textwidth]{image//2025-06-10-16-37-23.png}
 \caption{因果结构p.25 }
 \label{  }
\end{figure}

利用上面定义的符号，式\eqref{eq:qcqcprocessvec}，QC-QC的过程矩阵是
(这样的过程矩阵有投影刻画吗？)
$$
\begin{aligned}
    W & =\operatorname{Tr}_{\alpha_F}\left|w_{(\mathcal{N}, F)}\right\rangle\left\langle w_{(\mathcal{N}, F)}\right|
    \end{aligned}
$$
eq-eq-qcqcprocesm

式\eqref{eq:qcqcprocesm}中的控制系统已经被缩并了。保迹性条件来自于内部操作$\tilde{V}_i$(式\eqref{eq:internalisometry})的等距性，在构建一个QC-QC时，应该从这一点出发，直接从缩并掉控制系统后的保迹条件出发是很难构造的。
> [!theorem] QC-QC的等价刻画{} （[[mothe2024ReassessingAdvantageIndefinite\|mothe2024ReassessingAdvantageIndefinite]] (24)）
> - 正定矩阵$W$是QC-QC中的元素当且仅当对于任意的$n$，$\mathcal{N}=\{1,\ldots ,N\}$的势为$n-1$任意真子集$\mathcal{K}_{n-1}$，以及任意$k_n\in \mathcal{N} \backslash \mathcal{K}_{n-1}$，存在正定矩阵$W_{\left(\mathcal{K}_{n-1}, k_n\right)} \in B\left(\mathsf{H}^{A_{\mathcal{K}_{n-1}}^{I O} A_{k_n}^I}\right)$，使得特定的保迹条件得到满足
>
$$
\begin{aligned}
& \operatorname{Tr}_F W=\sum_{k_N \in \mathcal{N}} W_{\left(\mathcal{N} \backslash\left\{k_N\right\}, k_N\right)} \otimes \mathbb{I}^{A_{k_N}^O}, \\ & \forall n=1, \ldots, N-1, \forall \emptyset \subsetneq {\mathcal { K } _ { n } \subsetneq \mathcal { N } ,}   \sum_{k_{n+1} \in \mathcal{N} \backslash \mathcal{K}_n} \operatorname{Tr}_{A_{k_{n+1}}^I} W_{\left(\mathcal{K}_n, k_{n+1}\right)}  =\sum_{k_n \in \mathcal{K}_n} W_{\left(\mathcal{K}_n \backslash\left\{k_n\right\}, k_n\right)} \otimes \mathbb{I}_{k_n}, \\
& \sum_{k_1 \in \mathcal{N}} \operatorname{Tr} W_{\left(\emptyset, k_1\right)}=1,  \forall n=1, \ldots, N,\\
& \forall \mathcal{K}_{n-1} \subsetneq \mathcal{N},   \forall k_n \in \mathcal{N} \backslash \mathcal{K}_{n-1}, W_{\left(\mathcal{K}_{n-1}, k_n\right)} \geq 0
\end{aligned}
$$
> [!note]
> - 在上述刻画中，不需要显式出现辅助系统$\alpha_k$。为什么和蔡氏向量的刻画是相反的？

下面的等式[[wechs2021QuantumCircuitsClassical\|wechs2021QuantumCircuitsClassical]](B40)沟通了两种不同的刻画
$$\begin{aligned}
W_{\left(\mathcal{K}_{n-1}, k_n\right)}:= & \operatorname{Tr}_{\alpha_n}\left|w_{\left(\mathcal{K}_{n-1}, k_n\right)}\right\rangle\left\langle w_{\left(\mathcal{K}_{n-1}, k_n\right)}\right| \\
& \in \mathcal{L}\left(\mathcal{H}^{P A_{\mathcal{K}_{n-1}}^{I O} A_{k_n}^I}\right) .
\end{aligned}$$
### 关于QC-QC的问题
嵌套的QC-QC，这是否能够提供更广的不定因果过程？如何对不同类型的QC-QC进行分类，找到其中的标准型，从而为各种任务提供参考？

## 例子
### 例：串联与并联
   最简单的例子是退化为并联和串联情形，并联例在原文中给出\cite[Apd.C]{wechs2021QuantumCircuitsClassical}，串联不知道怎么构造但可以通过把原文\cite[(D1)]{wechs2021QuantumCircuitsClassical}中的第一个操作与恒等置换初态缩并得到，即

$$\left|V_{\emptyset, \emptyset}^{\rightarrow k_1}\right\rangle_{\mathsf{Seq}} = |\mathbb{I}\rangle\rangle^{P_t A_{k_1}^I} \otimes \sum_{\substack{\pi \in \Pi_{\mathcal{N}}: \\ \pi(1)=k_1}}\langle \mathrm{id}|\pi\rangle^{P_c}  \otimes|\pi\rangle^{\alpha_1} = |\mathbb{I}\rangle\rangle^{P_t A_{k_1}^I} \otimes |\mathrm{id}\rangle^{\alpha_1}\delta_{k_1,1}

$$

后续操作保持不变，就能够得到一个串联过程。如果将后续操作也化简，将控制系统$C_n$全部视为1维的，则有

$$ |V_{\mathcal{K}_{n-1},k_n^{\to k_{n+1}}}\rangle_{\mathsf{Seq}}=|\mathbb{I}\rangle _{A_n^O A_{n + 1}^I}\delta_{k_n,n}\delta_{k_{n+1},n+1}\delta_{\mathcal{K}_{n-1},\{1,\cdots,n\}} $$

$$ |\tilde{V}_{\mathcal{\mathcal { N }} \backslash k_N, k_N}^{ \rightarrow F} \rangle_{\mathsf{Seq}}=|\mathbb{I}^{A_{k_N}^OF}\rangle\delta_{k_N,N} $$

每步的等距操作为

$$    \begin{aligned}
   |\tilde{V}_1  \rangle = & |\mathbb{I}\rangle^{PA_1^I} \otimes    |\emptyset, 1 \rangle^{C_1} \in \mathsf{H}^{P \tilde{A}_1^I \alpha_1 C_1}, \\

   |\tilde{V}_{n+1}  \rangle= &  |\mathbb{I} \rangle^{ A_n^O A_{n + 1}^I} \otimes |\{1,\cdots,n - 1\}, n \rangle^{C_n^{\prime}}  \otimes|\{1,\cdots,n \} , {n+1} \rangle^{C_{n+1}}  \in \mathsf{H}^{\tilde{A}_n^o \alpha_n C_n^{\prime} \tilde{A}_{n+1}^I \alpha_{n+1} C_{n+1}}, \\

   |\tilde{V}_{N+1}  \rangle= &  |\mathbb{I} \rangle^{ A_{N^O}F} \otimes   | \{1,\cdots,N - 1\}, N \rangle^{C_N^{\prime}}  \in \tilde{\mathsf{H}}^{\tilde{A}_N^O \alpha_N C_N^{\prime} F \alpha_F}  
\end{aligned}$$

显然上式缩并掉会导致一个平凡的将多个信道复合的过程，这是一个FO过程，这意味着它一定满足QC-QC的保迹条件，但上式并不完全符合QC-QC的原始形式，因为如果仍然认为控制系统是完整的，则对应的$|\tilde{V}_n\rangle$不是等距而是偏等距，根据原文的推导，这些算符只是保持内积，这是偏等距的定义，并没有保证一定是等距，所以偏等距是没有问题的。当缩并掉控制系统之后，似乎可以对等距算符在控制系统上的行为做一些改变而不影响整体的QC-QC，也就是说控制系统实际上存在一些自由度？

好的，我们将给出一个由三方（$A_1, A_2, A_3$）组成的固定顺序过程的例子，并根据您提供的 **Proposition 7 (QC-QC 的等价刻画)** 来严格证明它是一个合法的 QC-QC。==这里的大致思路是没有问题的，但一些细节可能是错误的==。

#### 1. 例子：固定顺序过程 $\pi = (1, 2, 3)$

我们考虑一个最简单的固定顺序过程：一个初始量子态从“过去”（Past, P）输入，依次通过 $A_1$, $A_2$, $A_3$ 三方的操作，最终输出到“未来”（Future, F）。这个过程仅仅是在各方之间传递量子态，因此可以用一系列连接的恒等信道来描述。

其过程矩阵 $W$ 可以表示为这些恒等信道的 Choi 矩阵的张量积（或链式乘积）：
$$
W_{\pi=(1,2,3)} = ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_2^O A_3^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_3^O F}
$$
其中，$||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{XY}$ 是从希尔伯特空间 $\mathsf{H}^X$ 到 $\mathsf{H}^Y$ 的恒等信道的 Choi 矩阵。为满足命题中的归一化条件，我们假设“过去”空间 $\mathsf{H}^P$ 是一维的，即 $d_P=1$。

#### 2. 证明过程

为了证明 $W_{\pi=(1,2,3)}$ 是一个合法的 QC-QC，我们需要根据 Proposition 7 的要求，构造出一组正定矩阵 $W_{(\mathcal{K}_{n-1}, k_n)}$，并验证它们满足所有的保迹条件。

##### 步骤 1: 构造分解矩阵 $W_{(\mathcal{K}_{n-1}, k_n)}$

由于我们的过程只对应于一个固定的顺序 $(1, 2, 3)$，因此只有沿着这条路径的分解矩阵是非零的。我们定义如下：

*   **对于 n=1:** ($\mathcal{K}_0 = \emptyset$)
    $$
    \begin{aligned}
    W_{(\emptyset, 1)} & := ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \\
    W_{(\emptyset, 2)} & := 0 \\
    W_{(\emptyset, 3)} & := 0
    \end{aligned}
    $$
*   **对于 n=2:** ($\mathcal{K}_1 \subset \mathcal{N}$)
    $$
    \begin{aligned}
    W_{(\{1\}, 2)} & := ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \\
    W_{(\mathcal{K}_1, k_2)} & := 0 \quad \text{对于所有其他情况}
    \end{aligned}
    $$
*   **对于 n=3:** ($\mathcal{K}_2 \subset \mathcal{N}$)
    $$
    \begin{aligned}
    W_{(\{1,2\}, 3)} & := ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_2^O A_3^I} \\
    W_{(\mathcal{K}_2, k_3)} & := 0 \quad \text{对于所有其他情况}
    \end{aligned}
    $$

##### 步骤 2: 验证 Proposition 7 的条件

现在我们逐一验证这些构造出的矩阵满足命题中的四个条件。

1.  **正定性条件 ($W_{(\mathcal{K}_{n-1}, k_n)} \geq 0$)**
    我们构造的非零矩阵是 $||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||$ 算子（这是一个秩为1的投影算子）的张量积，因此它们是正定的。零矩阵也是半正定的。此条件满足。

2.  **归一化条件 ($\sum_{k_1 \in \mathcal{N}} \operatorname{Tr} W_{\left(\emptyset, k_1\right)}=1$)**
$$    \begin{aligned}
    \sum_{k_1 \in \{1,2,3\}} \operatorname{Tr} W_{(\emptyset, k_1)} &= \operatorname{Tr}(W_{(\emptyset, 1)}) + \operatorname{Tr}(W_{(\emptyset, 2)}) + \operatorname{Tr}(W_{(\emptyset, 3)}) \\
    &= \operatorname{Tr}_{P A_1^I}(||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I}) + 0 + 0 \\
    &= d_P = 1 \quad (\text{因为我们假设 } d_P=1)
    \end{aligned}$$
    此条件满足。

3.  **顶层条件 ($\operatorname{Tr}_F W=\sum_{k_N \in \mathcal{N}} W_{\left(\mathcal{N} \backslash\left\{k_N\right\}, k_N\right)} \otimes \mathbb{I}^{A_{k_N}^O}$)**
    对于 $N=3$，我们需要验证 $\operatorname{Tr}_F W = \sum_{k_3 \in \{1,2,3\}} W_{(\{1,2,3\}\backslash\{k_3\}, k_3)} \otimes \mathbb{I}^{A_{k_3}^O}$。
    *   **等式左边 (LHS):**
$$        \begin{aligned}
        \operatorname{Tr}_F(W_{\pi=(1,2,3)}) &= \operatorname{Tr}_F\left(||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes \dots \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_3^O F}\right) \\
        &= ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_2^O A_3^I} \otimes \mathbb{I}^{A_3^O}
        \end{aligned}$$
    *   **等式右边 (RHS):**
$$        \begin{aligned}
        \text{RHS} &= W_{(\{1,2\},3)} \otimes \mathbb{I}^{A_3^O} + W_{(\{1,3\},2)} \otimes \mathbb{I}^{A_2^O} + W_{(\{2,3\},1)} \otimes \mathbb{I}^{A_1^O} \\
        &= W_{(\{1,2\},3)} \otimes \mathbb{I}^{A_3^O} + 0 + 0 \\
        &= \left(||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_2^O A_3^I}\right) \otimes \mathbb{I}^{A_3^O}
        \end{aligned}$$
    LHS = RHS。此条件满足。

4.  **递归条件 ($\forall n=1, \ldots, N-1, \dots$)**
    *   **验证 n=1:** 我们需要验证 $\sum_{k_2 \in \mathcal{N}\backslash\mathcal{K}_1} \operatorname{Tr}_{A_{k_2}^I} W_{(\mathcal{K}_1, k_2)} = \sum_{k_1 \in \mathcal{K}_1} W_{(\mathcal{K}_1\backslash\{k_1\}, k_1)} \otimes \mathbb{I}^{A_{k_1}^O}$。
        *   **情况 1: $\mathcal{K}_1=\{1\}$**
            *   LHS: $\sum_{k_2 \in \{2,3\}} \operatorname{Tr}_{A_{k_2}^I} W_{(\{1\}, k_2)} = \operatorname{Tr}_{A_2^I} W_{(\{1\}, 2)} + \operatorname{Tr}_{A_3^I} W_{(\{1\}, 3)} = \operatorname{Tr}_{A_2^I} W_{(\{1\}, 2)} + 0 = ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes \mathbb{I}^{A_1^O}$.
            *   RHS: $\sum_{k_1 \in \{1\}} W_{(\emptyset, k_1)} \otimes \mathbb{I}^{A_{k_1}^O} = W_{(\emptyset, 1)} \otimes \mathbb{I}^{A_1^O} = ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes \mathbb{I}^{A_1^O}$.
            *   LHS = RHS。
        *   **情况 2: $\mathcal{K}_1=\{2\}$ 或 $\mathcal{K}_1=\{3\}$**
            *   LHS: 因为所有 $W_{(\{2\},\cdot)}$ 和 $W_{(\{3\},\cdot)}$ 均为零，所以 LHS = 0。
            *   RHS: 因为 $W_{(\emptyset, 2)}$ 和 $W_{(\emptyset, 3)}$ 均为零，所以 RHS = 0。
            *   LHS = RHS。
    *   **验证 n=2:** 我们需要验证 $\sum_{k_3 \in \mathcal{N}\backslash\mathcal{K}_2} \operatorname{Tr}_{A_{k_3}^I} W_{(\mathcal{K}_2, k_3)} = \sum_{k_2 \in \mathcal{K}_2} W_{(\mathcal{K}_2\backslash\{k_2\}, k_2)} \otimes \mathbb{I}^{A_{k_2}^O}$。
        *   **情况 1: $\mathcal{K}_2=\{1,2\}$**
            *   LHS: $\sum_{k_3 \in \{3\}} \operatorname{Tr}_{A_{k_3}^I} W_{(\{1,2\}, k_3)} = \operatorname{Tr}_{A_3^I} W_{(\{1,2\}, 3)} = ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \otimes \mathbb{I}^{A_2^O}$.
            *   RHS: $\sum_{k_2 \in \{1,2\}} W_{(\{1,2\}\backslash\{k_2\}, k_2)} \otimes \mathbb{I}^{A_{k_2}^O} = W_{(\{2\}, 1)} \otimes \mathbb{I}^{A_1^O} + W_{(\{1\}, 2)} \otimes \mathbb{I}^{A_2^O} = 0 + W_{(\{1\}, 2)} \otimes \mathbb{I}^{A_2^O} = ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{P A_1^I} \otimes ||\mathbb{I}\rangle\rangle\langle\langle\mathbb{I}||^{A_1^O A_2^I} \otimes \mathbb{I}^{A_2^O}$.
            *   LHS = RHS。
        *   **情况 2: $\mathcal{K}_2=\{1,3\}$ 或 $\mathcal{K}_2=\{2,3\}$**
            *   LHS: 所有相关的 $W$ 矩阵均为零，LHS = 0。
            *   RHS: 所有相关的 $W$ 矩阵均为零，RHS = 0。
            *   LHS = RHS。

所有递归条件均满足。

### 例：两路的量子开关
> [!example] 两路的量子开关
> - 以第\ref{ex:quantumswitch}小节的量子开关为例，它的过程矩阵的蔡氏向量中的每一项都写为
>
$$
\begin{aligned}
\left.\left|V_{\emptyset, \emptyset}^{\rightarrow k_1}\right\rangle\right\rangle & =| \mathbb{I}\rangle\rangle^{P_t A_{k_1}^I} \otimes\left|k_1\right\rangle^{P_c}, \\
\left.\left|V_{\emptyset, k_1}^{\rightarrow k_2}\right\rangle\right\rangle & =| \mathbb{I}\rangle\rangle^{A_{k_1}^O A_{k_2}^I}, \\
\left.\left|V_{\left\{k_1\right\}, k_2}^F\right\rangle\right\rangle & =| \mathbb{I}\rangle\rangle^{A_{k_2}^O F_t} \otimes\left|k_1\right\rangle^{F_c} .
\end{aligned}
$$
>   根据式\eqref{eq:qcqcprocessvec}，我们要把所有可能的顺序相干地叠加起来得到量子开关的过程矩阵的蔡氏向量
>
$$
\begin{aligned}
|w_{\mathsf{DS}} \rangle=        |1\rangle^{P_c}| \mathbb{I} \rangle^{P_t A_1^I}| \mathbb{I} \rangle^{A_1^O A_2^I}| \mathbb{I} \rangle^{A_2^O F_t}|1\rangle^{F_c}       +|2\rangle^{P_c}| \mathbb{I} \rangle^{P_t A_2^I}| \mathbb{I} \rangle^{A_2^O A_1^I}| \mathbb{I} \rangle^{A_1^O F_t}|2\rangle^{F_c}  \in \mathcal{H}^{P_c P_t A_1^{I O} A_2^{I O} F_t F_c},
\end{aligned}
$$
### 例：一个只有部分记忆的量子开关
> [!example] ~一个只有部分记忆的量子开关
> - 如果希望每个外部系统之间的操作是恒等操作，但又要保持每个时间步上的变换是等距的，就不可避免地引入一些辅助系统(我只在必要的时候引入辅助系统)，这最终导致了一个特殊的量子开关，它的行为完全可以通过在\eqref{eq:qsarbinput}中取合适的初态来实现。
>
$$
\begin{aligned}
& \left|V^{\rightarrow k_1}\right\rangle=|\mathbb{I}\rangle^{P A_{k_1}^I}\left|k_1\right\rangle^{P_c} \\
& \left|V^{\rightarrow k_2}\right\rangle=\frac{1}{\sqrt{2}}|\mathbb{I}\rangle^{A_{k_1}^O A_{k_3}^I} \\
& \left|V^{\rightarrow k_3}\right\rangle=|\mathbb{I}\rangle^{A_{k_1}^O A_{k_3}^I}\left|k_2\right\rangle^{\alpha_3} \\
& \left|V^{\rightarrow F}\right\rangle=|\mathbb{I}\rangle^{A_{k_3}^O F}\left|k_3\right\rangle^{F_c}|\mathbb{I}\rangle^{\alpha_3 \alpha_F}
\end{aligned}
$$
>
>   最终的蔡氏向量为
>
$$
\left|w_{(\mathcal{N}, F)}\right\rangle=\sum_{\left(k_1, k_2, k_3\right)} \frac{1}{\sqrt{2}}\left|\mathbb{I}^3\right\rangle^{P A_1 A_2 A_3 F}\left|k_1\right\rangle^{P_c}\left|k_2\right\rangle^{\alpha_F}\left|k_3\right\rangle^{F_c}
$$
>
>   这是一个只接受3维控制输入的量子开关，如果接受控制系统上的一个初态$\frac{1}{\sqrt{3}} |\psi\rangle^{P_c}=\sum_{k_1} |k_1\rangle$，那么它就会等效为一个等权重叠加的量子开关。其构建过程如下图：
>   \begin{figure}[htbp]
>   \centering
>   \includegraphics[width=0.7\textwidth]{image//2025-07-08-10-50-57.png}
>   \caption{因果结构p.28}
>   \label{  }
>   \end{figure}
>   
>   重复类似的推导，可以得到一些没有完整记忆的$N$体量子开关(待补充)，基本方法是如果控制系统的维度在变大，我们可以丢掉记忆并引入一个因子来保证保迹性(例如$\tilde{V}_2$)，如果控制系统的维度在减小，则引入辅助系统来保证单时间步算符的等距性(例如$\tilde{V}_3$和例如$\tilde{V}_4$)。而多体且拥有完整记忆的量子开关的构建参考（[[wechs2021QuantumCircuitsClassical\|wechs2021QuantumCircuitsClassical]] (D1)），这需要引入更多辅助系统，记忆之前的外部系统调用顺序。在受控系统上进行一些非等距的操作似乎是取得动态控制的必要条件。

### 动态相干控制的三路开关
> [!example] 动态相干控制的三路开关
> - 相干、动态的顺序叠加的等效比特信道（[[wechs2021QuantumCircuitsClassical\|wechs2021QuantumCircuitsClassical]] (67)）。
>
$$
\begin{aligned}
& V_{\emptyset, \emptyset}^{ \rightarrow k_1}=\frac{1}{\sqrt{3}}|\psi\rangle^{A_{k_1}^I}, \\
& V_{\emptyset, k_1}^{ \rightarrow k_2}= \left\{\begin{array}{lll}
|0\rangle^{A_{k_2}^I} \langle   0 |^{A_{k_1}^O}   & \text { if } k_2=k_1+1 & (\bmod 3)  \\
|1\rangle^{A_{k_2}^I} \langle   1 |^{A_{k_1}^O}   & \text { if } k_2=k_1+2 & (\bmod 3)
\end{array}, \right. \\
& V_{ \{k_1 \}, k_2}^{ \rightarrow k_3}= \left\{\begin{array}{ll}
|0\rangle^{A_{k_3}^I}|0\rangle^{\alpha_3} \langle   0 |^{A_{k_2}^O}+\mid 1 \rangle^{A_{k_3}^I}|1\rangle^{\alpha_3} \langle   1 |^{A_{k_2}^O}   & \text { if } k_2=k_1+1 \quad(\bmod 3) \\
|0\rangle^{A_{k_3}^I}|1\rangle^{\alpha_3} \langle   0 |^{A_{k_2}^O}+\mid 1 \rangle^{A_{k_3}^I}|0\rangle^{\alpha_3} \langle   1 |^{A_{k_2}^O}   & \text { if } k_2=k_1+2 \quad(\bmod 3)
\end{array},  \right. \\
& V_{ \{k_1, k_2 \}, k_3}^{\rightarrow F}=\mathbb{I}^{A_{k_3}^O \alpha_3  \rightarrow \alpha_F^{(1)}} \otimes |k_3 \rangle^{\alpha_F^{(2)}},
\end{aligned}
$$
>
>   eq-eq-truethreeswitch



>   $\alpha^{(1)}_F = F_t \alpha_F ,\alpha^{(2)}_F=F_c$。
>
>   修改式\eqref{eq:truethreeswitch}，显式地加入输入和输出空间，假设$P$和$F$都是单比特空间，
>
$$
\begin{aligned}
& V_{\emptyset, \emptyset}^{ \rightarrow k_1}=\frac{1}{\sqrt{3}}\mathbb{I}^{P\rightarrow A_{k_1}^I}, \\
& V_{\emptyset, k_1}^{ \rightarrow k_2}= \left\{\begin{array}{lll}
|0\rangle^{A_{k_2}^I} \langle   0 |^{A_{k_1}^O}   & \text { if } k_2=k_1+1 & (\bmod 3)  \\
|1\rangle^{A_{k_2}^I} \langle   1 |^{A_{k_1}^O}   & \text { if } k_2=k_1+2 & (\bmod 3)
\end{array}, \right. \\
& V_{ \{k_1 \}, k_2}^{ \rightarrow k_3}= \left\{\begin{array}{ll}
|0\rangle^{A_{k_3}^I}|0\rangle^{\alpha_3} \langle   0 |^{A_{k_2}^O}+\mid 1 \rangle^{A_{k_3}^I}|1\rangle^{\alpha_3} \langle   1 |^{A_{k_2}^O}   & \text { if } k_2=k_1+1 \quad(\bmod 3) \\
|0\rangle^{A_{k_3}^I}|1\rangle^{\alpha_3} \langle   0 |^{A_{k_2}^O}+\mid 1 \rangle^{A_{k_3}^I}|0\rangle^{\alpha_3} \langle   1 |^{A_{k_2}^O}   & \text { if } k_2=k_1+2 \quad(\bmod 3)
\end{array},  \right. \\
& V_{ \{k_1, k_2 \}, k_3}^F=\mathbb{I}^{A_{k_3}^O \alpha_3  \rightarrow F^t \alpha_F } \otimes |k_3 \rangle^{F^c},
\end{aligned}
$$
>   


>   其中，输出空间的辅助系统为$\alpha_F$，是比特系统，输出空间$F$由两部分组成，$F=F^cF^t$，$F^c$是三维系统，$F^t$是比特系统。更进一步的推广是
>
$$
\begin{aligned}
&V_{\emptyset, \emptyset}^{\rightarrow k_1}:=\mathbb{I}^{P_t \rightarrow A_{k_1}^I} \otimes\left\langle\left. k_1\right|^{P_c},\right.\\
&V_{\emptyset, k_1}^{\rightarrow k_2}:=\left(\mathbb{I}^{A_{k_2}^I} \otimes\left\langle\left.\sigma_{\left(k_1, k_2\right)}\right|^\alpha\right) \mathcal{V}_{k_1},\right.\\
& V_{\left\{k_1\right\}, k_2}^{\rightarrow k_3}:=\mathcal{V}_{k_3}^{\prime}\left(\mathbb{I}^{A_{k_2}^O} \otimes\left|\sigma_{\left(k_1, k_2\right)}\right\rangle^{\alpha^{\prime}}\right),\\
& V_{\left\{k_1, k_2\right\}, k_3}^{\rightarrow F }:=\mathbb{I}^{A_{k_3}^O \rightarrow F_t} \otimes \mathbb{I}^{\alpha_3 \rightarrow \alpha_F} \otimes\left|k_3\right\rangle^{F_c} .
\end{aligned}
$$
>
>   eq-eq-generalizedthreeswitch


>   其中 $\mathcal{V}_{k_1}: \mathcal{H}^{A_{k_1}^O} \rightarrow \mathcal{H}^{A_{k_2}^I \alpha},\mathcal{V}_{k_3}^{\prime}: \mathcal{H}^{A_{k_2}^O \alpha^{\prime}} \rightarrow \mathcal{H}^{A_{k_3}^I \alpha_3}$，$P^c$是三维系统，受控系统$P_t ,F_t$的相同维度而任意。$\sigma_{\left(k_1, k_2\right)}=0 \text { if } k_2=k_1+1(\bmod 3)$，$\sigma_{\left(k_1, k_2\right)}=1 \text { if } k_2=k_1+2(\bmod 3)$。构造这类过程的关键在于要满足保迹性条件，可以检验保迹性。
>
>
> -
$$
\sum_{k_1} \text{tr}_{A_{k_1}^I} | w_{(\emptyset,k_1)}\rangle \langle  w_{(\emptyset,k_1)}| = \sum_{k_1} \text{tr}_{A_{k_1}^I} |V_{\emptyset,\emptyset}^{\to k_1}\rangle \langle V_{\emptyset,\emptyset}^{\to k_1}|
$$
>
$$
= \sum_{k_1} \text{tr}_{A_{k_1}^I} |\mathbb{I}\rangle \langle \mathbb{I}|_{P_t A_{k_1}^I} \otimes |k_1\rangle \langle k_1|_{P_c} = \mathbb{I}_{P_t} \otimes \mathbb{I}_{P_c} = \mathbb{I}_P.
$$
> - 大小为1的集合有3种可能的选取方式 \($\mathcal{K}_1 = \{1 \}, \{2 \}, \{3 \}$\)
>
$$
| w_{(\mathcal{K}_1,k_2)}\rangle = \sum_{k_1 \in \mathcal{K}_1} | w_{(k_1,k_2)}\rangle = | w_{(k_1,k_2)}\rangle \otimes |V_{\emptyset,k_1}^{\to k_2}\rangle, k_1 \in \mathcal{K}_1
$$
>
>   利用双矢量公式，有
>
$$
|V_{\emptyset,k_1}^{\to k_2}\rangle_{A_{k_1}^OA_{k_2}^I} = \mathbb{I}_{A_{k_1}^I} \otimes \langle \sigma_{(k_1,k_2)}|_\alpha \otimes \mathbb{I}_{A_{k_1}^O} |V_{k_1}\rangle_{A_{k_2}^I \alpha A_{k_1}^I} = \langle \sigma_{(k_1,k_2)}| \mathcal{V}_{k_1}\rangle_{A_{k_2}^I A_{k_1}^O}
$$
>
>
$$
\sum_{k_2 \notin \mathcal{K}_1} \text{tr}_{A_{k_2}^I} | w_{(\mathcal{K}_1,k_2)}\rangle \langle  w_{(\mathcal{K}_1,k_2)}| = | w_{(k_1)}\rangle \langle  w_{(k_1)}| \otimes \sum_{k_2 \notin \mathcal{K}_1} \text{tr}_{A_{k_2}^I} |V_{\emptyset,k_1}^{\to k_2}\rangle \langle V_{\emptyset,k_1}^{\to k_2}|
$$
>
$$
= | w_{(k_1)}\rangle \langle  w_{(k_1)}| \otimes \sum_{k_2} \text{tr}_{A_{k_2}^I} \langle \sigma_{(k_1,k_2)}| \mathcal{V}_{k_1}\rangle \langle \mathcal{V}_{k_1}| \sigma_{(k_1,k_2)} \rangle
$$
>
$$
= | w_{(k_1)}\rangle \langle  w_{(k_1)}| \otimes \text{tr}_{A_{k_2}^I\alpha } | \mathcal{V}_{k_1}\rangle \langle \mathcal{V}_{k_1}|
$$
>
$$
= | w_{(1)}\rangle \langle  w_{(1)}| \left( \text{tr}_{A_2^I} \langle 0 | \mathcal{V}_1\rangle \langle \mathcal{V}_1| 0\rangle + \text{tr}_{A_3^I} \langle 1| \mathcal{V}_1\rangle \langle \mathcal{V}_1| 1\rangle \right), \text{ 当 }k_1 = 1, k_2 = 2,3
$$
>
$$
= | w_{(1)}\rangle \langle  w_{(1)}| \otimes \mathbb{I}_{A_1^o}
$$
>   当\(k_1\)取其它值时也有类似结果。添加辅助系统的意义就是利用不同系统上的内积和trace得到对$\mathcal{V}_{k_1}$的蔡氏矩阵的输出空间的trace，从而得到$A_{k_1}^O$上的单位阵。


$\mathcal{K}_2=\{12 \}, \{2 3\}, \{13 \}$
>
$$
\begin{aligned}
&\sum_{k_3 \notin \mathcal{K}_2} \text{tr}_{A_{k_3}^I \alpha_3} | w_{(\mathcal{K}_2, k_3)}\rangle \langle  w_{(\mathcal{K}_2, k_3)}| \\
=& \sum_{k_3 \notin \mathcal{K}_2} \text{tr}_{A_{k_3}^I \alpha_3} \sum_{k_2, q_2 \in \mathcal{K}_2} | w_{(\mathcal{K}_2 \setminus \{k_2\}, k_2)}\rangle \langle  w_{(\mathcal{K}_2 \setminus \{q_2\}, q_2)}| \otimes |V_{\mathcal{K}_2 \setminus \{k_2\}, k_2}^{\to k_3}\rangle \langle V_{\mathcal{K}_2 \setminus \{q_2\}, q_2}^{\to k_3}| \\
=& \sum_{k_2, q_2 \in \mathcal{K}_2} | w_{(\mathcal{K}_2 \setminus \{k_2\}, k_2)}\rangle \langle  w_{(\mathcal{K}_2 \setminus \{q_2\}, q_2)}| \otimes \text{tr}_{A_{k_3}^I \alpha_3} |V_{\mathcal{K}_2 \setminus \{k_2\}, k_2}^{\to k_3}\rangle \langle V_{\mathcal{K}_2 \setminus \{q_2\}, q_2}^{\to k_3}| \quad (1)
\end{aligned}
$$
>   利用双矢量公式，有
>
$$
|V_{\mathcal{K}_2 \setminus \{k_2\}, k_2}^{\to k_3}\rangle = (\mathbb{I}_{A_{k_2}^O}\otimes \mathcal{V}_{k_3}^\prime   ) |\mathbb{I}\rangle_{A_{k_2}^O A_{k_2}^O} \otimes |\sigma_{(k_1, k_2)}\rangle_{\alpha'}
$$
>
$$
\text{tr}_{A_{k_3}^I \alpha_3} |V_{\mathcal{K}_2 \setminus \{k_2\}, k_2}^{\to k_3}\rangle \langle V_{\mathcal{K}_2 \setminus \{q_2\}, q_2}^{\to k_3}| = \sum_{ij} \text{tr}_{A_{k_3}^I \alpha_3} (\mathcal{V}_{k_3}' |i\rangle \langle j|_{A_{k_2}^o} \otimes |\sigma_{(\mathcal{K}_2 \setminus \{k_2\}, k_2)}\rangle \langle \sigma_{(\mathcal{K}_2 \setminus \{q_2\}, q_2)}|_{\alpha^\prime } \mathcal{V}_{k_3}^{\prime \dagger }) \otimes |i\rangle \langle j|_{A_{k_2}^o}
$$
>
$$
= \delta_{k_2 q_2} \mathbb{I}_{A_{k_2}^o} \quad (2)
$$
>   综合 (1), (2)，有
>
$$
\sum_{k_3 \notin \mathcal{K}_2} \text{tr}_{A_{k_3}^I \alpha_3} | w_{(\mathcal{K}_2, k_3)}\rangle \langle  w_{(\mathcal{K}_2, k_3)}| = \sum_{k_2 \in \mathcal{K}_2} | w_{(\mathcal{K}_2 \setminus \{k_2\}, k_2)}\rangle \langle  w_{(\mathcal{K}_2 \setminus \{q_2\}, q_2)}| \otimes \mathbb{I}_{A_{k_2}^o}
$$

最后一步
>  $$ \begin{align*}
>
>
>
>   &| w_{(\mathcal{N},F)}\rangle=\sum_{k_1,k_2,k_3}| w_{(k_1,k_2,k_3)}\rangle\star|V_{\{k_1,k_2\},k_3}^{\to F}\rangle=\sum|V_{\emptyset ,\emptyset}^{\to k_1}\rangle\otimes|V_{\emptyset,k_1}^{\to k_2}\rangle\otimes|V_{\{k_1\},k_2}^{\to k_3}\rangle\star|V_{\{k_1,k_2\},k_3}^{\to F}\rangle\\
>   =& \sum|V_{\emptyset,\emptyset}^{\to k_1}\rangle\otimes|V_{\emptyset,k_1}^{\to k_2}\rangle\otimes|V_{\{k_1\},k_2}^{\to k_3}\rangle|\mathbb{I}\rangle_{A_{k_3}^O F_t}|k_3\rangle_{F_c}\\
>   =& \sum_{k_3}\sum_{k_1k_2}| w_{(k_1,k_2,k_3)}\rangle|\mathbb{I}\rangle|k_3\rangle \\
>   =&\sum_{k_3} | w_{(\mathcal{N}\setminus  k_3,k_3)}\rangle|\mathbb{I}\rangle|k_3\rangle\,
>   \end{align*}$$
>   上式已经利用了
>
$$
| w_{(\mathcal{N}\setminus  k_3,k_3)}\rangle=\sum_{k_1k_2}| w_{(k_1,k_2,k_3)}\rangle=\sum_{k_1k_2}|V_{\emptyset,\emptyset}^{\to k_1}\rangle\star|V_{\emptyset,k_1}^{\to k_2}\rangle\star|V_{\{k_1,k_2\}}^{\to k_3}\rangle
$$
>   以及
>
$$
\begin{aligned}
\left|V_{\{k_1\}, k_2}^{\rightarrow k_3}\right\rangle *\left|V_{\left\{k_1, k_2\right\}, k_3}^{\rightarrow F}\right\rangle & =\left(\left|V_{\left\{k_1\right\}, k_2}^{\rightarrow k_3}\right\rangle_{A_{k_3}^I \alpha_3 A_{k_2}^O}^{T_{\alpha_3}} \otimes \mathbb{I}_{F_t F_c \alpha_F}\right)\left(|\mathbb{I}\rangle_{A_{k_3}^O F_t} \otimes|\mathbb{I}\rangle_{\alpha_3 \alpha_F} \otimes\left|k_3\right\rangle_{F_c}\right) \\
& =\mathbb{I}^{\alpha_3 \rightarrow \alpha_F}\left|V_{\left\{k_1\right\}, k_2}^{\rightarrow k_3}\right\rangle_{A_{k_3}^I \alpha_3 A_{k_2}^O}|\mathbb{I}\rangle_{A_{k_3}^O F_t}\left|k_3\right\rangle_{F_c}
\end{aligned}
$$
>   保迹条件写为
>  $$ \begin{align*}
   &\mathrm{tr}_{F\alpha_F}| w(\mathcal{N},F)\rangle\langle  w(\mathcal{N},F)|=\mathrm{tr}_{F\alpha_F}\left(\sum_{k_3,q_3} | w_{(\mathcal{N}\setminus  k_3,k_3)}\rangle\langle  w_{(\mathcal{N}\setminus  q_3,q_3)}| \otimes|\mathbb{I}\rangle_{A_{k_3}^OF_t}\langle\mathbb{I}|\otimes|k_3\rangle_{F_c}\langle q_3|\right)\\
   =&\mathrm{tr}_{\alpha_F}| w_{(\mathcal{N}\setminus  k_3,k_3)}\rangle\langle  w_{(\mathcal{N}\setminus  q_3,q_3)}|\otimes\mathbb{I}_{A_{k_3}^O}\otimes\delta_{k_3q_3}\\
   =&\mathrm{tr}_{\alpha_F}| w_{(\mathcal{N}\setminus  k_3,k_3)}\rangle\langle  w_{(\mathcal{N}\setminus  k_3,k_3)}|\otimes\mathbb{I}_{A_{k_3}^O}
   \end{align*}$$
>   



>   
>  一个更具启发性且更简单的过程保迹性检验方式是利用$V_n$的等距性：
>
> -
$$
\begin{aligned}
|\widetilde{V}_1\rangle &= \sum_{k_1} |\mathbb{I}\rangle^{P_t A_{k_1}^I} |k_1\rangle^{P_c} | \phi, k_1 \rangle^{C_1},\\
\mathrm{tr}_{A_1^IC_1}  | \widetilde{V}_1 \rangle\langle \widetilde{V}_1|&= \mathbb{I}_{P_t}\otimes \mathbb{I}_{P_c}\otimes \mathbb{I}_{C_1}
\end{aligned}
$$
> -
$$
\begin{aligned}
|\widetilde{V}_2\rangle &= \sum_{ k_1 k_2 k_3} \langle \sigma_{(k_1,k_2)}| \mathcal{V}_{k_1}\rangle_{A_{k_2}^I A_{k_1}^O}  | \phi, k_2 \rangle^{C_1'} |\{k_1\}, k_2\rangle^{C_2}, \\
\mathrm{tr}_{A_2^I}  | \widetilde{V}_2 \rangle\langle \widetilde{V}_2| &= \sum_{(k_1,k_2) \atop (q_1,q_2)} \mathrm{tr}_{A_2^I}\langle \sigma_{(k_1,k_2)} | \mathcal{V}_1\rangle \langle \mathcal{V}_1 | \sigma_{(q_1,q_2)} \rangle | \phi, k_1 \rangle\langle \phi, q_1 |^{C_1'} \mathrm{tr}|\{k_1\}, k_2\rangle\langle\{q_1\}, q_2|^{C_2} \\
&= \mathbb{I}_{A_1^o} \otimes \mathbb{I}_{C_1'}.
\end{aligned}
$$
> -
$$
\begin{aligned}
|V_3\rangle &= \sum_{k_1,k_2,k_3} \mathbb{I}_{A_3^o} \otimes \mathcal{V}_3^\prime  |\mathbb{I}\rangle_{A_3^o A_3^o} |\sigma_{(k_1,k_2)}\rangle^{\alpha'} |\{k_1\}, k_2\rangle^{C_2^\prime} |\{k_1,k_2\}, k_3\rangle^{C_3}, \\
\mathrm{tr}_{\alpha_2A_3^I C_3} | \widetilde{V}_3 \rangle\langle \widetilde{V}_3|  &= \sum_{\{k,k_2\} \atop =\{q_1,q_2\}} \mathrm{tr}_{\alpha_3 A_3^I} \left( \mathbb{I}_{A_3^o} \otimes \mathcal{V}_3^\prime  \right) |\mathbb{I}\rangle_{\alpha_3^o A_3^o} \otimes |\sigma_{(k,k_2)}\rangle_{\alpha'} \langle \mathbb{I} |_{\alpha_3^o A_3^o} \langle \sigma_{(q_1,q_2)} | \left( \mathbb{I}_{A_3^o} \otimes \mathcal{V}_3^{\prime\dagger} \right) \otimes |\{k_1\}, k_2\rangle\langle\{q_1\}, q_2| \\
&= \sum_{\{k_1,k_2\} \atop =\{q_1,q_1\}} |i\rangle\langle j| \otimes \mathrm{tr}\left(\mathcal{V}_3^\prime  |i\rangle\langle j|  \otimes   \left| \sigma_{(k_1,k_2)} \right\rangle   \langle \sigma_{(q_1,q_2)} | \mathcal{V}_3^{\prime\dagger}\right) \otimes |\{k_1\}, k_2\rangle\langle\{q_1\}, q_2| \\
&= \mathbb{I}_{A_2^o} \sum_{\{k_1,k_2\} \atop =\{q_1,q_2\}} \langle \sigma_{(q_1,q_2)} | \sigma_{(k_1,k_2)} \rangle |\{k_1\}, k_2\rangle\langle\{q_1\}, q_2| \\
&= \mathbb{I}_{A_2^o} \otimes \mathbb{I}_{C_2'}.
\end{aligned}
$$
> -
$$
\begin{aligned}
|\widetilde{V}_4\rangle &= \sum_{k_3} |V\rangle^{P_t} \otimes |\{k_1,k_2\}, k_3\rangle^{C_3'}, \\
&= |\mathbb{I}\rangle^{A_2^o F_t} \otimes |\mathbb{I}\rangle \sum_{k_3} |k_3\rangle^{F_c} |\{k_1,k_2\}, k_3\rangle^{C_3'}, \\
\mathrm{tr}_{\alpha_F F_c} |V^4\rangle\langle V^4| &= \mathbb{I}_{A_3^o} \otimes \mathbb{I}_{\alpha_3} \otimes \mathbb{I}_{C_3'}.
\end{aligned}
$$
>
>
>   式\eqref{eq:generalizedthreeswitch}组合成一个动态开关(dynamical switch)，如果取初态控制系统为均匀叠加态$|\psi\rangle _{P_c} = \frac{1}{\sqrt{3}}(|0\rangle +|1\rangle +|2\rangle)$，两个等距算符分别为COPY和CNOT，则蔡氏向量为
>
$$
|w_{\mathsf{DS}}\rangle =  \sum_{(k_1,k_2,k_3)} |V_{\emptyset, \emptyset}^{\rightarrow k_1} \rangle   * |V_{\emptyset, k_1}^{\rightarrow k_2} \rangle   * |V_{ \{k_1 \}, k_2}^{\rightarrow k_3} \rangle      * |V_{ \{k_1,  k_{2} \}, k_3}^{\rightarrow F} \rangle
$$
>   求和项数为6，显式给出求和结果的表达式参见QC-QC计算.nb-无输入，保留输出α2F1。插入三个完全退极化信道(QC-QC计算.nb-插入完全退极化信道，解析方法求偏迹)
>
$$
\begin{aligned}
&    |w_{\mathsf{DS}}\rangle \langle w_{\mathsf{DS}}| \star  \rho^\mathsf{Dp} \star  \rho^\mathsf{Dp} \star  \rho^\mathsf{Dp} \\
=   &8 (\frac{1}{2}  (\mathbb{I}_{P_tF_tF_cP_c} - \mathbb{I}_{P_tF_t}\otimes\sum_{i = 1}^{3}|i\rangle\langle i|_{F_c} |i\rangle \langle i|_{P_c}  )\\ &+
|00\rangle\langle00|\otimes(|\psi^1\rangle\langle\psi^1|-(|01\rangle\langle01| + |12\rangle\langle 12|+|20\rangle\langle20|)) \\& +|11\rangle\langle 11|\otimes(|\psi^2\rangle\langle\psi^2|-(|02\rangle\langle02| + |10\rangle\langle 10|+|21\rangle\langle21|))  )\\
&|\psi^1\rangle = |01\rangle+|12\rangle + |20\rangle\\
&|\psi^2\rangle = |02\rangle+|10\rangle+|12\rangle
\end{aligned}
$$
>
>   插入三个完全退极化信道后，得到等效信道(QC-QC计算.nb-给定控制系统初态)
>
$$
\begin{aligned}
& \rho^{\mathsf{DS}_{\mathrm{eff}}}=|\psi\rangle _{P_c}\langle \psi| \star |w_{\mathsf{DS}}\rangle \langle w_{\mathsf{DS}}| \star  \rho^\mathsf{Dp} \star  \rho^\mathsf{Dp} \star  \rho^\mathsf{Dp} \\  = & \frac{1}{8}\left( (|0 0\rangle\langle 0 0|+|1 1\rangle\langle 1 1|)_{P_t F_t}\otimes|\psi\rangle\langle\psi|_{F_c}+(\mathbb{I}_{P_t F_t}+\frac{1}{3}|0 1\rangle\langle 0 1|+|1 0\rangle\langle 1 0|)\otimes\mathbb{I}_{F_c} \right)
\end{aligned}
$$
>   上面的解析表达式只对均匀叠加态$|\psi\rangle =\frac{1}{\sqrt{3}}(|0\rangle +|1\rangle +|2\rangle)$成立。
>
>   将未来的控制比特系统trace掉将得到完全退极化信道
>
$$
\mathrm{tr}_{F_c}(\rho^{\mathsf{DS}_{\mathrm{eff}}}) = \frac{\mathbb{I}_{P_t  F_t}}{2}
$$
>   是否存在一些过程，它被插入一些完全退极化信道且将辅助系统求迹之后得到的等效信道不是完全退极化的？当然是存在的，这完全取决于辅助系统的定义，信息可以在辅助系统中传递，而不经过完全退极化信道。
>
>   这个等效信道看上去性能不太好，尝试其他的选择，最理想的情形是确定最优化的目标，给出最优化算法，对特定的问题找到最优通信策略。将CNOT改为恒等信道，则式\eqref{eq:generalizedthreeswitch}的中间两式成为
>
$$
\begin{aligned}
& V_{\emptyset, k_1}^{ \rightarrow k_2}= \left\{\begin{array}{lll}
|0\rangle^{A_{k_2}^I} \langle   0 |^{A_{k_1}^O}   & \text { if } k_2=k_1+1 & (\bmod 3)  \\
|1\rangle^{A_{k_2}^I} \langle   1 |^{A_{k_1}^O}   & \text { if } k_2=k_1+2 & (\bmod 3)
\end{array}, \right. \\
& V_{ \{k_1 \}, k_2}^{ \rightarrow k_3}= \left\{\begin{array}{ll}
|0\rangle^{A_{k_3}^I}|0\rangle^{\alpha_3} \langle   0 |^{A_{k_2}^O}+\mid 1 \rangle^{A_{k_3}^I}|0\rangle^{\alpha_3} \langle   1 |^{A_{k_2}^O}   & \text { if } k_2=k_1+1 \quad(\bmod 3) \\
|0\rangle^{A_{k_3}^I}|1\rangle^{\alpha_3} \langle   0 |^{A_{k_2}^O}+\mid 1 \rangle^{A_{k_3}^I}|1\rangle^{\alpha_3} \langle   1 |^{A_{k_2}^O}   & \text { if } k_2=k_1+2 \quad(\bmod 3)
\end{array},  \right. \\
\end{aligned}
$$
>
>   eq-eq-truethreeswitch


### 例：动态相干控制的四体和N体开关

> [!example] 动态相干控制的$4$体开关I——推广原文的三体开关
> -
$$
\begin{aligned}
V_{\emptyset, \emptyset}^{\rightarrow k_1}&=\mathbb{I}^{P_t \rightarrow A_{k_1}^I} \otimes\left\langle\left. k_1\right|^{P_c},\right.\\
V_{\emptyset, k_1}^{\rightarrow k_2} &=\left(\mathbb{I}^{A_{k_2}^I} \otimes\left\langle\left.\sigma_{\left(k_1, k_2\right)}\right|^\alpha\right) \mathcal{V}_{k_1}^{(1)},\right.\\
V_{\left\{k_1\right\}, k_2}^{\rightarrow k_3}& =\mathcal{V}_{k_3}^{(3)}\left(\mathbb{I}^{A_{k_2}^O} \otimes\left|\sigma_{\left(k_1, k_2\right)}\right\rangle^{\alpha^{\prime}}\right),\\
V_{\{k_1, k_2\}, k_3} ^{\to k_4} &= \left( \mathcal{V}_{k_4}^{(4)} \left( \mathbb{I}^{A_{k_3}^O} \otimes \left| \theta(\{k_1, k_2\}, k_3) \right\rangle^{\alpha_4^{(1)\prime}} \right) \right) \otimes \mathbb{I}^{\alpha_3 \to \alpha_4^{(2)}}  \\
V_{\{k_1, k_2, k_3\}, k_4} ^{\to F} &= \mathbb{I}^{A_{k_4}^O \to F} \otimes \mathbb{I}^{\alpha_4^{(1)\prime} \alpha_4^{(2)} \to \alpha_F} \otimes\left| k_4 \right\rangle^{F_c}
\end{aligned}
$$
>   其中
>   $\mathcal{V}_{k_4}^{(4)}  : A_{k_3}^O \alpha_4^{(1)'} \to A_{k_4}^I \alpha_4^{(1)}$，$\mathcal{V}_{k_1}^{(1)}: \mathcal{H}^{A_{k_1}^O} \rightarrow \mathcal{H}^{A_{k_2}^I \alpha},\mathcal{V}_{k_3}^{\prime}: \mathcal{H}^{A_{k_2}^O \alpha^{\prime}} \rightarrow \mathcal{H}^{A_{k_3}^I \alpha_3}$是任意等距算符，$\alpha_4^{(1)}$是三维辅助系统




$$
\theta(\{k_1, k_2\}, k_3) =
\begin{cases}
0 & \text{if } (k_1, k_2), k_3 \text{ corresponds to } (1,2), 3; \ (1,2), 4; \ (1,3), 4; \ (3,4), 2 \\
1 & \text{if } (k_1, k_2), k_3 \text{ corresponds to } (1,3), 2; \ (2,4), 1; \ (3,4), 1; \ (2,3), 4 \\
2 & \text{if } (k_1, k_2), k_3 \text{ corresponds to } (2,3), 1; \ (1,4), 2; \ (1,4), 3; \ (2,4), 3
\end{cases}
$$
>
>   eq-eq-def_controltheta



>   而$\sigma$的定义与之前类似，
$$
\sigma(k_1, k_2) =
\begin{cases}
0 & \text{if } k_2 = k_1 + 1 \pmod{4} \\
1 & \text{if } k_2 = k_1 + 2 \pmod{4} \\
2 & \text{if } k_2 = k_1 + 3 \pmod{4}
\end{cases}
$$

前三个算符的等距性与3体开关类似，只检验$V_4$的等距性，
$$   \begin{align*}
  & \mathrm{tr}_{\alpha_4 A_4^I} \left( \left| \widetilde{V}_4 \right> \left< \widetilde{V}_4 \right| \right) \\
  &= \sum_{\substack{\{k_1, k_2\}, k_3 \\ \{q_1, q_2\}, q_3 \\ \{k_1, k_2, k_3\} = \{q_1, q_2, q_3\}}} |i\rangle\left< j \right| \mathrm{tr} \left({\mathcal{V}_{k_4}^{(4)}}  \left| i \right> \left< j \right| \otimes \left| \theta(\{k_1, k_2\}, k_3) \right> \left< \theta(\{q_1, q_2\}, q_3) \right| \mathcal{V}_{k_4}^{\prime \dagger}\right) \left| \{k_1, k_2\}, k_3 \right> \left< \{q_1, q_2\}, q_3 \right| \otimes |\mathbb{I}\rangle \left\langle \mathbb{I} \right| \\
  &= \sum \mathbb{I}_{A_3^o} \mathbb{I}_{\alpha_3} \left< \theta(\{k_1, k_2\}, k_3) \right| \left. \theta(\{q_1, q_2\}, q_3) \right> \left| \{k_1, k_2\}, k_3 \right> \left< \{q_1, q_2\}, q_3 \right| \\
  &= \sum \mathbb{I}_{A_3^o} \mathbb{I}_{\alpha_3} \delta_{k_3 q_3} \delta_{\{k_1, k_2\}, \{q_1, q_2\}} \left| \{k_1, k_2\}, k_3 \right> \left< \{q_1, q_2\}, q_3 \right| \\
  &= \mathbb{I}_{A_3^o} \mathbb{I}_{\alpha_3} \mathbb{I}_{C^3}
  \end{align*}$$


  
  引入新的辅助系统以及等距算符然后取得等距性的关键在于$\theta$的设计。在式\eqref{eq:def_controltheta}的每一行中，即
>   $\theta$的每一个取值中，只有 $\{k_1, k_2, k_3\} = \{q_1, q_2, q_3\}$的交叉项会出现，因此可以使得  $\left\langle \theta(\{k_1, k_2\}, k_3) \right| \theta(\{q_1, q_2\}, q_3) \rangle = \delta_{k_3q_3}\delta_{\{k_1,k_2\},\{q_1,q_2\}}$成立。$\theta$定义中的每一列可以任意交换，不影响等距性。


> [!example] 动态相干控制的$4$体开关II——简易版本(希望不会退回到平凡情形)
> -
$$
\begin{aligned}
V_{\emptyset, \emptyset}^{\rightarrow k_1}&=\mathbb{I}^{P_t \rightarrow A_{k_1}^I} \otimes\left\langle\left. k_1\right|^{P_c},\right.\\
V_{\emptyset, k_1}^{\rightarrow k_2} &= \mathcal{V}_{k_2}^{(2)}\\
V_{\left\{k_1\right\}, k_2}^{\rightarrow k_3}& =\mathcal{V}_{k_3}^{(3)}\left(\mathbb{I}^{A_{k_2}^O} \otimes\left|\sigma_{\left(k_1, k_2\right)}\right\rangle^{\alpha_3^{\prime}}\right),\\
V_{\{k_1, k_2\}, k_3} ^{\to k_4} &= \left( \mathcal{V}_{k_4}^{(4)} \left( \mathbb{I}^{A_{k_3}^O} \otimes \left| \theta(\{k_1, k_2\}, k_3) \right\rangle^{\alpha_4^{\prime}} \right) \right) \otimes \mathbb{I}^{\alpha_3 \to \beta_3}  \\
V_{\{k_1, k_2, k_3\}, k_4} ^{\to F} &= \mathbb{I}^{A_{k_4}^O \to F} \otimes \mathbb{I}^{\alpha_4^{(1) } \alpha_4^{(2)} \to \alpha_F} \otimes\left| k_4 \right\rangle^{F_c}
\end{aligned}
$$
> [!example] 动态相干控制的$N$体开关
> -
$$
\begin{aligned}
V_{\emptyset, \emptyset}^{\rightarrow k_1}&=\mathbb{I}^{P_t \rightarrow A_{k_1}^I} \otimes\left\langle\left. k_1\right|^{P_c},\right.\\
V_{\emptyset, k_1}^{\rightarrow k_2} &=\frac{1}{\sqrt{N-1}} \mathcal{V}_{k_2}^{(2)}\\
V_{ \{ k_1, \ldots, k_{n-1} \} , k_n }^{ \to k_{n+1} }&  = \left( \mathcal{V}_{k_{n+1}}^{ (n+1) } \left( \mathbb{I}^{A_{k_n}^o} \otimes |\sigma^{ (n-1) } \left( \{ k_1, \ldots, k_{n-1} \}, k_n \right)\rangle^{ \beta_{n+1}' }  \right) \right) \otimes \mathbb{I} ^{\alpha_n \to  \gamma_n},~n=2,\ldots ,N-1\\
V_{ \{ k_1, \ldots, k_{N-1} \} , k_N }^{\to {F}}&  = \mathbb{I}^{A_{k_N}^{O} \to F} \otimes \mathbb{I}^{\alpha_N \rightarrow F} \otimes |k_N\rangle ^{F_c}
\end{aligned}
$$
>   其中$\mathcal{V}_{k_{n }}^{ (n ) }: A_{k_{n }}^o\beta_{n }^\prime   \to A_{k_{n }}^I \beta_{n },~n=3,\ldots ,N$，辅助系统$\alpha_{n+1}=\beta_n\gamma_n \simeq \beta_n\alpha_n$，$\mathrm{dim}  \beta_n = n-1$。
>   辅助系统中的$\sigma^{(n-1)}$定义如下，定义集合$S_{\mathcal{K}_n}=\{(\{k_1,\ldots,k_{n-1}\},k_n )| \{k_1,\ldots,k_{n-1}\} \cup k_n = \mathcal{K}_n\}$，共有$\binom{N}{n}$个不同的集合$S_{\mathcal{K}_n}$，显然他们两两交集为空，满足$\{(\{k_1,\ldots,k_{n-1}\},k_n) \} = \bigcup_{\mathcal{K}_n} S_{\mathcal{K}_n}$，且对于任意的${\mathcal{K}_n}$，$|S_{\mathcal{K}_n}|=n$，即$|S_{\mathcal{K}_n}|$中有$n$个元素。$\sigma^{(n-1)}: \bigcup_{\mathcal{K}_n} S_{\mathcal{K}_n} \to \{1,\ldots,n\}$只需要满足$\sigma^{(n-1)}|_{S_{\mathcal{K}_n}}$是单射即可。这可以保证下面的保迹条件。
>
$$
\begin{aligned}
|\widetilde{V}_{n+1}\rangle
&= \sum_{k_{n-1}, k_n, k_{n+1}} \mathbb{I}_{A_{n+1}^o} \otimes \widetilde{V}_{n+1} |\mathbb{I}\rangle_{A_{n+1}^o A_{n+1}^o} \left| \sigma^{(n-1)} \left( \{k_1, \ldots, k_{n-1}\}, k_n \right) \right\rangle^{\beta_{n+1}'}
|\{k_1, \ldots, k_{n+1}\}, k_n\rangle^{C_{n-1}} |\{k_1, \ldots, k_n\}, k_{n+1}\rangle^{C_n} |\mathbb{I}\rangle^{\alpha_n \gamma_n} \\
\mathrm{tr} \left( |\widetilde{V}^{n+1}\rangle \langle \widetilde{V}^{n+1}| \right)  & = \mathbb{I}_{\alpha_n} \mathbb{I}_{A_{n+1}^o} \sum \langle \sigma^{(n-1)}( \{k_1, \ldots, k_{n-1}\}, k_n) | \sigma^{(n-1)} (\{q_1, \ldots, q_{n-1}\}, q_n )\rangle  |\{k_1, \ldots, k_{n-1}\}, k_n \rangle \langle q_1, \ldots, q_{n-1}, q_n| \\
& = \mathbb{I}_{\alpha_n} \mathbb{I}_{A_{n+1}^o} \mathbb{I}_{C_n}
\end{aligned}
$$
>
>   这个开关与$N$-SWICH的主要区别是辅助系统是逐个引入的，而不是预先确定的(还没搞清楚到底是不是同一个过程)。


## 系统的划分
这是一个非常深刻的问题，触及了QC-QC框架的核心。简而言之：

**在概念层面，每个时间步骤都有明确的控制和受控系统划分；但在物理交互层面，这种划分在通用的QC-QC线路中会变得模糊，因为两者会发生纠缠。只有在退化到更窄的类别（如经典控制或固定顺序）时，这种划分才会变得清晰且持久。**

以下是作者们在文章中如何阐述这一点的详细解析：

### 1. 概念上的划分：角色是明确的

在QC-QC的理论构建中，作者们**始终**从一个概念上清晰划分的系统开始。他们将整个系统所在的希尔伯特空间（Hilbert Space）构建为几个部分的张量积：
$$
\mathcal{H}_{\text{total}} = \mathcal{H}_{\text{target}} \otimes \mathcal{H}_{\text{control}} \otimes \mathcal{H}_{\text{ancilla}}
$$

*   **受控系统 (Target System)**：这是“数据”或“工作”量子比特，外部各方（$A_1, A_2, \dots$）的操作将直接作用于这个系统上。它的**角色**是承载计算任务。
*   **控制系统 (Control System)**：这是一个独立的量子系统，它的**角色**是作为“调度员”或“程序计数器”。它的状态，例如 `|Kₙ₋₁, kₙ⟩`，编码了关于因果顺序的信息（即哪些操作已经执行过，以及下一个该轮到谁）。
*   **辅助系统 (Ancilla System)**：这是一个可选的“内存”系统，用于在不同步骤之间传递量子信息，或者用于“净化”内部操作。

所以，从**系统构建和角色分工**的角度来看，控制系统和受控系统是两个完全不同的实体，它们的划分是明确的。

### 2. 物理交互中的模糊：内部操作是联合的

问题的关键在于**时间步骤之间**发生了什么。在两个外部操作（例如 $A_{k_n}$ 和 $A_{k_{n+1}}$）之间，会有一个**内部操作 $V_{n+1}$** 被施加。

根据作者的描述，这个内部操作 $V_{n+1}$ 是一个**联合操作（Joint Operation）**，它同时作用于上述的多个子系统上。其数学形式为：
$$
V_{n+1} : \mathcal{H}_{\text{target}} \otimes \mathcal{H}_{\text{control}} \otimes \mathcal{H}_{\text{ancilla}} \rightarrow \mathcal{H}'_{\text{target}} \otimes \mathcal{H}'_{\text{control}} \otimes \mathcal{H}'_{\text{ancilla}}
$$

这就是划分变得模糊的地方。作者们明确指出，这种联合作用是QC-QC实现其功能的关键，它会导致以下后果：

*   **信息从受控系统流向控制系统**：内部操作 $V_{n+1}$ 可以是一个受控操作，其作用方式**依赖于**受控系统（Target System）的状态。例如，如果受控系统处于状态 $|0\rangle$，则下一个操作是 $A_i$；如果处于状态 $|1\rangle$，则下一个操作是 $A_j$。这种条件性操作意味着受控系统（数据）的状态**影响**了控制系统（调度员）的决策，从而动态地改变了未来的因果顺序。
*   **产生纠缠（Entanglement）**：由于 $V_{n+1}$ 是一个联合操作，它可以（并且在很多有趣的例子中确实会）在**控制系统和受控系统之间产生纠缠**。一旦两者纠缠在一起，整个系统的状态就不能再写成 $\rho_{\text{control}} \otimes \rho_{\text{target}}$ 的形式。你无法再孤立地谈论控制系统的状态而不涉及受控系统，反之亦然。从物理的角度看，这时它们已经不是两个独立的实体了，**清晰的划分在这一刻消失了**。

**作者的观点**：作者们通过这种数学形式（联合操作）精确地表达了这一点。他们并没有说“划分消失了”，而是通过定义作用于联合希尔伯特空间上的操作，来表明这两个系统是**相互作用**和**相干耦合**的。这种耦合正是“量子控制”的精髓所在，也是QC-QC能够实现因果顺序叠加和干涉的根本原因。

### 3. 在更窄类别中划分的恢复

当QC-QC退化到更窄的类别时，这种模糊性会逐渐消失，划分也随之变得清晰。

*   **退化到 QC-CC (经典控制)**：
    *   **作者的描述**：在这种情况下，控制系统被限制为**经典的**。它的状态只能是像 `[(k₁, ..., kₙ)]` 这样的经典概率分布。
    *   **后果**：经典系统无法与量子系统产生纠缠。因此，内部操作虽然仍然可以读取控制系统的经典信息来决定如何操作受控（量子）系统，但受控系统的量子状态**不能反过来相干地影响**控制系统的状态。信息流是单向的（从经典控制到量子目标）。因此，在QC-CC中，控制和受控系统的**划分比QC-QC更清晰**，它们之间只有经典关联，没有量子纠缠。

*   **退化到 QC-FO (固定顺序)**：
    *   **作者的描述**：这是最受限的情况。控制系统的演化路径是**完全预设和确定的**。
    *   **后果**：内部操作 $V_n$ 的功能被极度简化。它完全**不需要**从受控系统获取任何信息来做决策。它的作用与受控系统的状态**完全解耦（decoupled）**。它只是机械地将受控系统从一个端口路由到下一个端口，同时更新一下经典的路径标签。在这种情况下，控制系统和受控系统在**整个过程中的每一步都保持着完全清晰的划分**，它们之间没有任何有意义的相互作用。

### 总结

| 电路类别 | 在内部操作期间，控制和受控系统的划分是否清晰？ | 原因（根据作者的描述） |
| :--- | :--- | :--- |
| **QC-QC (通用)** | **不清晰/模糊** | 内部操作是作用于联合空间的**联合操作**，可以产生**纠缠**，信息可以在两者之间双向流动。 |
| **QC-CC (经典控制)** | **比较清晰** | 控制系统是经典的，**不能产生纠缠**。信息只能从经典控制流向量子受控系统。 |
| **QC-FO (固定顺序)** | **完全清晰** | 控制系统的演化是预设的，与受控系统的状态**完全解耦**。内部操作仅起路由作用。 |

因此，作者们通过一个统一的框架，展示了从一个控制和受控系统完全分离且无交互的简单模型（QC-FO），如何通过逐步引入更复杂的相互作用（QC-CC的经典条件作用，以及QC-QC的量子相干联合作用），最终达到一个两者深度融合、界限模糊的通用模型。这种“模糊化”恰恰是开启不定因果效应和相关量子优势的关键。

## 带噪声的QC-QC
控制系统遭受噪声会怎样？下面是粗略的可能错误的分析。
这是一个非常好的问题，它触及了量子相干性在因果顺序控制中的核心作用。

总的来说，**控制系统带噪声的QC-QC会退化为更特殊的情形，最典型的就是退化为一个QC-CC（具有经典因果顺序控制的量子电路），或者是一个QC-CC与一个（相干性减弱的）QC-QC的混合体。它不会离开QC-QC的范畴，因为带有噪声的电路本身仍然是一个物理上可实现的、遵循QC-QC构造规则的电路。**

下面我们来详细分析作者的框架是如何导向这个结论的。

### 核心机制：退相干 (Decoherence)

QC-QC 与 QC-CC 最根本的区别在于**控制系统**的性质：
*   **QC-QC**：控制系统是**量子**的，能够维持不同因果路径的**相干叠加 (Coherent Superposition)**。
*   **QC-CC**：控制系统是**经典**的，只能表示不同因果路径的**经典概率混合 (Classical Mixture)**。

噪声，尤其是退相干类型的噪声（如相位阻尼通道），其主要作用就是破坏量子相干性。当噪声作用于QC-QC的控制系统上时，它会系统性地将不同因果路径之间的量子相位关系抹去。

一个处于叠加态的控制系统，其状态可以抽象地写成：
$$
|\psi\rangle_{\text{control}} = \alpha |\text{路径 1}\rangle + \beta |\text{路径 2}\rangle
$$
经过一个完全的退相干过程后，这个纯态会变成一个混合态：
$$
\rho_{\text{control}} = |\alpha|^2 |\text{路径 1}\rangle\langle\text{路径 1}| + |\beta|^2 |\text{路径 2}\rangle\langle\text{路径 2}|
$$
这个混合态在数学上**等价于**一个经典概率分布：以概率 $|\alpha|^2$ 选择路径1，以概率 $|\beta|^2$ 选择路径2。这正是 QC-CC 的核心特征。

### 以量子开关为例

我们可以用最典型的QC-QC例子——量子开关——来说明这个过程。

1.  **理想的（无噪声）量子开关 (QC-QC)**：
    *   控制量子比特被置于叠加态 $|+\rangle = \frac{1}{\sqrt{2}}(|0\rangle + |1\rangle)$。
    *   电路相干地执行：如果控制是 $|0\rangle$，则顺序为 $(A, B)$；如果控制是 $|1\rangle$，则顺序为 $(B, A)$。
    *   最终，整个过程实现了两个因果顺序的**相干叠加**。其过程矩阵是秩为1的，表明了纯态和相干性。

2.  **带噪声的量子开关**：
    *   假设在控制系统用于决定第一个操作之后，但在所有操作完成、信息被重新组合之前，控制量子比特经历了一个**完全的相位阻尼（dephasing）**。
    *   这个噪声通道的作用是将控制量子比特的非对角线元素（相干项）置零。
    *   原本的相干叠加 `(顺序 A,B) + (顺序 B,A)` 就因为控制系统的退相干而变成了**概率混合**：`50% 的概率是 (A, B) 顺序，50% 的概率是 (B, A) 顺序`。
    *   这个最终的过程**正是经典开关（Classical Switch）**，它是QC-CC的一个典型例子。

### 在形式化框架中的解释

作者们在论文中建立的数学框架也支持这个结论。

*   **噪声作为量子通道**：噪声本身可以被数学地描述为一个量子通道，即一个完备正定保迹（CPTP）映射。
*   **电路的组合**：一个带有噪声的QC-QC可以被看作是一个理想的QC-QC与一个作用于其控制系统子空间上的噪声通道的**组合**。
*   **仍然是合法的QC-QC**：QC-QC的定义是**构造性**的，即它是由一系列合法的内部操作 $V_n$ 组合而成的。将一个噪声通道作用于控制系统，无非是在这些内部操作之间或之后增加了一个额外的、合法的物理过程。整个组合起来的电路仍然是一个物理上可以构建的电路，因此其过程矩阵**必然满足QC-QC的表征（Proposition 7）**。
*   **满足更强的约束**：然而，由于噪声破坏了相干性，这个新的、带有噪声的过程矩阵现在会**额外满足**更严格的约束。例如，如果噪声是完全的退相干，那么其过程矩阵不仅满足QC-QC的分解条件，还将**同时满足QC-CC的分解条件（见您在上一个问题中提到的定理的经典版本）**。因为QC-CC是QC-QC的一个真子集，所以这个过程实际上是退化到了这个更窄的类别中。

### 总结

| 情况 | 控制系统状态 | 因果顺序 | 所属类别 |
| :--- | :--- | :--- | :--- |
| **理想QC-QC** | 纯态，相干叠加 | 量子叠加 | QC-QC \ QC-CC (通常) |
| **部分噪声的QC-QC** | 混合态，相干性减弱 | 部分相干叠加，部分概率混合 | 仍然是 QC-QC (但“量子性”减弱) |
| **完全退相干的QC-QC** | 完全混合的对角态 | 经典概率混合 | 退化为 **QC-CC** (但技术上仍是QC-QC的一个特例) |

**作者的观点总结**：
作者们构建的层级结构（QC-FO ⊂ QC-CC ⊂ QC-QC）本身就暗示了这一点。从一个更广义的类别退化到一个更窄的类别，通常对应于系统中“量子资源”（如相干性、纠缠）的减少或丧失。噪声作为一个物理上不可避免的退相干过程，自然地扮演了这个“降级”的角色，它将一个具有相干叠加能力的量子控制过程，变成了一个只能进行经典概率选择的经典控制过程。

## QC-QC的潜在应用
### K-Unitary Equivalence Determination
[[wechs2021QuantumCircuitsClassical\|wechs2021QuantumCircuitsClassical]] Application部分
当然。**K-幺正等价性确定** (K-Unitary Equivalence Determination) 是一个量子信息处理任务，可以被看作是一个精巧的“量子匹配游戏”。

这个任务的核心是：在一个信息受限的环境下，辨别出一个未知的量子操作。

下面我们来分解这个任务的各个组成部分：

### 1. 任务的设置（你拥有的资源）

想象你面前有一个工作台，上面有以下物品：

*   **K 个参考黑箱 (Reference Boxes)**：这些是 $K$ 个量子设备，标记为 $U_1, U_2, \dots, U_K$。你知道每一个黑箱都会执行一个幺正操作（Unitary Operation），但你可能不知道这些操作具体是什么。它们是你的“参考样品”或“嫌疑人名单”。
*   **1 个目标黑箱 (Target Box)**：这是另一个量子设备，标记为 $U_T$。
*   **一个承诺 (The Promise)**：你得到了一个绝对可靠的承诺：目标黑箱 $U_T$ 所执行的操作**完全等同于** K 个参考黑箱中的**某一个**。也就是说，存在一个未知的索引 $k$（在 1 到 K 之间），使得 $U_T = U_k$。每一种可能性（$U_T=U_1$, $U_T=U_2$, ...）的概率都是均等的，即 $1/K$。

### 2. 任务的目标（你要做什么）

你的目标是设计一个量子电路（或协议），这个电路将使用所有这 $K+1$ 个黑箱，并最终输出一个**经典数字**，这个数字就是你对未知索引 $k$ 的**猜测**。

任务成功的衡量标准是**最大化你猜对的平均概率**。

### 3. 关键的约束（游戏的规则）

这是使这个任务变得非凡且困难的核心规则：

**每一个黑箱（包括 K 个参考箱和 1 个目标箱）都只能被使用一次。**

这个“一次性使用”的约束极大地限制了你的策略。你不能这样做：
*   **重复测试**：你不能先用 $U_T$ 操作一个量子比特，看看结果，然后再用 $U_1$ 操作另一个相同的量子比特，比较结果。因为这需要多次使用 $U_T$ 或需要多个初始量子比特的副本。
*   **简单的逐一比较**：你不能设计一个简单的流程，比如用一个“交换测试”（Swap Test）来比较 $U_T$ 和 $U_1$，然后再用另一个交换测试来比较 $U_T$ 和 $U_2$。因为一旦你在第一个测试中使用了 $U_T$，你就不能在第二个测试中再次使用它。

你必须设计一个**单一的、整体的量子过程**，在这个过程中，所有 $K+1$ 个操作被巧妙地编排在一起，以在一次运行中提取出所需的信息。

### 4. 为什么这个任务与不定因果序（QC-QC）有关？

这个任务的精妙之处在于它揭示了不同因果结构处理信息的能力差异。

*   **固定顺序策略 (QC-FO/QC-CC)**：
    如果你必须按照一个固定的、或经典的动态顺序来使用这些黑箱，你的策略会受到很大限制。例如，你可能会选择这样一个顺序：$(U_1, U_2, \dots, U_T, \dots, U_K)$。信息是线性流动的。你可以利用先前的操作结果来准备后续操作的输入态，但这本质上是一种串行处理。你很难在一个单一的流程中实现对 $U_T$ 与**所有** $U_k$ 的“公平”或“同步”比较。

*   **不定因果序策略 (QC-QC)**：
    QC-QC（如量子开关的推广）允许你将不同的因果顺序置于**量子叠加**中。你不是在执行一个固定的顺序，而是在相干地执行“先用 $U_1$ 再用 $U_T$”**和**“先用 $U_2$ 再用 $U_T$”等等所有可能性的叠加。

    **直观理解**：这就像是创建了一个复杂的量子干涉仪。目标黑箱 $U_T$ 在这个干涉仪中被同时与**所有**参考黑箱 $U_k$ 进行“量子比较”。
    *   当 $U_T$ 恰好等于某个 $U_k$ 时，对应于这个匹配的那个“因果路径”会与其他路径发生特定的**相长或相消干涉**。
    *   通过在最后进行一次全局测量，你可以从干涉的结果中以更高的概率推断出是哪条路径发生了这种特殊的干涉，从而猜出 $k$ 的值。

**文章的结论**：对于 $K=2$ 的情况，最好的经典动态策略（QC-CC）和量子策略（QC-QC）的成功概率是相同的。然而，当问题变得更复杂，即 **$K=3$** 时，QC-QC策略的最高成功概率就**严格超过**了任何QC-CC策略。这表明，当需要在一个单一过程中协调和比较多个操作时，不定因果序所提供的“量子并行性”成为了一种实实在在的计算资源。