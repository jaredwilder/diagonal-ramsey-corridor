# diagonal-ramsey-corridor

**A 23-card research program on the asymptotics of the diagonal Ramsey number — including an
unconditional transfer principle for Erdős's own \$100 question, a precise conditional route that
would settle it, and two barrier cards that measure exactly how far the route falls short.**

Author: Jared Wilder. Cards dated 2026. First public timestamp: 2026-09-11.

**Nothing here closes anything.** Whether `lim R(k)^{1/k}` exists is open, and this does not decide
it. What is here is a program that states its own conditionals and then quantifies its own gap.

Every constant below was **recomputed independently on 2026-09-11** and matches the cards to ten
decimal places.

---

## The unconditional core

**P01 — Thin-Corridor Ramsey Inequality.** For integers `n > a ≥ 0`,

```
r(n−a, n)  ≤  R(n)  ≤  4^a · r(n−a, n)
```

Proof on the card: iterate `r(s,t) ≤ r(s−1,t) + r(s,t−1)` from `(n,n)`, halting each branch when a
coordinate reaches `n−a`. Branches have length at most `2a−1`, so there are fewer than `4^a` leaves.

**P02 — Thin-Corridor Equivalence.** If `a_n = o(n)` then

```
(1/n)·log R(n) − (1/n)·log r(n−a_n, n)  →  0
```

and therefore

```
limsup R(n)^{1/n} = limsup r(n−a_n, n)^{1/n}
liminf R(n)^{1/n} = liminf r(n−a_n, n)^{1/n}
```

**Convergence on any one sublinear corridor is equivalent to convergence on the diagonal.** It
follows from P01 by dividing `0 ≤ log R(n) − log r(n−a_n,n) ≤ a_n log 4 = o(n)` by `n`.

This is the card worth reading. Whether `lim R(k)^{1/k}` exists is a question Erdős offered \$100
for, and P02 says the entire sublinear off-diagonal corridor is exponentially interchangeable with
the diagonal for that purpose.

**P03.** With `h(N) = min_{|V(G)|=N} max{ω(G), α(G)}`, we have `R(k) > N ⟺ h(N) < k`.

**P04 — Clone Saturation.** In any red/blue colouring of `K_{R(k)−1}` with no monochromatic `K_k`,
every vertex lies in a red `K_{k−1}` and a blue `K_{k−1}`. Proved by cloning `v`, colouring `vv'`
red, using the resulting `K_{R(k)}`, then repeating with `vv'` blue. The card does not claim
novelty, and this is likely folklore.

## The conditional route

**P06 (unconditional).** A binary operation on witnesses that multiplies vertex counts and satisfies
the stated near-additivity can be parenthesised so that `M_q ≤ qK(1 + O(1/log K))`, uniformly in
`q ≥ 1`. Dyadic doubling; the cumulative log distortion is `O(Σ_j (log K + j log 2)^{-2}) =
O(1/log K)`.

**P07 (conditional, and labelled `CHECKABLE-CONDITIONAL`).** Put `A(k) = R(k) − 1`. **If** there are
constants `C, k₀` such that for all `m,n ≥ k₀` there is an integer `0 ≤ E(m,n) ≤ C(m+n)/log²(m+n)`
with `A(m+n+E(m,n)) ≥ A(m)A(n)`, **then `lim R(k)^{1/k}` exists.** A Fekete-style argument over P06.

The card says outright that this proves the implication and **not** the hypothesis.

**P09.** Taking Bradač's `r(s,Cs) ≥ 2^{(1−1/(2C))s}` as input and optimising through P08:

| quantity | value | recomputed |
|---|---|---|
| `C* = (1+√3)/2` | 1.3660254038 | ✓ |
| `f(C*) = 4 − 2√3` | 0.5358983849 | ✓ |
| conditional diagonal base `2^{4−2√3}` | **1.4498447106** | ✓ |
| `> √2 = 1.4142135624` | yes | ✓ |

The algebra is unconditional; the Ramsey conclusion is conditional on P08.

## The barriers — the part that makes this worth keeping

Two cards, both marked `DIAGNOSTIC`, measure how far the architecture falls short of its own target.

**P19.** A proof using only `N^t` candidate ordered tuples with `N = 2^{βt+o(t)}` under a raw-count
plus uniform-rank architecture **cannot close for β > 1/2**. At the Bradač-complementary optimum
`β = 4 − 2√3`, so the missing structural entropy dividend is at least

```
β − 1/2  =  7/2 − 2√3  =  0.0358983849
```

**recomputed, and it equals `(4−2√3) − 0.5` exactly.**

**P20.** For `p₁ ~ t/(1+C)` and `p₂ ~ Ct/(1+C)`, two cross matrices carry
`2p₁p₂ ~ (2C/(1+C)²)t²` bits. At `C*` that coefficient is

```
2C*/(1+C*)²  =  0.4880338717
```

against the target exponent `0.5358983848`, a shortfall of **0.0478645131**. Both recomputed and
both match the cards digit for digit.

A program that computes the size of its own gap is rarer, and more useful, than one that announces
a win.

## The construction machinery

**P10.** For `p ≥ 1`, `D_p` has `V(D_p) = {(a,b) ∈ (F₂^p \ {0})² : a·b = 1}` with an arc
`(a,b) → (a',b')` iff `a·b' = 0`. Then `D_p` is loopless, `T_{p+1}`-free, has exactly
`(2^p − 1)2^{p−1}` vertices, and `|D_{p₁+p₂+1}| / (|D_{p₁}||D_{p₂}|) → 8`.

**P22.** The valid-pair incidence graph `H_p` is `2^{p−1}`-regular, so a bijection `π` exists with
`a·π(a) = 1` for every `a ≠ 0`. P23 builds the matching-restricted digraph from it.

P11–P18 and P21 carry the product, arc-pattern and rank machinery. Fourteen of the twenty-three
cards carry a proof body; the rest carry statements only.

## A discrepancy the program recorded against a preprint

The P10 card notes that **arXiv:2605.28793v3, Lemma 3.1** displays an exact vertex count that
instead equals the ordered orthogonal-pair count. It then says explicitly that this packet **does
not rely on that displayed count**, and that the discrepancy is lower-order and does not affect the
paper's quoted exponential asymptotics.

That is recorded here as the card records it — as a noted discrepancy, not as a correction anyone
has adjudicated.

## Status labels, as the bank assigns them

`PROVED-IN-SESSION` means proved inside the session that produced it, not refereed and not checked
against the literature. `CHECKABLE-CONDITIONAL` means an implication whose hypothesis is open.
`DIAGNOSTIC` means a barrier measurement, not a theorem about Ramsey numbers.

**No novelty is claimed for any card here.** Several of these are the kind of statement a specialist
may recognise immediately; P04 in particular is probably folklore, and the card says so.

## License

Apache-2.0.
