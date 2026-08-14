# KL Robustness Learns Logarithmically

## Abstract

How many samples are needed to learn a classifier whose risk is robust to a forward Kullback-Leibler ball? We determine the distribution-free answer for zero-one loss. If the ball has radius $\rho$ and the target robust excess is $\varepsilon$, define $b_\rho(\varepsilon)$ by $\mathrm{kl}(\varepsilon\\|b_\rho(\varepsilon))=\rho$. For a class of VC dimension $d$, the realizable sample complexity is $\Theta((d+\log(1/\delta))/b_\rho(\varepsilon))$, while the agnostic complexity is, up to logarithmic factors,

$$\Theta\\!\left((d+\log(1/\delta))\max\\{\varepsilon^{-2},\\,b_\rho(\varepsilon)^{-1}\\}\right).$$

The inverse binary-KL scale satisfies $b_\rho(\varepsilon)\asymp\varepsilon e^{-\rho/\varepsilon}$. Thus any fixed positive radius changes both learning curves from polynomial decay to $\rho/\log n$. The agnostic transition occurs at $\rho\asymp\varepsilon\log(1/\varepsilon)$.

The main proof challenge is a localized spacing inequality for the inverse binary-KL map. It matches relative VC fluctuations simultaneously near zero and at positive Bayes error. We also give an endpoint-uniform Cressie-Read inequality that turns the polynomial fixed-order scale into the KL exponential as the order tends to one. Earlier work established event-probability rescaling and invariant zero-one minimizers. Our contribution is the minimax statistical consequence, including matching lower bounds and the singular endpoint phase diagram.

## Main results

**Theorem (KL-robust PAC complexity).** There are universal constants $c,C,\varepsilon_0>0$ such that for every $\rho\geq 0$, $0<\varepsilon\leq\varepsilon_0$, $0<\delta\leq 1/8$, and $1\leq d<\infty$,

$$M^{\mathrm{real}}_{\mathrm{KL},\rho}(\varepsilon,\delta,d) = \Theta\\!\left(\frac{d+\log(1/\delta)}{b}\right),$$

$$cA(d+\log(1/\delta)) \leq M^{\mathrm{agn}}_{\mathrm{KL},\rho}(\varepsilon,\delta,d) \leq CA\\{d\log(eA)+\log(1/\delta)\\}.$$

The realizable upper bound is attained by an optimal ordinary PAC learner, and the agnostic upper bound by ordinary empirical risk minimization. The agnostic bounds match up to the displayed logarithmic factor.

**Proposition (Exponential inverse scale).** For every $0<q<1$ and $\rho\geq 0$,

$$e^{-1}q\\,e^{-\rho/q} \leq B_\rho(q) \leq q\\,e^{-\rho/q}.$$

This is what converts polynomial learning curves into logarithmic ones: at any fixed positive radius the effective accuracy shrinks exponentially, so the achievable excess risk after $n$ samples decays like $\rho/\log n$ rather than a power of $n$.

**Theorem (Localized inverse spacing).** There are universal $c>0$ and $\varepsilon_0>0$ such that for $0<\varepsilon\leq\varepsilon_0$ and every $\rho\geq 0$, with $a=\min\\{\varepsilon^2,B_\rho(\varepsilon)\\}$, every $q\in[0,1-\varepsilon]$ and $p=B_\rho(q)$ satisfy

$$B_\rho(q+\varepsilon)-B_\rho(q) \geq c\\{a+\sqrt{ap}\\}.$$

This is the technical core. The additive term handles the region near zero error and the square-root term handles positive Bayes error, so a single inequality matches relative VC fluctuations in both regimes at once. Convexity of $B_\rho$ is what makes the two branches combine.

**Theorem (Endpoint-uniform Cressie-Read bridge).** For every $s>0$, $\rho\geq 0$, and $0<q<1$, with $p=B_{1+s,\rho}(q)$,

$$\left[1+\frac{(1+s)s\rho}{q}\right]^{1/s} \leq \frac{q}{p} \leq \left[1+s+\frac{(1+s)s\rho}{q}\right]^{1/s}.$$

For fixed $s$ this gives the polynomial scale $B_{1+s,\rho}(q)\asymp_s q^{1+1/s}\rho^{-1/s}$, and as $s\downarrow 0$ it degenerates to the KL exponential $e^{\rho/q}\leq q/B_\rho(q)\leq e^{1+\rho/q}$. The bound is uniform up to the endpoint, so it explains the singular transition rather than merely taking a limit.

## Keywords

distributionally robust learning, PAC learning, VC dimension, Kullback-Leibler divergence, Cressie-Read divergence, sample complexity, minimax rates, agnostic learning, phase transition, logarithmic learning curves

## Files

- `main.pdf`
- `main.tex`
- `references.bib`
- `kl_phase.pdf` phase-diagram figure
- `iclr2027_conference.sty`, `iclr2027_conference.bst`, `natbib.sty`, `fancyhdr.sty`
- `supplement.zip` verification scripts and raw numerical checks
- `main.pdf.ots`, `README.md.ots`, `supplement.zip.ots` OpenTimestamps priority proofs
