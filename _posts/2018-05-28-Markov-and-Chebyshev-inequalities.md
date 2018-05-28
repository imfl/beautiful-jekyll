---
use-site-title: true
mathjax: true
mermaid: true
---

考虑一枚不均匀的骰子。无论它如何不均匀，摇得3到6点的概率，都不可能超过期望的1/3。为什么？

## Intuition

Consider an unfair die. No matter unfair it is made, we assert that the probability that it is rolling a 3, 4, 5 or 6 cannot be more than $\frac13$ of the expectation. That is, for its result $X$,

$$
Pr (X \geq 3) \leq \frac{1}{3} EX
$$

Why?

Let's start with its expectation $EX = \sum_{x = 1}^6 x Pr(X=x)$. It is essentially a weighted average, which we will shrink twice. 

1. We shrink it by ignoring any contribution to expectation when the die is rolling a $1$ or $2$. That is, $EX \geq \sum_{x = 3}^6 x Pr(X=x)$.
   
2. We further shrink it by observing that when the die is rolling a 3, 4, 5, or 6, it is rolling at least a 3. This nonsense leads to 

$$
\sum_{x = 3}^6 x Pr(X=x) \geq \sum_{x = 3}^6 3 Pr(X=x) = 3 \sum_{x = 3} ^6 Pr(X=x) = 3 Pr(X \geq 3)
$$

This two-step shrinkage is key to proving Markov's inequality.

两步放缩法是证明马尔可夫不等式的关键。

## Derivation

### Markov's Inequality

Given a nonnegative random variable $X$,  for $c > 0$, we have

$$
\begin{align}
    EX & = \int_0^{\infty} xdP(x) \\
    & = \int_0^c xdP(x) + \int_c^{\infty} xdP(x) \\
    & \geq \int_c^{\infty} xdP(x)  \tag*{1st shrinkage 放缩}\\
    & \geq \int_c^{\infty} kdP(x)  \tag*{2nd shrinkage 再放缩}\\
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

马尔可夫不等式告诉我们，一个非负随机变量，出现2倍均值的概率不会超过$\dfrac12$，出现3倍均值的概率不会超过$\dfrac13$，以此类推。

### Chebyshev's Inequality

We don't like the requirement that $X$ be nonnegative. We want an inequality that holds for all random variables. What should we do? Variance is guaranteed to be nonnegative, but that's not a random variable. We are close.

Setting $X =  (Y-EY)^2$, where $Y$ can be any random variable that has an expectation and a variance, we have
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

切比雪夫不等式告诉我们，一个随机变量，在均值2倍标准差之外的概率不会超过$\dfrac14$，在均值3倍标准差之外的概率不会超过$\dfrac19$，以此类推。

## Application

Though just a special case of Markov's Inequality, Chebyshev's Inequality is a very useful one, because it makes no assumptions about the distribution.

虽然切比雪夫不等式仅仅是马尔可夫不等式的一个特例，但是它非常实用，因为它不假设任何分布。

Advanced algorithm is a tough course in computer science. The average score for the final was merely $\mu = 60$, with a standard deviation $\sigma = 10$. I scored $y = 76$. How good was I?

高级算法是一门很难的计算机课程，期末的平均分仅仅有60分，标准差是10。我得了76分，我大概排在什么位置呢？

Let $z = \frac{y - \mu}{\sigma} = 1.6$. Assuming normal distribution, $\Phi(z) = 95\%$. I was top 5%! Or was I? The distribution may not be normal at all. Let's be more conservative.

假设正态分布，我就排在前5%。不过，分数的分布可能一点也不正态！

According to Chebyshev's Inequality, 

$$
Pr \big( |Y - 60| \geq 1.6 \times 10\big) \leq \frac{1}{1.6^2} = 40 \%
$$

Assuming only symmetric distribution, I should be among top 20%. Not bad!

让我们试试切比雪夫不等式，它不假设任何分布。我在平均分的1.6倍标准差之外，无论怎样奇怪的分布，全班最多只有40%的同学在这个范围内。如果分数分布基本对称的话，我就应该排在前20%，还不错：）