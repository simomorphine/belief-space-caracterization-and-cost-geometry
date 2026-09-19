# Chapter 4: Exactness

---

In Chapter 3, we introduced the debt function as a transition quantity satisfying additivity and antisymmetry.

The defining relation was

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

We also saw that additivity imposes strong algebraic constraints on debt. However, we have not yet answered a deeper question:

> **Can every debt function be represented as the difference of a scalar quantity defined on states?**

In other words, does there exist a function

$$
\psi:\mathcal B\to\mathbb R
$$

such that

$$
\boxed{
D(b_i,b_j)=\psi(b_j)-\psi(b_i)?
}
$$

The answer is yes.

The result is remarkably elementary. It requires no metric, topology, differentiability, or integration. It follows directly from the composition law for debt.

We call this result the **basepoint theorem**.

The theorem will allow us to reinterpret debt in three equivalent ways:

$$
\boxed{
\text{transition quantity}
\quad\Longleftrightarrow\quad
\text{potential difference}
\quad\Longleftrightarrow\quad
\text{exact 1-cochain}.
}
$$

The cohomological interpretation will be developed after the elementary construction.

---

## 4.1 The basepoint theorem

### Theorem 4.1 (Basepoint theorem)

Let $\mathcal B$ be a nonempty set and let

$$
D:\mathcal B\times\mathcal B\to\mathbb R
$$

be a debt function satisfying (D1):

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

Choose any basepoint

$$
s_0\in\mathcal B.
$$

Define

$$
\boxed{
\psi_{s_0}(b):=D(s_0,b).
}
$$

Then, for every $b_i,b_j\in\mathcal B$,

$$
\boxed{
D(b_i,b_j)
=
\psi_{s_0}(b_j)-\psi_{s_0}(b_i).
}
$$

Thus every debt function can be represented as a difference of a scalar potential.

### Proof

Fix $s_0\in\mathcal B$ and define

$$
\psi_{s_0}(b)=D(s_0,b).
$$

By additivity, applied to the triple

$$
(b_i,s_0,b_j),
$$

we have

$$
D(b_i,b_j)
=
D(b_i,s_0)+D(s_0,b_j).
$$

By antisymmetry,

$$
D(b_i,s_0)
=
-D(s_0,b_i).
$$

Therefore,

$$
D(b_i,b_j)
=
-D(s_0,b_i)+D(s_0,b_j).
$$

Using the definition of $\psi_{s_0}$,

$$
D(b_i,b_j)
=
-\psi_{s_0}(b_i)+\psi_{s_0}(b_j).
$$

Hence

$$
\boxed{
D(b_i,b_j)
=
\psi_{s_0}(b_j)-\psi_{s_0}(b_i).
}
$$

$\square$

### Remark 4.2

The theorem is constructive.

Given a debt function $D$ and one chosen reference state $s_0$, the potential is obtained simply by evaluating

$$
\psi_{s_0}(b)=D(s_0,b).
$$

No path needs to be chosen.

No integration is required.

No topology is required.

The potential is already encoded inside the debt function.

---

## 4.2 Why the basepoint construction works

The construction above may initially look almost too simple.

We choose one state $s_0$ and measure every state relative to it:

$$
\psi_{s_0}(b)=D(s_0,b).
$$

Then additivity gives

$$
D(b_i,b_j)
=
D(b_i,s_0)+D(s_0,b_j).
$$

Antisymmetry converts the first term:

$$
D(b_i,s_0)=-D(s_0,b_i).
$$

Therefore,

$$
D(b_i,b_j)
=
D(s_0,b_j)-D(s_0,b_i).
$$

Thus the debt between two states is completely determined by their individual debts relative to the basepoint.

This is the central mechanism behind exactness.

### Remark 4.3

The important point is not the particular choice of $s_0$.

The basepoint is merely a reference.

Changing the reference changes the numerical values assigned to the potential, but not the differences between potentials.

This is the origin of the gauge freedom discussed later.

---

## 4.3 Uniqueness up to a constant

The potential representation is not unique.

### Proposition 4.4 (Uniqueness up to a constant)

Suppose $\psi$ and $\phi$ are two functions satisfying

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i)
$$

and

$$
D(b_i,b_j)
=
\phi(b_j)-\phi(b_i).
$$

Then there exists a constant $c\in\mathbb R$ such that

$$
\boxed{
\phi(b)=\psi(b)+c
}
$$

for every $b\in\mathcal B$.

### Proof

Since both functions represent the same debt,

$$
\psi(b_j)-\psi(b_i)
=
\phi(b_j)-\phi(b_i).
$$

Rearranging,

$$
\psi(b_j)-\phi(b_j)
=
\psi(b_i)-\phi(b_i).
$$

Since $b_i$ and $b_j$ are arbitrary, the function

$$
\psi-\phi
$$

has the same value at every point of $\mathcal B$.

Therefore it is constant.

Hence

$$
\phi=\psi+c
$$

for some $c\in\mathbb R$.

$\square$

### Corollary 4.5

The potential representing a debt function is unique up to an additive constant.

Thus the physically or mathematically meaningful quantity is not the absolute value of $\psi$, but its differences:

$$
\psi(b_j)-\psi(b_i).
$$

Those differences are exactly the debt values.

---

## 4.4 Change of basepoint

The freedom in the choice of potential can be made explicit.

### Proposition 4.6 (Change of basepoint)

Let $s_0,s_1\in\mathcal B$ be two basepoints. Define

$$
\psi_{s_0}(b)=D(s_0,b)
$$

and

$$
\psi_{s_1}(b)=D(s_1,b).
$$

Then

$$
\boxed{
\psi_{s_1}(b)
=
\psi_{s_0}(b)+D(s_1,s_0).
}
$$

### Proof

By additivity,

$$
D(s_1,b)
=
D(s_1,s_0)+D(s_0,b).
$$

Therefore,

$$
\psi_{s_1}(b)
=
D(s_1,s_0)+\psi_{s_0}(b).
$$

The quantity $D(s_1,s_0)$ is independent of $b$, so the two potentials differ only by a constant.

$\square$

### Remark 4.7

The basepoint therefore acts as a **gauge choice**.

Different basepoints give different numerical representations of the potential, but all of them generate exactly the same debt function.

---

## 4.5 Debt on paths

We can now derive the path properties that were not assumed in Chapter 3.

Consider a path

$$
\gamma=(b_0,b_1,\ldots,b_n).
$$

Its total debt is

$$
\operatorname{Debt}(\gamma)
=
\sum_{k=0}^{n-1}D(b_k,b_{k+1}).
$$

Using the potential representation,

$$
D(b_k,b_{k+1})
=
\psi(b_{k+1})-\psi(b_k).
$$

Therefore,

$$
\begin{aligned}
\operatorname{Debt}(\gamma)
&=
\sum_{k=0}^{n-1}
[\psi(b_{k+1})-\psi(b_k)]\\
&=
\psi(b_n)-\psi(b_0).
\end{aligned}
$$

Hence:

### Theorem 4.8 (Path reduction)

For every finite path

$$
\gamma=(b_0,b_1,\ldots,b_n),
$$

the total debt is

$$
\boxed{
\operatorname{Debt}(\gamma)
=
\psi(b_n)-\psi(b_0).
}
$$

The intermediate states disappear through telescoping.

### Remark 4.9

This gives a stronger interpretation of the additivity axiom.

Debt can be accumulated locally along transitions, but the final result depends only on the initial and final states.

The intermediate history cancels.

---

## 4.6 Path independence

### Corollary 4.10 (Path independence)

Let $\gamma_1$ and $\gamma_2$ be two finite paths with the same initial state $b_i$ and the same final state $b_j$.

Then

$$
\boxed{
\operatorname{Debt}(\gamma_1)
=
\operatorname{Debt}(\gamma_2).
}
$$

### Proof

By Theorem 4.8,

$$
\operatorname{Debt}(\gamma_1)
=
\psi(b_j)-\psi(b_i)
$$

and

$$
\operatorname{Debt}(\gamma_2)
=
\psi(b_j)-\psi(b_i).
$$

Therefore they are equal.

$\square$

### Remark 4.11

This property was **not assumed** in the definition of debt.

It is a consequence of additivity.

This distinction is important:

$$
\boxed{
\text{path independence is a theorem, not an axiom.}
}
$$

---

## 4.7 Closed paths and zero circulation

A closed path begins and ends at the same state.

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

with

$$
b_n=b_0.
$$

Then Theorem 4.8 gives

$$
\operatorname{Debt}(\gamma)
=
\psi(b_n)-\psi(b_0).
$$

Since $b_n=b_0$,

$$
\operatorname{Debt}(\gamma)=0.
$$

Therefore:

### Corollary 4.12 (Zero circulation)

Every closed path has zero total debt:

$$
\boxed{
\sum_{k=0}^{n-1}
D(b_k,b_{k+1})
=
0.
}
$$

This is sometimes described as **zero circulation**.

### Remark 4.13

A general directional quantity can have nonzero circulation around a loop.

Debt cannot.

This provides another way to distinguish debt from the antisymmetric part of cost $A$.

An antisymmetric function satisfies

$$
A(b_i,b_j)=-A(b_j,b_i),
$$

but this alone does not guarantee that its circulation around longer loops vanishes.

Debt has the stronger structure.

---

## 4.8 Exactness

We can now introduce the central terminology of this chapter.

Suppose we regard the states of $\mathcal B$ as vertices and transitions between states as directed edges.

A function assigning a number to each ordered pair of states can be viewed as a discrete 1-cochain.

For a function

$$
\psi:\mathcal B\to\mathbb R,
$$

define its discrete difference by

$$
(\delta\psi)(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

A 1-cochain $D$ is called **exact** if there exists a function $\psi$ such that

$$
D=\delta\psi.
$$

The basepoint theorem therefore gives:

### Theorem 4.14 (Exactness of debt)

Every debt function is exact.

Equivalently, for every debt function $D$, there exists a potential $\psi$ such that

$$
\boxed{
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
}
$$

### Remark 4.15

The word **exact** describes the fact that debt is generated by a state function.

The transition quantity $D$ is obtained from the potential by taking differences.

In this language,

$$
\boxed{
D=\delta\psi.
}
$$

The potential is the underlying scalar field, while debt records its change between states.

---

## 4.9 Cocycle interpretation

The additivity condition has an immediate cohomological interpretation.

For a 1-cochain $D$, define

$$
(\delta D)(b_i,b_j,b_k)
=
D(b_j,b_k)
-
D(b_i,b_k)
+
D(b_i,b_j).
$$

The condition

$$
\delta D=0
$$

is equivalent to

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

Therefore:

### Proposition 4.16

A debt function is a 1-cocycle.

In other words,

$$
\boxed{
\text{debt additivity}
\iff
\delta D=0.
}
$$

But the basepoint theorem tells us something stronger.

Every debt cocycle is also exact:

$$
D=\delta\psi.
$$

Thus, in the present complete-state setting,

$$
\boxed{
\text{debt}
\Longrightarrow
\text{1-cocycle}
\Longrightarrow
\text{exact 1-cochain}.
}
$$

In fact, the implications can be strengthened to an equivalence:

$$
\boxed{
\text{debt}
\iff
\text{1-cocycle}
\iff
\text{exact 1-cochain}.
}
$$

The final equivalence follows from the basepoint theorem.

---

## 4.10 Why exactness is special to the present setting

The exactness result should not be interpreted as saying that every conceivable discrete or continuous 1-form is automatically exact.

The result depends on the structure we have chosen.

Here, every pair of states is available as a transition, so the state space is represented by a complete directed structure.

This means that a basepoint can be connected directly to every state.

Consequently, the potential can simply be defined by

$$
\psi(b)=D(s_0,b).
$$

If instead we worked on a restricted graph in which some transitions were unavailable, the situation could be different.

A 1-cocycle might then fail to be globally exact because the graph could contain nontrivial topological structure.

This distinction will become important when we later study restricted transition spaces and possible circulation or holonomy.

---

## 4.11 Gauge freedom

The potential is unique only modulo constants.

If

$$
D=\delta\psi,
$$

and we define

$$
\psi'(b)=\psi(b)+c,
$$

then

$$
\begin{aligned}
(\delta\psi')(b_i,b_j)
&=
\psi'(b_j)-\psi'(b_i)\\
&=
[\psi(b_j)+c]-[\psi(b_i)+c]\\
&=
\psi(b_j)-\psi(b_i)\\
&=
D(b_i,b_j).
\end{aligned}
$$

Thus

$$
\boxed{
\delta(\psi+c)=\delta\psi.
}
$$

The potential therefore contains one redundant degree of freedom: its absolute zero.

Only differences matter.

### Remark 4.17

This is analogous to choosing the zero of an energy scale.

If every potential value is shifted by the same amount, no transition debt changes.

The gauge transformation is

$$
\boxed{
\psi\mapsto\psi+c.
}
$$

The debt function remains invariant.

---

## 4.12 A finite-state example

Let

$$
\mathcal B=\{b_1,b_2,b_3\}
$$

and suppose

$$
D(b_1,b_2)=2,
$$

$$
D(b_2,b_3)=3.
$$

By additivity,

$$
D(b_1,b_3)=5.
$$

Choose

$$
s_0=b_1.
$$

The basepoint construction gives

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
D(b_2,b_3)
=
\psi(b_3)-\psi(b_2)
=
5-2
=
3.
$$

The entire debt function can therefore be reconstructed from the three potential values, modulo an arbitrary constant.

---

## 4.13 Dimension of the debt space

The exact representation also clarifies the finite-dimensional structure of debt.

Suppose

$$
\mathcal B=\{b_1,\ldots,b_n\}.
$$

A potential is an element of

$$
\mathbb R^n.
$$

However, adding a constant to every component produces the same debt function.

Thus

$$
(\psi_1,\ldots,\psi_n)
$$

and

$$
(\psi_1+c,\ldots,\psi_n+c)
$$

represent the same debt.

The space of constant potentials is one-dimensional.

Therefore the space of debt functions has dimension

$$
\boxed{n-1}.
$$

Equivalently,

$$
\boxed{
\mathcal D(\mathcal B)
\cong
\mathbb R^n/\mathbb R.
}
$$

This is the precise mathematical meaning of the statement that a debt function contains only $n-1$ independent degrees of freedom on an $n$-state complete belief space.

---

## 4.14 The potential is not unique, but the debt is

There is an important distinction between the potential and the debt.

The potential is not unique:

$$
\psi\sim\psi+c.
$$

The debt is unique.

Indeed,

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i)
$$

is unchanged under every constant shift.

Thus the potential should be viewed as a representative of an equivalence class

$$
[\psi]
=
\{\psi+c:c\in\mathbb R\}.
$$

The debt function depends only on this equivalence class.

Symbolically,

$$
\boxed{
\{\text{debt functions}\}
\cong
\{\text{potentials}\}/\mathbb R.
}
$$

This quotient structure will be useful when we study the geometry induced by debt.

---

## 4.15 Relation to the energy quasi-metric

We now have two distinct structures on the belief space.

The first is the energy quasi-metric

$$
d(b_i,b_j),
$$

which measures the cost associated with moving from one state to another.

The second is the debt function

$$
D(b_i,b_j),
$$

which measures a signed transition quantity satisfying the additive composition law.

Their mathematical roles are different.

The cost may have directional asymmetry:

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

The associated antisymmetric component is

$$
A(b_i,b_j)
=
\frac12
[d(b_i,b_j)-d(b_j,b_i)].
$$

Debt, however, has the stronger structure

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

Therefore,

$$
\boxed{
A\text{ need not be exact},
\qquad
D\text{ is exact}.
}
$$

This distinction is one of the central structural separations in the theory.

---

## 4.16 Cohomological meaning

We can now formulate the result using cohomological language.

Let

$$
C^0(\mathcal B)
$$

denote the space of real-valued functions on states, and let

$$
C^1(\mathcal B)
$$

denote the space of real-valued functions on ordered pairs.

The coboundary operator is

$$
\delta:C^0(\mathcal B)\to C^1(\mathcal B),
$$

with

$$
(\delta\psi)(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

A 1-cochain is a cocycle if

$$
\delta D=0.
$$

The basepoint theorem establishes that every debt cocycle is a coboundary.

Therefore,

$$
\boxed{
H^1(\mathcal B;\mathbb R)=0
}
$$

for the complete simplicial structure used here.

In other words, there is no nontrivial cohomological obstruction to integrating a debt cocycle into a global potential.

### Remark 4.18

The cohomological language is useful, but the theorem itself is elementary.

The basepoint proof does not require prior knowledge of cohomology.

The logical order is therefore:

$$
\text{elementary algebra}
\longrightarrow
\text{potential}
\longrightarrow
\text{exactness}
\longrightarrow
\text{cohomological interpretation}.
$$

This order is intentional.

---

## 4.17 The discrete fundamental theorem analogy

The basepoint construction resembles a discrete version of integration.

In ordinary calculus, a function can sometimes be recovered from its derivative by integration.

Here, the debt function can be recovered from a potential by taking differences:

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

Conversely, given an additive debt function, the potential can be reconstructed relative to a basepoint:

$$
\psi_{s_0}(b)
=
D(s_0,b).
$$

Thus the correspondence is

$$
\boxed{
\psi
\quad\longleftrightarrow\quad
D=\delta\psi.
}
$$

The analogy should not be pushed too far: no differentiability or integration theory is involved here. The result is fundamentally algebraic.

---

## 4.18 Summary

Chapter 3 introduced debt as an additive transition quantity.

This chapter established the deeper structure hidden inside that axiom.

Given any basepoint $s_0$, define

$$
\psi_{s_0}(b)=D(s_0,b).
$$

Then

$$
\boxed{
D(b_i,b_j)
=
\psi_{s_0}(b_j)-\psi_{s_0}(b_i).
}
$$

Therefore every debt function is a potential difference.

From this representation we obtained:

* **Potential representation**

  $$
  D(b_i,b_j)=\psi(b_j)-\psi(b_i).
  $$

* **Uniqueness up to a constant**

  $$
  \psi\sim\psi+c.
  $$

* **Path reduction**

  $$
  \sum D(b_k,b_{k+1})
  =
  \psi(b_n)-\psi(b_0).
  $$

* **Path independence**

* **Zero circulation on closed paths**

* **Exactness**

  $$
  D=\delta\psi.
  $$

* **Cocycle interpretation**

  $$
  \delta D=0.
  $$

* **Trivial first cohomology in the complete-state setting**

  $$
  H^1(\mathcal B;\mathbb R)=0.
  $$

For a finite state space with $n$ states, the debt space has dimension

$$
n-1.
$$

The central result can therefore be summarized as

$$
\boxed{
\text{Additive debt}
\iff
\text{Potential difference}
\iff
\text{Exact 1-cochain}.
}
$$

The distinction between cost asymmetry and debt remains essential:

$$
A=\frac12(d-d^T)
$$

is an antisymmetric component of the energy cost, whereas

$$
D=\delta\psi
$$

is an exact transition quantity.

The next chapters can therefore build on a clean separation:

$$
\boxed{
\text{cost geometry}
\quad+\quad
\text{exact debt geometry}.
}
$$

---

## 4.19 Exercises

### Exercise 4.1

Let $D$ be a debt function and choose a basepoint $s_0$.

Define

$$
\psi(b)=D(s_0,b).
$$

Prove directly that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

### Exercise 4.2

Let

$$
\mathcal B=\{1,2,3,4\}
$$

and suppose

$$
D(i,j)=i^2-j^2.
$$

Verify additivity and antisymmetry.

Choose the basepoint $s_0=1$ and compute the corresponding potential.

### Exercise 4.3

Suppose $\psi$ and $\phi$ generate the same debt function.

Prove that

$$
\phi-\psi
$$

is constant.

### Exercise 4.4

Let $s_0$ and $s_1$ be two basepoints.

Prove

$$
\psi_{s_1}(b)
=
\psi_{s_0}(b)+D(s_1,s_0).
$$

### Exercise 4.5

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a path.

Prove that

$$
\sum_{k=0}^{n-1}D(b_k,b_{k+1})
=
D(b_0,b_n).
$$

Then derive the potential representation of the same expression.

### Exercise 4.6

Let $\gamma$ be a closed path.

Prove that its total debt is zero.

Give two proofs:

1. using the potential representation;
2. directly using additivity.

### Exercise 4.7

Let $\mathcal B$ have $n$ elements.

Use the potential representation and gauge freedom to prove that the vector space of debt functions has dimension

$$
n-1.
$$

### Exercise 4.8

Show that the transformation

$$
\psi\mapsto\psi+c
$$

does not change the debt function.

Explain why the constant functions form the kernel of the map

$$
\psi\mapsto\delta\psi.
$$

### Exercise 4.9

Let $A$ be an antisymmetric function on a three-state space.

Construct an example for which

$$
A(b_1,b_2)+A(b_2,b_3)+A(b_3,b_1)\neq0.
$$

Explain why this prevents $A$ from being represented as

$$
A(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

### Exercise 4.10

Explain in your own words the difference between:

$$
\text{antisymmetry},
$$

$$
\text{additivity},
$$

and

$$
\text{exactness}.
$$

Why is exactness stronger than antisymmetry?

---

## 4.20 References

The cohomological terminology used in this chapter is based on standard treatments of cochains, coboundaries, cocycles, and cohomology.

**Allen Hatcher.** *Algebraic Topology*, Chapter 3: Cohomology.

**Raoul Bott and Loring W. Tu.** *Differential Forms in Algebraic Topology*, Graduate Texts in Mathematics 82, Springer.

The construction used here is a discrete cochain framework adapted to the state space $\mathcal B$. It should not be identified without qualification with the classical de Rham complex of differential forms on a smooth manifold.
