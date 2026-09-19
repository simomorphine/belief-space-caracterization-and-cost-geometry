# Chapter 3: The Debt Function

## 3.1 The asymmetry of cost

Chapter 2 established the energy quasi-metric `d` as the cost of moving between states of the belief space. Because `d` is a quasi-metric, it need not be symmetric. In general,

$$
d(b_i,b_j) \neq d(b_j,b_i).
$$

This asymmetry is not an error in the construction. It records the fact that moving from `b_i` to `b_j` may have a different cost from moving in the opposite direction.

**Observation 3.1.** There may exist `b_i,b_j ∈ B` such that

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

The first task of this chapter is therefore to isolate the asymmetric part of the energy quasi-metric.

**Definition 3.2 (Symmetric and Antisymmetric Parts).** Assume that `d(b_i,b_j)<+\infty` for all `b_i,b_j∈B`. Define

$$
S(b_i,b_j)
:=
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right)
$$

and

$$
A(b_i,b_j)
:=
\frac12\left(d(b_i,b_j)-d(b_j,b_i)\right).
$$

We call `S` the **symmetric part** of the cost and `A` the **antisymmetric part** of the cost.

The function `A` measures the directional imbalance of the cost. It is positive when the transition from `b_i` to `b_j` is more expensive than the reverse transition, negative when it is cheaper, and zero when the two directions have equal cost.

**Proposition 3.3.** The antisymmetric part `A` satisfies:

1. `A(b_i,b_j)=-A(b_j,b_i)`;
2. `A(b,b)=0`;
3. `A(b_i,b_j)>0` if and only if `d(b_i,b_j)>d(b_j,b_i)`;
4.

$$
|A(b_i,b_j)|
\leq
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right).
$$

**Proof.**

For antisymmetry,

$$
A(b_j,b_i) = \frac12\left(d(b_j,b_i)-d(b_i,b_j)\right) = -A(b_i,b_j).
$$

On the diagonal,

$$
A(b,b) = \frac12\left(d(b,b)-d(b,b)\right) = 0.
$$

The sign property follows directly from the definition. Finally,

$$
|A(b_i,b_j)| = \frac12 \left| d(b_i,b_j)-d(b_j,b_i) \right|
$$

and therefore

$$
|A(b_i,b_j)|
\leq
\frac12
\left(
d(b_i,b_j)+d(b_j,b_i)
\right).
$$

`□`

The symmetric and antisymmetric parts reconstruct the original cost.

**Proposition 3.4 (Canonical Decomposition).** The energy quasi-metric admits the decomposition

$$
d=S+A,
$$

where `S` is symmetric and `A` is antisymmetric. This decomposition is unique.

**Proof.**

By definition,

$$
S(b_i,b_j)+A(b_i,b_j) = \frac12(d(b_i,b_j)+d(b_j,b_i)) + \frac12(d(b_i,b_j)-d(b_j,b_i)),
$$

so

$$
S(b_i,b_j)+A(b_i,b_j)=d(b_i,b_j).
$$

The function `S` is symmetric and `A` is antisymmetric by construction.

For uniqueness, suppose

$$
d=S'+A',
$$

where `S'` is symmetric and `A'` is antisymmetric. Evaluating the same equation with `b_i` and `b_j` exchanged, then adding and subtracting the two equations, gives

$$
S'=S,\qquad A'=A.
$$

Thus the decomposition is unique. `□`

**Remark 3.5.** The antisymmetric component `A` should not be identified with the debt function introduced in this chapter. `A` is determined directly by the asymmetry of the energy quasi-metric. Debt is a separate object whose mathematical structure will be introduced independently.

The distinction is important. Asymmetry tells us that the cost of a transition depends on its direction. It does not, by itself, tell us why this asymmetry exists, whether it can be represented by a potential, or whether it satisfies additional structural properties.

The purpose of the following sections is to investigate this additional structure.

In particular, Chapter 4 will ask whether the debt function can be represented as a difference of potentials,

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i),
$$

and what assumptions are required for such a representation to exist.

---

## 3.2 The debt function: definition

We now introduce the central object of the chapter.

**Definition 3.6 (Debt Function).** Let `B` be a belief space. A **debt function** is a function

$$
D:B\times B\to\mathbb R
$$

satisfying:

* **(D1) Additivity.**

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k)
$$

for all `b_i,b_j,b_k∈B`.

* **(D2) Antisymmetry.**

$$
D(b_i,b_j) = -D(b_j,b_i)
$$

for all `b_i,b_j∈B`.

These are the only axioms. Everything else in this chapter will be derived from them.

**Remark 3.7.** The axioms (D1) and (D2) are satisfied by every potential difference. If `ψ:B→R` is any function and

$$
D(b_i,b_j):=\psi(b_j)-\psi(b_i),
$$

then `D` satisfies both axioms.

The central result of Chapter 4 will establish the converse: every debt function arises from such a potential.

**Remark 3.8.** The debt function is not the same as the asymmetry `A`.

The asymmetry

$$
A(b_i,b_j) = \frac12 \left( d(b_i,b_j)-d(b_j,b_i) \right)
$$

measures directional imbalance in the cost.

Debt is a separate function satisfying the stronger structural condition of additivity. In particular, `A` need not be additive, whereas `D` is additive by axiom (D1).

---

## 3.3 Immediate consequences

The two axioms (D1) and (D2) have immediate consequences.

**Proposition 3.9 (Identity).** For every `b∈B`,

$$
D(b,b)=0.
$$

**Proof.** By (D2),

$$
D(b,b)=-D(b,b).
$$

Hence

$$
2D(b,b)=0,
$$

so

$$
D(b,b)=0.
$$

`□`

**Proposition 3.10 (Cycle Invariance).** For any closed path

$$
b_1\to b_2\to\cdots\to b_n\to b_1,
$$

the total debt is zero:

$$
\sum_{k=1}^{n}D(b_k,b_{k+1})=0,
$$

where `b_{n+1}:=b_1`.

**Proof.** By (D1),

$$
D(b_k,b_{k+1}) = D(b_1,b_{k+1})-D(b_1,b_k).
$$

Summing over `k=1,...,n` gives a telescoping sum:

$$
\sum_{k=1}^{n}D(b_k,b_{k+1}) = D(b_1,b_{n+1})-D(b_1,b_1).
$$

Since `b_{n+1}=b_1` and Proposition 3.9 gives `D(b_1,b_1)=0`,

$$
\sum_{k=1}^{n}D(b_k,b_{k+1})=0.
$$

`□`

**Proposition 3.11 (Path Independence).** If `γ_1` and `γ_2` are two paths from `b_i` to `b_j`, then

$$
\sum_{e\in\gamma_1}D(e) = \sum_{e\in\gamma_2}D(e).
$$

**Proof.** The concatenation

$$
\gamma_1\cdot\gamma_2^{-1}
$$

is a closed path. By Proposition 3.10, its total debt is zero. Therefore the debt accumulated along `γ_1` equals the debt accumulated along `γ_2`.

`□`

**Remark 3.12.** Proposition 3.11 is an important structural property. The total debt of a path depends only on its endpoints, not on the particular path taken.

This is stronger than the endpoint dependence of the energy quasi-metric. The energy quasi-metric is obtained by minimizing over possible paths. Debt is different: every path between the same endpoints has the same total debt.

**Proposition 3.13 (Gauge Invariance).** Let `ψ:B→R` and define

$$
D(b_i,b_j):=\psi(b_j)-\psi(b_i).
$$

Then `D` satisfies (D1) and (D2). Moreover, if

$$
\psi'=\psi+c
$$

for a constant `c∈R`, then

$$
D_{\psi'}=D_\psi.
$$

**Proof.**

For (D1),

$$
\psi(b_k)-\psi(b_i) = [\psi(b_j)-\psi(b_i)] + [\psi(b_k)-\psi(b_j)].
$$

For (D2),

$$
\psi(b_j)-\psi(b_i) = -[\psi(b_i)-\psi(b_j)].
$$

Finally,

$$
(\psi(b_j)+c)-(\psi(b_i)+c) = \psi(b_j)-\psi(b_i).
$$

Thus adding a constant to the potential does not change the debt.

`□`

**Remark 3.14.** Proposition 3.13 shows that every potential difference is a debt function. The converse—that every debt function is a potential difference—is the subject of Chapter 4.

---

## 3.6 The Debt of a Transition

Let us now interpret the debt function in the context of belief space.

**Definition 3.23 (Debt of a Transition).** For a transition

$$
b_i\to b_j,
$$

the debt is

$$
D(b_i,b_j).
$$

Once the potential representation has been established, this quantity can be interpreted as the change in a potential associated with the belief space.

**Interpretation 3.24.** Suppose

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

Then the debt records the change in the potential `ψ` produced by the transition.

* **Positive debt:** `D(b_i,b_j)>0`. The transition increases the potential.
* **Negative debt:** `D(b_i,b_j)<0`. The transition decreases the potential.
* **Zero debt:** `D(b_i,b_j)=0`. The transition preserves the potential.

The interpretation of `ψ` is deliberately left open. Depending on the application, it may represent entropy, free energy, computational obligation, information content, or another quantity.

The mathematical structure developed in this chapter does not require choosing one interpretation.

**Proposition 3.25 (Debt of a Path).** Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a path. If

$$
D=\delta\psi,
$$

then the total debt along the path is

$$
\sum_{k=0}^{n-1}D(b_k,b_{k+1}) = \psi(b_n)-\psi(b_0).
$$

**Proof.** Substituting the potential representation gives

$$
\sum_{k=0}^{n-1}
[\psi(b_{k+1})-\psi(b_k)].
$$

The sum telescopes:

$$
\psi(b_n)-\psi(b_0).
$$

`□`

**Corollary 3.26.** The total debt of a path depends only on its endpoints, not on the path itself.

**Proof.** Immediate from Proposition 3.25. `□`

**Remark 3.27.** This is the fundamental conservative property of debt.

The energy quasi-metric is endpoint-dependent in a different sense: `d(b_i,b_j)` is defined through a minimization over paths. Debt is stronger. Every path between the same endpoints has the same total debt.

---

## 3.8 Summary

This chapter introduced the debt function

$$
D:B\times B\to\mathbb R
$$

through two axioms:

* **(D1) Additivity**

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k);
$$

* **(D2) Antisymmetry**

$$
D(b_i,b_j) = -D(b_j,b_i).
$$

From these axioms we derived:

* **Identity**

$$
D(b,b)=0;
$$

* **Cycle invariance:** the total debt around every closed path is zero;
* **Path independence:** every path between the same endpoints has the same total debt;
* **Gauge invariance:** adding a constant to a potential does not change its differences;
* **Cohomological characterization:** debt functions are exactly the alternating `1`-cocycles of the cochain structure introduced above.

The central remaining question is whether every debt function arises from a potential.

That is, given `D` satisfying (D1) and (D2), does there exist

$$
\psi:B\to\mathbb R
$$

such that

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i)?
$$

For the complete state space considered here, the answer is yes. The proof is the subject of Chapter 4.



