# Diagonal Ramsey corridor

**A 23-card research program on the exponential growth of diagonal Ramsey numbers: an unconditional thin-corridor equivalence, exact structural lemmas, a precise conditional route to existence of the exponential limit, and quantitative barriers measuring what that route still lacks.**

Author: Jared Wilder. Cards dated 2026. First public timestamp: 2026-09-11.

The central open question is whether `lim R(k)^(1/k)` exists. This repository does not assume that conclusion; it develops exact reductions and construction machinery around it.

## The unconditional core

### P01 — Thin-Corridor Ramsey Inequality

For integers `n>a>=0`,

`r(n-a,n) <= R(n) <= 4^a r(n-a,n)`.

The upper bound follows by iterating the standard Ramsey recursion from `(n,n)` and stopping each branch when one coordinate reaches `n-a`.

### P02 — Thin-Corridor Equivalence

If `a_n=o(n)`, then

`(1/n) log R(n) - (1/n) log r(n-a_n,n) -> 0`.

Hence diagonal and sublinear off-diagonal corridors have the same exponential limsup and liminf. In particular, convergence along **any one sublinear corridor** is equivalent to convergence on the diagonal.

This is the program's cleanest transfer principle: the diagonal exponential-limit question can be studied on a whole `o(n)` off-diagonal corridor without changing the exponential scale.

### P03 — inverse homogeneous-set formulation

With

`h(N)=min_{|V(G)|=N} max{omega(G),alpha(G)}`,

one has

`R(k)>N iff h(N)<k`,

and the diagonal exponential limit can be translated into the corresponding asymptotic for `h(N)/log N`.

### P04 — clone saturation

In a red/blue colouring of `K_(R(k)-1)` with no monochromatic `K_k`, every vertex lies in both a red and a blue `K_(k-1)`. This is an exact extremal-structure lemma; historical novelty is not asserted.

## Conditional route to the limit

### P06 — summable composition-error accumulation

If a witness operation multiplies vertex counts while its parameter incurs only a sufficiently small `O(t/log^2 t)` additive loss, repeated balanced composition accumulates only `1+O(1/log K)` relative distortion.

### P07 — approximate supermultiplicativity criterion

Put `A(k)=R(k)-1`. If, for all sufficiently large `m,n`, there exists

`0 <= E(m,n) <= C(m+n)/log^2(m+n)`

such that

`A(m+n+E(m,n)) >= A(m)A(n)`,

then

`lim R(k)^(1/k)`

exists.

The implication is proved in the program. The approximate-supermultiplicativity hypothesis is the missing theorem.

### P09 — optimized conditional base

Combining the complementary off-diagonal route with the stated Bradač fixed-ratio lower bound gives

`C*=(1+sqrt(3))/2`,

`f(C*)=4-2sqrt(3)`,

and conditional diagonal base

`2^(4-2sqrt(3)) = 1.4498447106... > sqrt(2)`.

These constants were independently recomputed during release and match the cards.

## Quantitative barriers

The program does not merely state that the composition route is unfinished; it quantifies two deficits.

### P19 — raw-count / uniform-rank barrier

For a proof architecture with `N=2^(beta t+o(t))` candidate tuples and at most one independent binary equation per unordered pair, the raw first-moment exponent becomes

`(beta-1/2)t^2+o(t^2)`.

At the complementary optimum `beta=4-2sqrt(3)`, the missing structural entropy gain is at least

`7/2 - 2sqrt(3) = 0.0358983849...`.

This is an architecture-specific negative theorem, not a global impossibility result.

### P20 — two-cross-matrix information ceiling

At `C*`, two cross matrices supply asymptotic coefficient

`2C*/(1+C*)^2 = 0.4880338717...`

against target exponent

`0.5358983848...`,

a shortfall of

`0.0478645131...`.

Again, this diagnoses the investigated construction rather than all possible Ramsey compositions.

## Construction and rank machinery

The remaining cards develop the route in detail:

- **P10:** an explicit binary nonedge-polarity digraph `D_p`, loopless and `T_(p+1)`-free, with exact size `(2^p-1)2^(p-1)`;
- **P11–P13:** tagged direct sums, XOR arc identities, pattern-collision formulas and triangular orthogonality;
- **P14:** exact tensor-flag rank formula;
- **P15–P18:** bilinear mixer algebra, affine equation systems and rank-weighted first moments;
- **P21:** exact large independent coordinate fibers in the full Cartesian mixed product, falsifying that unthinned construction;
- **P22:** perfect matching in the valid-pair incidence graph;
- **P23:** matching-restricted polarity digraph eliminating the repeated-coordinate fibers.

Fourteen of the 23 cards include proof bodies; the remainder are conditional statements, diagnostics or recorded targets as labelled in the bank.

## Literature / discrepancy note

P10 records a discrepancy with a displayed finite-count formula in arXiv:2605.28793v3, Lemma 3.1. This repository does not rely on that displayed count, and the source card says the discrepancy is lower-order for the paper's quoted exponential asymptotics. The note is preserved as an observation rather than an adjudicated correction to the external paper.

## Evidence state

`PROVED-IN-SESSION` means the supplied card contains an argument for its stated scope; `CHECKABLE-CONDITIONAL` means the implication is established while its named hypothesis is not; `DIAGNOSTIC` denotes an architecture-specific barrier.

Historical novelty has not been globally adjudicated. Those literature questions are separate from the exact statements and calculations recorded here.

## Provenance

Earlier copies remain in `erdos-theorems/erdos77-ramsey-limit/` and the public intake archive. This repository is now the preferred human/citation home for the diagonal-corridor program.

## License

Apache-2.0.
