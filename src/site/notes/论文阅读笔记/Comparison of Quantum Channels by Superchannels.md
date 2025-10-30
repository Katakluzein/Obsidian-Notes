---
{"dg-publish":true,"permalink":"/论文阅读笔记/Comparison of Quantum Channels by Superchannels/","tags":["量子信息","开放量子系统","不定因果与因果结构"]}
---

# 论文信息和标签
- **标题**: Comparison of Quantum Channels by Superchannels (通过超信道比较量子信道)
- **作者**: Gilad Gour
- **年份**: 2019
- **期刊/会议**: IEEE Transactions on Information Theory
- **链接或 DOI**: 10.1109/TIT.2019.2907989
- **关键词**: 量子信道, 超信道, 量子纠缠, 条件最小熵, 量子马尔可夫链, 半正定规划, 资源理论

# 内容

## 领域
- 量子信息论
- 量子资源理论
- 量子香农理论
- 数学物理

## 摘要
我们将**条件最小熵**的定义从二体量子态推广到二体量子信道。我们证明了条件最小熵的许多性质都延续到了这个扩展版本上，包括当其中一个子系统是经典系统时，它具有一个作为猜测概率的操作性解释。然后，我们展示了扩展的条件最小熵可以用来完全刻画两个二体量子信道何时可以通过一个作用于其中一个子系统上的**超信道**（superchannel，也称为supermap或comb）相互关联。这种关系是一种预序关系，它将“**量子主序化**”（quantum majorization）的定义从二体态推广到二体信道，并且也可以用半正定规划来刻画。作为一个特例，我们的刻画为**一组量子信道何时能通过单个超信道与另一组信道相关联提供了充要条件**（==给定初始和变换后的信道，然后问是否存在2-comb实现这个变换==，应该不需要一族连续的变换吧，如果要求连续的话可能会更难实现。更高阶的版本是给定两个过程矩阵，然后问是否存在一个高阶量子变换联系他们。如何理解这个问题？）。我们讨论了我们的结果在信道辨别和量子过程资源理论中的应用。在此过程中，我们研究了信道散度、量子信道的熵函数，以及超信道的噪声模型，包括随机酉超信道和双随机超信道。对于后者，我们给出了一个物理意义，即它们是“完全保熵”的。

## 总体思路
- **核心问题**: 本文旨在解决量子信息论中一个根本性的问题：我们如何系统地比较两个量子过程（即**量子信道**）的“能力”？更精确地说，给定两组量子信道 $\{\Phi_j\}$ 和 $\{\Psi_j\}$，是否存在一个单一的、物理上允许的操作 $\Theta$（称为**超信道**），能够将每一组中的 $\Phi_j$ 都转换为对应的 $\Psi_j$？即对所有的 $j$ 都有 $\Psi_j = \Theta(\Phi_j)$。这本质上是在所有量子信道上建立一个**预序关系**，类似于数学中“大于等于”的概念，让我们能说一个信道比另一个“更强大”或“更有序”。

- **思路演进**:
    1.  **类比与推广**: 这个问题的灵感直接来自于对量子态的比较。对于量子态，已经存在一个成熟的理论框架叫做“**量子主序化**”。该理论回答了何时一个量子态可以通过某个量子操作（信道）转化为另一个量子态。近期的研究发现，这种转化可能性可以被一整套基于**条件最小熵**的无穷多个不等式完全刻画。本文的核心思想就是将这一整套成功的框架从静态的“态”推广到动态的“信道”。
    2.  **引入正确的工具**: 对态的操作是**信道**，那么对信道的操作是什么？作者使用了**超信道**（superchannel）这一概念。一个超信道可以被看作是一个“量子电路板”，上面有开放的输入和输出端口，你可以将一个待处理的量子信道“插入”进去，从而得到一个新的量子信道。这为“信道之间的转换”提供了严谨的物理和数学描述。
    3.  **定义核心度量**: 作者意识到，要刻画信道间的转换，必须有一个合适的度量标准。受到量子主序化理论的启发，他们将**条件最小熵** $H_{\min}(A|B)_\rho$ 从描述二体量子态 $\rho_{AB}$ 的不确定性，推广到了描述二体量子信道 $\Omega^{AB}$ 的不确定性，定义了“**扩展的条件最小熵**” $H_{\min}^{\text{ext}}(B|A)_\Omega$。这个新的量被证明满足一系列理想的熵的性质，例如在特定噪声（双随机超信道）下是单调的。
    4.  **建立核心定理**: 本文的中心结论（定理7）是，一个二体信道 $\Phi^{RA}$ 可以通过作用在系统A上的超信道转换为另一个信道 $\Psi^{RB}$，**当且仅当**，对于**所有**可能的“测试”信道 $\Lambda^{XYB}$，通过扩展的条件最小熵定义的某个量满足一个不等式。这表明，正如态的主序化一样，信道的主序化也可以被一整套无穷多个熵不等式完全刻画。
    5.  **实用性与应用**: 尽管这涉及无穷多个条件，作者证明了这个问题等价于一个**半正定规划**（SDP）问题。这意味着在实践中，我们总能通过高效的数值算法来判断一个信道是否可以模拟另一个信道。作者进一步将此框架应用于**量子热力学**的资源理论等领域，展示了其广泛的应用潜力。

# 技术

## 关键物理概念
- **量子信道 (Quantum Channel)**: 描述量子系统开放演化的数学对象，通常表示为一个完备正（CP）且保迹（TP）的线性映射 $\Phi: \mathcal{B}(\mathcal{H}_A) \to \mathcal{B}(\mathcal{H}_B)$，其中 $\mathcal{B}(\mathcal{H})$ 是希尔伯特空间 $\mathcal{H}$ 上的有界算子空间。它代表了从输入系统A到输出系统B的任何物理上可能的动力学过程。
- **超信道 (Superchannel)**: 一个对量子信道进行操作的物理过程。数学上，它是一个将CPTP映射集映射到CPTP映射集的线性映射 $\Theta: \mathcal{L}(\mathcal{H}_A \to \mathcal{H}_{A'}) \to \mathcal{L}(\mathcal{H}_B \to \mathcal{H}_{B'})$，并且它本身也满足更高阶的完备正性和保迹性条件。它可以被物理地实现为一个包含前处理和后处理的量子网络（如图1所示）。
- **量子主序化 (Quantum Majorization)**: 最初为量子态定义的一个预序关系。如果态 $\rho$ 可以通过某个量子信道 $\Phi$ 转换为态 $\sigma$（即 $\sigma = \Phi(\rho)$），则称 $\rho$ 主序化 $\sigma$。本文将这个概念从态推广到信道，如果信道 $\Phi$ 可以通过超信道 $\Theta$ 转换为信道 $\Psi$（即 $\Psi = \Theta(\Phi)$），则称 $\Phi$ 主序化 $\Psi$。
	- [[量子区分和排除任务\|量子区分和排除任务]] 这篇文章给出了两对量子信道能够建立pre-order的充要条件
- **条件最小熵 (Conditional Min-Entropy)**: 对于一个二体量子态 $\rho_{AB}$，其条件最小熵 $H_{\min}(A|B)_\rho$ 量化了在拥有对系统B的量子信息后，对系统A的不确定性的最小值。它与猜测概率密切相关，是单次（single-shot）量子信息论中的核心熵量。其定义为 $H_{\min}(A|B)_\rho = -\log \min_{\sigma_B} \text{Tr}[\sigma_B]$，约束条件为 $I_A \otimes \sigma_B \ge \rho_{AB}$。
- **扩展的条件最小熵 (Extended Conditional Min-Entropy)**: 本文的核心技术贡献。作者将条件最小熵的定义从态推广到二体量子信道 $\Omega^{AB}$。其定义（定义4）是一个半正定规划问题，量化了关于信道B的不确定性，条件是拥有对信道A的访问权。这个量被证明是刻画信道间量子主序化的关键。

## 主要数学记号及其定义
好的，这是一个更详尽、更结构化的重要符号列表，涵盖了论文中的关键定义和技术细节。

### 1. 基本对象 (Hilbert空间、算子空间、态)

-   $\mathcal{H}_A, \mathcal{H}_B$: 分别是系统 A, B 的有限维希尔伯特空间。
-   $\mathcal{B}(\mathcal{H})$: 希尔伯特空间 $\mathcal{H}$ 上所有有界线性算子的空间。
-   $\mathcal{B}_h(\mathcal{H})$: $\mathcal{B}(\mathcal{H})$ 中所有**厄米算子**的子空间。
-   $\mathcal{B}_+(\mathcal{H})$: $\mathcal{B}(\mathcal{H})$ 中所有**正半定算子**的子集。
-   $\mathcal{D}(\mathcal{H})$: $\mathcal{H}$ 上所有**密度算子**（迹为1的正半定算子）的子集。
-   $A_0, A_1$: 分别代表一个量子信道的**输入**和**输出**系统。联合系统记为 $A = A_0A_1$。
-   $d_A$: 系统A的希尔伯特空间维度, 即 $d_A = \dim(\mathcal{H}_A)$。
-   $|\Phi^+\rangle_{A\tilde{A}}$: 系统 A 与其副本 $\tilde{A}$ 之间的（未归一化）**最大纠缠态**，定义为 $\sum_{i=1}^{d_A} |i\rangle_A \otimes |i\rangle_{\tilde{A}}$。这是定义Choi矩阵的基础。
-   $u^A$: 系统A上的**最大混合态**，即 $u^A = I^A / d_A$。

### 2. 量子信道与超信道 (核心操作)
#### 信道
-   $\Phi^A: \mathcal{B}(\mathcal{H}_{A_0}) \to \mathcal{B}(\mathcal{H}_{A_1})$: 一个从输入系统 $A_0$ 到输出系统 $A_1$ 的**量子信道**，即一个CPTP映射。
-   $\mathcal{L}^A$: 从 $\mathcal{B}(\mathcal{H}_{A_0})$ 到 $\mathcal{B}(\mathcal{H}_{A_1})$ 的所有线性映射构成的空间。
-   $\mathcal{C}^A$: $\mathcal{L}^A$ 中所有量子信道（CPTP映射）的凸集。因为是Channel，所以叫C
-   $J_\Phi^A \in \mathcal{B}(\mathcal{H}_{A_0} \otimes \mathcal{H}_{A_1})$: 量子信道 $\Phi^A$ 的**Choi矩阵**，定义为 $J_\Phi^A = (\text{id}_{\tilde{A}_0} \otimes \Phi^A)(|\Phi^+\rangle\langle\Phi^+|_{\tilde{A}_0A_0})$。
#### 超信道
-   $\Theta: \mathcal{L}^A \to \mathcal{L}^B$: 一个**超信道**，将作用于A系统的信道映射为作用于B系统的信道。
-   $\mathbb{L}^{AB}=\{\Theta: \mathcal{L}^A \to \mathcal{L}^B\}$ 是超信道的集合
-   $\Theta^*: \mathcal{L}^B \to \mathcal{L}^A$: 超信道 $\Theta$ 的**对偶映射** (dual map)。
-   $J_\Theta^{AB} \in \mathcal{B}(\mathcal{H}_A \otimes \mathcal{H}_B)$: 超信道 $\Theta$ 的 Choi 矩阵。
-   $\Gamma_{\text{pre}}$ 和 $\Gamma_{\text{post}}$: 分别代表实现一个超信道所需的**前处理**和**后处理**量子信道 (见图1)。
-   $\mathcal{N}^A$: **均匀信道** (uniform channel)，也叫完全去极化信道，它将任何输入态都映射到最大混合态 $u^{A_1}$。
-   $\mathcal{E}_{a_0a_1}^{A_0 \to A_1}$: 这是为线性映射空间 $L^A$ 构建的一套**规范正交基** (canonical orthonormal basis)。
    *   **定义**: $\mathcal{E}_{a_0a_1}^{A_0 \to A_1}(\rho) \equiv \text{Tr}[X_{a_0}^* \rho] Y_{a_1}$
    *   **解释**:
        *   这里的 $\{X_{a_0}\}$ 和 $\{Y_{a_1}\}$ 分别是输入算子空间 $\mathcal{B}(\mathcal{H}_{A_0})$ 和输出算子空间 $\mathcal{B}(\mathcal{H}_{A_1})$ 的任意一组正交基（例如，由矩阵单位 $|i\rangle\langle j|$ 构成）。
        *   这个基映射 $\mathcal{E}$ 的作用是：对于任何输入的算子 $\rho$，它首先计算 $\rho$ 在输入基底 $X_{a_0}$ 上的投影（即内积 $\text{Tr}[X_{a_0}^* \rho]$），这是一个标量。然后，它用这个标量去缩放输出基底 $Y_{a_1}$。
        *   通过遍历输入和输出空间的所有基底组合（由复合索引 $a_0a_1$ 标记），这套 $\mathcal{E}_{a_0a_1}^{A_0 \to A_1}$ 构成了能够表示**任何**从 $\mathcal{B}(\mathcal{H}_{A_0})$ 到 $\mathcal{B}(\mathcal{H}_{A_1})$ 的线性映射的完备基底。就像任何向量都可以表示为基向量的线性组合一样，任何量子信道 $\Phi$ 也可以表示为这些基映射 $\mathcal{E}$ 的线性组合。
-   $\mathcal{J}_\Theta^{AB}$: 这是**超信道** $\Theta$ 的**Choi矩阵**。
    *   **定义**: $\mathcal{J}_\Theta^{AB} \equiv \sum_{a_0,a_1} J_{\mathcal{E}_{a_0a_1}}^{A} \otimes J_{\Theta[\mathcal{E}_{a_0a_1}]}^{B}$
    *   **解释**:
        *   这个定义是标准Choi矩阵概念向更高层映射（即超信道）的推广。它旨在将超信道 $\Theta$ 的完整信息编码到一个单一的、静态的矩阵 $\mathcal{J}_\Theta^{AB}$ 中。
        *   它的构造方法是：
            1.  取线性映射空间 $L^A$ (超信道的输入空间) 的一套完备正交基 $\{\mathcal{E}_{a_0a_1}^A\}$。
            2.  对于基底中的**每一个**基映射 $\mathcal{E}_{a_0a_1}^A$，我们计算它的标准Choi矩阵 $J_{\mathcal{E}_{a_0a_1}}^{A}$。
            3.  同时，我们将这个基映射 $\mathcal{E}_{a_0a_1}^A$ 输入到超信道 $\Theta$ 中，得到一个输出的线性映射 $\Theta[\mathcal{E}_{a_0a_1}^A]$。
            4.  我们也计算这个输出映射的Choi矩阵 $J_{\Theta[\mathcal{E}_{a_0a_1}]}^{B}$。
            5.  我们将输入的基映射的Choi矩阵与对应的输出映射的Choi矩阵做**张量积** $J_{\mathcal{E}_{a_0a_1}}^{A} \otimes J_{\Theta[\mathcal{E}_{a_0a_1}]}^{B}$。
            6.  最后，将所有基映射产生的张量积项**求和**，就得到了超信道 $\Theta$ 自己的Choi矩阵 $\mathcal{J}_\Theta^{AB}$。
        *   这个矩阵 $\mathcal{J}_\Theta^{AB}$ 作用在一个更大的希尔伯特空间 $\mathcal{H}_A \otimes \mathcal{H}_B = (\mathcal{H}_{A_0} \otimes \mathcal{H}_{A_1}) \otimes (\mathcal{H}_{B_0} \otimes \mathcal{H}_{B_1})$ 上。正如一个信道是完备正的（CP）当且仅当它的Choi矩阵 $J$ 是正半定的，一个超信道是物理上可实现的，也当且仅当它的Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 满足特定的正半定性和边际条件（如论文中的定理1所述）。
-   $\Lambda_\Theta^{A_0B_0 \to A_1B_1}$: 这是一个与**超信道** $\Theta$ 唯一对应的**线性映射**。
    *   **类型**: 这是一个作用于算子（或量子态）的普通线性映射，其输入空间为 $\mathcal{B}(\mathcal{H}_{A_0} \otimes \mathcal{H}_{B_0})$，输出空间为 $\mathcal{B}(\mathcal{H}_{A_1} \otimes \mathcal{H}_{B_1})$。
    *   **核心思想**: 超信道 $\Theta$ 是一个高阶的、从“映射空间”到“映射空间”的操作，这在数学上比较抽象。$\Lambda_\Theta$ 的引入，是为了将这个抽象的高阶操作“降维”，用一个作用于普通复合系统量子态的、更直观的线性映射来等价地描述它。可以说，$\Lambda_\Theta$ 是超信道 $\Theta$ 在标准量子态空间中的“投影”或“化身”。
    *   **定义关系 (via Formula 12)**: $\Lambda_\Theta$ 被**定义**为这样一个唯一的线性映射，它的标准Choi矩阵恰好就是超信道 $\Theta$ 的Choi矩阵 $\mathcal{J}_\Theta^{AB}$。
        $$
        \mathcal{J}_\Theta^{AB} = (\text{id}_{\tilde{A}_0\tilde{B}_0} \otimes \Lambda_\Theta^{A_0B_0 \to A_1B_1})(|\Phi^+\rangle\langle\Phi^+|_{\tilde{A}_0A_0} \otimes |\Phi^+\rangle\langle\Phi^+|_{\tilde{B}_0B_0})
        $$
        这个公式是连接抽象超信道 $\Theta$ 和具体线性映射 $\Lambda_\Theta$ 的桥梁。
    *   **显式构造 (via Formula after (13))**: 除了通过Choi矩阵的定义关系，我们还可以直接构造出 $\Lambda_\Theta$。它是通过对超信道 $\Theta$ 的输入空间基底进行操作来构建的：
        $$
        \Lambda_\Theta^{A_0B_0 \to A_1B_1} = \sum_{a_0,a_1} \mathcal{E}_{a_0a_1}^{A_0 \to A_1} \otimes \Theta[\mathcal{E}_{a_0a_1}^{A_0 \to A_1}]
        $$
        这个表达式的含义是，$\Lambda_\Theta$ 在复合系统 $A_0B_0$ 上的作用，可以分解为：在 $A_0$ 子系统上执行一系列基底操作 $\mathcal{E}$，同时在 $B_0$ 子系统上执行被超信道 $\Theta$ 变换后的对应基底操作 $\Theta[\mathcal{E}]$。注意两个两个张量积因子都是映射，且分别是$\mathcal{E}_{a_0a_1}^{A_0 \to A_1}: \mathcal{B}(\mathcal{H}_{A_0})\to \mathcal{B}( \mathcal{H}_{A_1})$ 与 $\Theta[\mathcal{E}_{a_0a_1}^{A_0 \to A_1}]:\mathcal{B}(\mathcal{H}_{B_0})\to \mathcal{B}( \mathcal{H}_{B_1})$，所以等号左右两边都是映射。

-   $\Upsilon^{A\tilde{A}}$: 这是一个特殊的、从复合系统 $A_0\tilde{A}_0$ 映射到 $A_1\tilde{A}_1$ 的**完备正(CP)映射**。
    *   **核心概念 (The Analogy)**: 理解 $\Upsilon^{A\tilde{A}}$ 最好的方式是论文中给出的类比——它是**最大纠缠态 $|\Phi^+\rangle$ 在量子信道层面的模拟** (the CP map analog of the maximally entangled state)。
        *   在**态**的层面, 最大纠缠态 $|\Phi^+\rangle_{A\tilde{A}}$ 是系统 A 和 $\tilde{A}$ 之间完美关联的资源。
        *   在**信道**的层面, $\Upsilon^{A\tilde{A}}$ 扮演了同样的角色：它是一个在信道“槽位” A 和 $\tilde{A}$ 之间建立完美关联的资源映射。因此，可以把它理解为一种**身份超信道**或**信道关联器**。
    *   **形式化定义**:
        $$
        \Upsilon^{A\tilde{A}} \equiv \sum_{a_0,a_1} \mathcal{E}_{a_0a_1}^{A_0 \to A_1} \otimes \mathcal{E}_{a_0a_1}^{\tilde{A}_0 \to \tilde{A}_1}
        $$
        这个定义说明，$\Upsilon^{A\tilde{A}}$ 的作用是将输入系统 $A_0\tilde{A}_0$ 的基底分量，完全相同地复制到输出系统 $A_1\tilde{A}_1$ 上，从而在输入和输出之间，以及在 A 和 $\tilde{A}$ 之间都建立了完美的关联。
    *   **作用方式 (Action)**:
        $$
        \Upsilon^{A\tilde{A}}(\rho^{A_0\tilde{A}_0}) = \text{Tr}[\phi^+_{A_0\tilde{A}_0} \rho^{A_0\tilde{A}_0}] \phi^+_{A_1\tilde{A}_1}
        $$
        这个公式揭示了它的操作本质：它实际上是一个**量子隐形传态**映射。它接收一个输入态 $\rho^{A_0\tilde{A}_0}$，对其进行一次贝尔基测量（由与最大纠缠态的迹运算 $\text{Tr}[\phi^+ \rho]$ 体现），然后根据测量结果在输出端制备一个最大纠缠态 $\phi^+_{A_1\tilde{A}_1}$。
    *   **在文中的作用**:
        $\Upsilon^{A\tilde{A}}$ 是一个至关重要的数学工具，其主要作用是建立抽象的**超信道** $\Theta$ 和其等价的**线性映射** $\Lambda_\Theta$ 之间的构造性联系。
        $$
        \Lambda_\Theta^{A\tilde{B}} = (I^A \otimes \Theta)[\Upsilon^{A\tilde{A}}]
        $$
        这个公式可以这样理解：
        1.  我们从一个完美的“信道关联器” $\Upsilon^{A\tilde{A}}$ 开始，它在 A 和 $\tilde{A}$ 两个“槽位”之间建立了身份关联。
        2.  然后，我们让超信道 $\Theta$ 只作用在第二个槽位 $\tilde{A}$ 上（将其变为系统 B）。
        3.  最终得到的这个新的、包含了变换信息的关联映射，就是 $\Lambda_\Theta^{A\tilde{B}}$。

		**总结**: $\Upsilon^{A\tilde{A}}$ 是一个基础性的数学对象，它将最大纠缠态的核心性质（完美关联、作为隐形传态的资源）提升到了量子信道和超信道的层面。在本文中，它充当了一个“脚手架”，使得从抽象的超信道 $\Theta$ 到具体的线性映射 $\Lambda_\Theta$ 的构造变得严谨和清晰。

		**总结**: $\Theta$ 和 $\Lambda_\Theta$ 是描述同一个物理过程的两种等价数学形式。$\Theta$ 从“操作作用于操作”的抽象层面描述，而 $\Lambda_\Theta$ 则从“一个整体操作作用于一个复合系统的态”的更具体层面描述。它们共享同一个Choi矩阵 $\mathcal{J}_\Theta^{AB}$，这保证了它们的物理等价性。


-   $\Delta_\Theta^{A \to B}$: 这是一个与超信道 $\Theta$ 相关联的**线性映射**，它描述了超信道 $\Theta$ 的作用在**Choi矩阵层面**上的体现。
    *   **类型**: 这是一个从“输入信道的Choi矩阵空间”到“输出信道的Choi矩阵空间”的线性映射。具体来说，它的定义域是 $\mathcal{B}(\mathcal{H}_{A_0} \otimes \mathcal{H}_{A_1})$，值域是 $\mathcal{B}(\mathcal{H}_{B_0} \otimes \mathcal{H}_{B_1})$。
    *   **核心定义 (via Formula 11)**:$$
        \Delta_\Theta^{A \to B}(J_\Psi^A) \equiv J_{\Theta[\Psi]}^B
        $$
        这个公式是 $\Delta_\Theta^{A \to B}$ 的**定义性关系**。它的意思是：将一个输入信道 $\Psi^A$ 的Choi矩阵 $J_\Psi^A$ 输入到映射 $\Delta_\Theta^{A \to B}$ 中，其输出**就是**将该信道 $\Psi^A$ 本身输入到超信道 $\Theta$ 中所得到的输出信道 $\Theta[\Psi^A]$ 的Choi矩阵 $J_{\Theta[\Psi]}^B$。
    *   **操作性实现 (via Formula 10)**:
        $$
        J_{\Theta[\Psi]}^B = \text{Tr}_A \left[ \mathcal{J}_\Theta^{AB} \left( (J_\Psi^A)^T \otimes I^B \right) \right]
        $$
        这个公式给出了 $\Delta_\Theta^{A \to B}$ 的具体**计算方法**。它展示了超信道的Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 是如何“作用”于输入信道的Choi矩阵 $J_\Psi^A$ 的：
        1.  取输入信道Choi矩阵 $J_\Psi^A$ 的**转置** $(J_\Psi^A)^T$。
        2.  将其与系统B上的单位算子 $I^B$ 做**张量积**。
        3.  将结果与超信道的Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 相乘。
        4.  最后，对系统A（包含 $A_0$ 和 $A_1$）进行**偏迹** (Partial Trace)。
        这个过程的最终结果就是输出信道的Choi矩阵 $J_{\Theta[\Psi]}^B$。

	**总结与解释**:$\Theta$ 和 $\Delta_\Theta^{A \to B}$ 是同一个物理过程的两种不同数学描述：
	*   **超信道 $\Theta$** 是一个**高阶映射**，它的输入和输出都是**量子信道**（即函数）。
	*   **映射 $\Delta_\Theta^{A \to B}$** 是一个**一阶映射**，它的输入和输出都是**矩阵**（具体来说是Choi矩阵）。

	论文中引入 $\Delta_\Theta^{A \to B}$ 的主要目的是为了**简化分析**。将对抽象函数（信道）的操作问题，转化为对具体矩阵的操作问题，使得我们可以利用线性代数和矩阵分析的强大工具（如正半定性、迹、内积等）来研究超信道的性质。可以说，$\Delta_\Theta^{A \to B}$ 是超信道 $\Theta$ 在Choi矩阵世界中的**“化身”或“表示” (representation)**。

### 3. 核心熵量 (比较工具)

-   $H_{\min}(A_1|A_0)_\rho$: 态 $\rho_{A_0A_1}$ 的**条件最小熵**。
-   $H_{\min}^{\text{ext}}(A)_{\Phi}$: 单个信道 $\Phi$ 的**扩展最小熵**。它量化了信道的“内在噪声”，定义为 $H_{\min}(A_1|A_0)_{J_\Phi/d_{A_0}}$。
-   $\Omega^{AB}$: 一个二体量子信道，$\Omega^{A_0B_0 \to A_1B_1}$。
-   $\omega^{AB}$: 二体信道 $\Omega^{AB}$ 的**归一化Choi矩阵**，$\omega^{AB} = J_\Omega^{AB} / (d_{A_0}d_{B_0})$。
-   $H_{\min}^{\text{ext}}(B|A)_\Omega$: 二体信道 $\Omega^{AB}$ 的**扩展条件最小熵**。这是本文最核心的定义，它量化了在拥有对信道A的完全访问权时，关于信道B的不确定性。它被定义为一个半正定规划 (SDP) 问题 (定义4)。
-   $P_{\text{guess}}(\Omega^{AB})$: **猜测概率**。当信道B是经典系统时，它表示Alice猜测Bob输出值的最大平均概率，与 $H_{\min}^{\text{ext}}(B|A)_\Omega$ 有直接的操作性联系。

### 4. 关键数学构造 (证明中的符号)

-   $\langle \Phi, \Psi \rangle$: 两个线性映射（信道）之间的**内积**，可以通过它们的Choi矩阵的希尔伯特-施密特内积来计算，即 $\text{Tr}[(J_\Phi)^\dagger J_\Psi]$。
-   $\gamma^{A_0B_0}$: 在扩展条件最小熵的原始SDP定义 (Eq. 62) 中，待优化的正半定算子。
-   $\alpha^{AB}$: 在扩展条件最小熵的对偶SDP定义 (Eq. 63) 中，待优化的算子。这个 $\alpha^{AB}$ 具有超信道Choi矩阵的所有性质，是连接熵与超信道的关键。
-   $\Phi^{XYA}$: 从一个含参考系统的量子信道 $\Phi^{RA}$ 构造出的**经典-量子信道**。其中X和Y是经典系统，用于将原始问题转化为一个更容易处理的形式。

### 5. 核心关系与定理 (结论性符号)

-   $\Psi \prec_q \Phi$: **量子主序化**符号。当应用到信道时，它表示信道 $\Psi$ 可以通过某个超信道从信道 $\Phi$ 得到，即存在 $\Theta$ 使得 $\Psi = \Theta(\Phi)$。
-   $\mathcal{S}^{A \to B}$: 所有从 $A$ 到 $B$ 的**超信道**的集合。
-   $\Lambda_\Phi^{BB}$: 在主定理 (定理7) 的证明中，由一个“测试信道” $\Lambda^{XYB}$ 和原始信道 $\Phi^{XYA}$ 共同构造出的一个新信道。定理的结论是，$\Psi \prec_q \Phi$ 当且仅当对于所有的测试信道 $\Lambda^{XYB}$，都有 $H_{\min}^{\text{ext}}(B|A)_{\Lambda_\Psi^{BB}} \le H_{\min}^{\text{ext}}(B|A)_{\Lambda_\Phi^{BB}}$。
## 研究方法和核心创意
- **研究方法**:
    1.  **公理化方法**: 作者首先为“信道的熵”提出了一套公理化的要求（单调性、加性、归一化），然后证明了他们定义的**扩展最小熵**满足这些要求。
    2.  **Choi-Jamiołkowski 同构**: 这是贯穿全文的核心数学技术。它允许将关于信道和超信道这种动态过程的操作问题，完全转化为关于它们的Choi矩阵（静态的量子态）的代数问题。这极大地简化了分析。
    3.  **凸优化和对偶性**: 文章的核心结论是，信道间的比较问题可以被精确地表述为一个**半正定规划**（SDP）问题。作者熟练地运用了SDP的原始问题和对偶问题之间的关系来推导和证明熵的各种性质。
- **核心创意**: 核心创意在于认识到，正如态之间的转换由一族熵函数（条件最小熵）完全支配一样，信道之间的转换也应该由类似的一族“超熵”函数来支配。作者成功地**定义**了这样一个量——**扩展的条件最小熵** $H_{\min}^{\text{ext}}(B|A)_\Omega$——并**证明**了它确实扮演了这个角色。这个证明巧妙地利用了凸集的分离定理，将“不存在这样一个超信道”等价于“存在一个分离超平面”，而这个分离超平面恰好可以用扩展条件最小熵来构造。这为比较量子动力学过程提供了一个完整、可计算的理论框架。

## 公式推导
- **关键假设**:
    - **单次机制 (Single-shot regime)**: 本文的分析不考虑多份信道的渐进行为，而是关注于一次转换的可能性。
    - **物理实现的映射**: 超信道的定义（定理1）基于其可以被一个包含前处理和后处理的物理量子网络实现。
- **推导过程**: 整个文章的逻辑链非常清晰。
    1.  **定义超信道**: 严谨定义了超信道及其Choi矩阵表示。
    2.  **定义噪声模型**: 定义了多种类型的噪声超信道（如随机酉、双随机等），并以此为基础，公理化地定义了信道熵应满足的单调性。
    3.  **定义扩展熵**: 定义了**扩展最小熵**和**扩展条件最小熵**，并证明了它们在双随机超信道下是单调的，且满足加性等良好性质。
    4.  **建立主定理**: 在第五部分，作者将核心问题——判断 $\Psi^{RB} \prec_q \Phi^{RA}$ 是否成立——转化为一个等价的经典-量子信道的比较问题。然后利用凸集分离定理证明，这个关系成立的充要条件是对于所有测试信道 $\Lambda^{XYB}$，不等式 $H_{\min}^{\text{ext}}(B|A)_{\Lambda_{\Phi}^{BB}} \geq H_{\min}^{\text{ext}}(B|A)_{\Lambda_{\Psi}^{BB}}$ 恒成立。
    5.  **转化为SDP**: 最后，作者明确地将判断主序关系是否成立的这个无穷条件问题，转化为一个可以高效求解的SDP（公式100-102）。
- **数学和物理上的困难**: 主要的挑战在于处理超信道这种高阶映射的复杂性，其Choi矩阵生活在一个非常大的张量积空间中。另一个难点在于将抽象的数学条件（如无穷多个熵不等式）与具体可计算的程序（SDP）联系起来，这需要对凸优化理论有深入的理解。

![Pasted image 20251029204102.png|500](/img/user/Pasted%20image%2020251029204102.png) 
### 定理1：超信道的等价刻画

令 $\Theta \in \mathcal{L}^{A \to B}$ 是一个将作用于系统A的线性映射变换为作用于系统B的线性映射的高阶映射。以下四个陈述是等价的：

1.  **物理定义**: $\Theta$ 是一个**超信道**。
    *   **含义**: 这是操作性的定义。一个超信道是物理上允许的操作，它必须保持物理过程的有效性。具体来说，它必须是**完备正定保持Completely CP-Preserving, CPP**和**保迹保持Trace-Preserving-Preserving, TPP**的。即，如果你输入一个有效的量子信道（CPTP map），输出的也必须是一个有效的量子信道。

2.  **Choi矩阵的条件**: $\Theta$ 对应的Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 是正半定的（$\mathcal{J}_\Theta^{AB} \ge 0$），并且其**边际marginals**满足：
    $$
    \text{Tr}_{A_0B_1}[\mathcal{J}_\Theta^{AB}] = I^{A_1B_0} \quad \text{以及} \quad \text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0} \otimes u^{A_1}
    $$
    其中 $u^{A_1} = I^{A_1}/d_{A_1}$ 是在系统 $A_1$ 上的最大混合态。
    *   **含义**: 这是在数学上最常用、最便捷的判据。它将判断一个抽象映射是否为超信道的问题，转化为了检查一个具体矩阵是否满足正半定性和两个特定的偏迹条件。这使得超信道问题可以用半正定规划(SDP)等工具来处理。这两个条件如果用投影刻画写的话更容易看出来是线性约束，但是用现在的写法可能在==计算上更简单==（SDP的变量数更少）？

3.  **降维映射的条件**: 映射 $\Delta_\Theta^{A \to B}$ 是完备正(CP)的，并且存在一个**幺正unital**的CP映射 $\Delta_\Theta^{A_0 \to B_0}$，使得通过对输出系统$B_1$求偏迹得到的降维映射 $\Delta_\Theta^{A \to B_0} \equiv \text{Tr}_{B_1} \circ \Delta_\Theta^{A \to B}$ 满足关系：
    $$
    \Delta_\Theta^{A \to B_0} = \Delta_\Theta^{A_0 \to B_0} \circ \text{Tr}_{A_1}
    $$
    *   **含义**: 这个条件揭示了超信道的因果结构。关系式 $\Delta_\Theta^{A \to B_0} = \Delta_\Theta^{A_0 \to B_0} \circ \text{Tr}_{A_1}$ 意味着，对于输出系统$B_0$而言，所有关于输入信道输出端$A_1$的信息都必须被“擦除”（通过 $\text{Tr}_{A_1}$）。这反映了一个物理事实：在信道被使用之前（即信息进入$A_0$），你无法从它的输出端$A_1$获得任何信息。

4.  **物理实现 (前处理-后处理)**: 存在一个辅助希尔伯特空间 $\mathcal{H}_E$ (维度 $d_E \le d_{A_0}d_{B_0}$)，以及两个作为有效量子信道的CPTP映射：
    *   **前处理 (Pre-processing)**: $\Gamma_{\text{pre}}^{B_0 \to A_0E}: \mathcal{B}(\mathcal{H}_{B_0}) \to \mathcal{B}(\mathcal{H}_{A_0} \otimes \mathcal{H}_E)$
    *   **后处理 (Post-processing)**: $\Gamma_{\text{post}}^{A_1E \to B_1}: \mathcal{B}(\mathcal{H}_{A_1} \otimes \mathcal{H}_E) \to \mathcal{B}(\mathcal{H}_{B_1})$

    使得对于任何输入的量子信道 $\Psi^A \in \mathcal{C}^A$，其变换都可以表示为这三部分的复合：$$
    \Theta[\Psi^A] = \Gamma_{\text{post}} \circ (\Psi^A \otimes \text{id}_E) \circ \Gamma_{\text{pre}}
    $$
    *   **含义**: 这是物理上最直观的图像。它表明任何超信道都可以被看作是一个“量子电路板”，如论文中的图1所示。你提供一个输入系统$B_0$，它通过前处理电路$\Gamma_{\text{pre}}$与一个内部辅助系统$E$纠缠，并将一部分送到输入信道$\Psi^A$的入口$A_0$。信道$\Psi^A$作用后，其输出$A_1$与辅助系统$E$一起进入后处理电路$\Gamma_{\text{post}}$，最终产生整个超信道的输出$B_1$。
是否能够给出==算法==？ 
### 定理1的证明

我们将证明一个蕴含关系的循环 `1 ⇒ 2 ⇒ 4 ⇒ 1`，并单独证明 `2 ⇔ 3`。

#### **证明 `1 ⇒ 2` (物理定义 ⇒ Choi矩阵条件)**

1.  **正半定性**: $\Theta$ 是CPP的，这意味着它将任何CP映射都映射为CP映射。我们知道一个映射是CP的**当且仅当**它的Choi矩阵是正半定的。$\Lambda_\Theta^{A\tilde{B}} = (I^A \otimes \Theta)[\Upsilon^{A\tilde{A}}]$。由于$\Upsilon^{A\tilde{A}}$是CP的，$\Theta$是CP保持的（从最原始的定义出发），所以$\Lambda_\Theta$是CP的。因此，$\Lambda_\Theta$的Choi矩阵，也就是$\mathcal{J}_\Theta^{AB}$，必须是正半定的。

- 保迹条件我给出了两个证明，其中第一个证明基于超信道的蔡氏矩阵和基底信道的蔡氏矩阵的关系式(8)，只对第一条式子给出了证明；第二个证明是完整而简洁的，利用了[[The Multi-round Process Matrix\|The Multi-round Process Matrix]] 中的[[投影刻画\|投影刻画]]和相关的定理。
- ![e0a479c0e8908afb048d79224695ac82.jpg|400](/img/user/e0a479c0e8908afb048d79224695ac82.jpg) ![6a979f0f33b1b667df6000250c1ae045.jpg|400](/img/user/6a979f0f33b1b667df6000250c1ae045.jpg)
- 证明一（部分证明）
$$
\begin{aligned}
& \text{Tr}_{A_0 B_1}[\mathcal{J}_\Theta^{AB}]  \qquad \text{(开始计算超信道Choi矩阵的偏迹)} \\
&= \text{Tr}_{A_0 B_1} \left[ \sum_{p,q,r,s} J_{\mathcal{E}_{pq,rs}}^A \otimes J_{\Theta[\mathcal{E}_{pq,rs}]}^B \right] \qquad \text{(代入}\mathcal{J}_\Theta^{AB}\text{的定义 (8)，其中}\mathcal{E}\text{是基底信道)} \\
&= \sum_{p,q,r,s} \text{Tr}_{A_0}[J_{\mathcal{E}_{pq,rs}}^A] \otimes \text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pq,rs}]}^B] \qquad \text{(利用迹的线性和在张量积上的可分离性)} \\
&= \sum_{p,q,r,s} \text{Tr}_{A_0}[|p\rangle\langle q|_{A_0} \otimes |r\rangle\langle s|_{A_1}] \otimes \text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pq,rs}]}^B] \qquad \text{(代入基底信道Choi矩阵的定义 }J_\mathcal{E} = |p\rangle\langle q| \otimes |r\rangle\langle s| \text{)} \\
&= \sum_{p,q,r,s} \delta_{pq} |r\rangle\langle s|_{A_1} \otimes \text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pq,rs}]}^B] \qquad \text{(计算第一个偏迹，Tr}[|p\rangle\langle q|] = \delta_{pq}\text{)} \\
&= \sum_{p,r,s} |r\rangle\langle s|_{A_1} \otimes \text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pp,rs}]}^B] \qquad \text{(利用}\delta_{pq}\text{的性质，对q求和后仅p=q项保留)} \\
&= \sum_{r} |r\rangle\langle r|_{A_1} \otimes \left( \sum_p \text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pp,rr}]}^B] \right) + \sum_{r \neq s} |r\rangle\langle s|_{A_1} \otimes \left( \sum_p \text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pp,rs}]}^B] \right) \qquad \text{(将和式分解为对角(r=s)与非对角(r≠s)部分)} \\
&= \sum_{r} |r\rangle\langle r|_{A_1} \otimes I^{B_0} + \sum_{r \neq s} |r\rangle\langle s|_{A_1} \otimes 0 \qquad \\ & \text{(核心步骤：因为}\Theta\text{是保迹保持(TPP)的，对于任何TP输入信道，输出也必为TP。这蕴含了}\sum_p\text{Tr}_{B_1}[J_{\Theta[\mathcal{E}_{pp,rr}]}^B] = I^{B_0}\text{且当r≠s时和为0)} \\
&= \left( \sum_{r} |r\rangle\langle r|_{A_1} \right) \otimes I^{B_0} \qquad \text{(非对角项为零)} \\
&= I^{A_1} \otimes I^{B_0} \qquad \text{(证明完毕，}\sum_r |r\rangle\langle r|_{A_1} = I^{A_1}\text{)}
\end{aligned}
$$
- 证明二（完整证明）

该证明源于一个更普适的**过程矩阵 (Process Matrix)** 框架。其核心思想是，任何物理上有效的过程（在此为超信道的Choi矩阵 $\mathcal{J}_\Theta^{AB}$），其归一化条件都可以被一个作用于其上的**投影算子** $\tilde{\mathcal{P}}$ 来等价地描述。

1.  **定义局部操作的子空间**:
    超信道作用的局部操作由两部分组成：一个任意的**保迹(TP)信道** $\Psi^A$ 和一个任意的**量子态** $\rho^{B_0}$。
    *   所有TP信道 $\Psi^A$ 的Choi矩阵 $J_\Psi^A$ 所在的子空间由投影算子 $\mathcal{P}_{TP} = I - \mathcal{D}_{A_1} + \mathcal{D}_{A_0A_1}$ 刻画，其中 $\mathcal{D}_X[\cdot] \equiv \frac{I_X}{d_X}\text{Tr}_X[\cdot]$。
    因此，所有有效的局部操作 $(J_\Psi^A)^T \otimes (\rho^{B_0})^T\otimes \mathbb{I}^{B_1}$ 所在的联合子空间由投影算子 $\mathcal{P}_{local} = \mathcal{P}_{TP} \otimes \mathcal{D}_{B_1}$ 刻画。

2.  **应用正交性原理**:
    根据过程矩阵理论，一个有效的过程 $\mathcal{J}_\Theta^{AB}$ 必须位于 $\mathcal{P}_{local}$ 所定义子空间的**准正交补空间 (quasiorthogonal complement)** 中。该补空间的投影算子为 $\tilde{\mathcal{P}} = I - \mathcal{P}_{local} + \mathcal{D}_{global}$。  因此，$\mathcal{J}_\Theta^{AB}$ 必须是该投影算子的不动点：
    $$
    \tilde{\mathcal{P}}[\mathcal{J}_\Theta^{AB}] = \mathcal{J}_\Theta^{AB}
    $$
    - 经过检验，这个总的投影算符 $\tilde{\mathcal{P}}$ 可以被分解为两个更基本的投影算符的乘积 $\tilde{\mathcal{P}} = \mathcal{P}_1 \mathcal{P}_2$，也就是条件(1)中的两个等式，其中：
    *   $\mathcal{P}_1 = \mathcal{I} - \mathcal{D}_{B_1} + \mathcal{D}_{B_1A_1}$
    *   $\mathcal{P}_2 = I - \mathcal{D}_{A_0B_1} + \mathcal{D}_{global}$
    检验参见：重写投影刻画.nb

==至于为什么trace掉A1和B1之后剩下的部分是某个特别的映射的蔡氏矩阵$J_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0}$ ，这实际上就是在定义$\Delta_{\Theta}^{A_0\to B_0}$==
#### 证明 `2 ⇒ 4` (Choi矩阵条件 ⇒ 物理实现)

**证明思路**: 这个证明的核心是**量子态纯化 (purification)** 和 **Uhlmann定理**。基本策略是：
1.  将我们研究的对象——超信道$\Theta$的Choi矩阵 $\mathcal{J}_\Theta^{AB}$（这是一个混合态算子）——“提升”为一个纯态 $|\phi\rangle^{ABC}$。
2.  利用**陈述2**中给出的关于 $\mathcal{J}_\Theta^{AB}$ 边际矩阵的条件，来约束其纯化 $|\phi\rangle^{ABC}$ 的结构。
3.  独立地，我们用一些简单的、已知的构建模块（另一个纯化态和一个最大纠缠态）来构造出这个边际矩阵的**另一个**纯化。
4.  根据**Uhlmann定理**  [[1 Stories of Bizzo's Life/2 凝聚态物理学/10 拓扑物理学#^dstg7s\|10 拓扑物理学#^dstg7s]]  同一个混合态的任意两个纯化之间，必然只相差一个作用在各自辅助系统上的**等距变换 (isometry)**。这个等距变换就是我们找到**后处理信道** $\Gamma_{\text{post}}$ 的关键。
5.  对剩下的构建模块进行分析，我们发现它正好对应一个**前处理信道** $\Gamma_{\text{pre}}$ 的Choi矩阵。
6.  最后，将这个 `pre-processing` -> `channel` -> `post-processing` 的结构代入超信道作用的通用公式，通过代数运算证明其结果与原始超信道的作用完全一致。

**详细步骤翻译与说明**:
在[[A theoretical framework for quantum networks\|A theoretical framework for quantum networks]] 的定理3中有一个更简单的证明。
我们现在证明 `2 ⇒ 4`。
令 $|\phi\rangle^{ABC}$ 为 $\mathcal{J}_\Theta^{AB}$ 的一个**纯化**，并令 $|\psi\rangle^{A_0B_0E}$ 为 $\frac{1}{d_{A_1}}\mathcal{J}_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0}$ 的一个纯化。后者总是存在的，其辅助系统E的维度满足 $d_E \le d_{A_0}d_{B_0}$。

> **说明**: 第一步，我们将要研究的两个核心矩阵（超信道的Choi矩阵和它的一个边际矩阵）都表示为更大系统中的纯态。这是量子信息论中的一个标准技巧，因为纯态的结构更简单，性质更好。

那么，根据**陈述2**中的关系式 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = \mathcal{J}_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0} \otimes u^{A_1}$，我们得出结论：$|\psi\rangle^{A_0B_0E} \otimes |\Phi^+\rangle^{A_1\tilde{A}_1}$ 是 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}]$ 的一个纯化。

> **说明**: 这里利用了纯化的一个重要性质：一个张量积形式的混合态的纯化，是其各自纯化的张量积。我们知道最大混合态 $u^{A_1}$ 的一个标准纯化是最大纠缠态 $|\Phi^+\rangle^{A_1\tilde{A}_1}$ (除以一个归一化因子)。

因此，由于 $|\phi\rangle^{ABC}$ (在对$B_1$求迹后) 也是 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}]$ 的一个纯化，根据**Uhlmann定理**，必然存在一个等距信道 $\mathcal{V}^{\tilde{A}_1E \to B_1C}$ 使得：
$$
|\phi\rangle^{ABC} = (\text{id}_{A_0B_0A_1} \otimes \mathcal{V}^{\tilde{A}_1E \to B_1C}) (|\psi\rangle^{A_0B_0E} \otimes |\Phi^+\rangle^{A_1\tilde{A}_1})
$$

对等式两边都对系统C求迹，并记**后处理信道** $\Gamma_{\text{post}}^{\tilde{A}_1E \to B_1} \equiv \text{Tr}_C \circ \mathcal{V}^{\tilde{A}_1E \to B_1C}$，我们得到：
$$
\mathcal{J}_\Theta^{AB} = (\text{id}_{A_0B_0A_1} \otimes \Gamma_{\text{post}}^{\tilde{A}_1E \to B_1}) (|\psi\rangle\langle\psi|^{A_0B_0E} \otimes |\Phi^+\rangle\langle\Phi^+|^{A_1\tilde{A}_1})
$$

> **说明**: 这是第一个关键成果。我们找到了后处理信道 $\Gamma_{\text{post}}$，它来自于**连接两个纯化的等距变换** $V$。

根据 $|\psi\rangle^{A_0B_0E}$ 的定义，它满足 $\text{Tr}_{A_0E}[|\psi\rangle\langle\psi|^{A_0B_0E}] = I^{B_0}$。因此，必然存在一个CPTP信道（实际上是一个**等距**）$\Gamma_{\text{pre}}^{B_0 \to A_0E}$ 使得 $|\psi\rangle\langle\psi|^{A_0B_0E} = (\text{id}_{B_0} \otimes \Gamma_{\text{pre}}^{B_0 \to A_0E}) (|\Phi^+\rangle\langle\Phi^+|^{B_0\tilde{B}_0})$。

> **说明**: 这个条件 $\text{Tr}_{A_0E}[...] = I^{B_0}$ 正是一个从 $B_0$ 到 $A_0E$ 的保迹信道的Choi矩阵所满足的条件。因此，我们可以将 $|\psi\rangle\langle\psi|^{A_0B_0E}$ 本身就看作是某个信道的Choi矩阵，这个信道我们定义为**前处理信道** $\Gamma_{\text{pre}}$。

因此，
$$
\mathcal{J}_\Theta^{AB} = (\text{id}_{A_1B_0} \otimes \Gamma_{\Theta}^{\tilde{A}_1\tilde{B}_0 \to A_0 B_1}) (|\Phi^+\rangle\langle\Phi^+|^{A_1\tilde{A}_1} \otimes |\Phi^+\rangle\langle\Phi^+|^{B_0\tilde{B}_0})
$$
其中我们定义了一个复合映射 $\Gamma_{\Theta}^{\tilde{A}_1\tilde{B}_0 \to A_0 B_1} \equiv (\text{id}_{A_0} \otimes \Gamma_{\text{post}}^{A_1E \to B_1}) \circ (\text{id}_{\tilde{A}_1} \otimes \Gamma_{\text{pre}}^{B_0 \to A_0E})$。


为了完成证明，记 $\Phi^B \equiv \Theta[\Psi^A]$，并从公式(10)可知，对于任意输入态 $\rho \in \mathcal{B}(\mathcal{H}_{B_0})$：这实际上就是 link product $\star$ 的计算规则
$$
\Phi(\rho) = \text{Tr}_{B_0}[J_\Phi^B (\rho^T \otimes I^{B_1})] = \text{Tr}_{AB_0}[\mathcal{J}_\Theta^{AB} ( (J_\Psi^A)^T \otimes \rho^T \otimes I^{B_1} )]
$$

接下来，我们将上面推导出的 $\mathcal{J}_\Theta^{AB}$ 的表达式代入，得到：
$$
\Phi(\rho) = \text{Tr}_{A} \left[ ((J_\Psi^A)^T \otimes I^{B_1}) \times (\text{id}_A \otimes \Gamma_{\text{post}}^{A_1E \to B_1})(|\Phi^+\rangle\langle\Phi^+|^{A_1\tilde{A}_1} \otimes \Gamma_{\text{pre}}^{B_0 \to A_0E}(\rho)) \right]
$$
其中我们在对$B_0$求迹后，利用了关系 $(\rho^T \otimes I^{\tilde{B}_0})|\Phi^+\rangle^{B_0\tilde{B}_0} = (I^{B_0} \otimes \rho)|\Phi^+\rangle^{B_0\tilde{B}_0}$。

最后，我们注意到关系式：
$$
(J_\Psi^A)^T = \sum_{i,j} |j\rangle\langle i|^{A_0} \otimes (\Psi^{\tilde{A}_0 \to A_1}[|i\rangle\langle j|^{\tilde{A}_0}])^T
$$
因此
$$
\text{Tr}_{A_1} \left[ ((J_\Psi^A)^T \otimes I^{\tilde{A}_1})(I^{A_0} \otimes |\Phi^+\rangle\langle\Phi^+|^{A_1\tilde{A}_1}) \right] = \sum_{i,j} |j\rangle\langle i|^{A_0} \otimes \Psi^{\tilde{A}_0 \to \tilde{A}_1}[|i\rangle\langle j|^{\tilde{A}_0}]
$$
将此结果代入(28)，我们最终得出结论：
$$
\begin{aligned}
\Phi(\rho) &= \sum_{i,j} \Gamma_{\text{post}}^{A_1E \to B_1} \left( \Psi^{\tilde{A}_0 \to \tilde{A}_1}[|i\rangle\langle j|^{\tilde{A}_0}] \otimes \langle i^{A_0} | \Gamma_{\text{pre}}^{B_0 \to A_0E}(\rho) | j^{A_0} \rangle \right) \\
&= \Gamma_{\text{post}}^{A_1E \to B_1} \left[ (\Psi^{A_0 \to A_1} \otimes \text{id}_E) (\Gamma_{\text{pre}}^{B_0 \to A_0E}(\rho)) \right]
\end{aligned}
$$
这与**陈述4**中给出的物理实现形式完全一致。

这便完成了 `2 ⇒ 4` 的证明。
#### **证明 `4 ⇒ 1` (物理实现 ⇒ 物理定义)**

这是最直接的蕴含关系。

1.  **CPP**: 我们假设 $\Theta[\Psi^A] = \Gamma_{\text{post}} \circ (\Psi^A \otimes \text{id}_E) \circ \Gamma_{\text{pre}}$。
    *   如果 $\Psi^A$ 是一个CP映射，那么 $\Psi^A \otimes \text{id}_E$ 也是一个CP映射（CP映射与恒等映射的张量积是CP的）。
    *   CP映射的复合（$\circ$）仍然是CP映射。
    *   因为 $\Gamma_{\text{pre}}$ 和 $\Gamma_{\text{post}}$ 都是CP的，所以整个表达式的结果必然是CP的。因此 $\Theta$ 是CP保持的。这个论证对于任意维度的辅助系统都成立，所以 $\Theta$ 是完备CP保持的（CPP）。

2.  **TPP**: 我们假设 $\Psi^A$ 是保迹的(TP)。我们需要证明 $\Theta[\Psi^A]$ 也是TP的。
    *   对于任何输入态 $\rho^{B_0}$，我们有：
        $$
        \text{Tr}[\Theta[\Psi^A](\rho^{B_0})] = \text{Tr}[\Gamma_{\text{post}} \circ (\Psi^A \otimes \text{id}_E) \circ \Gamma_{\text{pre}} (\rho^{B_0})]
        $$
    *   因为 $\Gamma_{\text{post}}$ 是TP的，所以 $\text{Tr}[\Gamma_{\text{post}}(...)] = \text{Tr}[...]$。
        $$
        = \text{Tr}[(\Psi^A \otimes \text{id}_E) \circ \Gamma_{\text{pre}} (\rho^{B_0})]
        $$
    *   因为 $\Psi^A \otimes \text{id}_E$ 也是TP的。
        $$
        = \text{Tr}[\Gamma_{\text{pre}} (\rho^{B_0})]
        $$
    *   因为 $\Gamma_{\text{pre}}$ 是TP的。
        $$
        = \text{Tr}[\rho^{B_0}] = 1
        $$
    *   因此，对于任何TP的 $\Psi^A$，$\Theta[\Psi^A]$ 也是TP的。所以 $\Theta$ 是TPP的。


### 证明 `2 ⇔ 3` 的等价性

这个证明旨在建立超信道的Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 所满足的代数条件（**陈述2**）与一个描述其因果结构的、关于降维映射 $\Delta_\Theta$ 的关系式（**陈述3**）之间的等价性。这是一个纯粹的代数证明，它依赖于Choi-Jamiołkowski同构的性质，即一个映射的性质与其Choi矩阵的性质一一对应。可以证明，对映射 $\Delta_\Theta^{A \to B}$ 的输出端 $B_1$ 求偏迹，在Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 层面，完全等价于对其求相应的偏迹。而条件3中的幺正性和迹关系，可以被直接翻译为条件2中关于Choi矩阵边际的具体形式。

#### **证明 `3 ⇒ 2` (降维映射条件 ⇒ Choi矩阵条件)**

**假设**: 我们假设**陈述3**成立。即：
*   映射 $\Delta_\Theta^{A \to B}$ 是完备正(CP)的。
*   存在一个**unital**且CP的映射 $\Delta_\Theta^{A_0 \to B_0}$。
*   关键关系式成立: $\Delta_\Theta^{A \to B_0} \equiv \text{Tr}_{B_1} \circ \Delta_\Theta^{A \to B} = \Delta_\Theta^{A_0 \to B_0} \circ \text{Tr}_{A_1}$。

**目标**: 从这些假设出发，推导出**陈述2**中关于Choi矩阵 $\mathcal{J}_\Theta^{AB}$ 的边际条件。

1.  **翻译关键关系式**: 我们需要将关于映射的关系式 $\Delta_\Theta^{A \to B_0} = \Delta_\Theta^{A_0 \to B_0} \circ \text{Tr}_{A_1}$ 翻译成Choi矩阵的语言。一个映射的Choi矩阵唯一确定了这个映射。因此，我们只需证明等式两边的映射具有相同的Choi矩阵。
    *   **LHS的Choi矩阵**: 映射 $\Delta_\Theta^{A \to B_0} = \text{Tr}_{B_1} \circ \Delta_\Theta^{A \to B}$ 的Choi矩阵，根据Choi-Jamiołkowski同构的性质，就是 $\mathcal{J}_\Theta^{AB}$ 对系统 $B_1$ 求偏迹的结果，即 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}]$ (在论文中记为 $\mathcal{J}_\Theta^{AB_0}$)。
    *   **RHS的Choi矩阵**: 映射 $\Delta_\Theta^{A_0 \to B_0} \circ \text{Tr}_{A_1}$ 是一个复合映射。
        *   首先，映射 $\text{Tr}_{A_1}: \mathcal{B}(\mathcal{H}_{A_0A_1}) \to \mathcal{B}(\mathcal{H}_{A_0})$ 的Choi矩阵是 $I^{A_0} \otimes u^{A_1}$ (这里 $u^{A_1}$ 是最大混合态)。
        *   将这个Choi矩阵输入到后续映射 $\Delta_\Theta^{A_0 \to B_0}$ 中，得到的复合映射的Choi矩阵是 $J_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0} \otimes u^{A_1}$。
    *   因此，关键关系式在Choi矩阵层面等价于：
        $$
        \text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0} \otimes u^{A_1}
        $$
        这正是**陈述2**中的第二个边际条件。

2.  **利用幺正(Unital)性质**: 我们假设了 $\Delta_\Theta^{A_0 \to B_0}$ 是幺正的，即 $\Delta_\Theta^{A_0 \to B_0}(I^{A_0}) = I^{B_0}$。
    *   一个映射是幺正的，当且仅当其Choi矩阵对输入系统求偏迹后得到单位矩阵（乘以输入维度），即 $\text{Tr}_{A_0}[J_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0}] = d_{A_0}I^{B_0}$。
    *   在超信道的框架下，一个更基本的因果约束（即不能从未来到过去通信）要求 $\text{Tr}_{A_0B_1}[\mathcal{J}_\Theta^{AB}] = I^{A_1B_0}$。我们可以验证，当且仅当 $\Delta_\Theta^{A_0 \to B_0}$ 是幺正时，这个条件才与上一步推导出的边际条件相容。具体来说，对 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J_{\Delta_\Theta^{A_0 \to B_0}}^{A_0B_0} \otimes u^{A_1}$ 两边同时对 $A_0$ 求迹，并利用幺正条件，即可恢复出对总信道迹的约束，这与 $\text{Tr}_{A_0B_1}[\mathcal{J}_\Theta^{AB}] = I^{A_1B_0}$ 相吻合。
    *   因此，`3 ⇒ 2` 得证。

#### **证明 `2 ⇒ 3` (Choi矩阵条件 ⇒ 降维映射条件)**

**假设**: 我们假设**陈述2**成立。即：
*   $\mathcal{J}_\Theta^{AB} \ge 0$。
*   边际条件成立: $\text{Tr}_{A_0B_1}[\mathcal{J}_\Theta^{AB}] = I^{A_1B_0}$ 且 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J^{A_0B_0} \otimes u^{A_1}$ (其中 $J^{A_0B_0}$ 是某个算子)。

**目标**: 构造一个满足**陈述3**性质的映射 $\Delta_\Theta^{A_0 \to B_0}$。

1.  **定义 $\Delta_\Theta^{A_0 \to B_0}$**: 我们利用边际条件来**定义**这个映射。从关系式 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J^{A_0B_0} \otimes u^{A_1}$ 中，算子 $J^{A_0B_0}$ 被唯一确定。我们就用这个 $J^{A_0B_0}$ 来定义 $\Delta_\Theta^{A_0 \to B_0}$，即 $\Delta_\Theta^{A_0 \to B_0}$ 是那个以 $J^{A_0B_0}$ 为Choi矩阵的唯一映射（==这与前面1到2的推导是一致的==）。

2.  **验证性质**: 现在需要验证这样定义的 $\Delta_\Theta^{A_0 \to B_0}$ 满足陈述3的要求。
    *   **CP性质**: 因为 $\mathcal{J}_\Theta^{AB} \ge 0$，所以它的偏迹 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J^{A_0B_0} \otimes u^{A_1}$ 也必须是正半定的。这意味着 $J^{A_0B_0}$ 必然是正半定的，因此其对应的映射 $\Delta_\Theta^{A_0 \to B_0}$ 是一个CP映射。
    *   **幺正(Unital)性质**: 我们需要证明 $\Delta_\Theta^{A_0 \to B_0}$ 是幺正的，即 $\text{Tr}_{A_0}[J^{A_0B_0}] = d_{A_0}I^{B_0}$。我们利用**陈述2**中的**另一个**边际条件 $\text{Tr}_{A_0B_1}[\mathcal{J}_\Theta^{AB}] = I^{A_1B_0}$。对这个等式两边同时对系统 $A_1$ 求迹，得到：
        $$
        \text{Tr}_{A_1}\left(\text{Tr}_{A_0B_1}[\mathcal{J}_\Theta^{AB}]\right) = \text{Tr}_{A_1}[I^{A_1B_0}]
        $$
        $$
        \text{Tr}_{A_0A_1B_1}[\mathcal{J}_\Theta^{AB}] = d_{A_1}I^{B_0}
        $$
        左边可以重新组合偏迹的顺序为 $\text{Tr}_{A_0A_1}[\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}]]$。代入我们已知的关系 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}] = J^{A_0B_0} \otimes u^{A_1}$：
        $$
        \text{Tr}_{A_0A_1}[J^{A_0B_0} \otimes u^{A_1}] = \text{Tr}_{A_0}[J^{A_0B_0}] \cdot \text{Tr}_{A_1}[u^{A_1}] = \text{Tr}_{A_0}[J^{A_0B_0}]
        $$
        因此，我们得到 $\text{Tr}_{A_0}[J^{A_0B_0}] = d_{A_1}I^{B_0}$。 (*注：原文此处似乎有一个维度因子的笔误，根据幺正性的标准定义，应为$d_{A_0}I^{B_0}$。这不影响其幺正的结论*)。所以 $\Delta_\Theta^{A_0 \to B_0}$ 是幺正的。
    *   **验证关键关系式**: 我们需要证明 $\text{Tr}_{B_1} \circ \Delta_\Theta^{A \to B} = \Delta_\Theta^{A_0 \to B_0} \circ \text{Tr}_{A_1}$。这等价于证明它们的Choi矩阵相等。
        *   LHS的Choi矩阵是 $\text{Tr}_{B_1}[\mathcal{J}_\Theta^{AB}]$。根据我们的假设，它等于 $J^{A_0B_0} \otimes u^{A_1}$。
        *   RHS的Choi矩阵，根据我们对 $\Delta_\Theta^{A_0 \to B_0}$ 的定义，就是 $J_{\Delta_\Theta^{A_0 \to B_0}} \otimes u^{A_1} = J^{A_0B_0} \otimes u^{A_1}$。
        *   两者相等，因此关键关系式成立。
    *   因此，`2 ⇒ 3` 得证。

由于我们证明了 `3 ⇒ 2` 和 `2 ⇒ 3`，所以**陈述2**和**陈述3**是完全等价的。
## 图表
- **图1**: 物理上实现一个**超信道** $\Theta$ 的示意图。一个待处理的信道 $\Psi^A$ 被“插入”到一个更大的量子网络中。这个网络包含一个与 $\Psi^A$ 输入端 $A_0$ 交互的前处理信道 $\Gamma_{\text{pre}}$，和一个与 $\Psi^A$ 输出端 $A_1$ 交互的后处理信道 $\Gamma_{\text{post}}$。整个过程的净效应就是将信道 $\Psi^A$ 转换为一个新的信道 $\Theta[\Psi^A]$。
- **图2 & 3**: 展示了与超信道相关的特定CPTP映射的实现方式，是图1的具体化和技术性分解。
- **图4**: 描绘了一个称为“**完全保均匀性**”的超信道的作用。如果一个输入的二体信道 $\Phi^{AC}$ 在A系统上是边际均匀的（即无论输入什么，A系统的输出总是最大混合态），那么经过这个超信道作用后，输出的信道 $\Psi^{BC}$ 在B系统上也必须是边际均匀的。这是一种强噪声的物理直观体现。
- **图5 & 6**: 提供了**扩展条件最小熵**的一种操作性解释。展示了Alice如何通过一个复杂的策略来猜测Bob的经典输出。Alice可以利用一个纠缠态，将其一部分通过她所拥有的信道部分，然后进行联合测量。最优的平均猜测概率与扩展条件最小熵直接相关。
- **图7**: 本文核心问题的直观表示。左边是一个二体信道 $\Phi^{RA}$，其中R可以看作是一个可控的参考系统。这个信道通过一个只作用在A系统上的**超信道** $\Theta$，被转换为右边的另一个二体信道 $\Psi^{RB}$。问题就是：给定 $\Phi^{RA}$ 和 $\Psi^{RB}$，是否存在这样的 $\Theta$？

# 点评

## 缺点和展望
- **知识体系的贡献**: 这篇文章**建立**了量子信息论中的一个基础性成果。它成功地将**量子主序化**理论从静态的量子态推广到了动态的量子信道，为理解和分类量子过程的内在能力提供了一个完整且可操作的框架。这是量子资源理论从研究“物”（态）到研究“法”（过程）迈出的关键一步。
- **引出的进一步问题**:
    1.  **渐进领域**: 本文完全聚焦于单次（single-shot）机制。一个自然的扩展是研究在可以使用大量相同信道副本的渐进（asymptotic i.i.d.）情况下，信道间的转换理论会变成什么样子。届时，各种熵和平滑熵可能会收敛到冯诺依曼熵类的量。
    2.  **平滑熵版本**: 单次机制中的熵通常具有“平滑”版本（smoothed entropy），允许有微小的误差以换取更好的熵值。定义和研究本文中扩展条件最小熵的平滑版本将是一个重要的后续工作。
    3.  **具体资源理论的应用**: 作者在文末简单提及了在量子热力学中的应用。将这个通用框架应用到其他具体的量子过程资源理论中（如非马尔可夫性、因果序等）将是非常有价值的。
- **前提假设的局限**:
    - 整个理论框架依赖于能够精确实现任意的**超信道**，这在实验上是极具挑战性的。
    - 问题的可解性（SDP）依赖于系统是有限维的。

## 关联
- **直接继承和推广**: 本文是Gour等人发表在Nature Communications上的关于**量子态主序化**工作的直接推广和续作。它采用了相同的哲学思想和类似的数学工具（条件熵、SDP），并将它们提升到了更高一层的抽象（信道而非态）。
- **建立在...之上**: 本文严重依赖Chiribella等人关于**量子梳**（quantum combs）和**超信道**的开创性工作。没有后者建立的严谨数学框架，本文的分析将无从谈起。
- **后续影响**: 这篇文章为之后兴起的**量子过程资源理论**（resource theories of quantum processes）提供了核心的数学工具和判据。任何想要讨论一种量子过程（如非幺正性、相干性生成能力）是否比另一种“更有资源”，都可以使用本文建立的框架。例如，它可以用来判断在热力学操作下，一个信道的模拟能否由另一个信道完成。

# 反思

## 灵感来源
作者的灵感来源非常清晰，是**类比驱动的推广**。
1.  **成功的范例**: 作者自己就是量子态主序化理论的主要贡献者之一。他们发现，条件最小熵族是刻画态转化的“金钥匙”。
2.  **提出自然的问题**: 一个自然而深刻的问题是：这个成功的范例能否从静态的“态”推广到动态的“信道”？物理世界根本上是由动力学过程描述的，因此这个推广具有基础性的重要意义。
3.  **寻找正确的工具**: 认识到这个问题需要将“信道”本身视为被操作的对象，自然而然地引向了Chiribella等人发展的“超信道”理论。
因此，本文的诞生是基于对一个领域（态的资源理论）的深刻理解，敏锐地看到了一个可以推广的开放问题，并找到了另一个领域（超信道理论）的现成工具来解决它。

## 自己提出的问题和假设
- **问题1**: 本文定义的扩展条件最小熵作为猜测概率的操作解释，依赖于一个相当复杂的量子策略（图5、图6）。是否存在一个更简单、更直接的操作性任务，其最优性能也由这个熵来刻画？
- **问题2**: 如果超信道本身是受限的（例如，在热力学中，超信道必须是热操作），那么信道间的转换条件会如何改变？**我假设**，这将导致需要满足的熵不等式更少或更宽松，从而允许更多的信道相互转化。
- **猜想**: 在渐进i.i.d.领域，两个信道系综之间的转换将完全由某个单一的、基于冯诺依曼熵的“信道相对熵”或者“互信息率”来决定，类似于量子态的渐进转换理论。

## 其他问题
- **为什么感兴趣**: 这篇文章解决了一个非常根本的问题：“什么时候一个量子过程比另一个更有用？” 它提供了一个数学上严谨且物理上有意义的答案。这种从具体到抽象，再反过来为具体问题提供解决方案的理论构建过程非常吸引人。
- **结论与认知的相符性**: 结论与物理直觉高度**相符**。一个更“无序”或“有能力”的信道应该能够模拟一个更“有序”或“能力弱”的信道，而熵正是衡量这种“无序”的工具。本文精确地证明了这一点。
- **有哪些学术上准确、生动的[[英语\|英语]]表达**
    - `carry over to the extended version`: 延续到扩展版本
    - `operational interpretation as a guessing probability`: 作为猜测概率的操作性解释
    - `a pre-order`: 一种预序关系
    - `necessary and sufficient conditions`: 充要条件
    - `in the single-shot regime`: 在单次机制下
    - `axiomatic approach`: 公理化方法
- **写得不好的，令人费解的语句**: 这篇文章的符号系统非常密集和复杂，对初学者极不友好。例如，在第二节和第三节中，同时处理多个系统及其“tilde”副本（如 $A_0, A_1, \tilde{A}_0, \tilde{A}_1$）和在它们之间定义的各种映射（如 $\Psi^A$, $J_\Psi^A$, $\Lambda_\Theta^{A \to B}$, $\Upsilon^{A\tilde{A}}$），需要读者有极大的耐心和很强的抽象符号处理能力。虽然对该领域的专家来说是标准的，但这构成了很高的入门门槛。

