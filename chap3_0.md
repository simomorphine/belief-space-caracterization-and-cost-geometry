# Chapter 3: The Debt Function

---

## 3.1 The asymmetry of cost

Chapter 2 established the energy quasi-metric $d$ as the cost of moving between states of the belief space. Because $d$ is a quasi-metric, it need not be symmetric. In general,

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

This asymmetry is not an error in the construction. It records the fact that moving from $b_i$ to $b_j$ may have a different cost from moving in the opposite direction.

**Observation 3.1.** There may exist $b_i,b_j\in\mathcal B$ such that

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

The first task of this chapter is therefore to isolate the asymmetric part of the energy quasi-metric.

### Definition 3.2 (Symmetric and antisymmetric parts)

Assume that $d(b_i,b_j)<+\infty$ for all $b_i,b_j\in\mathcal B$. Define

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

We call $S$ the **symmetric part** of the cost and $A$ the **antisymmetric part** of the cost.

The function $A$ measures the directional imbalance of the cost. It is positive when the transition from $b_i$ to $b_j$ is more expensive than the reverse transition, negative when it is cheaper, and zero when the two directions have equal cost.

### Proposition 3.3

The antisymmetric part $A$ satisfies:

1. $A(b_i,b_j)=-A(b_j,b_i)$;
2. $A(b,b)=0$;
3. $A(b_i,b_j)>0$ if and only if $d(b_i,b_j)>d(b_j,b_i)$;
4.

$$
|A(b_i,b_j)|
\leq
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right).
$$

**Proof.**

For antisymmetry,

$$
A(b_j,b_i)
=
\frac12\left(d(b_j,b_i)-d(b_i,b_j)\right)
=
-A(b_i,b_j).
$$

On the diagonal,

$$
A(b,b)
=
\frac12\left(d(b,b)-d(b,b)\right)
=
0.
$$

The sign property follows directly from the definition. Finally,

$$
|A(b_i,b_j)|
=
\frac12
\left|
d(b_i,b_j)-d(b_j,b_i)
\right|
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

$\square$

The symmetric and antisymmetric parts reconstruct the original cost.

### Proposition 3.4 (Canonical decomposition)

The energy quasi-metric admits the decomposition

$$
d=S+A,
$$

where $S$ is symmetric and $A$ is antisymmetric. This decomposition is unique.

**Proof.**

By definition,

$$
S(b_i,b_j)+A(b_i,b_j)
=
\frac12(d(b_i,b_j)+d(b_j,b_i))
+
\frac12(d(b_i,b_j)-d(b_j,b_i)),
$$

so

$$
S(b_i,b_j)+A(b_i,b_j)=d(b_i,b_j).
$$

The function $S$ is symmetric and $A$ is antisymmetric by construction.

For uniqueness, suppose

$$
d=S'+A',
$$

where $S'$ is symmetric and $A'$ is antisymmetric. Evaluating the same equation with $b_i$ and $b_j$ exchanged and adding and subtracting the two equations gives

$$
S'=S,
\qquad
A'=A.
$$

Thus the decomposition is unique.

$\square$

### Remark 3.5 — Asymmetry is not debt

The antisymmetric component $A$ should **not** be identified with the debt function introduced in this chapter.

The function $A$ is determined directly by the asymmetry of the energy quasi-metric. It measures a directional imbalance in cost.

Debt will be introduced as a separate mathematical object.

This distinction is important. Antisymmetry alone does not imply additivity. In particular, an arbitrary antisymmetric function need not satisfy

$$
A(b_i,b_k)
=
A(b_i,b_j)+A(b_j,b_k).
$$

The following sections investigate the stronger structure obtained when this additivity condition is imposed.

---

## 3.2 The debt function: the fundamental axiom

We now introduce the central object of the chapter.

### Definition 3.6 (Debt function)

Let $\mathcal B$ be a belief space. A **debt function** is a function

$$
D:\mathcal B\times\mathcal B\to\mathbb R
$$

satisfying the following axiom:

**(D1) Additivity.** For every $b_i,b_j,b_k\in\mathcal B$,

$$
\boxed{
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
}
$$

This is the fundamental axiom of debt.

No separate antisymmetry axiom is required.

### Remark 3.7 — Why only one axiom?

At first it is natural to impose both additivity and antisymmetry:

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k)
$$

and

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

However, the second condition is already forced by the first.

Thus antisymmetry is not an independent assumption.

This is an important structural simplification:

$$
\boxed{
\text{D1 alone}
\Longrightarrow
\text{D2}.
}
$$

The debt structure therefore has a single fundamental axiom: **additivity under composition of transitions**.

---

## 3.3 Consequences of additivity

The strength of (D1) becomes apparent immediately.

### Proposition 3.8 (Zero on the diagonal)

For every $b\in\mathcal B$,

$$
D(b,b)=0.
$$

**Proof.**

Apply (D1) with

$$
b_i=b_j=b_k=b.
$$

Then

$$
D(b,b)=D(b,b)+D(b,b).
$$

Subtracting $D(b,b)$ from both sides gives

$$
D(b,b)=0.
$$

$\square$

### Proposition 3.9 (Antisymmetry is derived)

For every $b_i,b_j\in\mathcal B$,

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

**Proof.**

Apply (D1) with $b_k=b_i$:

$$
D(b_i,b_i)
=
D(b_i,b_j)+D(b_j,b_i).
$$

By Proposition 3.8,

$$
0
=
D(b_i,b_j)+D(b_j,b_i).
$$

Therefore,

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

$\square$

Thus the property that was previously considered a second axiom is actually a theorem.

### Proposition 3.10 (Cycle invariance)

For any closed path

$$
b_1\to b_2\to\cdots\to b_n\to b_1,
$$

the total debt is zero:

$$
\sum_{k=1}^{n}D(b_k,b_{k+1})=0,
$$

where $b_{n+1}=b_1$.

**Proof.**

By (D1),

$$
D(b_k,b_{k+1})
=
D(b_1,b_{k+1})-D(b_1,b_k).
$$

Therefore,

$$
\begin{aligned}
\sum_{k=1}^{n}D(b_k,b_{k+1})
&=
\sum_{k=1}^{n}
\left[
D(b_1,b_{k+1})-D(b_1,b_k)
\right] \\
&=
D(b_1,b_{n+1})-D(b_1,b_1).
\end{aligned}
$$

Since $b_{n+1}=b_1$ and $D(b_1,b_1)=0$,

$$
\sum_{k=1}^{n}D(b_k,b_{k+1})=0.
$$

$\square$

### Proposition 3.11 (Path independence)

Let

$$
\gamma_1=(b_0,b_1,\ldots,b_m)
$$

and

$$
\gamma_2=(c_0,c_1,\ldots,c_n)
$$

be two paths with the same endpoints:

$$
b_0=c_0,
\qquad
b_m=c_n.
$$

Then

$$
\sum_{k=0}^{m-1}D(b_k,b_{k+1})
=
\sum_{k=0}^{n-1}D(c_k,c_{k+1}).
$$

**Proof.**

By repeatedly applying (D1),

$$
\sum_{k=0}^{m-1}D(b_k,b_{k+1})
=
D(b_0,b_m)
$$

and

$$
\sum_{k=0}^{n-1}D(c_k,c_{k+1})
=
D(c_0,c_n).
$$

Since the endpoints are identical,

$$
D(b_0,b_m)=D(c_0,c_n).
$$

Therefore the two path sums are equal.

$\square$

### Remark 3.12

This is stronger than ordinary endpoint dependence of a cost.

For the energy quasi-metric, $d(b_i,b_j)$ may represent the minimum cost required to move between two states.

For debt, **every path** between the same two states has the same total debt.

Thus debt is a conservative quantity.

---

## 3.4 The fundamental equivalence: additivity and potential

The previous results suggest that debt behaves like a difference of a scalar quantity.

We can now make this precise.

### Theorem 3.13 (Potential representation)

Let

$$
D:\mathcal B\times\mathcal B\to\mathbb R.
$$

Then the following are equivalent:

1. $D$ satisfies the additivity axiom (D1);
2. there exists a function

$$
\psi:\mathcal B\to\mathbb R
$$

such that

$$
\boxed{
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
}
$$

for all $b_i,b_j\in\mathcal B$.

In other words,

$$
\boxed{
\text{Debt is additive}
\iff
\text{Debt is a potential difference}.
}
$$

**Proof.**

### $(2)\Rightarrow(1)$

Suppose

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Then

$$
\begin{aligned}
D(b_i,b_j)+D(b_j,b_k)
&=
[\psi(b_j)-\psi(b_i)]
+
[\psi(b_k)-\psi(b_j)]\\
&=
\psi(b_k)-\psi(b_i)\\
&=
D(b_i,b_k).
\end{aligned}
$$

Therefore (D1) holds.

### $(1)\Rightarrow(2)$

Assume that $D$ satisfies (D1).

Choose an arbitrary reference state

$$
b_0\in\mathcal B.
$$

Define

$$
\psi(b):=D(b_0,b).
$$

Applying (D1) to the triple $(b_0,b_i,b_j)$ gives

$$
D(b_0,b_j)
=
D(b_0,b_i)+D(b_i,b_j).
$$

Therefore,

$$
D(b_i,b_j)
=
D(b_0,b_j)-D(b_0,b_i).
$$

Using the definition of $\psi$,

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

Thus a potential representation exists.

$\square$

### Remark 3.14 — What this means

This theorem changes the interpretation of the debt function.

We do not first assume additivity and then independently assume the existence of a potential.

Rather,

$$
\boxed{
\text{additivity and potential representation are equivalent descriptions of the same structure}.
}
$$

The additive formulation emphasizes **composition of transitions**.

The potential formulation emphasizes **differences between states**.

The two descriptions are mathematically interchangeable.

---

## 3.5 Gauge freedom of the potential

The potential representing a debt function is not unique.

### Proposition 3.15 (Gauge invariance)

Suppose

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

For any constant $c\in\mathbb R$, define

$$
\psi'(b)=\psi(b)+c.
$$

Then

$$
\psi'(b_j)-\psi'(b_i)
=
\psi(b_j)-\psi(b_i),
$$

so $\psi'$ generates exactly the same debt function.

**Proof.**

$$
\begin{aligned}
\psi'(b_j)-\psi'(b_i)
&=
[\psi(b_j)+c]-[\psi(b_i)+c]\\
&=
\psi(b_j)-\psi(b_i).
\end{aligned}
$$

$\square$

Thus the potential is determined only up to an additive constant.

### Corollary 3.16

For a fixed debt function $D$, any two potentials $\psi_1$ and $\psi_2$ satisfying

$$
D(b_i,b_j)
=
\psi_1(b_j)-\psi_1(b_i)
=
\psi_2(b_j)-\psi_2(b_i)
$$

differ by a constant.

That is,

$$
\psi_2=\psi_1+c
$$

for some $c\in\mathbb R$.

---

## 3.6 A cohomology reminder

The preceding results have a natural interpretation in cohomology.

We only need a small part of the general theory.

A **cochain** is a function assigned to objects of a specified dimension.

For a state space $\mathcal B$:

* a $0$-cochain assigns a number to each state;
* a $1$-cochain assigns a number to each ordered pair of states;
* a $2$-cochain assigns a number to each ordered triple of states.

We write these spaces as

$$
C^0(\mathcal B),\qquad
C^1(\mathcal B),\qquad
C^2(\mathcal B).
$$

Thus,

$$
\psi:\mathcal B\to\mathbb R
$$

is a $0$-cochain, while

$$
D:\mathcal B\times\mathcal B\to\mathbb R
$$

is a $1$-cochain.

The **coboundary operator** $\delta$ maps a $k$-cochain to a $(k+1)$-cochain.

For a $0$-cochain,

$$
(\delta\psi)(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

For a $1$-cochain,

$$
(\delta D)(b_i,b_j,b_k)
=
D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j).
$$

The fundamental property is

$$
\delta^2=0.
$$

A **cocycle** is a cochain whose coboundary vanishes.

Thus a $1$-cochain $D$ is a $1$-cocycle when

$$
\delta D=0.
$$

Expanding this condition gives

$$
D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j)=0,
$$

or equivalently,

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

Therefore:

$$
\boxed{
D\text{ is a 1-cocycle}
\iff
D\text{ satisfies additivity}.
}
$$

A **coboundary** is a cochain obtained by applying $\delta$ to another cochain.

Thus

$$
D=\delta\psi
$$

means

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Every coboundary is automatically a cocycle because

$$
\delta^2=0.
$$

Hence

$$
\operatorname{im}\delta
\subseteq
\ker\delta.
$$

The $k$-th cohomology group is, roughly,

$$
H^k
=
\frac{\ker(\delta:C^k\to C^{k+1})}
{\operatorname{im}(\delta:C^{k-1}\to C^k)}.
$$

Cohomology therefore measures cocycles that are not coboundaries.

In the present complete-state setting, the first cohomology is trivial. Consequently,

$$
\boxed{
\text{every 1-cocycle is a coboundary}.
}
$$

This is exactly the result proved directly in Theorem 3.13:

$$
D\text{ additive}
\Longrightarrow
D=\delta\psi.
$$

The potential representation is therefore not an additional assumption. It is the statement that, in this setting, every additive debt cocycle is exact.

---

## 3.7 Debt as an alternating 1-cocycle

We can now state the cohomological structure precisely.

### Definition 3.17 (Discrete cochain structure)

Let $\mathcal B$ be a set, viewed as the vertex set of a complete directed structure.

For $k\geq0$, let $C^k(\mathcal B)$ denote the space of real-valued functions on ordered $(k+1)$-tuples of elements of $\mathcal B$.

In particular,

$$
C^0(\mathcal B)
=
\{\psi:\mathcal B\to\mathbb R\},
$$

$$
C^1(\mathcal B)
=
\{D:\mathcal B\times\mathcal B\to\mathbb R\},
$$

and

$$
C^2(\mathcal B)
=
\{F:\mathcal B^3\to\mathbb R\}.
$$

We use this as a **discrete cohomological framework** adapted to the belief space. It should not be confused with the classical differential-form construction on a smooth manifold.

### Definition 3.18 (Coboundary)

The coboundary operator on $0$-cochains is

$$
(\delta\psi)(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

The coboundary operator on $1$-cochains is

$$
(\delta D)(b_i,b_j,b_k)
=
D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j).
$$

### Proposition 3.19 (Nilpotency)

For every $\psi\in C^0(\mathcal B)$,

$$
\delta^2\psi=0.
$$

**Proof.**

$$
\begin{aligned}
(\delta(\delta\psi))(b_i,b_j,b_k)
&=
(\delta\psi)(b_j,b_k)
-
(\delta\psi)(b_i,b_k)
+
(\delta\psi)(b_i,b_j)\\
&=
[\psi(b_k)-\psi(b_j)]
-
[\psi(b_k)-\psi(b_i)]
+
[\psi(b_j)-\psi(b_i)]\\
&=0.
\end{aligned}
$$

Therefore,

$$
\delta^2=0.
$$

$\square$

### Proposition 3.20 (Additivity is the cocycle condition)

A function

$$
D\in C^1(\mathcal B)
$$

satisfies (D1) if and only if

$$
\delta D=0.
$$

**Proof.**

The equation $\delta D=0$ means

$$
D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j)=0.
$$

Rearranging,

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k),
$$

which is exactly (D1).

$\square$

### Remark 3.21 — Alternation is derived

A $1$-cochain is called **alternating** if

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

For debt, this property is **not an additional axiom**.

By Proposition 3.9, every additive debt function is automatically alternating.

Therefore the correct hierarchy is:

$$
\boxed{
\text{additive 1-cochain}
\Longrightarrow
\text{alternating 1-cocycle}.
}
$$

More precisely, an additive $1$-cochain is automatically a $1$-cocycle by Proposition 3.20 and automatically alternating by Proposition 3.9.

### Corollary 3.22

A debt function is precisely an additive $1$-cochain, equivalently a $1$-cocycle, and every debt function is automatically alternating.

In the present complete-state setting,

$$
\boxed{
\text{Debt}
\iff
\text{1-cocycle}
\iff
\text{potential difference}.
}
$$

The alternation is a consequence rather than an independent defining condition.

### Remark 3.23 — Asymmetry is not debt

The cost asymmetry

$$
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right)
$$

is an alternating $1$-cochain.

However, it need not satisfy

$$
\delta A=0.
$$

Therefore it need not be a $1$-cocycle and need not admit a potential representation.

This gives the fundamental distinction:

$$
A:
\quad
\text{alternating 1-cochain}
$$

whereas

$$
D:
\quad
\text{additive 1-cochain}
=
\text{1-cocycle}.
$$

Thus antisymmetry alone is not enough to obtain the structure of debt.

---

## 3.8 The debt of a transition

We now return to the interpretation of debt in belief space.

### Definition 3.24 (Debt of a transition)

For a transition

$$
b_i\to b_j,
$$

the debt associated with the transition is

$$
D(b_i,b_j).
$$

By Theorem 3.13, there exists a potential $\psi$ such that

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

The interpretation of $\psi$ is deliberately left open.

Depending on the application, $\psi$ might represent entropy, free energy, information content, computational obligation, or another scalar quantity associated with a state.

The mathematics only requires that such a scalar potential exists.

### Interpretation 3.25

If

$$
D(b_i,b_j)>0,
$$

then

$$
\psi(b_j)>\psi(b_i),
$$

so the transition increases the potential.

If

$$
D(b_i,b_j)<0,
$$

then

$$
\psi(b_j)<\psi(b_i),
$$

so the transition decreases the potential.

If

$$
D(b_i,b_j)=0,
$$

then the potential is unchanged.

Thus debt measures a change in the potential associated with the state.

### Proposition 3.26 (Debt of a path)

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a path. Then its total debt is

$$
\sum_{k=0}^{n-1}D(b_k,b_{k+1})
=
\psi(b_n)-\psi(b_0).
$$

**Proof.**

Using the potential representation,

$$
\begin{aligned}
\sum_{k=0}^{n-1}D(b_k,b_{k+1})
&=
\sum_{k=0}^{n-1}
[\psi(b_{k+1})-\psi(b_k)]\\
&=
\psi(b_n)-\psi(b_0).
\end{aligned}
$$

All intermediate terms cancel.

$\square$

### Corollary 3.27

The total debt of a path depends only on its endpoints.

**Proof.**

The expression

$$
\psi(b_n)-\psi(b_0)
$$

contains only the initial and final states.

$\square$

### Remark 3.28

This is the conservative nature of debt.

A closed path satisfies

$$
\psi(b_0)-\psi(b_0)=0,
$$

so its total debt vanishes.

Thus debt cannot accumulate nonzero circulation around a closed loop.

This is fundamentally different from a general directional asymmetry in cost.

---

## 3.9 Why debt is a different object from cost asymmetry

The distinction between $A$ and $D$ can now be stated precisely.

The cost asymmetry is

$$
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right).
$$

It is automatically antisymmetric, but it need not be additive.

Debt satisfies

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

Therefore it is additive, and additivity forces antisymmetry.

The two objects therefore have different logical origins:

$$
\boxed{
A
\text{ is antisymmetric because of the definition of cost asymmetry}.
}
$$

while

$$
\boxed{
D
\text{ is antisymmetric because of additivity}.
}
$$

This distinction is important.

Two functions can both satisfy

$$
F(b_i,b_j)=-F(b_j,b_i)
$$

without having the same mathematical structure.

The additional requirement

$$
F(b_i,b_k)
=
F(b_i,b_j)+F(b_j,b_k)
$$

is what forces the potential representation.

Hence:

$$
\boxed{
\text{antisymmetry}
\not\Rightarrow
\text{potential}
}
$$

but, in the present setting,

$$
\boxed{
\text{additivity}
\iff
\text{potential difference}.
}
$$

The precise relationship between the cost asymmetry $A$ and other decompositions of quasi-metrics will be investigated later in the book.

---

## 3.10 Summary

This chapter introduced the debt function as an additive quantity on the belief space.

The fundamental definition is:

$$
\boxed{
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
}
$$

Everything important follows from this single axiom.

First,

$$
D(b,b)=0.
$$

Second,

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

Thus antisymmetry does not need to be imposed separately.

Third, debt has zero circulation around every closed path:

$$
\sum_{\gamma}D=0.
$$

Fourth, debt is path-independent: all paths between the same endpoints have the same total debt.

Most importantly, additivity is equivalent to potential representation:

$$
\boxed{
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
}
$$

Thus we obtain the central equivalence

$$
\boxed{
\text{additivity}
\iff
\text{1-cocycle}
\iff
\text{potential difference}.
}
$$

The potential is unique up to an additive constant.

From the cohomological viewpoint, debt is a $1$-cocycle, and in the complete-state setting every such cocycle is a coboundary.

The distinction from cost asymmetry is equally important:

$$
A
=
\frac12(d-d^T)
$$

is an alternating $1$-cochain, but it need not be a cocycle.

Debt therefore represents a much more constrained structure than mere directional asymmetry.

The main conceptual lesson is:

> **Additivity is not just one property of debt. It is the structural condition that makes debt a potential difference.**

---

## 3.11 References

The cohomological language used in this chapter is based on standard treatments of cochains, coboundaries, cocycles, and cohomology.

**Allen Hatcher.** *Algebraic Topology*, Chapter 3: Cohomology.

**Raoul Bott and Loring W. Tu.** *Differential Forms in Algebraic Topology*, Graduate Texts in Mathematics 82, Springer.

The construction used here is a discrete cochain framework adapted to the state space $\mathcal B$. It should therefore be understood as a discrete cohomological formulation inspired by standard constructions, rather than as a direct reproduction of the classical de Rham complex.

---

## 3.12 Exercises

**Exercise 3.1.** Verify directly that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

satisfies (D1) for every function

$$
\psi:\mathcal B\to\mathbb R.
$$

Then prove that antisymmetry follows.

---

**Exercise 3.2.** Prove that (D1) implies

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

Explain why there cannot exist a function satisfying (D1) but not antisymmetry.

---

**Exercise 3.3.** Let

$$
\mathcal B=\{1,2,3\}
$$

and define

$$
D(1,2)=2,\qquad
D(2,3)=3,\qquad
D(1,3)=5.
$$

Extend $D$ using antisymmetry and $D(i,i)=0$.

Verify that $D$ is additive and find a potential $\psi$ such that

$$
D=\delta\psi.
$$

---

**Exercise 3.4.** Let $\mathcal B$ be a set and let $D$ satisfy (D1). Choose a basepoint $s_0\in\mathcal B$ and define

$$
\psi_{s_0}(b)=D(s_0,b).
$$

Prove directly that

$$
D(b_i,b_j)
=
\psi_{s_0}(b_j)-\psi_{s_0}(b_i).
$$

---

**Exercise 3.5.** Prove that the decomposition

$$
d=S+A
$$

is unique.

---

**Exercise 3.6.** Construct an antisymmetric function $A$ on a three-state space that is **not** additive. Verify explicitly that

$$
A(b_1,b_3)
\neq
A(b_1,b_2)+A(b_2,b_3).
$$

---

**Exercise 3.7.** Let $D$ be a debt function. Show that replacing its potential $\psi$ by

$$
\psi'= \psi+c
$$

for any constant $c$ leaves $D$ unchanged.

---

**Exercise 3.8.** Let $\mathcal B$ be a finite set with $n$ elements. Show that the vector space of debt functions is isomorphic to

$$
\mathbb R^{n-1}.
$$

Hint: potentials are defined only up to an additive constant.

---

**Exercise 3.9.** Let $D_1$ and $D_2$ be debt functions. Prove that

$$
aD_1+bD_2
$$

is also a debt function for any $a,b\in\mathbb R$.

What is the corresponding potential?

---

**Exercise 3.10.** Let $D$ be a debt function and let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a closed path. Prove directly from (D1), without using the potential representation, that

$$
\sum_{k=0}^{n-1}D(b_k,b_{k+1})=0.
$$

---

**Exercise 3.11.** Explain in a few lines why antisymmetry alone is insufficient to define debt, while additivity is sufficient.
