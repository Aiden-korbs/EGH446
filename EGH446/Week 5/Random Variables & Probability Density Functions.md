## Random Variables
- **Discrete-valued**: finite or countable sample space (coin toss, dice roll).
- **Continuous-valued**: uncountable sample space (thermal noise).

## Probability Density Function (PDF)
For scalar continuous $x$:
$$
p_x(\zeta) = \lim_{\Delta x \to 0} \frac{P(\zeta - \Delta x < x \le \zeta)}{\Delta x}
$$

### Properties
- Non-negative: $p_x(x) \ge 0$
- Integrates to 1:
$$
\int_{-\infty}^{\infty} p_x(x) \, dx = 1
$$

## Examples

**Uniform** on $[a, b]$:
$$
p_{\text{uni}}(x) =
\begin{cases}
\frac{1}{b-a}, & x \in [a,b] \\
0, & \text{elsewhere}
\end{cases}
$$

**Gaussian** $x \sim \mathcal{N}(\mu, \sigma^2)$:
$$
p_{\text{norm}}(x) = \frac{1}{\sqrt{2 \pi} \sigma} \,
\exp\left( -\frac{(x-\mu)^2}{2\sigma^2} \right)
$$
