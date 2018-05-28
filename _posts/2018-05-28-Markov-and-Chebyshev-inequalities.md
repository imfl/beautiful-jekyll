---
use-site-title: true
mathjax: true
mermaid: true
---

## Derivation

### Markov's Inequality

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

which is Markov's Inequality.

As an alternative form, setting $c = a EX$, where $a > 1$, we have
$$
Pr(X \geq aEX) \leq \frac{1}{a} \tag{2}
$$

### Chebyshev's Inequality

Now $X \geq 0\ a.s.$ is a constraint we don't like. We don't make any pledge about a random variable before we use it. Or can we? We know variance is guaranteed to be nonnegative. But that's not a random variable. We are close. Setting $X =  (Y-EY)^2$, where $Y$ can be any random variable that has an expectation and a variance. 

We have

$$
Pr\bigg( (Y-EY)^2 \geq c \bigg) \leq \frac{Var(Y)}{c} \tag{3}
$$

Or in the alternative form,

$$
Pr\bigg( (Y-EY)^2 \geq a\ Var(Y) \bigg) \leq \frac{1}{a} \tag{4}
$$

Writing $\mu = EY$ and $\sigma^2 = Var(Y)$, setting $a = k^2$ for $k > 1$, and noting that, as events,

$$
\bigg\{\omega\ \bigg|\ (Y(\omega) - \mu)^2 \geq k^2 \sigma^2 \bigg\} = \bigg\{\omega\ \bigg|\ |Y(\omega) - \mu| \geq k \sigma \bigg\}
$$

we have

$$
Pr\bigg( |Y-\mu| \geq k \sigma \bigg) \leq \frac{1}{k^2} \tag{5}
$$

which is Chebyshev's Inequality.

