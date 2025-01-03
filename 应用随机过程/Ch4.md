# Ch4

## 4.1

4.1.1 Lemma (Itô Isometry). Let $\phi=\left(\phi_t\right)_{t \geq 0} \in \mathscr{L}^2$ be simple and $0 \leq S<T \leq \infty$. Then $\mathcal{I}[\phi]_S^T \in L^2(\Omega, \mathscr{F}, \mathbb{P})$ and
$$
\mathrm{E}\left[\left(\int_S^T \phi_t d B_t\right)^2\right]^{1 / 2}=\mathrm{E}\left[\int_S^T \phi_t^2 d t\right]^{1 / 2}
$$

Particularly, $\|\mathcal{I}[\phi]\|_2=\|\phi\|_2$.
Note (Exercise!). Let $\xi$ be a random variable independent of $B$. If $\phi \in \mathcal{F}^{\xi, B}$, then Lemma 4.1.1 still holds.



The idea now is to use the isometry Lemma 4.1.1 to extend the definition from simple functions to general functions in $\mathscr{L}^2$. We do this in several steps.

Step 1. Let $g=\left(g_t(\omega)\right)_{t \geq 0} \in \mathscr{L}^2$ be bounded and $g_t(\omega)$ continuous in $t$ for each $\omega$. Then there exists a sequence of simple functions $\phi^{(n)} \in \mathscr{L}^2$ such that

$$
\mathrm{E}\left[\int_0^{\infty}\left(g_t-\phi_t^{(n)}\right)^2 d t\right] \rightarrow 0 \quad \text { as } n \rightarrow \infty
$$

that is, $\lim _{n \rightarrow \infty}\left\|g-\phi^{(n)}\right\|_2=0$.
Proof. For any integer $n>0$, define

$$
\phi_t^{(n)}(\omega)=\sum_{j=0}^{2^{2 n}-1} g\left(t_j, \omega\right) 1_{\left[t_j, t_{j+1}\right)}(t)
$$
where $0=t_0<t_1<t_2<\cdots$ is a $2^{-n}$-partition of $\mathbb{R}_{+}$by

$$
t_j=\frac{j}{2^n}, \quad j=0,1,2, \ldots
$$


Then $\phi^{(n)}=\left(\phi_t^{(n)}\right)_{t \geq 0} \in \mathscr{L}^2$ is simple, and by Vitali's (Lebesgue's dominated) convergence theorem for $d t \otimes \mathbb{P}(d \omega)$ (noting that $\left\{\phi^{(n)}\right\}$ is uniformly integrable ${ }^2$ ),

$$
\int_{\Omega} \int_0^{\infty}\left(g_t(\omega)-\phi_t^{(n)}(\omega)\right)^2 d t d \mathbb{P}(\omega) \rightarrow 0 \quad \text { as } n \rightarrow \infty
$$

This completes the proof of Step 1 .

>  ${ }^2$ Since $\beta:=\|g\|_{\infty}<\infty$, so $\left|\phi^{(n)}-g\right|^2 \leq 4 \beta^2$ and thus $\left\{\left|\phi^{(n)}-g\right|^2\right\}$ is uniformly integrable on $[0, \infty) \times \Omega$.

Step 2. Let $h=\left(h_t(\omega)\right)_{t \geq 0} \in \mathscr{L}^2$ be bounded. Then there exists a sequence of bounded $t$-continuous functions $g^{(n)} \in \mathscr{L}^2$, and

$$
\mathrm{E}\left[\int_0^{\infty}\left(h_t-g_t^{(n)}\right)^2 d t\right] \rightarrow 0 \quad \text { as } n \rightarrow \infty
$$

that is, $\lim _{n \rightarrow \infty}\left\|h-g^{(n)}\right\|_2=0$.
Proof. Suppose $|h(t, \omega)| \leq M<\infty$ for all $(t, \omega)$. For any $n>1$, let $\psi_n$ be a nonnegative continuous function on $\mathbb{R}$ such that
(i) $\psi_n(x)=0$ for $x \leq-\frac{1}{n}$ and $x \geq 0$; and
(ii) $\int \psi_n(x) d x=1$.

Now define

$$
g^{(n)}(t, \omega)=\int_0^t \psi_n(s-t) h(s, \omega) d s
$$


Then $g^{(n)}(t, \omega)$ is continuous in $t$ for each $\omega$ and $\left|g^{(n)}\right| \leq M$. We can show $g^{(n)}$ is adapted to $\mathcal{F}$ and jointly measurable in $(t, \omega)$. Moreover,

$$
\int_0^{\infty}\left(g_t^{(n)}-h_t\right)^2 d t \rightarrow 0 \quad \text { as } n \rightarrow \infty
$$

by $\psi_n(s-t) d s \rightarrow \delta_t(d s)$ as $n \rightarrow \infty$ in the sense of weak-* topology, and therefore $\lim _{n \rightarrow \infty}\left\|h-g^{(n)}\right\|_2=0$ by Vitali's convergence theorem and $g^{(n)} \in \mathscr{L}^2$.

This completes the proof of Step 2.
Step 3. Let $f=\left(f_t(\omega)\right)_{t \geq 0} \in \mathscr{L}^2$. Then there exists a sequence of bounded functions $h^{(n)} \in \mathscr{L}^2$ such that

$$
\mathrm{E}\left[\int_0^{\infty}\left(f_t-h_t^{(n)}\right)^2 d t\right] \rightarrow 0 \quad \text { as } n \rightarrow \infty
$$

that is, $\lim _{n \rightarrow \infty}\left\|f-h^{(n)}\right\|_2=0$.

Proof. For any $n \geq 1$, define a bounded function

$$
h^{(n)}(t, \omega)= \begin{cases}f(t, \omega) & \text { if }-n \leq f(t, \omega) \leq n \\ 0 & \text { if }|f(t, \omega)|>n\end{cases}
$$

Then $\left|h^{(n)}(t, \omega)\right| \leq|f(t, \omega)|$ and the conclusion follows by the dominated convergence theorem.



Uniformly integrable
Let $f_n$ be measurable functions on $(\Omega, \mathscr{B}, P)$. Motivated by

$$
\xi \in L^1 \Leftrightarrow \lim _{a \rightarrow \infty} \int_{\{|\xi| \geq a\}}|\xi| d P=0
$$

now $\left\{f_n\right\}$ is referred to as uniformly integrable (cf. Section 0.7.6 for more detailed formulations) if

$$
\lim _{\alpha \rightarrow \infty} \sup _n \int_{\left\{\left|f_n\right| \geq \alpha\right\}}\left|f_n(\omega)\right| P(d \omega)=0
$$


Then the following covers the Lebesgue dominated convergence theorem.
0.2.8 Theorem (Vitali's convergence theorem). Suppose that $f_n \rightarrow f$ a.e. (P). If the $f_n$ are uniformly integrable, then $f$ is integrable and such that

$$
\int f_n d P \rightarrow \int f d P
$$


This theorem will be extended by Theorem 0.7 .9 in Section 0.7.6. It should be noticed that the foregoing four convergence theorems still hold for measure space $(\Omega, \bar{B}, \mu)$ instead of a probability space.



## 4.3



4.3.6 Lemma. Let $v(t, \omega) \in \mathscr{L}^2$ and $g(t, x) \in \mathrm{C}^2([0, \infty) \times \mathbb{R})$ be any given. If

$$
d g\left(t, X_t\right)=\left[\frac{\partial g}{\partial t}\left(t, X_t\right)+u \frac{\partial g}{\partial x}\left(t, X_t\right)+\frac{1}{2} v^2 \frac{\partial^2 g}{\partial x^2}\left(t, X_t\right)\right] d t+v \frac{\partial g}{\partial x}\left(t, X_t\right) d B_t
$$

for any Itô process $X_t$ given by

$$
d X_t=u d t+v d B_t \quad \text { where } u \in \mathscr{L}^{\infty}
$$

then the Itô formula (4.3.6) also holds for any Itô process $X_t$ given by

$$
d X_t=u d t+v d B_t \quad \text { where } u \in \mathscr{L}^1
$$


Proof. Define

$$
u^{(n)}(t, \omega)= \begin{cases}u(t, \omega) & \text { if }|u(t, \omega)| \leq n \\ 0 & \text { if others }\end{cases}
$$


Then $u^{(n)}(t, \omega) \rightarrow u(t, \omega)$ a.e. and $u^{(n)} \in \mathscr{L}^{\infty}$. Without loss of generality, assume $g, \partial g / \partial t$, $\partial g / \partial x, \partial^2 g / \partial t \partial x$ and $\partial^2 g / \partial x^2$ all are bounded. Given any $t>0$, we need only to prove that

$$
\int_0^t u^{(n)} \frac{\partial g}{\partial x} d s \xrightarrow{\text { a.e. }} \int_0^t u \frac{\partial g}{\partial x} d s \quad \text { as } n \rightarrow \infty .
$$


However, this is obvious by the dominated convergence theorem.