---
title: Does TSS = ESS + RSS always hold?
use-site-title: true
mathjax: true
---

学习计量经济学的时候，我们把这个公式记得滚瓜烂熟，然而它必然成立吗？

$$
TSS = ESS + RSS
$$



## Formulae

$$
\begin{align}
    TSS & = \sum \big( y_i - \bar{y} \big)^2 \\
    ESS & = \sum \big( \hat{y_i} - \bar{y} \big)^2 \\
    RSS & = \sum \big( y_i - \hat{y_i} \big)^2
\end{align}
$$

$$
\begin{align}
    TSS & = ESS + RSS \\
    \iff  \sum \big( y_i - \bar{y} \big)^2  & = \sum \big( \hat{y_i} - \bar{y} \big)^2 + \sum \big( y_i - \hat{y_i} \big)^2 \\
    \iff  \sum \Big( y_i^2 + \bar{y}^2 - 2 y_i \bar{y} \Big)  & = 
            \sum \bigg[ \Big( \hat{y_i}^2 + \bar{y}^2 - 2 \hat{y_i} \bar{y} \Big)
            + \Big(y_i^2 + \hat{y_i}^2 - 2 y_i \hat{y_i} \Big) \bigg] \\
    \iff \sum\big(  \hat{y_i} - \bar{y} \big) \big(  \hat{y_i} - y_i \big) & = 0
\end{align}
$$

