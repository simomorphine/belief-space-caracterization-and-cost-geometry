
## 3.4 A Cohomology Reminder

Before interpreting debt cohomologically, it is useful to recall the basic language.

Cohomology provides a mathematical framework for studying structures that satisfy local consistency conditions and asking whether those structures arise from global potentials.

For the purposes of this book, only a small part of the general theory is required.

The basic objects are **cochains**, **cocycles**, **coboundaries**, and **cohomology groups**.

A **cochain** is a function defined on objects of a specified dimension.

Given a state space `B`:

* a `0`-cochain assigns a number to each state;
* a `1`-cochain assigns a number to each ordered pair of states;
* a `2`-cochain assigns a number to each ordered triple of states.

We denote the corresponding spaces by

$$
C^0(B),\qquad C^1(B),\qquad C^2(B).
$$

Thus,

$$
\psi:B\to\mathbb R
$$

is a `0`-cochain, while

$$
D:B\times B\to\mathbb R
$$

is a `1`-cochain.

The **coboundary operator** `δ` maps a `k`-cochain to a `(k+1)`-cochain.

For a `0`-cochain,

$$
(\delta\psi)(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

For a `1`-cochain,

$$
(\delta D)(b_i,b_j,b_k) = D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j).
$$

The fundamental property is

$$
\delta^2=0.
$$

That is, applying the coboundary operator twice always gives zero.

A **cocycle** is a cochain whose coboundary vanishes.

For a `1`-cochain `D`, this means

$$
\delta D=0.
$$

Expanding the definition gives

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k).
$$

Thus, in the present framework, the cocycle condition is exactly the additivity condition (D1).

A **coboundary** is a cochain obtained by applying `δ` to another cochain.

For example, if

$$
D=\delta\psi,
$$

then

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

Every coboundary is automatically a cocycle because

$$
\delta D = \delta(\delta\psi) = \delta^2\psi = 0.
$$

Therefore,

$$
\text{coboundaries}\subseteq\text{cocycles}.
$$

The converse need not hold in a general cohomological setting. A cocycle does not necessarily have to be a coboundary.

Cohomology measures this difference.

Very roughly, the `k`-th cohomology group is

$$
H^k = \frac{\ker(\delta:C^k\to C^{k+1})} {\mathrm{im}(\delta:C^{k-1}\to C^k)}.
$$

Thus, cohomology studies cocycles modulo those cocycles that are already explained as coboundaries.

In the present framework, this distinction is important for debt.

If `D` is a `1`-cocycle, then

$$
\delta D=0.
$$

If `D` is also a coboundary, then there exists a potential `ψ` such that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

The question of whether every debt cocycle is a coboundary is therefore a cohomological question.

For the complete simplex considered in this chapter, the relevant first cohomology is trivial. Consequently, every `1`-cocycle is a coboundary. This is the mathematical reason that the potential representation of debt will emerge in Chapter 4.

---

## 3.5 Debt as an Alternating 1-Cocycle

The axioms (D1) and (D2) now have a precise interpretation in the language of cohomology.

**Definition 3.15 (Discrete De Rham Complex).** Let `B` be a set, viewed as the vertex set of a complete directed graph. We use the term *discrete de Rham complex* for the following cochain structure.

For `k≥0`, let `C^k(B)` be the `R`-vector space of real-valued functions on `(k+1)`-tuples of elements of `B`.

In particular:

* `C^0(B)` is the space of functions `ψ:B→R`;
* `C^1(B)` is the space of functions `D:B×B→R`;
* `C^2(B)` is the space of real-valued functions on `B×B×B`.

**Definition 3.16 (Coboundary).** The coboundary operator

$$
\delta:C^0(B)\to C^1(B)
$$

is defined by

$$
(\delta\psi)(b_i,b_j)
:=
\psi(b_j)-\psi(b_i).
$$

The coboundary operator

$$
\delta:C^1(B)\to C^2(B)
$$

is defined by

$$
(\delta D)(b_i,b_j,b_k)
:=
D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j).
$$

**Proposition 3.17 (Nilpotency of the Coboundary).** For every `ψ∈C^0(B)`,

$$
\delta^2\psi=0.
$$

**Proof.**

Applying the coboundary operator twice gives

$$
(\delta(\delta\psi))(b_i,b_j,b_k) = (\delta\psi)(b_j,b_k) - (\delta\psi)(b_i,b_k) + (\delta\psi)(b_i,b_j).
$$

Substituting the definition,

$$
= [\psi(b_k)-\psi(b_j)] - [\psi(b_k)-\psi(b_i)] + [\psi(b_j)-\psi(b_i)].
$$

All terms cancel, giving

$$
\delta^2\psi=0.
$$

`□`

**Proposition 3.18 (Additivity is the Cocycle Condition).** A function `D∈C^1(B)` satisfies (D1) if and only if

$$
\delta D=0.
$$

In other words, `D` is a `1`-cocycle.

**Proof.**

The condition `δD=0` means

$$
D(b_j,b_k)-D(b_i,b_k)+D(b_i,b_j)=0.
$$

Rearranging,

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k),
$$

which is exactly (D1).

`□`

**Remark 3.19 (Alternating 1-Cochains).** A `1`-cochain `D∈C^1(B)` is called *alternating* if

$$
D(b_i,b_j) = -D(b_j,b_i)
$$

for all `b_i,b_j∈B`.

This is precisely the content of axiom (D2). Thus (D2) says that the debt function is an alternating `1`-cochain.

Alternation is not a consequence of the cocycle condition. It is a separate structural requirement imposed by the definition of debt.

**Corollary 3.20 (Debt Functions are Alternating 1-Cocycles).** A function `D∈C^1(B)` is a debt function if and only if it is an alternating `1`-cocycle of the discrete de Rham complex on `B`.

**Proof.**

By Definition 3.6, `D` is a debt function if and only if it satisfies (D1) and (D2).

By Proposition 3.18, (D1) is equivalent to

$$
\delta D=0,
$$

so `D` is a `1`-cocycle.

By Remark 3.19, (D2) is equivalent to `D` being alternating.

Therefore, `D` is a debt function if and only if it is an alternating `1`-cocycle.

`□`

**Remark 3.21 (Debt as a Cohomological Object).** Corollary 3.20 provides a cohomological characterization of debt.

The two debt axioms have distinct mathematical meanings:

* (D1) expresses closure:

$$
\delta D=0;
$$

* (D2) expresses alternation:

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

The basepoint theorem in Chapter 4 will show that, on the complete structure considered here, every such cocycle is a coboundary. That is, there exists a potential `ψ∈C^0(B)` such that

$$
D=\delta\psi,
$$

or equivalently,

$$
D(b_i,b_j) = \psi(b_j)-\psi(b_i).
$$

This corresponds to the triviality of the first cohomology of the complete simplex.

**Remark 3.22 (Asymmetry is Not Debt).** The asymmetry `A` introduced in Definition 3.2 is also an alternating `1`-cochain, since

$$
A(b_i,b_j) = -A(b_j,b_i).
$$

However, `A` need not be a cocycle. As Example 3.8 demonstrates,

$$
\delta A\neq0
$$

in general.

Thus `A` and `D` belong to the same cochain space `C^1(B)`, but they satisfy different structural requirements:

$$
A:\quad\text{alternating 1-cochain},
$$

while

$$
D:\quad\text{alternating 1-cocycle}.
$$

For `|B|≥3`, the space of alternating `1`-cocycles is a proper subspace of the space of alternating `1`-cochains.

This distinction is fundamental. `A` represents the asymmetry of the cost function, whereas `D` is a separate debt structure constrained by both antisymmetry and additivity.

---

## 3.9 References

The cohomological language used in this chapter is standard mathematical terminology, although the particular discrete construction used here is adapted to the state space `B`.

A standard introduction to cochains, coboundaries, cocycles, and cohomology is:

Allen Hatcher, *Algebraic Topology*, Chapter 3, “Cohomology.”

The book is freely available from the author's Cornell webpage.

For the relationship between cohomology and differential forms, see:

Raoul Bott and Loring W. Tu, *Differential Forms in Algebraic Topology*, Graduate Texts in Mathematics 82, Springer.

The present construction should therefore be understood as a discrete cochain framework inspired by standard cohomological constructions, rather than as a direct reproduction of the classical de Rham complex.

---

## 3.10 Exercises

**Exercise 3.1.** Verify that the function

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i)
$$

satisfies (D1) and (D2) for any

$$
\psi:B\to\mathbb R.
$$

**Exercise 3.2.** Give an example of a function

$$
D:B\times B\to\mathbb R
$$

that satisfies (D1) but not (D2).

Then give an example that satisfies (D2) but not (D1).

**Exercise 3.3.** Let

$$
B=\{1,2,3\}
$$

and define

$$
D(1,2)=2,\qquad
D(2,3)=3,\qquad
D(1,3)=5,
$$

with `D` extended by antisymmetry and `D(i,i)=0`.

Verify that `D` satisfies (D1) and (D2). Find a potential `ψ` such that

$$
D=\delta\psi.
$$

**Exercise 3.4.** Let `B` be a set and let `D` satisfy (D1) and (D2). Fix a basepoint `s_0∈B` and define

$$
\psi_{s_0}(b):=D(s_0,b).
$$

Prove that

$$
D(b_i,b_j)
=
\psi_{s_0}(b_j)-\psi_{s_0}(b_i).
$$

**Exercise 3.5.** Prove that the decomposition

$$
d=S+A
$$

of Proposition 3.4 is unique.

*Hint:* Consider `d-d^T`, where

$$
d^T(b_i,b_j):=d(b_j,b_i).
$$

**Exercise 3.6.** Show that the asymmetry `A` is not additive in general. Construct a belief space and a triple `(b_i,b_j,b_k)` such that

$$
A(b_i,b_k)
\neq
A(b_i,b_j)+A(b_j,b_k).
$$

**Exercise 3.7.** Let `D=δψ`. Show that replacing `ψ` by

$$
\psi'= \psi+c
$$

for a constant `c` leaves `D` unchanged.

What happens if the transformation is

$$
\psi'=\psi+\chi
$$

for a nonconstant function `χ`?

**Exercise 3.8.** Let `B` be a finite set with `n` elements. Show that the space of debt functions on `B` is isomorphic to

$$
\mathbb R^{n-1}.
$$

*Hint:* Use Exercise 3.4 to construct the correspondence between debt functions and potentials, and identify the freedom to add a constant to the potential.

**Exercise 3.9.** Prove that the asymmetry

$$
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right)
$$

is not a debt function in general.

*Hint:* Use Exercise 3.6.

**Exercise 3.10.** Let `D` be a debt function and let `c∈R`. Show that

$$
cD
$$

is also a debt function. If `D=δψ`, determine the corresponding potential.

**Exercise 3.11.** Consider the following question:

Why should debt be additive rather than satisfy some weaker condition?

Give a short mathematical argument based on telescoping, path independence, and potential representation.


---

## 3.7 Why Debt is the Right Object to Study

We can now state the central structural difference between asymmetry and debt.

The asymmetry `A` is not additive in general. There may exist states `b_i,b_j,b_k` such that

$$
A(b_i,b_k)
\neq
A(b_i,b_j)+A(b_j,b_k).
$$

Consequently, `A` does not generally telescope and does not define a path-independent quantity.

Debt `D`, by definition, is additive:

$$
D(b_i,b_k) = D(b_i,b_j)+D(b_j,b_k).
$$

Therefore, debt telescopes along paths.

This difference has a direct cohomological interpretation.

The asymmetry is an alternating `1`-cochain:

$$
A\in C^1(B),
\qquad
A(b_i,b_j)=-A(b_j,b_i),
$$

but generally

$$
\delta A\neq0.
$$

Debt is an alternating `1`-cocycle:

$$
D\in C^1(B),
\qquad
D(b_i,b_j)=-D(b_j,b_i),
\qquad
\delta D=0.
$$

Thus the important distinction is not that one quantity is asymmetric and the other is not. Both are antisymmetric.

The distinction is **additivity**.

Additivity is what makes the debt telescope. On the complete state space, this ultimately leads to the potential representation

$$
D=\delta\psi.
$$

The precise relationship between the cost asymmetry `A` and the debt function `D` is a separate question and should not be assumed from the definitions alone.
