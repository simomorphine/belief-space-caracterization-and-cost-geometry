# Chapter 5: Cohomology & Minimality

---

In Chapter 3, we introduced the debt function $D$ through two axioms:

* **(D1) Additivity**

$$
D(b_i,b_k)=D(b_i,b_j)+D(b_j,b_k).
$$

* **(D2) Antisymmetry**

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

In Chapter 4, we showed that these axioms imply a stronger structural result: every debt function can be written as the difference of a potential,

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

The basepoint construction gives the potential explicitly.

This raises a new question:

> **Are both axioms actually necessary?**

There is also a second question.

The exactness result of Chapter 4 assumes that the debt function is defined on every ordered pair of states. What happens if some transitions are unavailable?

These questions lead naturally to two different mathematical ideas:

1. **minimality** — determining which axioms are logically independent;
2. **cohomology** — understanding what prevents a locally consistent debt function from being globally representable by a potential.

The distinction is important.

On a complete state space, the situation is exceptionally rigid. On a sparse graph, nontrivial cycles can appear, and the global structure becomes richer.

---

## 5.1 Logical Minimality

We begin with the simplest question.

Suppose

$$
D:B\times B\to\mathbb{R}
$$

satisfies the additivity axiom

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k)
$$

for every

$$
b_i,b_j,b_k\in B.
$$

Do we need to separately assume antisymmetry?

Surprisingly, no.

Antisymmetry follows from additivity.

This does **not** mean that D2 should be removed from our conceptual framework. It means that D2 is logically redundant once D1 is assumed globally.

---

## 5.2 Additivity Implies Identity

We first recover the identity property.

### Proposition 5.1 — Additivity Implies Zero Self-Debt

Suppose $D$ satisfies D1 for every triple of states. Then

$$
D(b,b)=0
$$

for every $b\in B$.

### Proof

Set

$$
b_i=b_j=b.
$$

Then D1 gives

$$
D(b,b_k) = D(b,b)+D(b,b_k).
$$

Subtracting $D(b,b_k)$ from both sides gives

$$
D(b,b)=0.
$$

Therefore,

$$
\boxed{D(b,b)=0.}
$$

$\square$

So the identity property does not need to be introduced independently either.

---

## 5.3 Additivity Implies Antisymmetry

We can now derive D2.

### Proposition 5.2 — Additivity Implies Antisymmetry

Suppose $D$ satisfies D1 for every triple of states. Then

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

### Proof

Set

$$
b_k=b_i.
$$

Then D1 gives

$$
D(b_i,b_i) = D(b_i,b_j)+D(b_j,b_i).
$$

By Proposition 5.1,

$$
D(b_i,b_i)=0.
$$

Therefore,

$$
0 = D(b_i,b_j)+D(b_j,b_i),
$$

and hence

$$
\boxed{ D(b_i,b_j)=-D(b_j,b_i). }
$$

$\square$

Thus D1 already contains the information expressed separately by D2.

---

## 5.4 A Stronger Minimality Result

The previous propositions give the following theorem.

### Theorem 5.3 — Additivity Alone Is Sufficient

Let $B$ be a nonempty set and let

$$
D:B\times B\to\mathbb{R}.
$$

If D satisfies

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k)
$$

for every $b_i,b_j,b_k\in B$, then:

1. $D(b,b)=0$ for every $b\in B$;
2. $D(b_i,b_j)=-D(b_j,b_i)$;
3. every closed path has zero total debt;
4. $D$ is representable as

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

   for some potential $\psi:B\to\mathbb{R}$.

### Proof

Parts 1 and 2 follow from Propositions 5.1 and 5.2.

For part 3, let

$$
b_0,b_1,\ldots,b_n
$$

be a closed path with $b_n=b_0$.

Repeated application of D1 gives

$$
D(b_0,b_n) = \sum_{k=0}^{n-1}D(b_k,b_{k+1}).
$$

Since $b_n=b_0$,

$$
D(b_0,b_n)=D(b_0,b_0)=0.
$$

Therefore,

$$
\sum_{k=0}^{n-1}D(b_k,b_{k+1})=0.
$$

Finally, by Chapter 4, the basepoint construction gives a potential $\psi$ satisfying

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

$\square$

---

## 5.5 Why Keep Two Axioms?

If D1 logically implies D2, why did we introduce both?

Because **logical minimality and conceptual decomposition are different things**.

The two axioms express different interpretations:

* D1 describes how debt accumulates along successive transitions.
* D2 describes reversal of a transition.
* D1 says debt is compositional.
* D2 says reversing direction changes the sign.

Keeping both axioms therefore makes the intended structure visible.

We can distinguish two statements:

> **Conceptual formulation:** debt satisfies additivity and antisymmetry.

and

> **Minimal logical formulation:** global additivity alone is sufficient.

There is no contradiction between these statements.

The first describes the structure we want to study.

The second describes the logical redundancy inside that structure.
(The main reason is that I'm still discovering this, so I will keep (D2) for now. Maybe we will remove it in a future version of the book if we find out that it is unnecessary.)

---

# 5.6 Debt as a Discrete Differential

Chapter 4 showed that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

This suggests a useful interpretation.

The potential $\psi$ assigns a scalar quantity to each state.

The debt function records the difference between two states.

We may therefore think of $D$ as a **discrete differential** of $\psi$.

Symbolically,

$$
D=\delta\psi,
$$

where $\delta$ denotes the operation that converts a potential into pairwise differences.

Thus,

$$
(\delta\psi)(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

The notation is useful because it separates two objects:

* $\psi$ lives on states;
* $D$ lives on transitions between states.

The debt function therefore contains information about **changes**, while the potential contains information about **levels**.

---

# 5.7 Potentials Have a Gauge Freedom

Suppose

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

Let $c\in\mathbb{R}$ and define

$$
\widetilde{\psi}(b)=\psi(b)+c.
$$

Then

$$
\widetilde{\psi}(b_j)-\widetilde{\psi}(b_i) = (\psi(b_j)+c)-(\psi(b_i)+c).
$$

Therefore,

$$
\widetilde{\psi}(b_j)-\widetilde{\psi}(b_i) = \psi(b_j)-\psi(b_i).
$$

Hence

$$
\boxed{
\delta(\psi+c)=\delta\psi.
}
$$

The constant is invisible to the debt function.

This is the gauge freedom already encountered in Chapter 4.

---

# 5.8 The Kernel of the Difference Operator

The previous observation can be stated more abstractly.

Consider the operator

$$
\delta:\psi\mapsto D
$$

defined by

$$
(\delta\psi)(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

Suppose

$$
\delta\psi=0.
$$

Then

$$
\psi(b_j)-\psi(b_i)=0
$$

for every pair of states.

Therefore,

$$
\psi(b_i)=\psi(b_j)
$$

for every $b_i,b_j\in B$.

If $B$ is nonempty, $\psi$ must be constant.

Thus the kernel consists exactly of constant functions:

$$
\boxed{ \ker\delta = \{\text{constant functions}\}. }
$$

This explains mathematically why potentials are unique only up to an additive constant.

---

# 5.9 Finite State Spaces

Suppose

$$
B=\lbrace b_1,\ldots,b_n\rbrace.
$$

A potential is determined by the $n$ values

$$
\psi(b_1),\ldots,\psi(b_n).
$$

But adding the same constant to all of them does not change the debt.

Therefore, only $n-1$ independent quantities remain.

For example, we may impose the normalization

$$
\psi(b_1)=0.
$$

Then

$$
\psi(b_i)=D(b_1,b_i)
$$

for every $i$.

The potential is completely determined.

This gives the dimension count

$$
n-1
$$

for the space of potentials modulo constants.

---

# 5.10 The Complete State Space

There is an important reason why the theory becomes so simple when $D$ is defined on every pair.

Consider the complete directed graph associated with $B$.

Every pair of states has a directed transition.

Therefore, every triple

$$
(b_i,b_j,b_k)
$$

can be tested against the additivity relation

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k).
$$

This condition is extremely strong.

It forces every two-step path from $b_i$ to $b_k$ to have exactly the same debt as the direct transition.

In particular,

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k)
$$

for **every possible intermediate state** $b_j$.

Consequently, the entire pairwise structure is determined by a single potential.

This is the rigid case.

---

# 5.11 What Changes on a Sparse Graph?

Now suppose not every transition exists.

Let

$$
G=(V,E)
$$

be a directed graph.

The debt function is defined only on available edges:

$$
D:E\to\mathbb{R}.
$$

For an edge

$$
e=(u,v),
$$

we write its debt as

$$
D(u,v).
$$

Now the expression

$$
D(u,v)+D(v,w)
$$

only makes sense as a path debt when the corresponding edges exist.

More importantly, there may be no direct edge from $u$ to $w$.

Therefore, the global equation

$$
D(u,w)=D(u,v)+D(v,w)
$$

cannot always be imposed.

This changes the mathematical problem.

---

# 5.12 Path Debt on a Directed Graph

Let

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

be a directed path.

Define its debt by

$$
D(\gamma) = \sum_{k=0}^{n-1}D(b_k,b_{k+1}).
$$

A potential representation would require

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i)
$$

on every available edge.

Then every path would satisfy

$$
D(\gamma) = \psi(b_n)-\psi(b_0).
$$

Therefore, if two paths connect the same states, they must have the same total debt.

This gives a practical criterion for exactness.

---

# 5.13 Closed Paths and Obstructions

Consider a closed directed path

$$
\gamma=(b_0,b_1,\ldots,b_n)
$$

with

$$
b_n=b_0.
$$

If

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i),
$$

then

$$
D(\gamma) = \psi(b_n)-\psi(b_0) = 0.
$$

Therefore, every exact debt function must satisfy

$$
\boxed{ D(\gamma)=0 }
$$

for every closed path.

This condition is necessary.

Under appropriate graph assumptions, such as considering the relevant connected component and allowing the necessary path comparisons, the vanishing of all closed-loop debt is also the condition that allows a global potential to be constructed.

The important idea is:

> **Nonzero debt around a closed loop is an obstruction to global exactness.**

---

# 5.14 A Simple Cycle

Consider three states

$$
b_1,\quad b_2,\quad b_3
$$

with directed edges

$$
b_1\to b_2,
\qquad
b_2\to b_3,
\qquad
b_3\to b_1.
$$

Suppose

$$
D(b_1,b_2)=1,
$$

$$
D(b_2,b_3)=2,
$$

and

$$
D(b_3,b_1)=1.
$$

The debt around the cycle is

$$
1+2+1=4.
$$

Therefore,

$$
D(\gamma)=4\neq0.
$$

No potential $\psi$ can satisfy

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)
$$

on all three edges.

Indeed, the first two edges would require

$$
\psi(b_2)-\psi(b_1)=1,
$$

and

$$
\psi(b_3)-\psi(b_2)=2.
$$

Adding gives

$$
\psi(b_3)-\psi(b_1)=3.
$$

But the third edge requires

$$
\psi(b_1)-\psi(b_3)=1,
$$

which implies

$$
\psi(b_3)-\psi(b_1)=-1.
$$

The two requirements contradict one another.

The cycle therefore carries a genuine obstruction.

---

# 5.15 Exact and Non-Exact Debt

We can now distinguish two cases.

### Exact debt

A debt function is exact if there exists a potential $\psi$ such that

$$
D(u,v)=\psi(v)-\psi(u)
$$

for every relevant transition.

Then every closed path has zero total debt.

### Non-exact debt

A debt function is non-exact if no such global potential exists.

A nonzero closed-loop debt provides a concrete obstruction:

$$
D(\gamma)\neq0.
$$

The distinction is important because local transition values need not always come from a global scalar potential.

---

# 5.16 From Exactness to Cohomology

The language of cohomology provides a systematic way to organize this distinction.

Very informally:

* a **cochain** assigns values to geometric objects such as vertices or edges;
* a **cocycle** satisfies a consistency condition;
* a **coboundary** is generated from a lower-dimensional object;
* **cohomology** measures cocycles that are not coboundaries.

For our purposes, the potential $\psi$ is a $0$-dimensional object, while the debt function $D$ is a $1$-dimensional object.

The operation

$$
\delta\psi
$$

produces the debt difference

$$
(\delta\psi)(u,v) = \psi(v)-\psi(u).
$$

Therefore, exact debt functions are precisely those that arise as differences of potentials.

Symbolically,

$$
D=\delta\psi.
$$

The quotient between consistent transition structures and those generated by potentials is the natural place where a first cohomology group appears.

---

# 5.17 The First Cohomology Group

At a structural level, one may write

$$
H^1 = \frac{\text{closed 1-cochains}} {\text{exact 1-cochains}}.
$$

The precise definition depends on the underlying graph or simplicial structure and on the chosen cochain conventions.

The important interpretation is:

> $H^1$ measures the obstruction to representing a consistent transition quantity globally as a potential difference.

If

$$
H^1=0,
$$

then every closed 1-cochain is exact.

If

$$
H^1\neq0,
$$

then there exist closed structures that cannot be represented globally by a single potential.

This gives a mathematical language for the distinction between **local consistency** and **global exactness**.

---

# 5.18 Why the Complete Case Is Special

For the full state space considered in Chapters 3 and 4, every pair of states is available.

The resulting structure is highly constrained.

Once a basepoint $s_0$ is chosen, define

$$
\psi(b)=D(s_0,b).
$$

Then

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

There is therefore no additional global degree of freedom.

The debt is exact.

The interesting cohomological phenomena become more relevant when the transition structure is restricted.

This is one reason to distinguish:

* **belief-space geometry on a complete pairwise structure**, and
* **belief-space geometry on a sparse directed graph**.

They are mathematically related but not identical problems.

---

# 5.19 A Graph-Theoretic Interpretation

Consider again a directed graph

$$
G=(V,E).
$$

A potential assigns a number

$$
\psi(v)
$$

to each vertex.

Each edge then receives the induced difference

$$
D(u,v)=\psi(v)-\psi(u).
$$

Thus the edge values are generated from vertex values.

The map

$$
\psi\mapsto D
$$

can be viewed as a discrete gradient.

In this language:

$$
D=\nabla\psi
$$

is exact.

A closed-loop condition then resembles the familiar statement that a conservative field has zero circulation.

For a closed path $\gamma$,

$$
\oint_\gamma D=0.
$$

This notation is only an analogy unless a specific graph calculus has been defined. The rigorous object remains the finite sum

$$
D(\gamma)
=
\sum_{e\in\gamma}D(e).
$$

---

# 5.20 Path Independence

Suppose two paths $\gamma_1$ and $\gamma_2$ connect the same states:

$$
\gamma_1:b_i\leadsto b_j,
$$

$$
\gamma_2:b_i\leadsto b_j.
$$

If $D$ is exact, then

$$
D(\gamma_1)
=
\psi(b_j)-\psi(b_i)
$$

and

$$
D(\gamma_2)
=
\psi(b_j)-\psi(b_i).
$$

Therefore,

$$
\boxed{
D(\gamma_1)=D(\gamma_2).
}
$$

Thus exactness, path independence, and zero closed-loop debt are deeply connected.

For a path-independent debt structure, the total debt depends only on the endpoints.

---

# 5.21 Constructing a Potential from Paths

Suppose a graph is connected in the relevant sense and every closed path has zero total debt.

Choose a reference state

$$
s_0.
$$

For any state $b$, choose a path

$$
\gamma_{s_0\to b}
$$

from $s_0$ to $b$ and define

$$
\psi(b)
=
D(\gamma_{s_0\to b}).
$$

At first this definition appears to depend on the chosen path.

But if every closed path has zero debt, then any two paths from $s_0$ to $b$ have equal total debt.

Therefore $\psi(b)$ is well-defined.

Once $\psi$ is constructed,

$$
D(u,v)=\psi(v)-\psi(u)
$$

on the relevant transitions.

This is the graph analogue of the basepoint construction from Chapter 4.

---

# 5.22 Minimality Has Two Different Meanings

At this point we should distinguish two kinds of minimality.

### Logical minimality

Which axioms are sufficient to derive the desired properties?

For the complete pairwise debt function,

$$
\boxed{\text{D1 alone is sufficient.}}
$$

D2 follows from D1.

### Structural minimality

What is the smallest set of conditions needed for exactness on a restricted graph?

This is a different question.

On a sparse graph, the answer depends on:

* which edges exist;
* which paths exist;
* which cycles exist;
* whether the graph is connected;
* whether paths can be reversed;
* what cochain structure is being used.

Therefore, the sparse-graph problem cannot simply be reduced to the complete-space result.

---

# 5.23 Exactness as a Global Constraint

The potential representation

$$
D(u,v)=\psi(v)-\psi(u)
$$

has a strong consequence.

Once $\psi$ is known, all edge debts are constrained.

They cannot be chosen independently.

For example, suppose

$$
\psi(b_1)=0,
$$

$$
\psi(b_2)=2,
$$

$$
\psi(b_3)=5.
$$

Then necessarily,

$$
D(b_1,b_2)=2,
$$

$$
D(b_2,b_3)=3,
$$

and

$$
D(b_1,b_3)=5.
$$

The third quantity is not independent.

It is determined by the first two.

This is the fundamental rigidity created by exactness.

---

# 5.24 Number of Independent Quantities

For a finite set of $n$ states, a potential has $n$ values.

But one degree of freedom is the additive gauge.

Therefore,

$$
n-1
$$

independent potential values remain after normalization.

The complete debt matrix may appear to contain many more values:

$$
D(b_i,b_j),
\qquad
1\leq i,j\leq n.
$$

But exactness imposes strong relations among them.

All those pairwise quantities are generated from only $n-1$ independent potential differences.

This is another way of seeing why exact debt is highly structured.

---

# 5.25 Example: Recovering the Entire Debt Matrix

Let

$$
B=\{b_1,b_2,b_3,b_4\}
$$

and choose

$$
\psi(b_1)=0,
\qquad
\psi(b_2)=1,
\qquad
\psi(b_3)=4,
\qquad
\psi(b_4)=7.
$$

Then

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Therefore,

$$
D=
\begin{pmatrix}
0 & 1 & 4 & 7\\
-1 & 0 & 3 & 6\\
-4 & -3 & 0 & 3\\
-7 & -6 & -3 & 0
\end{pmatrix}.
$$

Every entry is determined by the four potential values.

After fixing the gauge $\psi(b_1)=0$, only three independent values remain.

For example,

$$
D(b_1,b_2)=1,
\qquad
D(b_1,b_3)=4,
\qquad
D(b_1,b_4)=7.
$$

All other entries follow.

---

# 5.26 A Warning About Sparse Directed Graphs

The complete-space theorem should not be applied blindly to a sparse directed graph.

Suppose the edge

$$
b_i\to b_k
$$

does not exist.

Then the expression

$$
D(b_i,b_k)
$$

may simply be undefined.

Therefore, one cannot automatically write

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

Similarly, if the reverse edge

$$
b_j\to b_i
$$

does not exist, then the antisymmetry expression

$$
D(b_i,b_j)=-D(b_j,b_i)
$$

may not even be meaningful within the edge-based model.

This is why the complete-state formulation and the directed-graph formulation require separate definitions.

---

# 5.27 The Main Structural Picture

We can now summarize the mathematical hierarchy.

For a complete pairwise debt function:

$$
\boxed{
\text{Additivity}
\Longrightarrow
\text{Antisymmetry}
\Longrightarrow
\text{Exactness}
}
$$

More precisely, additivity alone implies antisymmetry, and together with the complete domain it yields the potential representation.

For a restricted graph, the picture becomes:

$$
\boxed{
\text{edge data}
\longrightarrow
\text{path sums}
\longrightarrow
\text{closed-loop constraints}
\longrightarrow
\text{exactness or obstruction}
}
$$

The obstruction is what cohomology is designed to organize.

---

# 5.28 What We Have Learned

The debt function has two complementary descriptions.

### Algebraic description

Debt satisfies the composition law

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

### Potential description

Debt is generated by a scalar potential:

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

The first description emphasizes transitions.

The second emphasizes states.

The basepoint theorem establishes their equivalence in the complete pairwise setting.

---

# 5.29 Summary

The main results of this chapter are:

1. Additivity implies zero self-debt:

   $$
   D(b,b)=0.
   $$

2. Additivity implies antisymmetry:

   $$
   D(b_i,b_j)=-D(b_j,b_i).
   $$

3. Therefore, D2 is logically redundant when D1 holds globally.

4. We nevertheless retain D1 and D2 as conceptual axioms because they describe different structural meanings.

5. The potential-to-debt map is

   $$
   (\delta\psi)(b_i,b_j)
   =
   \psi(b_j)-\psi(b_i).
   $$

6. Potentials are unique up to an additive constant.

7. Exact debt has zero total debt around every closed path.

8. Exact debt is path independent.

9. On a finite state space with $n$ states, exact debt is determined by $n-1$ independent potential differences.

10. Sparse directed graphs require a separate treatment because not every pairwise relation exists.

11. Nonzero debt around a closed loop is an obstruction to a global potential.

12. Cohomology provides a natural language for studying the difference between closed and exact structures.

The central idea can be summarized as

$$
\boxed{
\text{Debt}
=
\text{Potential Difference}
}
$$

in the complete setting, while in more general transition structures the question becomes whether such a global potential exists at all.

---

# Exercises

## Exercise 5.1 — Redundancy of Antisymmetry

Suppose

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k)
$$

for every triple of states.

Prove directly that

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

Do not assume antisymmetry during the proof.

---

## Exercise 5.2 — Zero Self-Debt

Using only D1, prove that

$$
D(b,b)=0.
$$

Explain why this means that zero self-debt does not need to be introduced as a separate axiom.

---

## Exercise 5.3 — Potential Construction

Let

$$
B=\{b_1,b_2,b_3,b_4\}
$$

and suppose

$$
D(b_1,b_2)=2,
$$

$$
D(b_1,b_3)=5,
$$

$$
D(b_1,b_4)=1.
$$

Construct a potential $\psi$ using $b_1$ as the basepoint.

Then compute

$$
D(b_2,b_3),
\qquad
D(b_2,b_4),
\qquad
D(b_3,b_4).
$$

---

## Exercise 5.4 — Gauge Freedom

Suppose

$$
\psi(b_1)=0,
\qquad
\psi(b_2)=3,
\qquad
\psi(b_3)=7.
$$

Define

$$
\widetilde{\psi}(b)=\psi(b)+10.
$$

Verify that $\psi$ and $\widetilde{\psi}$ generate exactly the same debt function.

---

## Exercise 5.5 — Closed Cycle

Consider

$$
b_1\to b_2\to b_3\to b_1
$$

with

$$
D(b_1,b_2)=2,
$$

$$
D(b_2,b_3)=-1,
$$

and

$$
D(b_3,b_1)=-1.
$$

Compute the total debt around the cycle.

Can the debt be represented as a potential difference?

---

## Exercise 5.6 — Nonzero Cycle Debt

Consider the same graph but let

$$
D(b_1,b_2)=2,
$$

$$
D(b_2,b_3)=1,
$$

and

$$
D(b_3,b_1)=1.
$$

Show that no potential $\psi$ can generate these three edge values.

---

## Exercise 5.7 — Path Independence

Suppose two paths $\gamma_1$ and $\gamma_2$ connect the same states $b_i$ and $b_j$.

Assume every closed path has zero total debt.

Show that

$$
D(\gamma_1)=D(\gamma_2).
$$

Be explicit about how the two paths are combined to form a closed path when the relevant reverse traversal is available.

---

## Exercise 5.8 — Reconstructing a Potential

Let $G$ be a connected graph with a debt value assigned to every relevant edge.

Choose a reference state $s_0$.

Assume every closed path has zero total debt.

Define

$$
\psi(b)
=
D(\gamma_{s_0\to b}).
$$

Explain why this definition does not depend on the chosen path.

---

## Exercise 5.9 — Dimension Count

Let

$$
B=\{b_1,\ldots,b_n\}.
$$

Explain why potentials form an $n$-dimensional vector space, while potentials modulo additive constants have dimension

$$
n-1.
$$

---

## Exercise 5.10 — Complete Debt Matrix

Let

$$
\psi=(0,2,5,9).
$$

Construct the complete debt matrix

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Verify:

1. $D(b_i,b_i)=0$;
2. $D(b_i,b_j)=-D(b_j,b_i)$;
3. D1 holds.

---

## Exercise 5.11 — Sparse Graph

Consider a graph with states

$$
B=\{b_1,b_2,b_3\}
$$

and edges

$$
b_1\to b_2,
\qquad
b_2\to b_3.
$$

There is no edge from $b_1$ to $b_3$.

Explain why the equation

$$
D(b_1,b_3)
=
D(b_1,b_2)+D(b_2,b_3)
$$

cannot automatically be treated as an equality between three edge values.

What additional structure would be needed to define the left-hand side?

---

## Exercise 5.12 — Conceptual Question

We have shown that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Does this mean that the potential $\psi$ is more fundamental than the debt $D$?

Give arguments for both interpretations.

The theorem establishes a mathematical representation, but it does not by itself determine which object should be regarded as conceptually primary.
