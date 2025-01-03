Chapter 2

Optimal Stopping Times of Markov Chains

This chapter will need the notion "conditional expectations" defined in $\S 0.4$.
Consider a fair game in which on each play a dollar is won or lost with equal probability. We let $Y_1, Y_2, \ldots$ be independent identically distributed random variables with

$$
\mathbb{P}\left\{Y_n=+1\right\}=\mathbb{P}\left\{Y_n=-1\right\}=\frac{1}{2}
$$


Let $X_n=Y_1+\cdots+Y_n$ be the player's net gain at stage $n$. We know that $\mathrm{E}\left[X_n\right]=0$, the mean net gain is zero. But the player need not play forever, nor need he predetermine a particular time $n$ for stopping. Rather, he might let the choice of when to stop be determined depending on how the game evolves. For example he might try to stop when ahead.

Let $T$ be the time the player ends his play and let $X_T$ be his net gain then. We know $\mathrm{E}\left[X_n\right]=0$ for all $n$, but is it necessarily true that $\mathrm{E}\left[X_T\right]>0$ ? Can the player stop when ahead? The answer is "yes" but there are a number of qualifications. For that, we need to introduce a concept-Markov time. Markov times, also called stopping times sometimes, occur in many contexts. In this chapter, let

$$
Y=\left\langle Y_n:(\Omega, \mathscr{F}, \mathbb{P}) \rightarrow \mathbb{Z}_{+}\right\rangle_{n \geq 0}
$$

be a Markov chain with the transition probability matrix $P=\left(p_{i j}\right)$. In fact, many of our arguments do not need the Markov property of $Y$.



## 2.1

### 2.1.1

2.1.1 Definition. A function $T: \Omega \rightarrow \mathbb{Z}_{+} \cup\{+\infty\}$ is called a Markov time, or sometimes stopping time with respect to $Y$ if, for every $n \in \mathbb{Z}_{+}$, the event $\{T=n\}$ is determined by $\left\{Y_0, \ldots, Y_n\right\}$.

Question: Is, for $j \in S=\mathbb{Z}_{+}$, the first visiting time $T_j$ defined in $\S 1.2 .1$ a Markov time?
Exercise 1. If $T$ is a Markov time, then for every $n$ the events $\{T \leq n\},\{T>n\},\{T \geq n\}$, and $\{T<n\}$ are also determined by $\left\{Y_0, \ldots, Y_n\right\}$.
Exercise 2. Conversely, if for every $n$, the event $\{T \leq n\}$ is determined by $\left\{Y_0, \ldots, Y_n\right\}$, then $T$ is a Markov time. Or, if for every $n$, the event $\{T>n\}$ is determined by $\left\{Y_0, \ldots, Y_n\right\}$, then $T$ is a Markov time.

Exercise 3. Let for every $n$, the event $\{T \geq n\}$ be determined by $\left\{Y_0, \ldots, Y_n\right\}$. Is $T$ necessarily a Markov time? Provide a proof or a counterexample to support your claim.
2.1.2 Some examples of Markov times
(a) The fixed time $T \equiv k$, for any $0 \leq k \leq+\infty$, is a Markov time.
(b) The first time when the process $Y$ reaches a subset $A \subset \mathbb{Z}_{+}$, i.e., $T_A=\min \left\{n \geq 0: Y_n \in A\right\}$, is a Markov time. (Particularly, $A=\{j\}$ or $=$ a recurrent class.)
(c) More generally, for any fixed $k \geq 1$, the $k$ th time when process visits a set $A$ is a Markov time $T_A^{(k)}$. However, the last time $l_A$ a process visits a set $A$ is not a Markov time.



### 2.1.3 Elementary properties of Markov times
(1) If $T_1$ and $T_2$ are Markov times, then so is $T_1+T_2$.
(2) The smaller of two Markov times $T_1, T_2$, denoted by $T_1 \wedge T_2=\min \left\{T_1, T_2\right\}$, is also a Markov time. This is clear because of the relation
$$
\left\{T_1 \wedge T_2>n\right\}=\left\{T_1>n, T_2>n\right\}=\left\{T_n>n\right\} \cap\left\{T_2>n\right\} \in \sigma\left(Y_0, Y_1, \ldots, Y_n\right)
$$

(3) If $T_1$ and $T_2$ are Markov times, then so is the larger $T_1 \vee T_2=\max \left\{T_1, T_2\right\}$, since

$$
\left\{T_1 \vee T_2 \leq n\right\}=\left\{T_1 \leq n\right\} \cap\left\{T_2 \leq n\right\} \in \sigma\left(Y_0, Y_1, \ldots, Y_n\right)
$$

(4) Let $T$ be a Markov time. If $\mathbb{P}\{T<+\infty\}=1$, then $Y_T: \Omega \rightarrow \mathbb{Z}_{+}$is a random variable because of $Y_T(\omega)=\sum_{n=0}^{+\infty} \mathbb{1}_{\{T=n\}}(\omega) Y_n(\omega)$ for a.e. $\omega \in \Omega$.

The following lemma will be useful for optional stopping theorems in the martingale theory.
2.1.2 Lemma. Let $W \in L^1(\Omega, \mathscr{F}, \mathbb{P})$ and let $T$ be a Markov time such that $\mathbb{P}\{T<+\infty\}=1$. Then

$$
\lim _{n \rightarrow+\infty} \mathrm{E}\left[W \mathbb{1}_{\{T>n\}}\right]=0 \quad \text { and } \quad \lim _{n \rightarrow+\infty} \mathrm{E}\left[W \mathbb{1}_{\{T \leq n\}}\right]=\mathrm{E}[W]
$$







## 2.2 The optimal stopping times of Markov chains

Let $f: \mathbb{Z}_{+} \rightarrow \mathbb{R}$ be the profit function of the game, which is bounded, i.e. $|f(k)| \leq \beta$ for all $k \geq 0$ for some $\beta<\infty$. So, $f(k)$ means that if the process $\left\langle Y_n(\omega)\right\rangle_{n \geq 0}$ stops at the state $k$ (i.e., $Y_T(\omega)=k$, where $T$ is a stopping time - a strategy), then the profit of player $\omega$ is $f\left(Y_T(\omega)\right)=f(k)$. For a stopping time $T$, the expectation profit is $\mathrm{E}\left[f\left(Y_T\right)\right]$. If $\mathrm{E}\left[f\left(Y_n\right)\right]=0$ for all $n \geq 0$, then we wish to find "good" $T$ so that $\mathrm{E}\left[f\left(Y_T\right)\right]>0$.

To seek the best $\mathrm{E}\left[f\left(Y_T\right)\right]$, for every $k \in \mathbb{Z}_{+}$let

$$
\begin{gathered}
v(k)=\max _T \mathrm{E}\left[f\left(Y_T\right): Y_0=k\right] \\
\left(\mathrm{E}\left[f\left(Y_T\right): Y_0=k\right]=\mathbb{P}\left(Y_0=k\right)^{-1} \int 1_{\left\{Y_0=k\right\}} f\left(Y_T\right) d \mathbb{P}=\mathrm{E}_{\mathbb{P}\left(\cdot \mid Y_0=k\right)}\left[f\left(Y_T\right)\right]\right),
\end{gathered}
$$

where $T$ runs over all stopping times of $Y$ with $T<\infty$; which is called the value of the state $k$ under the optimal stopping strategy. Our aim is to find an optimal stopping time or equivalently the values $v(k)$.

Clearly, the maximal-value sequence $v=(v(k))_{k \in \mathbb{Z}_{+}}$should satisfy the following two inequalities:

$$
v \geq f(\text { i.e. } v(k) \geq f(k) \forall k \geq 0)
$$

and

$$
\left.v \geq P v \text { (i.e. } v(k) \geq \sum_{j \geq 0} p_{k j} v(j) \forall k \geq 0\right) \text {. }
$$


In fact,

$$
v(k)=\max \left\{f(k), \sum_j p_{k j} v(j)\right\} \quad \forall k \geq 0 .
$$


Let $\mathbb{T}$ be a stopping time such that $v(k)=\mathrm{E}\left[f\left(Y_{\mathrm{T}}\right): Y_0=k\right]$ for all $k \geq 0$ and $\mathbb{P}\{\mathbb{T}<\infty\}=1$; that is, $\mathbb{T}$ is an optimal stopping time. For example, assume and write



### 2.2.1 Super harmonic sequences

We shall consider the properties of the value sequence $v=(v(k))_{k \geq 0}$ under the optimal stopping strategy. A sequence $u=(u(k))_{k \geq 0}$ of real numbers is called super $\bar{h}$ armonic associated to $P$, if it satisfies

$$
\|u\|_{\infty}:=\sup _k|u(k)|<+\infty \quad \text { and } \quad u \geq P u ; \quad \text { i.e., } u(k) \geq \sum_{j \geq 0} p_{k j} u(j) \forall k \geq 0 .
$$


Clearly, $v=(v(k))_{k \geq 0}$ is a super harmonic sequence by (2.2.2).
Let $T$ be a stopping time in what follows. Then there holds the following optional stopping lemma:
2.2.1 Lemma (Optional stopping lemma). Let $u=(u(k))_{k \geq 0}$ be a super harmonic sequence of $P$. Then

$$
u(k) \geq \mathrm{E}\left[u\left(Y_{T \wedge n}\right): Y_0=k\right] \geq \mathrm{E}\left[u\left(Y_n\right): Y_0=k\right]
$$

for all $k \geq 0$ and $n \geq 0$, where $\mathrm{E}[X: A]=\mathbb{P}(A)^{-1} \int_A X d \mathbb{P}$ for all $A \in \mathscr{F}$ with $\mathbb{P}(A)>0$.



Secondly, we claim

$$
\mathrm{E}\left[u\left(Y_n\right) \mathbb{1}_{\{T=\ell\}} \mid Y_0=k\right] \leq \mathrm{E}\left[u\left(Y_{\ell}\right) \mathbb{1}_{\{T=\ell\}} \mid Y_0=k\right] \quad \forall n \geq \ell .
$$

(Exercise). (2.2.4) follows from

$$
\begin{aligned}
\mathrm{E}\left[u\left(Y_n\right) \mathbb{1}_{\{T=\ell\}} \mid Y_0=k\right] & =\mathrm{E}\left[\mathrm{E}\left[u\left(Y_n\right) \mathbb{1}_{\{T=\ell\}} \mid Y_0, \ldots, Y_{\ell}\right] \mid Y_0=k\right] \\
& =\mathrm{E}\left[\mathbb{1}_{\{T=\ell\}} \mathrm{E}\left[u\left(Y_n\right) \mid Y_0, \ldots, Y_{\ell}\right] \mid Y_0=k\right] \\
& \leq \mathrm{E}\left[u\left(Y_{\ell}\right) \mathbb{1}_{\{T=\ell\}} \mid Y_0=k\right]
\end{aligned}
$$

by $(2.2 .3)$ for $n=\ell+(n-\ell)$.



补充：条件期望的塔性质（又称为「分解性质」或「迭代法则」）是概率论中的一个重要性质，描述了条件期望的迭代过程。

（以下内容来自 MIT 15.070J / 6.265J Advanced Stochastic Processes Fall 2013 Lec9 课件）

Tower property. Suppose $\mathcal{G}_1 \subset \mathcal{G}_2 \subset \mathcal{F}$. Then $\mathbb{E}\left[\mathbb{E}\left[X \mid \mathcal{G}_1\right] \mid \mathcal{G}_2\right]=\mathbb{E}\left[X \mid \mathcal{G}_1\right]$ and $\mathbb{E}\left[\mathbb{E}\left[X \mid \mathcal{G}_2\right] \mid \mathcal{G}_1\right]=\mathbb{E}\left[X \mid \mathcal{G}_1\right]$. That is the smaller field wins.

Proof. By definition $\mathbb{E}\left[X \mid \mathcal{G}_1\right]$ is $\mathcal{G}_1$ measurable. Therefore it is $\mathcal{G}_2$ measurable. Then the first equality follows from the fact $\mathbb{E}[X \mid \mathcal{G}]=X$, when $X \in \mathcal{G}$, which we established earlier. Now fix any $A \in \mathcal{G}_1$. Denote $\mathbb{E}\left[X \mid \mathcal{G}_1\right]$ by $Y_1$ and $\mathbb{E}\left[X \mid \mathcal{G}_2\right]$ by $Y_2$. Then $Y_1 \in \mathcal{G}_1, Y_2 \in \mathcal{G}_2$. Then

$$
\mathbb{E}\left[Y_1 1\{A\}\right]=\mathbb{E}[X 1\{A\}]
$$

simply by the definition of $Y_1=\mathbb{E}\left[X \mid \mathcal{G}_1\right]$. On the other hand, we also have $A \in \mathcal{G}_2$. Therefore

$$
\mathbb{E}[X 1\{A\}]=\mathbb{E}\left[Y_2 1\{A\}\right]
$$


Combining the two equalities we see that $\mathbb{E}\left[Y_2 1\{A\}\right]=\mathbb{E}\left[Y_1 1\{A\}\right]$ for every $A \in \mathcal{G}_1$. Therefore, $\mathbb{E}\left[Y_2 \mid \mathcal{G}_1\right]=Y_1$, which is the desired result.

An important special case is when $\mathcal{G}_1$ is a trivial $\sigma$-field $\{\varnothing, \Omega\}$. We obtain that for every field $\mathcal{G}$

$$
\mathbb{E}[\mathbb{E}[X \mid \mathcal{G}]]=\mathbb{E}[X]
$$