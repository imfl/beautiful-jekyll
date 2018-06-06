---
title: Does TSS = ESS + RSS always hold?
use-site-title: true
mathjax: true
---

学习计量经济学的时候，我们把这个公式记得滚瓜烂熟，然而它必然成立吗？

$$
TSS = ESS + RSS
$$

You may have memorized the formula for exams. But does it always hold?

## Definition

$$
\begin{align}
    TSS &\equiv \sum \big( y_i - \bar{y} \big)^2 \tag*{total sum of squares} \\~\\
    ESS & \equiv \sum \big( \hat{y_i} - \bar{y} \big)^2 \tag*{explained sum of squares}\\~\\
    RSS & \equiv \sum \big( y_i - \hat{y_i} \big)^2 \tag*{residual sum of squares}
\end{align}
$$

## Interpretation

Consider a group of people. Collectively, they have a mean weight $\bar{y}$. But as individuals, they must have different weights $y_i$, which differs from the mean. The total variation of $y_i$ from $\bar{y}$ is measured by $TSS$.

To explain the variation, we build a model, which predicts each of their weights at $\hat{y_i}$.

The variation explained by the model is measured by $ESS$. That unexplained by $RSS$.

## Derivation

$$
\begin{align}
    TSS & = ESS + RSS \\~\\
    \iff  \sum \big( y_i - \bar{y} \big)^2  & = \sum \big( \hat{y_i} - \bar{y} \big)^2 + \sum \big( y_i - \hat{y_i} \big)^2 \\~\\
    \iff  \sum \Big( y_i^2 + \bar{y}^2 - 2 y_i \bar{y} \Big)  & = 
            \sum \bigg[ \Big( \hat{y_i}^2 + \bar{y}^2 - 2 \hat{y_i} \bar{y} \Big)
            + \Big(y_i^2 + \hat{y_i}^2 - 2 y_i \hat{y_i} \Big) \bigg] \\~\\
    \iff \sum \big(  \hat{y_i} - \bar{y} \big) \big(  \hat{y_i} - y_i \big) & = 0 \tag{1}
\end{align}
$$

That is, $\ TSS = ESS + RSS\ $ holds if and only if $\ \sum \big(  \hat{y_i} - \bar{y} \big) \big(  \hat{y_i} - y_i \big) = 0\ $, which is not always true, because we may build a model to predict $y_i$ as wild as it can be.

## Exploration

The culprit for a false impression that $\ TSS = ESS + RSS\ $ always holds may be it usually appears in the ordinary least squares (OLS) setting. Yes, $\text{OLS} \implies TSS = ESS + RSS$. I will show this is true in what follows, without explicitly solving OLS equations.

> OLS chooses the parameters of a linear function by minimizing the sum of the squares of the differences between the observed and the predicted.

Suppose we predict that $y_i$ can be explained linearly by feature $x_i$. We have

$$
\hat{y_i} = a + b x_i
$$

Our goal is to

$$
\min_{a, b} \sum \big(y_i - \hat{y_i} \big)^2
$$

In other words,

$$
\begin{align}
    & \min_{a, b} \ \sum \big( y_i -\hat{y_i} \big)^2 =  \sum \big( y_i - a - b x_i \big)^2  \\~\\
    \text{let} \qquad & f(a, b) = \sum \big( y_i - a - b x_i \big)^2 \\~\\
    \text{set} \qquad &
    \left\{
        \begin{aligned}
            &  \frac{\partial{f}}{\partial{a}} = 0 \\~\\
            &  \frac{\partial{f}}{\partial{b}} = 0 \\
        \end{aligned}
    \right.\\~\\
    \implies & 
    \left\{
        \begin{aligned}
            & \sum \big( y_i - \hat{y_i} \big) = 0 \\~\\
            & \sum x_i \big( y_i - \hat{y_i} \big) = 0
        \end{aligned} \tag{OLS requirements}
    \right.
\end{align}
$$

**There is no need to solve these equations for $a​$ and $b​$ !**

Observe that for $\ TSS = ESS + RSS\ $ to hold, we only need

$$
\begin{align}
    & \sum \big(  \hat{y_i} - \bar{y} \big) \big(  \hat{y_i} - y_i \big) = 0 \tag{1} \\~\\
    \impliedby & \sum \big(  a + b x_i - \bar{y} \big) \big(  \hat{y_i} - y_i \big) = 0 \\~\\
    \impliedby & \sum b x_i \big(  \hat{y_i} - y_i \big) + \sum \big(a - \bar{y} \big) \big(  \hat{y_i} - y_i \big) = 0 \\~\\
    \impliedby & b \underbrace{\sum  x_i \big(  \hat{y_i} - y_i \big)}_{0\ \text{as required by OLS}}+ \big(a - \bar{y} \big) \underbrace{\sum \big(  \hat{y_i} - y_i \big)}_{0\ \text{as required by OLS}} = 0 

\end{align}
$$

In one word, so long as OLS requirements are met, formula $\ TSS = ESS + RSS\ $ will hold.

## Implication

$R^2 \equiv 1 - \dfrac{RSS}{TSS}\ $ is a frequently used measure for model fit. By its name, it appears that it must be nonnegative. However, this is only true in certain circumstances (for example, OLS). Since it is perfectly possible that $RSS > TSS$, $R^2$ may well be negative.