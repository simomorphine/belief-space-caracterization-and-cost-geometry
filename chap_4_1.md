# Chapter 4: Exactness and the Basepoint Theorem

---

In Chapter 3, we introduced the debt function $D$ through two axioms:

* **(D1) Additivity**
* **(D2) Antisymmetry**

From these axioms, we derived several consequences, including identity, cycle invariance, and path independence.

We also observed that any function of the form

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

automatically satisfies the two debt axioms.

The central question of this chapter is the converse:

> **Does every debt function arise as the difference of a potential?**

The answer is yes.

The main result is the **basepoint theorem**. It gives an explicit construction of the potential from the debt function and shows that the potential is unique up to an additive constant.

This establishes that, on the complete state space considered in this book, every debt function is **exact**.

---

## 4.1 The Exactness Question

Let $\mathcal{B}$ be a state space and let

$$
D:\mathcal{B}\times\mathcal{B}\to\mathbb{R}
$$

be a debt function satisfying (D1) and (D2).

We know from Chapter 3 that debt is path independent. If

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

is a path from $b_0$ to $b_n$, then its total debt is

$$
D(\gamma) = \sum_{k=0}^{n-1}D(b_k,b_{k+1}).
$$

The path independence result tells us that

$$
D(\gamma)=D(b_0,b_n).
$$

This suggests that debt may not fundamentally depend on the transition itself.

Instead, it may arise from a quantity attached to the states.

Suppose there exists a function

$$
\psi:\mathcal{B}\to\mathbb{R}
$$

such that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Then the debt between two states is simply the change in the value of $\psi$.

The function $\psi$ will be called a **potential**.

The question is therefore:

> Given a debt function $D$, can we construct such a potential $\psi$?

The answer is provided by the following theorem.

---

## 4.2 The Basepoint Theorem

### Theorem 4.1 — Basepoint Theorem

Let $\mathcal{B}$ be a nonempty set and let

$$
D:\mathcal{B}\times\mathcal{B}\to\mathbb{R}
$$

satisfy:

**(D1) Additivity**

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k)
$$

for all $b_i,b_j,b_k\in\mathcal{B}$.

**(D2) Antisymmetry**

$$
D(b_i,b_j) = -D(b_j,b_i)
$$

for all $b_i,b_j\in\mathcal{B}$.

Choose any basepoint

$$
s_0\in\mathcal{B}.
$$

Define

$$
\psi_{s_0}(b):=D(s_0,b).
$$

Then

$$
\boxed{ D(b_i,b_j) = \psi_{s_0}(b_j)-\psi_{s_0}(b_i) }
$$

for all $b_i,b_j\in\mathcal{B}$.

Furthermore, if another function

$$
\phi:\mathcal{B}\to\mathbb{R}
$$

satisfies

$$
D(b_i,b_j)=\phi(b_j)-\phi(b_i),
$$

then there exists a constant $c\in\mathbb{R}$ such that

$$
\phi=\psi_{s_0}+c.
$$

Thus the potential exists and is unique up to an additive constant.

---

## 4.3 Proof of the Basepoint Theorem

The proof is constructive.

### Step 1: Choose a basepoint

Fix

$$
s_0\in\mathcal{B}.
$$

Define

$$
\psi_{s_0}(b):=D(s_0,b).
$$

This assigns a real number to every state relative to the chosen basepoint.

In particular,

$$
\psi_{s_0}(s_0)=D(s_0,s_0).
$$

From Chapter 3, identity gives

$$
D(s_0,s_0)=0.
$$

Therefore,

$$
\psi_{s_0}(s_0)=0.
$$

The chosen basepoint therefore fixes the additive normalization of the potential.

---

### Step 2: Compute the difference between two potential values

For arbitrary $b_i,b_j\in\mathcal{B}$,

$$
\psi_{s_0}(b_j)-\psi_{s_0}(b_i) = D(s_0,b_j)-D(s_0,b_i).
$$

By antisymmetry,

$$
D(s_0,b_i)=-D(b_i,s_0).
$$

Therefore,

$$
D(s_0,b_j)-D(s_0,b_i) = D(s_0,b_j)+D(b_i,s_0).
$$

Now apply additivity to the triple

$$
(b_i,s_0,b_j).
$$

We obtain

$$
D(b_i,b_j) = D(b_i,s_0)+D(s_0,b_j).
$$

Hence,

$$
\psi_{s_0}(b_j)-\psi_{s_0}(b_i) = D(b_i,b_j).
$$

Therefore,

$$
\boxed{ D(b_i,b_j) = \psi_{s_0}(b_j)-\psi_{s_0}(b_i) }.
$$

This proves the existence of a potential representation.

---

### Step 3: Uniqueness up to a constant

Suppose $\psi$ and $\phi$ are two potentials representing the same debt function:

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i)
$$

and

$$
D(b_i,b_j) = \phi(b_j)-\phi(b_i).
$$

Therefore,

$$
\psi(b_j)-\psi(b_i) = \phi(b_j)-\phi(b_i).
$$

Rearranging,

$$
\psi(b_j)-\phi(b_j) = \psi(b_i)-\phi(b_i).
$$

Since $b_i$ and $b_j$ are arbitrary,

$$
\psi(b)-\phi(b)
$$

has the same value at every point of $\mathcal{B}$.

Therefore there exists a constant $c\in\mathbb{R}$ such that

$$
\psi(b)-\phi(b)=c.
$$

Hence,

$$
\boxed{
\psi=\phi+c
}.
$$

The potential is therefore unique up to an additive constant.

$\square$

---

## 4.4 What the Basepoint Theorem Tells Us

The theorem contains three important facts.

### 1. A potential exists

Every debt function satisfying D1 and D2 can be represented as

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Thus the debt is **exact**.

### 2. The potential can be constructed directly

We do not need to solve a differential equation or perform an optimization.

Choose any state $s_0$ and define

$$
\psi_{s_0}(b)=D(s_0,b).
$$

The potential is obtained directly from the debt function.

### 3. The potential is not unique

If $\psi$ is a potential, then

$$
\psi'(b)=\psi(b)+c
$$

for any constant $c$ gives the same debt:

$$
\psi'(b_j)-\psi'(b_i) = [\psi(b_j)+c]-[\psi(b_i)+c].
$$

Therefore,

$$
\psi'(b_j)-\psi'(b_i) = \psi(b_j)-\psi(b_i).
$$

The absolute level of the potential is irrelevant.

Only differences matter.

---

## 4.5 The Basepoint as a Normalization

Choosing a basepoint provides a natural normalization.

For the potential

$$
\psi_{s_0}(b)=D(s_0,b),
$$

we have

$$
\psi_{s_0}(s_0)=0.
$$

Thus choosing $s_0$ is equivalent to choosing the state at which the potential is set to zero.

This does not change the debt function.

It only chooses a representative from the family of equivalent potentials.

This is analogous to choosing a reference level for a physical potential.

For example, if

$$
\psi(b)
$$

represents an energy-like quantity, then replacing it by

$$
\psi'(b)=\psi(b)+c
$$

changes the zero of the energy but does not change any energy difference.

The same mathematical structure appears here.

---

## 4.6 Change of Basepoint

The potential constructed from one basepoint can be compared directly with the potential constructed from another.

### Proposition 4.2 — Change of Basepoint

Let

$$
s_0,s_1\in\mathcal{B}
$$

be two basepoints.

Define

$$
\psi_{s_0}(b)=D(s_0,b)
$$

and

$$
\psi_{s_1}(b)=D(s_1,b).
$$

Then

$$
\boxed{ \psi_{s_1}(b) = \psi_{s_0}(b)+D(s_1,s_0) }
$$

for every $b\in\mathcal{B}$.

### Proof

By additivity,

$$
D(s_1,b) = D(s_1,s_0)+D(s_0,b).
$$

Therefore,

$$
\psi_{s_1}(b) = D(s_1,s_0)+\psi_{s_0}(b).
$$

Since $D(s_1,s_0)$ does not depend on $b$, the two potentials differ only by a constant.

$\square$

### Remark 4.3

The basepoint is therefore a **gauge choice**.

Different basepoints produce different numerical representations of the potential, but they all represent exactly the same debt function.

---

## 4.7 Exactness

We can now introduce the term **exact**.

A debt function is called **exact** if there exists a potential

$$
\psi:\mathcal{B}\to\mathbb{R}
$$

such that

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

The basepoint theorem therefore gives the following result.

### Corollary 4.4 — Exactness of Debt

Every debt function on $\mathcal{B}$ is exact.

### Proof

The basepoint theorem constructs a potential

$$
\psi_{s_0}(b)=D(s_0,b)
$$

satisfying

$$
D(b_i,b_j) = \psi_{s_0}(b_j)-\psi_{s_0}(b_i).
$$

Therefore $D$ is exact.

$\square$

The importance of this result is structural.

The debt function was initially introduced as an independent function on pairs of states.

The theorem shows that it has a simpler representation:

$$
\boxed{
D=\delta\psi
}
$$

where $\delta$ denotes the discrete difference operator.

Thus a transition quantity can be represented as the difference of a state quantity.

---

## 4.8 Debt Along a Path

The potential representation makes the path structure transparent.

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a path.

Its total debt is

$$
D(\gamma) = \sum_{k=0}^{n-1} D(b_k,b_{k+1}).
$$

Using the potential representation,

$$
D(b_k,b_{k+1}) = \psi(b_{k+1})-\psi(b_k).
$$

Therefore,

$$
D(\gamma) = \sum_{k=0}^{n-1} \left[ \psi(b_{k+1})-\psi(b_k) \right].
$$

The sum telescopes:

$$
D(\gamma) = \psi(b_n)-\psi(b_0).
$$

Hence,

$$
\boxed{ D(\gamma) = \psi(b_n)-\psi(b_0) }.
$$

The total debt of a path depends only on its endpoints.

This gives another interpretation of path independence.

### Corollary 4.5 — Path Independence

If $\gamma_1$ and $\gamma_2$ are two paths with the same initial state and final state, then

$$
D(\gamma_1)=D(\gamma_2).
$$

### Proof

Suppose both paths start at $b_0$ and end at $b_n$.

Then

$$
D(\gamma_1)=\psi(b_n)-\psi(b_0)
$$

and

$$
D(\gamma_2)=\psi(b_n)-\psi(b_0).
$$

Therefore,

$$
D(\gamma_1)=D(\gamma_2).
$$

$\square$

---

## 4.9 Closed Paths

The same argument gives an immediate result for closed paths.

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

with

$$
b_n=b_0.
$$

Then

$$
D(\gamma) = \psi(b_n)-\psi(b_0) = \psi(b_0)-\psi(b_0) = 0.
$$

Therefore:

### Corollary 4.6 — Zero Debt Around Closed Paths

For every closed path $\gamma$,

$$
\boxed{
D(\gamma)=0
}.
$$

This is the discrete analogue of the fact that an exact differential has zero integral around a closed path.

It also shows why cycle invariance and potential representation are closely connected.

---

## 4.10 A Finite Example

Consider the state space

$$
\mathcal{B}=\lbrace b_1,b_2,b_3\rbrace.
$$

Suppose

$$
D(b_1,b_2)=2,
$$

and

$$
D(b_2,b_3)=3.
$$

By additivity,

$$
D(b_1,b_3) = D(b_1,b_2)+D(b_2,b_3),
$$

so

$$
D(b_1,b_3)=5.
$$

By antisymmetry,

$$
D(b_2,b_1)=-2,
$$

$$
D(b_3,b_2)=-3,
$$

and

$$
D(b_3,b_1)=-5.
$$

Choose

$$
s_0=b_1.
$$

The basepoint potential is

$$
\psi(b_1)=D(b_1,b_1)=0,
$$

$$
\psi(b_2)=D(b_1,b_2)=2,
$$

and

$$
\psi(b_3)=D(b_1,b_3)=5.
$$

Therefore,

$$
D(b_2,b_3) = \psi(b_3)-\psi(b_2) = 5-2 = 3.
$$

Similarly,

$$
D(b_1,b_3) = \psi(b_3)-\psi(b_1) = 5-0 = 5.
$$

The entire debt function has been reconstructed from the potential

$$
\psi:
\begin{cases}
b_1\mapsto0,\\
b_2\mapsto2,\\
b_3\mapsto5.
\end{cases}
$$

---

## 4.11 A General Finite Construction

Suppose

$$
\mathcal{B}=\lbrace b_1,\ldots,b_n\rbrace.
$$

Choose

$$
s_0=b_1.
$$

Then the potential is simply

$$
\psi(b_i)=D(b_1,b_i).
$$

Thus the values

$$
D(b_1,b_1),
D(b_1,b_2),
\ldots,
D(b_1,b_n)
$$

determine the entire debt function.

Indeed,

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i)
$$

gives

$$
D(b_i,b_j) = D(b_1,b_j)-D(b_1,b_i).
$$

Therefore, once the debt relative to one reference state is known, all pairwise debt values are determined.

This is an important reduction in the number of independent quantities.

If $|\mathcal{B}|=n$, the potential has $n$ values, but one additive constant is irrelevant.

Thus only $n-1$ independent potential differences are required.

The precise vector-space formulation and its relation to cohomology will be developed in the next chapter.

---

## 4.12 The Discrete Fundamental Theorem of Calculus

The basepoint theorem has a useful analogy with the fundamental theorem of calculus.

In ordinary calculus, if a function $f$ has an antiderivative $F$, then

$$
F'(x)=f(x).
$$

Conversely, under appropriate conditions, integrating $f$ constructs such an $F$.

The discrete situation is simpler.

The debt function plays the role of a difference quantity:

$$
D(b_i,b_j).
$$

The potential plays the role of the primitive:

$$
\psi(b).
$$

The relationship is

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

The basepoint construction is

$$
\psi_{s_0}(b)=D(s_0,b).
$$

Thus we may view the theorem schematically as

$$
\boxed{
\text{debt}
\longrightarrow
\text{potential}
}
$$

through evaluation relative to a reference state.

The analogy should not be taken too literally.

There is no derivative, integral, or topology required here.

The theorem is purely algebraic.

---

## 4.13 What Assumptions Were Actually Used?

It is useful to be precise about the scope of the theorem.

The proof did **not** require:

* a metric on $\mathcal{B}$;
* a topology on $\mathcal{B}$;
* a vector-space structure on $\mathcal{B}$;
* differentiability;
* continuity;
* probability;
* finite cardinality.

The proof used only:

1. a nonempty state space;
2. a real-valued debt function;
3. the debt axioms (D1) and (D2).

The state space may therefore be finite or infinite.

It may be discrete or continuous.

The theorem concerns the algebraic structure of the debt function, not the geometric structure of the underlying state space.

This distinction will become important later when we combine debt with the energy quasi-metric.

---

## 4.14 Potential Representation Is Not an Additional Axiom

It is important not to add the potential representation as a third axiom.

We began with

$$
\text{(D1) Additivity}
$$

and

$$
\text{(D2) Antisymmetry}.
$$

The basepoint theorem proves that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

follows from those assumptions.

Therefore the potential representation is a **theorem**, not an independent assumption.

This distinction matters for the logical structure of the theory.

We can summarize it as

$$
\boxed{
\text{D1 + D2}
\Longrightarrow
\text{potential representation}
}
$$

rather than

$$
\text{D1 + D2 + potential representation}.
$$

The latter would introduce unnecessary redundancy.

---

## 4.15 Summary

Chapter 3 introduced the debt function through two axioms:

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k)
$$

and

$$
D(b_i,b_j)
=
-D(b_j,b_i).
$$

Chapter 4 established the converse relationship between debt and potential.

For any basepoint

$$
s_0\in\mathcal{B},
$$

define

$$
\psi_{s_0}(b)=D(s_0,b).
$$

Then

$$
\boxed{
D(b_i,b_j)
=
\psi_{s_0}(b_j)-\psi_{s_0}(b_i)
}.
$$

Therefore every debt function is exact.

The potential is unique up to an additive constant:

$$
\psi'(b)=\psi(b)+c.
$$

Changing the basepoint produces precisely such a constant shift.

The potential representation also makes path independence transparent:

$$
D(\gamma)
=
\psi(b_{\mathrm{final}})
-
\psi(b_{\mathrm{initial}}).
$$

Consequently, every closed path has zero total debt.

The main structural result of the chapter can therefore be summarized as

$$
\boxed{
\text{Debt}
=
\text{difference of a potential}.
}
$$

In the next chapter, we will investigate this structure more deeply. In particular, we will study its cohomological interpretation and ask an important logical question:

> **Are both debt axioms actually necessary, or is one sufficient to generate the entire structure?**

---

# Exercises

### Exercise 4.1 — Constructing the Potential

Let

$$
\mathcal{B}=\{b_1,b_2,b_3,b_4\}
$$

and suppose $D$ is a debt function.

Choose $b_1$ as the basepoint and define

$$
\psi(b)=D(b_1,b).
$$

Show directly that

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i)
$$

for every pair of states.

---

### Exercise 4.2 — Explicit Potential

Let

$$
D(i,j)=i^2-j^2
$$

on

$$
\mathcal{B}=\{1,2,3,4\}.
$$

1. Verify that $D$ satisfies (D1).
2. Verify that $D$ satisfies (D2).
3. Choose $s_0=1$.
4. Compute $\psi_{s_0}(i)$.
5. Verify that

$$
D(i,j)=\psi_{s_0}(j)-\psi_{s_0}(i).
$$

---

### Exercise 4.3 — Change of Basepoint

Let $D$ be a debt function and let $s_0,s_1\in\mathcal{B}$.

Define

$$
\psi_{s_0}(b)=D(s_0,b)
$$

and

$$
\psi_{s_1}(b)=D(s_1,b).
$$

Prove that

$$
\psi_{s_1}(b)
=
\psi_{s_0}(b)+D(s_1,s_0).
$$

Explain why the difference between the two potentials does not depend on $b$.

---

### Exercise 4.4 — Uniqueness

Suppose $\psi$ and $\phi$ satisfy

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

and

$$
D(b_i,b_j)=\phi(b_j)-\phi(b_i).
$$

Prove that there exists $c\in\mathbb{R}$ such that

$$
\phi=\psi+c.
$$

---

### Exercise 4.5 — Closed Paths

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a closed path, so that

$$
b_n=b_0.
$$

Using the potential representation, prove that

$$
D(\gamma)=0.
$$

---

### Exercise 4.6 — Path Independence

Let $\gamma_1$ and $\gamma_2$ be two paths with the same initial state and final state.

Use the potential representation to prove that

$$
D(\gamma_1)=D(\gamma_2).
$$

Explain why no minimization over paths is necessary.

---

### Exercise 4.7 — Recovering the Debt Function

Suppose

$$
\mathcal{B}=\{b_1,b_2,b_3\}
$$

and

$$
\psi(b_1)=1,\qquad
\psi(b_2)=4,\qquad
\psi(b_3)=-2.
$$

Compute:

$$
D(b_1,b_2),
\qquad
D(b_2,b_3),
\qquad
D(b_3,b_1).
$$

Verify that the resulting function satisfies both debt axioms.

---

### Exercise 4.8 — Gauge Transformation

Let

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Define

$$
\psi'(b)=\psi(b)+c
$$

for some constant $c$.

Prove that $\psi'$ generates exactly the same debt function.

Then consider

$$
\psi'(b)=\psi(b)+\chi(b)
$$

where $\chi$ is not constant.

Under what condition does $\psi'$ generate the same debt function?

---

### Exercise 4.9 — Number of Independent Values

Let $\mathcal{B}$ contain $n$ states.

Using the basepoint construction, explain why a debt function is completely determined by its values relative to one chosen basepoint.

How many independent real parameters are required?

---

### Exercise 4.10 — Infinite State Spaces

Prove that the basepoint theorem does not require $\mathcal{B}$ to be finite.

Identify every step of the proof and explain why the argument remains valid when $\mathcal{B}$ is infinite.

---

### Exercise 4.11 — The Discrete Fundamental Theorem

Compare the following two expressions:

$$
F(b_j)-F(b_i)
$$

and

$$
\int_{x_i}^{x_j}f(x)\,dx.
$$

Explain mathematically why

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

can be viewed as a discrete analogue of an accumulated change.

---

### Exercise 4.12 — Conceptual Question

The debt function was introduced independently of any potential.

After proving the basepoint theorem, should we regard the potential or the debt function as the more fundamental object?

Give arguments for both viewpoints.

Do not assume that the theorem itself decides this philosophical question.
