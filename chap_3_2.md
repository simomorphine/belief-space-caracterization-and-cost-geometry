# Chapter 3: The Debt Function

---

## 3.1 The asymmetry of cost

Chapter 2 established the energy quasi-metric `d` as the cost of moving between states of the belief space. Because `d` is a quasi-metric, it need not be symmetric. In general,

```math
d(b_i,b_j)\neq d(b_j,b_i).
```

This asymmetry is not an error in the construction. It records the fact that moving from `b_i` to `b_j` may have a different cost from moving in the opposite direction.

**Observation 3.1.** There may exist $b_i,b_j\in B$ such that

```math
d(b_i,b_j)\neq d(b_j,b_i).
```

The first task of this chapter is therefore to isolate the asymmetric part of the energy quasi-metric.

**Definition 3.2 (Symmetric and Antisymmetric Parts).** Assume that $d(b_i,b_j)<+\infty$ for all $b_i,b_j\in B$. Define

```math
S(b_i,b_j)
:=
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right)
```

and

```math
A(b_i,b_j)
:=
\frac12\left(d(b_i,b_j)-d(b_j,b_i)\right).
```

We call `S` the **symmetric part** of the cost and `A` the **antisymmetric part** of the cost.

The function `A` measures the directional imbalance of the cost. It is positive when the transition from `b_i` to `b_j` is more expensive than the reverse transition, negative when it is cheaper, and zero when the two directions have equal cost.

**Proposition 3.3.** The antisymmetric part `A` satisfies:

1. `A(b_i,b_j)=-A(b_j,b_i)`;
2. `A(b,b)=0`;
3. `A(b_i,b_j)>0` if and only if `d(b_i,b_j)>d(b_j,b_i)`;
4.

```math
|A(b_i,b_j)|
\leq
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right).
```

**Proof.**

For antisymmetry,

```math
A(b_j,b_i)
=
\frac12\left(d(b_j,b_i)-d(b_i,b_j)\right)
=
-A(b_i,b_j).
```

On the diagonal,

```math
A(b,b)
=
\frac12\left(d(b,b)-d(b,b)\right)
=
0.
```

The sign property follows directly from the definition. Finally,

```math
|A(b_i,b_j)|
=
\frac12
\left|
d(b_i,b_j)-d(b_j,b_i)
\right|
```

and therefore

```math
|A(b_i,b_j)|
\leq
\frac12
\left(
d(b_i,b_j)+d(b_j,b_i)
\right).
```

`□`

The symmetric and antisymmetric parts reconstruct the original cost.

**Proposition 3.4 (Canonical Decomposition).** The energy quasi-metric admits the decomposition

```math
d=S+A,
```

where `S` is symmetric and `A` is antisymmetric. This decomposition is unique.

**Proof.**

By definition,

```math
S(b_i,b_j)+A(b_i,b_j)
=
\frac12(d(b_i,b_j)+d(b_j,b_i))
+
\frac12(d(b_i,b_j)-d(b_j,b_i)),
```

so

```math
S(b_i,b_j)+A(b_i,b_j)=d(b_i,b_j).
```

The function `S` is symmetric and `A` is antisymmetric by construction.

For uniqueness, suppose

```math
d=S'+A',
```

where `S'` is symmetric and `A'` is antisymmetric. Evaluating the same equation with `b_i` and `b_j` exchanged, then adding and subtracting the two equations, gives

```math
S'=S,
\qquad
A'=A.
```

Thus the decomposition is unique. `□`

**Remark 3.5.** The antisymmetric component `A` should not be identified with the debt function introduced in this chapter. `A` is determined directly by the asymmetry of the energy quasi-metric. Debt is a separate object whose mathematical structure will be introduced independently.

The distinction is important. Asymmetry tells us that the cost of a transition depends on its direction. It does not, by itself, tell us whether the directional quantity satisfies additional structural properties such as additivity or path independence.

The purpose of the following sections is to investigate this additional structure.

---

## 3.2 The debt function: definition

We now introduce the central object of the chapter.

**Definition 3.6 (Debt Function).** Let `B` be a belief space. A **debt function** is a function

$$
D:B\times B\to\mathbb R
$$

satisfying:

* **(D1) Additivity.**

```math
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k)
```

for all $b_i,b_j,b_k\in B$.

* **(D2) Antisymmetry.**

```math
D(b_i,b_j)
=
-D(b_j,b_i)
```

for all $b_i,b_j\in B$.

These are the only axioms. Everything else in this chapter will be derived from them.

**Remark 3.7.** The axioms (D1) and (D2) are satisfied by every potential difference. If $\psi:B\to\mathbb R$ is any function and

```math
D(b_i,b_j):=\psi(b_j)-\psi(b_i),
```

then `D` satisfies both axioms.

The converse—that every debt function arises from such a potential—is the subject of Chapter 4.

**Remark 3.8.** The debt function is not the same as the asymmetry `A`.

The asymmetry

```math
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right)
```

measures directional imbalance in the cost.

Debt is a separate function satisfying the stronger structural condition of additivity. In particular, `A` need not be additive, whereas `D` is additive by axiom (D1).

---

## 3.3 Immediate consequences

The two axioms (D1) and (D2) have immediate consequences.

**Proposition 3.9 (Identity).** For every $b\in B$,

```math
D(b,b)=0.
```

**Proof.** By (D2),

```math
D(b,b)=-D(b,b).
```

Hence

```math
2D(b,b)=0,
```

so

```math
D(b,b)=0.
```

`□`

---

**Proposition 3.10 (Cycle Invariance).** For any closed path

```math
b_1\to b_2\to\cdots\to b_n\to b_1,
```

the total debt is zero:

```math
\sum_{k=1}^{n}D(b_k,b_{k+1})=0,
```

where $b_{n+1}:=b_1$.

**Proof.** By (D1),

```math
D(b_k,b_{k+1})
=
D(b_1,b_{k+1})-D(b_1,b_k).
```

Summing over $k=1,\ldots,n$ gives a telescoping sum:

```math
\sum_{k=1}^{n}D(b_k,b_{k+1})
=
D(b_1,b_{n+1})-D(b_1,b_1).
```

Since $b_{n+1}=b_1$ and Proposition 3.9 gives $D(b_1,b_1)=0$,

```math
\sum_{k=1}^{n}D(b_k,b_{k+1})=0.
```

`□`

---

**Proposition 3.11 (Path Independence).** If $\gamma_1$ and $\gamma_2$ are two paths from $b_i$ to $b_j$, then

```math
\sum_{e\in\gamma_1}D(e)
=
\sum_{e\in\gamma_2}D(e).
```

**Proof.** The concatenation

```math
\gamma_1\cdot\gamma_2^{-1}
```

is a closed path. By Proposition 3.10, its total debt is zero.

By (D2), reversing a transition reverses its debt:

```math
D(b_{k+1},b_k)=-D(b_k,b_{k+1}).
```

Therefore,

```math
\sum_{e\in\gamma_1}D(e)
-
\sum_{e\in\gamma_2}D(e)
=
0.
```

Hence

```math
\sum_{e\in\gamma_1}D(e)
=
\sum_{e\in\gamma_2}D(e).
```

`□`

**Remark 3.12.** Proposition 3.11 is an important structural property. The total debt of a path depends only on its endpoints, not on the particular path taken.

This is stronger than the endpoint dependence of the energy quasi-metric. The energy quasi-metric is obtained by minimizing over possible paths. Debt is different: every path between the same endpoints has the same total debt.

---

**Proposition 3.13 (Gauge Invariance of Potential Representations).** Let $\psi:B\to\mathbb R$ and define

```math
D(b_i,b_j):=\psi(b_j)-\psi(b_i).
```

Then `D` satisfies (D1) and (D2). Moreover, if

```math
\psi'=\psi+c
```

for a constant $c\in\mathbb R$, then

```math
D_{\psi'}=D_\psi.
```

**Proof.**

For (D1),

```math
\psi(b_k)-\psi(b_i)
=
[\psi(b_j)-\psi(b_i)]
+
[\psi(b_k)-\psi(b_j)].
```

For (D2),

```math
\psi(b_j)-\psi(b_i)
=
-[\psi(b_i)-\psi(b_j)].
```

Finally,

```math
(\psi(b_j)+c)-(\psi(b_i)+c)
=
\psi(b_j)-\psi(b_i).
```

Thus adding a constant to the potential does not change the debt.

`□`

**Remark 3.14.** Proposition 3.13 establishes the forward direction: every potential difference is a debt function. The converse is not assumed here. It is the central question of Chapter 4.

---

## 3.4 Why Debt?

The energy quasi-metric `d` describes the cost associated with moving between states of the belief space. Its asymmetry records the fact that the cost of moving from `b_i` to `b_j` may differ from the cost of moving from `b_j` to `b_i`.

But cost asymmetry alone does not provide a complete description of what happens during an information-processing transition.

An information-processing system does not merely move between states. As it moves, it accumulates information, changes its internal state, makes decisions, and carries the consequences of previous transitions into future states. This motivates introducing a second quantity that is distinct from energetic cost.

We call this quantity **debt**.

The purpose of the debt function is not to measure how expensive a transition is. Instead, it records a directed quantity that accumulates along transitions and cancels when a closed cycle is completed.

This distinction is fundamental.

The cost function answers a question such as:

> **How much does it cost to move from one state to another?**

The debt function answers a different question:

> **What directed quantity is carried from one state to another?**

These quantities need not coincide.

In particular, the antisymmetric part of the energy quasi-metric,

```math
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right),
```

measures the directional imbalance of cost. There is no reason, in general, for this quantity to satisfy the additivity required of a debt function.

Debt is therefore introduced as an independent mathematical object rather than being defined as a transformation of the energy quasi-metric.

The two axioms imposed on debt express the structure we require.

**Additivity** means that debt accumulated over successive transitions is the sum of the debts of the individual transitions. Thus, for

```math
b_i\to b_j\to b_k,
```

the total debt is

```math
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
```

**Antisymmetry** means that reversing a transition reverses the sign of its debt:

```math
D(b_i,b_j)
=
-D(b_j,b_i).
```

Together, these properties imply that debt is path-independent and that the total debt around every closed path is zero.

This gives debt a structure fundamentally different from the energy cost.

A path may have different energetic costs depending on how it is traversed, and the energy quasi-metric may therefore require a minimization over possible paths. Debt behaves differently: once the two endpoints are fixed, the total debt is already determined.

This observation leads to the central mathematical question of the next chapter.

If the debt between two states depends only on its endpoints, can the debt always be represented by assigning a scalar potential to each state?

That is, does there necessarily exist a function

```math
\psi:B\to\mathbb R
```

such that

```math
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i)?
```

Chapter 4 investigates this question.

---

## 3.5 The Debt of a Path

The path-independence result allows us to define the total debt accumulated along a path without introducing any additional structure.

**Definition 3.15 (Debt of a Path).** Let

```math
\gamma=(b_0,b_1,\ldots,b_n)
```

be a path in `B`. The **total debt** along `\gamma` is defined by

```math
D(\gamma)
:=
\sum_{k=0}^{n-1}D(b_k,b_{k+1}).
```

The quantity `D(\gamma)` is the accumulated debt along the sequence of transitions making up the path.

**Proposition 3.16 (Endpoint Determination).** For any path

```math
\gamma=(b_0,b_1,\ldots,b_n),
```

the total debt satisfies

```math
D(\gamma)=D(b_0,b_n).
```

**Proof.**

Repeated application of (D1) gives

```math
D(b_0,b_n)
=
D(b_0,b_1)
+
D(b_1,b_2)
+\cdots+
D(b_{n-1},b_n).
```

Therefore,

```math
D(\gamma)=D(b_0,b_n).
```

`□`

**Remark 3.17.** Proposition 3.16 gives another formulation of path independence. The total debt accumulated along a path is completely determined by its initial and final states.

No minimization over paths is required.

This property is one of the main structural differences between debt and the energy quasi-metric.

---

## 3.6 A finite example

Consider the belief space

```math
B=\{b_1,b_2,b_3\}.
```

Suppose

```math
D(b_1,b_2)=2
```

and

```math
D(b_2,b_3)=3.
```

By additivity,

```math
D(b_1,b_3)
=
D(b_1,b_2)+D(b_2,b_3)
=
2+3
=
5.
```

By antisymmetry,

```math
D(b_2,b_1)=-2,
```

```math
D(b_3,b_2)=-3,
```

and

```math
D(b_3,b_1)=-5.
```

Consider the closed path

```math
b_1\to b_2\to b_3\to b_1.
```

Its total debt is

```math
2+3-5=0.
```

Thus the cycle has zero total debt, as predicted by Proposition 3.10.

Now compare the two paths from `b_1` to `b_3`:

```math
b_1\to b_3
```

and

```math
b_1\to b_2\to b_3.
```

The first has total debt

```math
D(b_1,b_3)=5,
```

while the second has total debt

```math
D(b_1,b_2)+D(b_2,b_3)=2+3=5.
```

The two paths therefore have the same total debt.

The example illustrates the distinction between **path-dependent cost** and **path-independent debt**.

---

## 3.7 Summary

This chapter introduced the debt function

```math
D:B\times B\to\mathbb R
```

through two axioms:

* **(D1) Additivity**

```math
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k);
```

* **(D2) Antisymmetry**

```math
D(b_i,b_j)
=
-D(b_j,b_i).
```

From these axioms we derived:

* **Identity**

```math
D(b,b)=0;
```

* **Cycle invariance:** the total debt around every closed path is zero;
* **Path independence:** every path between the same endpoints has the same total debt;
* **Endpoint determination:** the total debt of a path equals the debt between its endpoints.

We also distinguished the debt function from the antisymmetric part of the energy quasi-metric.

The central remaining question is whether every debt function arises from a scalar potential.

That is, given `D` satisfying (D1) and (D2), does there exist

```math
\psi:B\to\mathbb R
```

such that

```math
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i)?
```

This is the central question of Chapter 4.

---

# Exercises

### Exercise 3.1 — Antisymmetric cost

Let

```math
d(b_1,b_2)=7
```

and

```math
d(b_2,b_1)=3.
```

Compute the symmetric part `S(b_1,b_2)` and the antisymmetric part `A(b_1,b_2)`.

Verify that

```math
d(b_1,b_2)=S(b_1,b_2)+A(b_1,b_2).
```

---

### Exercise 3.2 — Reconstructing the cost

Suppose

```math
S(b_i,b_j)=4
```

and

```math
A(b_i,b_j)=-1.
```

Compute

```math
d(b_i,b_j)
```

and

```math
d(b_j,b_i).
```

---

### Exercise 3.3 — Basic debt values

Suppose

```math
D(b_1,b_2)=4
```

and

```math
D(b_2,b_3)=-7.
```

Use (D1) to determine `D(b_1,b_3)`.

Then use (D2) to determine:

```math
D(b_2,b_1),
D(b_3,b_2),
D(b_3,b_1).
```

---

### Exercise 3.4 — Zero debt on a cycle

Let

```math
D(b_1,b_2)=2,
```

```math
D(b_2,b_3)=5,
```

and

```math
D(b_3,b_1)=-7.
```

Verify directly that the total debt around the cycle

```math
b_1\to b_2\to b_3\to b_1
```

is zero.

---

### Exercise 3.5 — Path independence

Suppose there are two paths from `b_1` to `b_4`:

```math
\gamma_1:
b_1\to b_2\to b_4
```

and

```math
\gamma_2:
b_1\to b_3\to b_4.
```

The debt values are

```math
D(b_1,b_2)=2,
```

```math
D(b_2,b_4)=5,
```

```math
D(b_1,b_3)=4,
```

and

```math
D(b_3,b_4)=3.
```

Determine whether these values can define a debt function satisfying (D1).

---

### Exercise 3.6 — Detecting inconsistency

Consider the directed transitions

```math
D(b_1,b_2)=2,
```

```math
D(b_2,b_3)=4,
```

and

```math
D(b_1,b_3)=7.
```

Can these three values belong to a debt function satisfying (D1)?

Explain why or why not.

---

### Exercise 3.7 — Cycle test

Suppose a directed graph contains the cycle

```math
b_1\to b_2\to b_3\to b_4\to b_1.
```

The debt values on the first three edges are

```math
2,\quad -1,\quad 5.
```

What must the debt on the final edge be if the function satisfies cycle invariance?

---

### Exercise 3.8 — Path reversal

Let

```math
\gamma:
b_1\to b_2\to b_3\to b_4
```

with edge debts

```math
3,\quad -2,\quad 6.
```

Compute the total debt of the reversed path

```math
\gamma^{-1}:
b_4\to b_3\to b_2\to b_1.
```

---

### Exercise 3.9 — Path debt

Let

```math
\gamma=(b_0,b_1,b_2,b_3,b_4)
```

and suppose

```math
D(b_0,b_1)=1,
```

```math
D(b_1,b_2)=4,
```

```math
D(b_2,b_3)=-2,
```

and

```math
D(b_3,b_4)=6.
```

Compute `D(\gamma)`.

What does Proposition 3.16 imply about `D(b_0,b_4)`?

---

### Exercise 3.10 — Potential differences

Let

```math
\psi(b_1)=2,
\qquad
\psi(b_2)=5,
\qquad
\psi(b_3)=1.
```

Define

```math
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
```

Compute

```math
D(b_1,b_2),
D(b_2,b_3),
D(b_1,b_3).
```

Verify (D1) for the three states.

---

### Exercise 3.11 — Gauge transformation

Let

```math
\psi(b_1)=2,
\qquad
\psi(b_2)=7.
```

Define

```math
D(b_1,b_2)=\psi(b_2)-\psi(b_1).
```

Now define

```math
\psi'(b)=\psi(b)+10.
```

Show that the debt remains unchanged.

---

### Exercise 3.12 — Conceptual distinction

Explain in your own words why the antisymmetric part

```math
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right)
```

cannot automatically be identified with the debt function `D`.

Your answer should address the role of additivity.
