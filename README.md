# Diagonal Ramsey corridor

Let `R(n)=r(n,n)` be the diagonal Ramsey number. This repository studies whether the exponential growth rate

\[
\lim_{n\to\infty}R(n)^{1/n}
\]

exists, by transferring the problem to sublinear off-diagonal corridors and isolating an approximate-composition theorem that would force the limit.

## Thin-corridor inequality

For integers `n>a>=0`,

\[
\boxed{r(n-a,n)\le R(n)\le4^a r(n-a,n)}.
\]

The upper bound follows by iterating the standard Ramsey recursion and stopping each branch when one coordinate reaches `n-a`.

If `a_n=o(n)`, then

\[
\frac1n\log R(n)-\frac1n\log r(n-a_n,n)\to0.
\]

Therefore every sublinear off-diagonal corridor has the same exponential limsup and liminf as the diagonal. In particular:

> convergence of the exponential rate along any one `o(n)` corridor is equivalent to convergence on the diagonal.

This is the main unconditional reduction in the repository.

## Inverse homogeneous-set formulation

Define

\[
h(N)=\min_{|V(G)|=N}\max\{\omega(G),\alpha(G)\}.
\]

Then

\[
R(k)>N\iff h(N)<k.
\]

Thus the same exponential-limit question can be expressed as an asymptotic problem for `h(N)/\log N`.

## A sufficient approximate-composition theorem

Put `A(k)=R(k)-1`. The program proves the following implication:

If for all sufficiently large `m,n` there exists

\[
0\le E(m,n)\le C\frac{m+n}{\log^2(m+n)}
\]

such that

\[
A(m+n+E(m,n))\ge A(m)A(n),
\]

then

\[
\lim_{k\to\infty}R(k)^{1/k}
\]

exists.

The missing ingredient is the approximate-supermultiplicativity inequality itself.

## Quantified barriers to the current construction

The repository also measures why one investigated composition architecture falls short.

For a candidate family with `N=2^{\beta t+o(t)}` objects and at most one independent binary constraint per unordered pair, the raw first-moment exponent is

\[
(\beta-1/2)t^2+o(t^2).
\]

At the complementary optimum `\beta=4-2\sqrt3`, this leaves a structural entropy deficit of at least

\[
\frac72-2\sqrt3
=0.0358983849\ldots
\]

within that architecture.

A related two-cross-matrix calculation gives information coefficient

\[
0.4880338717\ldots
\]

against target exponent

\[
0.5358983848\ldots,
\]

leaving a gap of

\[
0.0478645131\ldots.
\]

These are diagnostics of the specific construction, not impossibility theorems for all approaches.

## Construction machinery

The remaining notes develop:

- an explicit binary nonedge-polarity digraph;
- tagged direct sums and XOR arc identities;
- tensor-flag rank formulas;
- bilinear mixers and affine equation systems;
- rank-weighted first moments;
- a counterexample to the full Cartesian mixed-product construction;
- a perfect-matching reduction that removes the repeated-coordinate fibres.

The complete 23-card source bank is retained in the repository; 14 cards contain proof bodies, while the others are conditional reductions, diagnostics, or open targets.

The diagonal exponential-limit problem remains open. The unconditional result here is the sublinear-corridor equivalence and the exact structural machinery around the proposed composition route.

Author: Jared Wilder. License: Apache-2.0.
