---
use-site-title: true
mathjax: true
mermaid: true
---

## Derivation

Given a nonnegative random variable $X$,  for $c > 0$, we have


$$
\begin{align}
    EX & = \int_0^{\infty} xdP(x) \\
    & = \int_0^c xdP(x) + \int_c^{\infty} xdP(x) \\
    & \geq \int_c^{\infty} xdP(x)  \\
    & \geq \int_c^{\infty} kdP(x)  \\
    & = c \int_c^{\infty} dP(x) \\
    & = c\ Pr(X  \geq c) \\~\\
    \implies & Pr(X \geq c) \leq \frac{EX}{c} \tag{1}
\end{align}
$$

Letting $X =  (Y-EY)^2$ and $c = k^2 EX = k^2  E(Y-EY)^2 = k^2 Var(Y)$, we have
$$
Pr\bigg( (Y-EY)^2 \geq k^2 Var(Y) \bigg) \leq \frac{Var(Y)}{k^2 Var(Y)}  = \frac{1}{k^2} \tag{2}
$$

Writing $\mu = EY$ and $\sigma = E(Y-EY)^2$, and noting that 

$$
\bigg\{\omega\ \bigg|\ (Y-EY)^2 \geq k^2 Var(Y)\bigg\} = \bigg\{\omega\ \bigg|\ |Y-\mu| \geq k \sigma \bigg\}
$$

we have

$$
Pr\bigg( |Y-\mu| \geq k \sigma \bigg) \leq \frac{1}{k^2} \tag{3}
$$


