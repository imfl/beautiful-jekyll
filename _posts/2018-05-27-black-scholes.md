---
mathjax: true
---

# A very quick derivation of Black-Scholes equation

**Replicates** cash flow of an European option by a self-financing portfolio of an asset and a bond

**Assumes** asset price is governed by a geometric Brownian motion

**Uses** Ito Lemma

### Notation


|  symbol   | stands for                                                   |
| :-------: | ------------------------------------------------------------ |
|    $t$    | current time (time of option pricing)                        |
|    $T$    | time of expiry of the option                                 |
|   $S_t$   | asset price at time $t$, a geometric Brownian motion with drift rate $\mu$ and volatility rate $\sigma$ |
| $\beta_t$ | bond price at time $t$, determined by constant interest rate $r$ |
|   $V_t$   | value of the replicating portfolio at time $t$               |
|   $a_t$   | units of the asset $S$ in the replicating portfolio $V$ at time $t$ |
|   $b_t$   | units of the bond $\beta$  in the replicating portfolio $V$ at time $t$ |

*To focus on the main idea, in what follows, we aggressively suppress the subscript $t$ whenever possible. Please note that, for example, $a$ stands for $a_t$ --- it is not a constant coefficient but a process that changes with time $t$.*

### Derivation

**Step 1** $\qquad$ Price dynamics

$$
\left\{
\begin{align}
    \frac{dS}{S} & = \mu dt + \sigma dB	\\
    \frac{d\beta}{\beta} & = rdt
\end{align}
\right.
$$

**Step 2** $\qquad​$ A replicating portfolio

$$
V = a S + b \beta
$$

**Step 3** $\qquad$ Self-financing

$$
\begin{align}
    dV & = a dS + b d\beta \\
    & = a \bigg(\mu S dt + \sigma S dB \bigg) + br\beta dt \\
    & = \bigg(a\mu S +br\beta \bigg) dt + a\sigma S dB
\end{align}
$$

**Step 4** $\qquad​$ Applies Ito Lemma

$$
\begin{align}
    dV & = dV(t, S) \\
    & = \frac{\partial V}{\partial t} dt + \frac{\partial V}{\partial S} dS + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2}d\langle S \rangle \\
    & = \frac{\partial V}{\partial t} dt + \frac{\partial V}{\partial S} \bigg(\mu S dt + \sigma S dB \bigg) + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 dt \\
    & = \bigg(\frac{\partial V}{\partial t} + \frac{\partial V}{\partial S} \mu S + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 \bigg) dt + \bigg( \frac{\partial V}{\partial S} \sigma S \bigg) dB

\end{align}
$$

**Step 5** $\qquad​$ Hedge ratio

$$
\begin{align}
    \bigg( \frac{\partial V}{\partial S} \sigma S \bigg) dB & =  a\sigma S dB \\
    \implies a_t & = \frac{\partial V}{\partial S}
\end{align}
$$

**Step 6** $\qquad$ Black-Scholes equation

$$
\begin{align}
   & \bigg(\frac{\partial V}{\partial t} + \frac{\partial V}{\partial S} \mu S + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 \bigg) dt = \bigg(a\mu S +br\beta \bigg) dt \\
   & b = \frac{V - aS}{\beta} \\
    \implies & \frac{\partial V}{\partial t} + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 + \frac{\partial V}{\partial S} rS  - rV = 0
\end{align}
$$
