### 1.2.3 Examples of recurrent Markov chains

$1 D$-random walk on $\mathbb{Z}$. Consider the random walk $X=\left\{X_n\right\}_{n \geq 0}$ on $\mathbb{Z}$, where at each transition the particle moves with probability $p$ one unit to the right and with probability $q=1-p$ one unit to the left $(0<p<1)$. It is irreducible and not aperiodic. In fact, $d=2$. Hence
$$
p_{00}^{(2 n+1)}=0 \forall n \geq 0, \quad \text { and } \quad p_{00}^{(2 n)}=\binom{2 n}{n} p^n q^n=\frac{(2 n)!}{n!n!} p^n q^n \forall n \geq 0 .
$$


We appeal now to Stirling's formula: as $n$ sufficiently big,

$$
n!\sim n^{n+\frac{1}{2}} e^{-n \sqrt{2 \pi}}
$$


Applying the Stirling formula we obtain

$$
p_{00}^{(2 n)} \sim \frac{(p q)^n 2^{2 n}}{\sqrt{\pi n}}=\frac{(4 p q)^n}{\sqrt{\pi n}} .
$$


It is readily verified that

$$
p(1-p)=p q \leq \frac{1}{4} \quad \text { with equality holding iff } p=q=\frac{1}{2}
$$

Hence, $\sum_{n=1}^{+\infty} p_{00}^{(n)}=\infty$ if and only if $p=\frac{1}{2}$. Therefore, from Theorem 1.2.1, it follows that
The one-dimensional random walk on $\mathbb{Z}$ is recurrent iff $p=q=\frac{1}{2}$; i.e., "symmetric".



$\binom{2 n}{n} \sim \frac{4^n}{\sqrt{\pi n}}$



1.3.1 Nonrecurrent case and definition

First of all, by Theorem 1.2.9 there follows some simple facts:
Let $k \in S$ be non-recurrent. Then $\lim _{n \rightarrow \infty} p_{i j}^{(n)}=0 \forall i, j \in C(k)$.
However, even in the recurrent case, this phenomenon still might occur; For example, the symmetric one-dimensional random walk on $\mathbb{Z}$ (Example 1 in Section 1.2.3), $p_{00}^{(2 n)} \sim 1 / \sqrt{\pi n} \rightarrow 0$ and $p_{00}^{(n)} \rightarrow 0$.

Let $k \in S$. If $\lim _{n \rightarrow \infty} p_{i j}^{(n)}=0$ for some $i, j \in C(k)$, then $\lim _{n \rightarrow \infty} p_{i j}^{(n)}=0 \forall i, j \in C(k)$. 10
If $k$ is recurrent, then $\sum_{n=1}^{\infty} p_{i j}^{(n)}=\infty \forall i, j \in C(k)$
It is known that by the equality $(*)$ on p. 45 and Theorems 1.2.1 and 1.2.10 in $\S 1.2 .1$ and $\S 1.2 .2$.



${ }^9$ Exercise Let $P$ be an irreducible $N \times N$ Markov matrix where $N<\infty$. Prove it is (positive) recurrent (cf. Corollary 1.3 .10 ).



(P52 Footnote10) Let $k \in S$. If $\lim _{n \rightarrow \infty} p_{i j}^{(n)}=0$ for some $i, j \in C(k)$, then $\lim _{n \rightarrow \infty} p_{i j}^{(n)}=0 \forall i, j \in C(k)$. 

Proof. The statement comes from the fact that $p_{i^{\prime} j^{\prime}}^{(n+m+\ell)} \geq p_{i^{\prime} i}^{(n)} p_{i j}^{(m)} p_{j j^{\prime}}^{(\ell)}$.