# Chapter 6: We Continue with Cohomology.

---

In the previous chapters, we studied the structure of the debt function.

We began with the two conceptual axioms

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k)
$$

and

$$
D(b_i,b_j) = -D(b_j,b_i).
$$

We then showed that, on a complete state space, the debt function can be represented by a potential:

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

This representation made several properties transparent:

* debt is path independent;
* debt around a closed path is zero;
* potentials are unique up to an additive constant;
* the debt function is determined by potential differences.

Chapter 5 then examined the logical structure of the axioms and showed that, on the complete pairwise domain, additivity alone already implies antisymmetry.

We now have a new mathematical question.

> **What mathematical language organizes the distinction between potential differences, closed structures, and obstructions to global potentials?**

The answer is **cohomology**.

The purpose of this chapter is not to assume cohomology as known.

Instead, we will build the basic vocabulary step by step:

$$
\boxed{
\text{cochain}
\rightarrow
\text{coboundary}
\rightarrow
\text{cocycle}
\rightarrow
\text{exactness}
\rightarrow
\text{cohomology}
}
$$

Only after introducing these concepts will we return to debt and interpret the previous chapters in cohomological language.

---

# 6.1 Why Do We Need Cohomology?

Consider again the potential representation

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

Suppose we are given only the transition values $D$.

We want to know whether there exists some function $\psi$ such that

$$
D=\delta\psi.
$$

This is an **existence problem**.

The question is not merely:

> Can we calculate the debt of a particular transition?

It is:

> **Can all the transition debts be generated consistently from a single global potential?**

This distinction becomes important when the state space has a nontrivial transition structure.

For a complete pairwise space, Chapter 4 gave us a direct construction.

For a more general graph or simplicial structure, we need a language for discussing:

* local consistency;
* global consistency;
* potential-generated quantities;
* closed structures;
* obstructions to exactness.

Cohomology provides precisely such a language.

---

# 6.2 From States to Transitions

Let

$$
B
$$

be a set of states.

A potential is a function

$$
\psi:B\to\mathbb{R}.
$$

It assigns one number to every state.

The debt function, however, is associated with pairs of states or transitions.

For a directed transition

$$
b_i\to b_j,
$$

we assign

$$
D(b_i,b_j).
$$

Thus the two objects live at different structural levels:

$$
\psi:
\text{states}\to\mathbb{R},
$$

while

$$
D:
\text{transitions}\to\mathbb{R}.
$$

This suggests that we need different spaces for objects defined on states and objects defined on transitions.

That is the beginning of the cochain viewpoint.

---

# 6.3 Cochains

A **cochain** is, roughly speaking, a function that assigns values to geometric or combinatorial objects of a specified dimension.

For our purposes, the first two levels are enough to begin.

A **0-cochain** assigns values to states.

Thus a potential

$$
\psi:B\to\mathbb{R}
$$

can be regarded as a 0-cochain.

We may write

$$
\psi\in C^0.
$$

A **1-cochain** assigns values to transitions or oriented edges.

Thus a debt function can be regarded as a 1-cochain:

$$
D\in C^1.
$$

So we have the correspondence

$$
\boxed{
\psi\in C^0
}
$$

and

$$
\boxed{
D\in C^1.
}
$$

This is already a useful change in viewpoint.

The potential lives on states.

The debt lives on transitions.

---

# 6.4 Why Orientation Matters

Suppose an edge connects two states:

$$
b_i\longrightarrow b_j.
$$

The reverse transition is

$$
b_j\longrightarrow b_i.
$$

For a debt function satisfying antisymmetry,

$$
D(b_j,b_i) = -D(b_i,b_j).
$$

Thus reversing orientation reverses the sign.

This is exactly the behavior expected of an oriented 1-cochain.

For an oriented edge

$$
[b_i,b_j],
$$

we can write

$$
D([b_i,b_j]) = -D([b_j,b_i]).
$$

The orientation is therefore not merely graphical decoration.

It is part of the algebraic structure.

---

# 6.5 The Coboundary Operator

We now introduce the central operator.

Given a 0-cochain

$$
\psi,
$$

define its coboundary by

$$
(\delta\psi)(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

Thus

$$
\delta:C^0\to C^1.
$$

The expression

$$
\psi(b_j)-\psi(b_i)
$$

should look familiar.

It is exactly the potential representation of debt from Chapter 4.

Therefore,

$$
\boxed{ D=\delta\psi }
$$

means

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

In other words:

> **An exact debt function is a coboundary of a potential.**

---

# 6.6 Why Is It Called a Coboundary?

The terminology comes from the general structure of cochain complexes.

A boundary usually moves from a higher-dimensional object to a lower-dimensional one.

The coboundary operator goes in the opposite direction.

Schematically,

$$
C^0
\xrightarrow{\delta}
C^1
\xrightarrow{\delta}
C^2
\xrightarrow{\delta}
C^3
\rightarrow\cdots
$$

The precise construction depends on the underlying graph, simplicial complex, or other combinatorial structure.

For the moment, the important part is the first map:

$$
C^0\xrightarrow{\delta}C^1.
$$

It converts a potential on states into differences on transitions.

---

# 6.7 Example of a Coboundary

Let

$$
B=\{b_1,b_2,b_3\}
$$

and define

$$
\psi(b_1)=0,
\qquad
\psi(b_2)=2,
\qquad
\psi(b_3)=5.
$$

Then

$$
D=\delta\psi
$$

gives

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

Reversing the edges gives

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

The entire transition structure was generated from the three potential values.

Because adding a constant to $\psi$ changes none of these differences, only potential differences matter.

---

# 6.8 Exact Cochains

A 1-cochain $D$ is called **exact** if there exists a 0-cochain $\psi$ such that

$$
D=\delta\psi.
$$

Thus,

$$
\boxed{
D\text{ exact}
\iff
\exists\psi\text{ such that }D=\delta\psi.
}
$$

For HST, this means:

> Debt is exact when it can be generated globally from a scalar potential over the state space.

This is precisely the property established in Chapter 4 for the complete pairwise setting.

---

# 6.9 Why Exactness Matters

Suppose

$$
D=\delta\psi.
$$

Consider a path

$$
\gamma=(b_0,b_1,\ldots,b_n).
$$

Its total debt is

$$
D(\gamma) = \sum_{k=0}^{n-1} D(b_k,b_{k+1}).
$$

Substituting

$$
D(b_k,b_{k+1}) = \psi(b_{k+1})-\psi(b_k),
$$

we obtain

$$
D(\gamma) = \sum_{k=0}^{n-1} \left[ \psi(b_{k+1})-\psi(b_k) \right].
$$

The sum telescopes:

$$
D(\gamma) = \psi(b_n)-\psi(b_0).
$$

Therefore the path debt depends only on its endpoints.

This is the cohomological language behind the path-independence result of Chapter 4.

---

# 6.10 Closed Paths

Now consider a closed path:

$$
b_0\to b_1\to\cdots\to b_n=b_0.
$$

If $D$ is exact, then

$$
D(\gamma) = \psi(b_n)-\psi(b_0).
$$

Since

$$
b_n=b_0,
$$

we obtain

$$
D(\gamma)=0.
$$

Therefore,

$$
\boxed{
\text{exact}
\Longrightarrow
\text{zero debt around closed paths}.
}
$$

This is one of the most important structural consequences of exactness.

---

# 6.11 From Paths to Higher-Dimensional Structures

So far we have discussed states and edges.

But cohomology becomes interesting when we also consider higher-dimensional objects.

For example, suppose we have three states

$$
b_i,\quad b_j,\quad b_k.
$$

They can form a triangle:

$$
[b_i,b_j,b_k].
$$

The three oriented edges form its boundary.

Schematically,

$$
[b_i,b_j,b_k]
\longrightarrow
[b_i,b_j]
+
[b_j,b_k]
+
[b_k,b_i].
$$

The precise sign convention depends on the chosen orientation.

The important idea is that a 2-dimensional object has a boundary consisting of 1-dimensional objects.

This allows us to define a second coboundary operator

$$
\delta:C^1\to C^2.
$$

Now the cochain sequence becomes

$$
C^0
\xrightarrow{\delta}
C^1
\xrightarrow{\delta}
C^2.
$$

This is where the relation between local consistency and global exactness becomes clearer.

---

# 6.12 The Fundamental Identity $\delta^2=0$

A central property of the coboundary operator is

$$
\boxed{
\delta^2=0.
}
$$

This means that if we start with a 0-cochain,

$$
\psi\in C^0,
$$

then

$$
\delta\psi\in C^1,
$$

and applying $\delta$ again gives

$$
\delta(\delta\psi)=0.
$$

Symbolically,

$$
C^0
\xrightarrow{\delta}
C^1
\xrightarrow{\delta}
C^2
$$

satisfies

$$
\boxed{
\delta\circ\delta=0.
}
$$

This identity is the algebraic foundation of cohomology.

---

# 6.13 Verifying $\delta^2=0$ for a Potential

Let

$$
D=\delta\psi.
$$

For three states $b_i,b_j,b_k$, the corresponding 2-dimensional coboundary evaluates schematically as

$$
(\delta D)(b_i,b_j,b_k) = D(b_i,b_j) + D(b_j,b_k) + D(b_k,b_i).
$$

Substituting

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i),
$$

we obtain

$$
\begin{aligned}
(\delta D)(b_i,b_j,b_k)
&=
[\psi(b_j)-\psi(b_i)]
\\
&\quad+
[\psi(b_k)-\psi(b_j)]
\\
&\quad+
[\psi(b_i)-\psi(b_k)].
\end{aligned}
$$

Everything cancels:

$$
(\delta D)(b_i,b_j,b_k)=0.
$$

Therefore,

$$
\delta(\delta\psi)=0.
$$

This is the concrete meaning of

$$
\delta^2=0
$$

in this setting.

---

# 6.14 Cocycles

We can now define a **cocycle**.

A 1-cochain $D$ is a 1-cocycle if

$$
\delta D=0.
$$

Thus,

$$
\boxed{
D\in Z^1
\iff
\delta D=0.
}
$$

The notation

$$
Z^1
$$

is commonly used for the space of 1-cocycles.

The condition says that $D$ satisfies the appropriate local consistency relation.

In the triangle example,

$$
D(b_i,b_j) + D(b_j,b_k) + D(b_k,b_i) = 0.
$$

This can be interpreted as zero circulation around the oriented boundary of the triangle.

---

# 6.15 Every Exact Cochain Is a Cocycle

We have already established

$$
D=\delta\psi.
$$

Applying $\delta$ gives

$$
\delta D = \delta(\delta\psi).
$$

Because

$$
\delta^2=0,
$$

we obtain

$$
\delta D=0.
$$

Therefore,

$$
\boxed{
\text{exact}
\Longrightarrow
\text{cocycle}.
}
$$

In symbols,

$$
B^1\subseteq Z^1,
$$

where

$$
B^1=\mathrm{im}\delta
$$

is the space of 1-coboundaries.

This inclusion is automatic.

The interesting question is whether the inclusion is strict.

---

# 6.16 Exact Versus Closed

We can now introduce the basic distinction.

An exact 1-cochain has the form

$$
D=\delta\psi.
$$

A cocycle satisfies

$$
\delta D=0.
$$

Therefore,

$$
\boxed{
\text{exact}\Rightarrow\text{closed}.
}
$$

But in general,

$$
\boxed{
\text{closed}\not\Rightarrow\text{exact}.
}
$$

This is the central phenomenon that cohomology measures.

A structure may satisfy every local consistency condition while still failing to arise globally from a single potential.

The failure of the converse is where topology and global structure enter.

---

# 6.17 A Simple Intuition

Imagine walking around a complicated space.

At each local step, everything appears consistent.

You measure a quantity along every edge.

Every elementary consistency condition is satisfied.

Yet after traveling around a large loop, you may return to the starting point with a nonzero accumulated quantity.

Then the local data cannot be represented globally by a single-valued potential.

This is the basic intuition behind a nontrivial cohomology class.

The exact mathematical behavior depends on the underlying structure.

---

# 6.18 Cohomology

We can now define the first cohomology group.

The first cohomology group is

$$
\boxed{
H^1
=
\frac{Z^1}{B^1}.
}
$$

Equivalently,

$$
\boxed{
H^1
=
\frac{\ker\delta:C^1\to C^2}
{\operatorname{im}\delta:C^0\to C^1}.
}
$$

The numerator consists of cocycles.

The denominator consists of exact 1-cochains.

Thus two cocycles are considered equivalent when they differ by an exact cochain.

---

# 6.19 What Does $H^1$ Measure?

The most useful interpretation for our purposes is:

> **$H^1$ measures the obstruction to turning a closed 1-cochain into a global potential difference.**

If

$$
H^1=0,
$$

then every 1-cocycle is exact.

Therefore,

$$
\delta D=0
\quad\Longrightarrow\quad
D=\delta\psi.
$$

If

$$
H^1\neq0,
$$

then there exist cocycles that are not coboundaries.

Those structures satisfy the local consistency condition but cannot be globally generated by a potential.

This is the mathematical distinction between **closed** and **exact**.

---

# 6.20 Why the Quotient Appears

Suppose

$$
D_1
$$

and

$$
D_2
$$

are two cocycles.

Suppose their difference is exact:

$$
D_1-D_2=\delta\psi.
$$

Then they differ only by something generated from a potential.

Cohomology regards them as belonging to the same cohomology class.

Thus $H^1$ does not keep track of every possible representative.

It keeps track of the part that cannot be removed by changing the potential.

Symbolically,

$$
[D_1]=[D_2]
$$

when

$$
D_1-D_2\in B^1.
$$

---

# 6.21 Relation to Gauge Freedom

There is a useful connection with the gauge freedom already encountered.

If

$$
\psi
$$

is replaced by

$$
\psi+c,
$$

then

$$
\delta(\psi+c)=\delta\psi.
$$

Therefore, the potential itself is not uniquely observable through debt.

The debt sees only differences.

This is a simple gauge freedom.

Cohomology goes further.

It asks whether the entire transition structure can be explained by **any** potential at all.

Thus there are two different questions:

### Gauge question

How many potentials produce the same exact debt?

Answer:

$$
\psi\sim\psi+c.
$$

### Cohomological question

Does a potential exist that generates the debt?

Answer:

This depends on whether the relevant cocycle is exact.

---

# 6.22 Complete Spaces Revisited

We can now reinterpret the previous chapters.

On the complete pairwise state space, we constructed

$$
\psi(b)=D(s_0,b).
$$

Then

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

Thus every debt function satisfying the Chapter 3 structure is exact.

The cohomological language does not replace the basepoint theorem.

It explains the theorem from a broader structural perspective.

The basepoint theorem gives an explicit construction.

Cohomology gives a language for asking when such a construction is possible in more general spaces.

---

# 6.23 Sparse Structures

Now consider a directed graph

$$
G=(V,E).
$$

Suppose the debt is defined only on edges:

$$
D:E\to\mathbb{R}.
$$

The potential question becomes:

> Does there exist $\psi:V\to\mathbb{R}$ such that

$$
D(u,v)=\psi(v)-\psi(u)
$$

for every edge $(u,v)\in E$?

This is no longer automatically true.

The answer depends on the structure of the graph and on the consistency of the edge values.

In particular, cycles become important.

---

# 6.24 A Cycle as an Obstruction

Consider the directed cycle

$$
b_1\to b_2\to b_3\to b_1.
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
D(b_3,b_1)=-3.
$$

Then

$$
1+2-3=0.
$$

The cycle has zero total debt.

This is consistent with a potential representation.

Indeed, choose

$$
\psi(b_1)=0.
$$

Then

$$
\psi(b_2)=1,
$$

and

$$
\psi(b_3)=3.
$$

The final edge requires

$$
\psi(b_1)-\psi(b_3)
=
-3,
$$

which is satisfied.

Now change the final debt to

$$
D(b_3,b_1)=1.
$$

Then

$$
1+2+1=4.
$$

The cycle has nonzero debt.

A global potential cannot satisfy all three edge equations simultaneously.

The cycle therefore detects the obstruction.

---

# 6.25 Local and Global Consistency

This suggests an important distinction.

A condition may hold locally without guaranteeing global exactness.

For example, every small piece of a structure may satisfy a consistency relation, while a larger loop may still carry a nontrivial obstruction.

Cohomology is designed to capture this distinction.

Very roughly:

$$
\boxed{
\text{local consistency}
\neq
\text{global potential}
}
$$

in general.

The precise relationship depends on the topology and combinatorial structure under consideration.

---

# 6.26 A Word About Topology

Cohomology is closely related to topology because the existence of global potentials can depend on the shape of the underlying space.

Two spaces can have locally similar structures but different global properties.

For example, a space containing a genuine loop that cannot be continuously contracted away can support global structures that have no global potential representation.

We do not need to develop algebraic topology in full here.

For the purposes of HST, the important idea is:

> **Global structure can create obstructions that are invisible from purely local equations.**

This is precisely the kind of phenomenon that motivates the use of cohomology.

---

# 6.27 Cohomological Vocabulary for HST

We can now translate our previous terminology.

| HST object                  | Cohomological language                 |
| --------------------------- | -------------------------------------- |
| Potential $\psi$            | 0-cochain                              |
| Debt $D$                    | 1-cochain                              |
| $D=\delta\psi$              | $D$ is exact                           |
| $\delta D=0$                | $D$ is a cocycle                       |
| $\delta^2=0$                | Coboundaries are cocycles              |
| $H^1$                       | Obstruction classes modulo exact terms |
| Additive constant in $\psi$ | Gauge freedom                          |

This table is not intended to replace the definitions.

It is a dictionary between the language developed in previous chapters and the new language introduced here.

---

# 6.28 What Cohomology Adds

The previous chapters already gave us a powerful result:

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

Why introduce all this additional machinery?

Because the potential representation answers the problem only when exactness is available.

Cohomology lets us ask a broader class of questions:

* What if the state space is sparse?
* What if only certain transitions exist?
* What if there are nontrivial cycles?
* What if local consistency holds but global exactness fails?
* How many distinct obstructions exist?
* Can different debt structures differ only by an exact correction?
* What information is genuinely global rather than potential-generated?

These questions cannot be answered merely by writing down a potential in advance.

---

# 6.29 The Role of $H^1$

The first cohomology group therefore becomes a diagnostic object.

If

$$
H^1=0,
$$

then there are no nontrivial first-order cohomological obstructions.

Every cocycle is exact.

If

$$
H^1\neq0,
$$

then there are nontrivial classes.

Some closed structures cannot be reduced to global potential differences.

Thus the transition

$$
H^1=0
\quad\longrightarrow\quad
H^1\neq0
$$

marks a qualitative change in the mathematical structure.

---

# 6.30 What We Should Not Conclude Yet

It is important not to overinterpret the cohomological language.

We have not yet developed:

* a complete theory of graph cohomology;
* the precise relationship between directed graphs and simplicial complexes;
* relative cohomology;
* homology;
* higher-dimensional cochains;
* computational methods for $H^1$;
* the conditions under which zero circulation is sufficient for exactness in every directed setting.

Those are separate mathematical questions.

For now, we have introduced the basic language needed to investigate them rigorously.

---

# 6.31 Summary

We introduced the basic cohomological framework.

A potential is a 0-cochain:

$$
\psi\in C^0.
$$

A debt function is naturally represented as a 1-cochain:

$$
D\in C^1.
$$

The coboundary operator maps potentials to transition differences:

$$
\delta:C^0\to C^1,
$$

with

$$
(\delta\psi)(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

A debt function is exact when

$$
D=\delta\psi.
$$

The next coboundary operator gives

$$
\delta:C^1\to C^2.
$$

The fundamental identity is

$$
\boxed{\delta^2=0}.
$$

Therefore every exact 1-cochain is a cocycle:

$$
\boxed{
\text{exact}\Rightarrow\text{cocycle}.
}
$$

The first cohomology group is

$$
\boxed{
H^1=\frac{Z^1}{B^1}.
}
$$

It measures, in a precise algebraic sense, the difference between closed and exact structures.

For HST, the central interpretation is:

$$
\boxed{
\text{Debt is a 1-cochain.}
}
$$

When

$$
D=\delta\psi,
$$

the debt is generated by a global potential and is therefore exact.

When a closed structure is not exact, cohomology provides a framework for describing the resulting obstruction.

---

# Exercises

## Exercise 6.1 — Identify the Cochains

For each object, determine whether it is naturally a 0-cochain or a 1-cochain:

1. a function assigning a value to every state;
2. a function assigning a value to every directed edge;
3. a potential $\psi$;
4. a debt function $D$.

Explain your answers.

---

## Exercise 6.2 — Compute a Coboundary

Let

$$
\psi(b_1)=1,
\qquad
\psi(b_2)=4,
\qquad
\psi(b_3)=9.
$$

Compute

$$
(\delta\psi)(b_1,b_2),
$$

$$
(\delta\psi)(b_2,b_3),
$$

and

$$
(\delta\psi)(b_1,b_3).
$$

---

## Exercise 6.3 — Gauge Freedom

Let

$$
\widetilde{\psi}=\psi+c.
$$

Prove directly that

$$
\delta\widetilde{\psi}
=
\delta\psi.
$$

Explain why this corresponds to the nonuniqueness of potentials.

---

## Exercise 6.4 — Exact Debt

Suppose

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Show that $D$ is exact.

What is the corresponding 0-cochain?

---

## Exercise 6.5 — Closed Triangle

Suppose

$$
D(b_1,b_2)=2,
$$

$$
D(b_2,b_3)=3,
$$

and

$$
D(b_3,b_1)=-5.
$$

Compute

$$
D(b_1,b_2)+D(b_2,b_3)+D(b_3,b_1).
$$

What does the result suggest about the existence of a potential?

---

## Exercise 6.6 — Nonzero Circulation

Suppose

$$
D(b_1,b_2)=2,
$$

$$
D(b_2,b_3)=3,
$$

and

$$
D(b_3,b_1)=1.
$$

Compute the circulation around the triangle.

Can $D$ be represented as

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i)?
$$

Explain.

---

## Exercise 6.7 — Verify $\delta^2=0$

Let

$$
\psi(b_1)=a,
\qquad
\psi(b_2)=b,
\qquad
\psi(b_3)=c.
$$

Compute

$$
\delta(\delta\psi)
$$

on the triangle $(b_1,b_2,b_3)$ and verify that it equals zero.

---

## Exercise 6.8 — Exact Implies Cocycle

Suppose

$$
D=\delta\psi.
$$

Use

$$
\delta^2=0
$$

to prove that

$$
\delta D=0.
$$

Explain why this establishes

$$
B^1\subseteq Z^1.
$$

---

## Exercise 6.9 — Exact or Not?

Consider the directed cycle

$$
b_1\to b_2\to b_3\to b_1
$$

with

$$
D(b_1,b_2)=4,
$$

$$
D(b_2,b_3)=-1,
$$

and

$$
D(b_3,b_1)=-3.
$$

Determine whether the total cycle debt is zero.

Construct a potential if possible.

---

## Exercise 6.10 — Potential Reconstruction

Choose

$$
\psi(b_1)=0.
$$

Suppose

$$
D(b_1,b_2)=3,
$$

$$
D(b_2,b_3)=4,
$$

and

$$
D(b_3,b_4)=-2.
$$

Construct a potential on

$$
\{b_1,b_2,b_3,b_4\}.
$$

Then compute

$$
D(b_1,b_4).
$$

---

## Exercise 6.11 — Closed Versus Exact

Explain in your own words the difference between:

$$
\delta D=0
$$

and

$$
D=\delta\psi.
$$

Which condition is stronger?

---

## Exercise 6.12 — Cohomology

Explain the meaning of

$$
H^1=\frac{Z^1}{B^1}.
$$

What mathematical information is lost when we identify two cocycles that differ by an exact cochain?

---

## Exercise 6.13 — Complete State Space

Explain why the basepoint construction from Chapter 4 gives an explicit potential for the complete pairwise debt structure.

How does this relate to exactness?

---

## Exercise 6.14 — Conceptual Question

Why might a local consistency condition fail to guarantee the existence of a global potential?

Give an example involving a cycle.

---

## Exercise 6.15 — HST Interpretation

In the language of HST, explain the following statement:

> “Epistemic debt can be represented as a 1-cochain, while a potential represents a 0-cochain whose coboundary generates the debt.”

What new questions become possible once debt is viewed this way?
