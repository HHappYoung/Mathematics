矩母函数MGF

The Moment Generating Function $\phi(t)$ of the random variable $X$ is defined for all values $t$ by
$$
\phi(t)=\mathrm{E}\left(e^{t X}\right)
$$


Important Fact: There is a one-to-one correspondence between the moment generating function for a r.v. and its probability distribution (pmf or pdf).

$$
\begin{aligned}
& \text { Example: } X \sim N\left(\mu, \sigma^2\right): f_X(x)=\frac{1}{\sqrt{2 \pi \sigma^2}} e^{-(x-\mu)^2 / 2 \sigma^2} \\
& \qquad \begin{aligned}
& \phi_X(t)=\mathrm{E}\left(e^{t X}\right)=\int_{-\infty}^{\infty} \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-(x-\mu)^2 / 2 \sigma^2} e^{t x} d x \\
= & \int_{-\infty}^{\infty} \frac{1}{\sqrt{2 \pi \sigma^2}} e^{- \left(x^2-2 \mu x-2 \sigma^2 t x+\mu^2\right) / 2 \sigma^2} d x \\
= & e^{t \mu+t^2 \sigma^2 / 2} \int_{-\infty}^{\infty} \frac{1}{\sqrt{2 \pi \sigma^2}} e^{-\frac{\left(x-\left(\mu+t \sigma^2\right)\right)^2}{2 \sigma^2}} d x \\
= & e^{t \mu+t^2 \sigma^2 / 2}
\end{aligned}
\end{aligned}
$$
We call $\phi(t)$ the moment generating function because all of the moments of $X$ can be obtained by successively differentiating $\phi(t)$ :

$$
\phi^{\prime}(0)=\mathrm{E}(X) \quad \phi^{\prime \prime}(0)=\mathrm{E}\left(X^2\right) \quad \phi^n(0)=\mathrm{E}\left(X^n\right), n \geq 1
$$


Example: $X \sim N\left(\mu, \sigma^2\right) \Rightarrow \phi(t)=e^{t \mu+t^2 \sigma^2 / 2}$

$$
\begin{aligned}
& \phi^{\prime}(t)=\left(\mu+t \sigma^2\right) e^{t \mu+t^2 \sigma^2 / 2} \\
& \phi^{\prime \prime}(t)=\left(\mu+t \sigma^2\right)^2 e^{t \mu+t^2 \sigma^2 / 2}+\sigma^2 e^{t \mu+t^2 \sigma^2 / 2}
\end{aligned}
$$


Therefore, we have
- $\mathrm{E}(X)=\phi^{\prime}(0)=\mu$
- $\mathrm{E}\left(X^2\right)=\phi^{\prime \prime}(0)=\mu^2+\sigma^2$
- $\operatorname{VAR}(X)=\mathrm{E}\left(X^2\right)-(\mathrm{E}(X))^2=\sigma^2$