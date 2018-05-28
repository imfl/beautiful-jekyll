---
use-site-title: true
mathjax: true
---

<script src="/js/mermaid.full.min.js"></script>

**Replicates** cash flow of an option with a self-financing portfolio of an asset and a bond

**Assumes** asset price is governed by a geometric Brownian motion

**Uses** Ito Lemma

## Notation


|  symbol   | stands for                                                   |
| :-------: | ------------------------------------------------------------ |
|    $t$    | current time (time of option pricing)                        |
|    $T$    | time of expiry of the option                                 |
|   $B_t$   | Brownian motion                                              |
|   $S_t$   | asset price at time $t$, a geometric Brownian motion with drift rate $\mu$ and volatility rate $\sigma$ |
| $\beta_t$ | bond price at time $t$, determined by constant interest rate $r$ |
|   $V_t$   | value of the replicating portfolio at time $t$               |
|   $a_t$   | units of the asset $S$ in the replicating portfolio $V$ at time $t$ |
|   $b_t$   | units of the bond $\beta$  in the replicating portfolio $V$ at time $t$ |

*To focus on the main idea, in what follows, we aggressively suppress the subscript whenever possible. Please note that, for example, $a$ stands for $a_t$ --- it is NOT a constant coefficient but a process that changes with time $t$.*

## Derivation

**Step 1** $\quad$ Price dynamics

$$
\left\{
\begin{align}
    \frac{dS}{S} & = \mu dt + \sigma dB \\~\\
    \frac{d\beta}{\beta} & = rdt
\end{align} \tag{1}
\right.
$$

**Step 2** $\quad$ Replicating portfolio

$$
V = a S + b \beta \tag{2}
$$

**Step 3** $\quad$ Self-financing

$$
\begin{align}
    dV & = a dS + b d\beta \\
    & = a \bigg(\mu S dt + \sigma S dB \bigg) + br\beta dt \\
    & = \bigg(a\mu S +br\beta \bigg) dt + a\sigma S dB \tag{3}
\end{align}
$$

**Step 4** $\quad$ Applies Ito Lemma to $(2)$, making use of $(1)$

$$
\begin{align}
    dV & = dV(t, S) \\
    & = \frac{\partial V}{\partial t} dt + \frac{\partial V}{\partial S} dS + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2}d\langle S \rangle \\
    & = \frac{\partial V}{\partial t} dt + \frac{\partial V}{\partial S} \bigg(\mu S dt + \sigma S dB \bigg) + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 dt \\
    & = \bigg(\frac{\partial V}{\partial t} + \frac{\partial V}{\partial S} \mu S + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 \bigg) dt + \bigg( \frac{\partial V}{\partial S} \sigma S \bigg) dB \tag{4}

\end{align}
$$

**Step 5** $\quad$ Hedge ratio, by equating $(3)$ and $(4)$ on $dB$

$$
\begin{align}
    \bigg( \frac{\partial V}{\partial S} \sigma S \bigg) dB & =  a\sigma S dB \\
    \implies a_t & = \frac{\partial V}{\partial S} \tag{5}
\end{align}
$$

**Step 6** $\quad$ Black-Scholes equation, by equating $(3)$ and $(4)$ on $dt$,  and using $(2)$ and $(5)$

$$
\left\{
\begin{align}
    & \bigg(\frac{\partial V}{\partial t} + \frac{\partial V}{\partial S} \mu S + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 \bigg) dt = \bigg(a\mu S +br\beta \bigg) dt \\~\\
    & b = \frac{V - aS}{\beta} \\~\\
    & a = \frac{\partial{V}}{\partial{S}}
\end{align}  \right.
$$

$$
\implies \frac{\partial V}{\partial t} + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 + \frac{\partial V}{\partial S} rS  - rV = 0 \tag{6}
$$

## Flow

<div class="mermaid">
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
</div>

