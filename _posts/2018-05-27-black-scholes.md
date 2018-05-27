# A very quick derivation of Black-Scholes equation and formula

**Approach** replicate a contingent claim by a self-financing portfolio of asset and bonds

**Assumption**  asset price is governed by a geometric Brownian process.

**Uses** Ito Lemma

**Step 1**
$$
\begin{align}
	\frac{dS}{S} & = \mu dt + \sigma dB	\\
	\frac{d\beta}{\beta} & = rdt
\end{align}
$$



**Step 2**


$$
V_t = a_t S_t + b_t \beta_t
$$



**Step 3**


$$
\begin{align}
	dV & = dV(t, S) \\
	& = \frac{\partial V}{\partial t} dt + \frac{\partial V}{\partial S} dS + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2}d\langle S \rangle \\
	& = \frac{\partial V}{\partial t} dt + \frac{\partial V}{\partial S} \bigg(\mu S dt + \sigma S dB \bigg) + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 dt \\
	& = \bigg(\frac{\partial V}{\partial t} + \frac{\partial V}{\partial S} \mu S + \frac12 \frac{\partial ^ 2 V}{\partial S ^ 2} \sigma^2 S^2 \bigg) dt + \bigg( \frac{\partial V}{\partial S} \sigma S \bigg) dB

\end{align}
$$

**Step 4**