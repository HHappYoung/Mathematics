# 1 离散时间马尔可夫链

这一章可参考大三上《随机过程》一课Ch4的课件

## 1.1 Introduction

上下文与背景

- **离散时间马尔可夫链**：指的是在离散时间点上进行的随机过程，状态空间是有限的或可列无限。
- **可测空间**：$(\Omega, \mathscr{F}, \mathbb{P})$是一个概率空间，其中\(\Omega\)是样本空间，\(\mathscr{F}\)是\(\sigma\)-代数，\(\mathbb{P}\)是概率测度。
- **状态空间 \(S\)**：是有限或可数无限的集合，常用于表示系统的所有可能状态。

随机变量与状态空间

- **随机变量**：$x: \Omega \rightarrow S$是一个随机变量，当且仅当对于每个状态 $s \in S$，集合 $\{x = s\}$ 是可测的，即属于$\mathscr{F}$。
- **状态空间示例**：
  - 有限状态空间：\(S = \{1, 2, \ldots, N\}\)
  - 无限状态空间：如自然数集 \(\mathbb{N}\)、整数集 \(\mathbb{Z}\)、非负整数集 \(\mathbb{Z}_{+}\)、以及二维整数网格 \(\mathbb{Z}^2\)。

马尔可夫链的定义

- **马尔可夫链**：是一个离散时间随机过程
  $$
  X = \left(X_n: \Omega \rightarrow S \mid n = 0, 1, 2, \ldots\right)
  $$
  满足马尔可夫性质。

- **马尔可夫性质**（Markov Property）：
  - 条件概率关系：
    $$
    \mathbb{P}\left\{X_n = j \mid X_{n_1} = i_1, \ldots, X_{n_k} = i_k\right\} = \mathbb{P}\left\{X_n = j \mid X_{n_k} = i_k\right\}
    $$
  - 表示在给定当前状态 $i_k$ 的情况下，未来状态 $X_n$ 取值 $j$ 的概率与过去的状态无关，只依赖于当前状态。
  - **解释**：这体现了马尔可夫链的核心思想：“未来”只依赖于“现在”而与“过去”无关。所有可能的过去的影响都浓缩在当前的状态中。



$l$ 步转移概率的计算类似于链式法则



We notice here that in (1.1.2), it is understood that if $p_{k_1 k_2}^{(n+1,+1)}$ is undefined, that is, $\mathbb{P}\left\{X_{n+1}=\right.$ $\left.k_1\right\}=0$, the corresponding summand $p_{i k_1}^{(n,+1)} p_{k_1 k_2}^{(n+1,+1)} \cdots p_{k_{\ell-1} j}^{(n+\ell-1,+1)}$ is to be taken as 0 ; we observe that, for such a value of $k_1, p_{i k_1}^{(n,+1)}=0$; similar for other $k$.
- In many important cases $P^{(n,+\ell)}$ is independent of $n$ so that we simply write $P^{(\ell)}=\left[p_{i j}^{(\ell)}\right]$ for $P^{(n,+\ell)}=\left[p_{i j}^{(n,+\ell)}\right]$ and speak of "time-homogeneous" transition probability matrix. In this case, simply write $P=P^{(1)}$ so that the following "Chapman-Kolmogorov equation" holds:

$$
P^{(\ell)}=P^{\ell} \quad \text { and } \quad P^{(m+n)}=P^m P^n
$$

for any $\ell \geq 1$ and $m, n \geq 1$.

时间齐次：转移概率与起始点无关，只与转移的步数有关。比如，我从t=0时的i转移到t=10的j，和从t=100时的i转移到t=110时的j的概率是一样的。

由于假设了时间齐次性，$P^{(l)}$ 表示 $l$ 步转移矩阵





In practice matrices $P^{(n,+1)}=\left[p_{i j}^{(n,+1)}\right]$ are given, satisfying (1.1.1), and then a Markov chain may be defined which has these matrices as transition probability matrix using Kolmogoroff's extension theorem (Theorem 0.5.4). This process is defined by choosing initial probabilities ${ }^2$
$$
p_i=\mathbb{P}\left\{X_0=i\right\} \quad \forall i \in S
$$

and defining finite-dimensional distributions

$$
\mathbb{P}\left\{X_0=i_0, X_1=i_1, \ldots, X_n=i_n\right\}=p_{i_0} p_{i_0 i_1}^{(0,+1)} \cdots p_{i_{n-1} i_n}^{(n-1,+1)} \quad \forall i_0, \ldots, i_n \in S
$$

for all $n \geq 1$. Therefore if $X=\left(X_n\right)_{n \geq 0}$ is a Markov chain (time-homogeneous) then the distribution $\mathbb{P}_{X_n}$ of $X_n$ is such that

$$
\mathbb{P}_{X_n}(\{k\})=\mathbb{P}\left\{X_n=k\right\}\left(=\sum_{j \in S} p_j P_{j k}^{(0,+n)}\right)=\sum_{j \in S} p_j P_{j k}^n \quad \forall k \in S
$$


### 1.1.2 Examples

独立同分布比马尔可夫性更强



### 1.1.3

参考《随机过程》课件

- Accessible: State $j$ is said to be accessible from state $i$ iff $P_{i j}^n>0$ for some $n \geq 0$, and we write $i \rightarrow j$.
- Communicate: Two states $i$ and $j$ that are accessible to each other are said to communicate, and we write $i \leftrightarrow j$.
- Note: $P_{i i}^0=1 \Rightarrow$ Any state communicates with itself.
- Tree properties of the relation of communication:

  - (i) State $i$ communicates with state $i$, all $i \geq 0$; $i \leftrightarrow i \quad$ Reflexive
  - (ii) If state $i$ communicates with state $j$, then state $j$ communicates with state $i$;

  $$
  i \leftrightarrow j \Rightarrow j \leftrightarrow i \quad \text { Symmetric }
  $$

    - (iii) If state $i$ communicates with state $j$, and state $j$ communicates with state $k$, then state $i$ communicates with state $k$.

$$
i \leftrightarrow j, j \leftrightarrow k \Rightarrow i \leftrightarrow k \quad \text { Transitive }
$$





- **Class（类）**: Two states that communicate are said to be in the same *class*. 
  - *Note*: Any two classes of states are either identical or disjoint.

- **Irreducible（不可约）**: The Markov chain is said to be *irreducible* if there is only one class, that is, if all states communicate with each other.
