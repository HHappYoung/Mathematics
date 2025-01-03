# Chapter 3 Martingale

This chapter will be devoted to providing an introduction to the important Martingale Theory.

## 3.1 Definitions and basic properties

Let $\mathbb{R}=(-\infty,+\infty)$ and $\mathbb{T} \subseteq \mathbb{R}$ as our time-parameter space. Based on a probability space $(\Omega, \mathscr{F}, \mathbb{P})$, a collection of sub $\sigma$-fields $\left(\mathscr{F}_t\right)_{t \in \mathbb{T}}$ of $\mathscr{F}$ is called a filtration if $\mathscr{F}_s \subseteq \mathscr{F}_t$ for all $s<t$ in $\mathbb{T}$. For example, let $Y=\left(Y_n\right)_{n \geq 0}$ be a Markov chain, then $\mathscr{F}_n=\sigma\left(Y_0, \ldots, Y_n\right), n=0,1, \ldots$ is a filtration. Write $\mathscr{F}_{\infty}=\bigvee_{t \in \mathbb{T}} \mathscr{F}_t=\sigma\left(\bigcup_{t \in \mathbb{T}} \mathscr{F}_t\right)$. From now on, let $(\Omega, \mathscr{F}, \mathbb{P})$ and a filtration $\left(\mathscr{F}_t\right)_{t \in \mathbb{T}}$ be any given unless stated otherwise.

If $\mathbb{T}=\mathbb{Z}_{+}$or $[0,+\infty)$, then we let $\overline{\mathbb{T}}=\mathbb{T} \cup\{+\infty\}$; on the other hand, if $\mathbb{T}=\mathbb{Z}_{-}$or $(-\infty, 0]$, then we let $\overline{\mathbb{T}}=\mathbb{T} \cup\{-\infty\}$



3.1.1 Definitions and basic properties

Let $\left(\mathscr{F}_t\right)_{t \in \mathbb{T}}$ be any given filtration for a probability space $(\Omega, \mathscr{F}, \mathbb{P})$, where $\mathbb{T} \subseteq \mathbb{R}$.
3.1.1 Definition. A stochastic process $X=\left(X_t\right)_{t \in \mathbb{T}}$ is called a martingale (resp. sub-martingale, super-martingale) relative to $\left(\mathscr{F}_t\right)_{t \in \mathbb{T}}$ if it holds the following conditions:
- $X$ is adapted to $\left(\mathscr{F}_t\right)_{t \in \mathbb{T}}$; i.e., $X_t \in \mathscr{F}_t$ for all $t \in \mathbb{T}$.
- $X_t \in L^1(\Omega, \mathscr{F}, \mathbb{P})$ for all $t \in \mathbb{T}$.
- $\mathrm{E}\left[X_t \mid \mathscr{F}_s\right]=($ resp. $\geq, \leq) X_s$ a.e. for any $s, t \in \mathbb{T}$ with $s<t$.

Further, for $\mathbb{T}=\mathbb{Z}_{+}$or $[0,+\infty)$, a random variable $\left.X_{\infty} \in L^1(\Omega, \mathscr{F})_{\infty}, \mathbb{P}\right)$ is called a right-closed element of $X$ if

$$
\mathrm{E}\left[X_{\infty} \mid \mathscr{F}_t\right]=(\text { resp. } \geq, \leq) X_t \text { a.e. } \quad \forall t \in \mathbb{T} .
$$

Similarly, we can define a left-closed element of $X$ for $\mathbb{T}=\mathbb{Z}_{-}$or $\mathbb{R}_{-}$.
Exercise. If $X$ is a martingale (resp. submartingale, supermartingale) and $0 \leq s<t$, then
$$
\mathrm{E}\left[X_t \mid X_s\right]=(\text { resp. } \geq, \leq) X_s \quad \text { and } \quad \mathrm{E}\left[X_t\right]=(\text { resp. } \geq, \leq) \mathrm{E}\left[X_0\right]
$$


3.1.2 Lemma. The following basic properties hold:
(1) If $X=\left(X_t\right)_{t \in \mathbb{T}}$ and $Y=\left(Y_t\right)_{t \in \mathbb{T}}$ are two martingales then $\left(a X_t+b Y_t\right)_{t \in \mathbb{T}}$ is a martingale for all $a, b \in \mathbb{R}$.
(2) If $X=\left(X_t\right)_{t \in \mathbb{T}}$ and $Y=\left(Y_t\right)_{t \in \mathbb{T}}$ are two supermartingales (submartingales) then $\left(a X_t+b Y_t\right)_{t \in \mathbb{T}}$ is a supermartingale (submartingale) for any $a, b \in \mathbb{R}_{+}$.
(3) If $X=\left(X_t\right)_{t \in \mathbb{T}}$ and $Y=\left(Y_t\right)_{t \in \mathbb{T}}$ are two supermartingales (submartingales) then

$$
X \wedge Y=\left(X_t \wedge Y_t\right)_{t \in \mathbb{T}} \quad\left(X \vee Y=\left(X_t \vee Y_t\right)_{t \in \mathbb{T}}\right)
$$

is a supermartingale (submartingale).
(4) Let $X=\left(X_t\right)_{t \in \mathbb{T}}$ be a martingale. If $f: \mathbb{R} \rightarrow \mathbb{R}$ is a convex function with $f\left(X_t\right) \in L^1$, then $f(X)=\left(f\left(X_t\right)\right)$ is a submartingale.
(5) Let $X=\left(X_t\right)_{t \in \mathbb{T}}$ be a submartingale. If $f: \mathbb{R} \rightarrow \mathbb{R}$ is nondecreasing convex with $f\left(X_t\right) \in L^1$, then $f(X)=\left(f\left(X_t\right)\right)$ is a submartingale.

注：$X \wedge Y = \min \{X,Y\}$ 



## 3.4 Convergence theorem

If $X=\left(X_n\right)_{n \in \mathbb{Z}_{+}}$is a martingale, we ask if or not $X_n \rightarrow X_{\infty}$ and $X_{\infty}$ is a closed element. For that the following is a powerful tool.
3.4.1 Theorem (Doob-Snell upcrossing inequality). Let $X=\left(X_n\right)_{n \in \mathbb{Z}}$ be a submartingale and for any $a<b$ in $\mathbb{R}$ and $N_1<N_2$ in $\mathbb{Z}$ let
$$
V_a^b\left(X ; N_1, N_2\right)=\#\left\{(i, j) \mid N_1 \leq i<j \leq N_2, X_i \leq a<X_k<b \leq X_j \text { for } i<k<j\right\}
$$
denote the number of $[a, b]$-upcrossings of $X$ from time $N_1$ to $N_2$. Then

$$
\mathrm{E}\left[V_a^b\left(X ; N_1, N_2\right)\right] \leq \frac{1}{b-a}\left\{\mathrm{E}\left[\left(X_{N_2}-a\right)^{+}\right]-\mathrm{E}\left[\left(X_{N_1}-a\right)^{+}\right]\right\} \leq \frac{\mathrm{E}\left[\left(X_{N_2}-a\right)^{+}\right]}{b-a}
$$


Proof. First note that for all $a<b$,

$$
V_a^b\left(X ; N_1, N_2\right)=V_0^{b-a}\left(X-a ; N_1, N_2\right)=V_0^{b-a}\left((X-a)^{+} ; N_1, N_2\right)
$$

and set $Y=(X-a)^{+}$that is a submartingale. Then $V_0^{b-a}\left(Y ; N_1, N_2\right) \leq N_2-N_1$. Next define stopping times:

$$
\begin{array}{ll}
\sigma_1=\min \left\{n: Y_n=0, N_1 \leq n \leq N_2\right\}, & \tau_1=\min \left\{n: Y_n \geq b-a, \sigma_1<n \leq N_2\right\} \\
\sigma_2=\min \left\{n: Y_n=0, \tau_1<n \leq N_2\right\}, & \tau_2=\min \left\{n: Y_n \geq b-a, \sigma_2<n \leq N_2\right\} \\
\ldots & \ldots \\
\sigma_k=\min \left\{n: Y_n=0, \tau_{k-1}<n \leq N_2\right\}, & \tau_k=\min \left\{n: Y_n \geq b-a, \sigma_k<n \leq N_2\right\} \\
\ldots & \ldots
\end{array}
$$

and let

$$
\min \{\emptyset\}=N_2
$$


Clearly

$$
\left(Y_{\tau_1}-Y_{\sigma_1}\right)+\cdots+\left(Y_{\tau_{v_0^{b-a}\left(Y_{;} N_1, N_2\right)}}-Y_{\sigma_{V_0^{b-a}\left(Y ; N_1, N_2\right)}}\right) \geq(b-a) V_0^{b-a}\left(Y ; N_1, N_2\right)
$$


Taking expectation,

$$
\mathrm{E}\left[Y_{\tau_1}-Y_{\sigma_1}\right]+\cdots+\mathrm{E}\left[Y_{\tau_{V_0^{b-a}}^{\left(Y_{\left.; N_1, N_2\right)}\right.}}-Y_{\sigma_{V_0^{b-a}\left(Y_{;} N_1, N_2\right)}}\right] \geq(b-a) \mathrm{E}\left[V_0^{b-a}\left(Y ; N_1, N_2\right)\right] .
$$


In addition, by Doob's bounded-stopping-time theorem, it follows that

$$
\begin{aligned}
& \mathrm{E}\left[Y_{\sigma_i}-Y_{\tau_{i-1}}\right] \geq 0, \quad i=1,2, \ldots, V_0^{b-a}\left(Y ; N_1, N_2\right), \text { where } \tau_0=N_1, \\
& \mathrm{E}\left[Y_{N_2}-Y_{\tau_{v_0^{b-a}}}, Y_{\left(Y_i N_1, N_2\right)}\right] \geq 0
\end{aligned}
$$


Adding these to the above inequality follows that

$$
\mathrm{E}\left[Y_{N_2}-Y_{N_1}\right] \geq(b-a) \mathrm{E}\left[V_0^{b-a}\left(Y ; N_1, N_2\right)\right] \Rightarrow \mathrm{E}\left[V_0^{b-a}\left(Y ; N_1, N_2\right)\right] \leq \frac{\mathrm{E}\left[Y_{N_2}\right]-\mathrm{E}\left[Y_{N_1}\right]}{b-a}
$$


This completes the proof of Theorem 3.4.1.



3.4.6 Lemma (Doob's uniform integrability lemma). Let $\xi \in L^1(\Omega, \mathscr{F}, \mathbb{P})$ and $\xi_{\mathcal{F}}=\mathrm{E}[\xi \mid \mathcal{F}]$ for every $\sigma$-subalgebra $\mathcal{F} \subseteq \mathscr{F}$. Then $\left\{\xi_{\mathcal{F}} \mid \mathcal{F} \subseteq \mathscr{F}\right\}$ is uniformly integrable.