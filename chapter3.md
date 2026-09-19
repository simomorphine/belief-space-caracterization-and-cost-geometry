# Chapter 3: The Debt Function

## 3.1 The asymmetry of cost

Chapter 2 introduced the energy quasi-metric $d$ as a measure of the cost of moving between states of the belief space. Because $d$ is a quasi-metric, it need not be symmetric. In general,

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

This asymmetry is meaningful. A transition from $b_i$ to $b_j$ may require a different amount of computational energy from the reverse transition.

We therefore begin by separating the symmetric and asymmetric components of the cost.

### Definition 3.1 (Symmetric and antisymmetric parts)

Assume that $d$ is finite on the pairs under consideration. Define

$$
S(b_i,b_j)
=
\frac{1}{2}
\left(
d(b_i,b_j)+d(b_j,b_i)
\right)
$$

and

$$
A(b_i,b_j)
=
\frac{1}{2}
\left(
d(b_i,b_j)-d(b_j,b_i)
\right).
$$

We call $S$ the **symmetric part** of the cost and $A$ the **antisymmetric part** of the cost.

The function $A$ measures directional imbalance in the cost. If

$$
A(b_i,b_j)>0,
$$

then moving from $b_i$ to $b_j$ costs more than moving in the reverse direction.

If

$$
A(b_i,b_j)<0,
$$

the opposite direction is more expensive.

If

$$
A(b_i,b_j)=0,
$$

the two directions have equal cost.

### Proposition 3.2

The functions $S$ and $A$ satisfy

$$
S(b_i,b_j)=S(b_j,b_i)
$$

and

$$
A(b_i,b_j)=-A(b_j,b_i).
$$

Moreover,

$$
\boxed{d=S+A.}
$$

### Proof

The symmetry of $S$ follows immediately:

$$
S(b_j,b_i)
=
\frac{1}{2}
\left(
d(b_j,b_i)+d(b_i,b_j)
\right)
=
S(b_i,b_j).
$$

Similarly,

$$
A(b_j,b_i)
=
\frac{1}{2}
\left(
d(b_j,b_i)-d(b_i,b_j)
\right)
=
-A(b_i,b_j).
$$

Finally,

$$
S(b_i,b_j)+A(b_i,b_j)
=
\frac{1}{2}(d_{ij}+d_{ji})
+
\frac{1}{2}(d_{ij}-d_{ji})
=
d_{ij}.
$$

Thus $d=S+A$.

### Remark 3.3 (Asymmetry is not debt)

The antisymmetric component $A$ is determined directly by the energy quasi-metric.

It is therefore important not to identify $A$ with debt.

The two concepts answer different questions:

* $A$ asks: **How different are the costs in the two directions?**
* $D$ asks: **Does a quantity assigned to transitions compose consistently along a sequence of transitions?**

An antisymmetric function need not have this compositional property.

This distinction will be fundamental throughout the following chapters.

---

# 3.2 Introducing debt

We now introduce the second structure.

The idea is that a transition may carry a quantity that can be accumulated as transitions are composed.

Let

$$
D:\mathcal B\times\mathcal B\to\mathbb R.
$$

We interpret $D(b_i,b_j)$ as the **debt associated with the transition**

$$
b_i\rightarrow b_j.
$$

At this stage we deliberately avoid assigning a specific physical interpretation to debt. It may eventually represent epistemic debt, computational obligation, information-related burden, or another quantity associated with a transition.

The mathematical structure comes first.

### Definition 3.4 (Debt function)

A **debt function** is a function

$$
D:\mathcal B\times\mathcal B\to\mathbb R
$$

satisfying the following two axioms.

### (D1) Additivity

For every $b_i,b_j,b_k\in\mathcal B$,

$$
\boxed{
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
}
$$

### (D2) Antisymmetry

For every $b_i,b_j\in\mathcal B$,

$$
\boxed{
D(b_i,b_j)=-D(b_j,b_i).
}
$$

These are the two defining properties of the debt structure.

### Remark 3.5 (Axiom redundancy)

Although we define debt using both (D1) and (D2), there is an important mathematical observation.

In the present setting, (D2) actually follows from (D1).

Indeed, setting $b_i=b_j=b_k=b$ in (D1) gives

$$
D(b,b)=D(b,b)+D(b,b),
$$

and therefore

$$
D(b,b)=0.
$$

Then setting $b_k=b_i$ gives

$$
D(b_i,b_i)
=
D(b_i,b_j)+D(b_j,b_i),
$$

so

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

Thus (D2) is mathematically redundant.

Nevertheless, we retain it in the definition because it expresses an important conceptual property of a transition quantity: reversing a transition reverses its debt.

This distinction between **conceptual axioms** and **minimal axiomatization** will be useful later.

---

# 3.3 Elementary properties of debt

The two axioms immediately impose strong restrictions on the possible form of $D$.

### Proposition 3.6 (Zero debt for the identity transition)

For every $b\in\mathcal B$,

$$
\boxed{D(b,b)=0.}
$$

### Proof

From (D1),

$$
D(b,b)=D(b,b)+D(b,b).
$$

Subtracting $D(b,b)$ from both sides gives

$$
D(b,b)=0.
$$

$\square$

### Proposition 3.7 (Reversal of a transition)

For every $b_i,b_j\in\mathcal B$,

$$
\boxed{
D(b_j,b_i)=-D(b_i,b_j).
}
$$

### Proof

This is precisely axiom (D2).

Alternatively, as shown in Remark 3.5, it follows from (D1).

$\square$

### Proposition 3.8 (Composition)

Suppose a transition

$$
b_i\rightarrow b_j
$$

is followed by

$$
b_j\rightarrow b_k.
$$

Then the debt associated with the composed transition satisfies

$$
\boxed{
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
}
$$

### Proof

This is axiom (D1).

$\square$

The important point is that debt is not assigned independently to every possible pair of states. The values must be compatible with composition.

For example, if

$$
D(b_1,b_2)=2
$$

and

$$
D(b_2,b_3)=5,
$$

then additivity requires

$$
D(b_1,b_3)=7.
$$

The value $D(b_1,b_3)$ cannot be chosen independently.

---

# 3.4 Debt on sequences of transitions

The additivity axiom can be applied repeatedly.

Consider a sequence

$$
b_0\rightarrow b_1\rightarrow b_2\rightarrow\cdots\rightarrow b_n.
$$

Its total debt is defined by

$$
D(b_0,b_1)
+
D(b_1,b_2)
+\cdots+
D(b_{n-1},b_n).
$$

Repeated application of (D1) gives

$$
D(b_0,b_n)
=
D(b_0,b_1)
+
D(b_1,b_2)
+\cdots+
D(b_{n-1},b_n).
$$

Thus:

### Proposition 3.9 (Finite composition)

For any sequence

$$
(b_0,b_1,\ldots,b_n),
$$

we have

$$
\boxed{
D(b_0,b_n)
=
\sum_{k=0}^{n-1}
D(b_k,b_{k+1}).
}
$$

### Proof

The result follows by induction.

For $n=2$, it is exactly (D1):

$$
D(b_0,b_2)
=
D(b_0,b_1)+D(b_1,b_2).
$$

Assume the result holds for $n$. Then

$$
D(b_0,b_{n+1})
=
D(b_0,b_n)+D(b_n,b_{n+1}).
$$

Using the induction hypothesis,

$$
D(b_0,b_{n+1})
=
\sum_{k=0}^{n-1}D(b_k,b_{k+1})
+
D(b_n,b_{n+1}),
$$

which gives

$$
D(b_0,b_{n+1})
=
\sum_{k=0}^{n}D(b_k,b_{k+1}).
$$

Therefore the result holds for every $n$.

$\square$

This proposition is simply the repeated application of the composition law.

It tells us that the debt assigned to a long sequence is determined by the debts assigned to its individual transitions.

---

# 3.5 The algebra of debt functions

Debt functions have a natural linear structure.

Suppose $D_1$ and $D_2$ are debt functions and let

$$
a,b\in\mathbb R.
$$

Define

$$
D=aD_1+bD_2.
$$

Then

$$
D(b_i,b_k)
=
aD_1(b_i,b_k)+bD_2(b_i,b_k).
$$

Using additivity of $D_1$ and $D_2$,

$$
\begin{aligned}
D(b_i,b_k)
&=
a[D_1(b_i,b_j)+D_1(b_j,b_k)]\\
&\quad+
b[D_2(b_i,b_j)+D_2(b_j,b_k)]\\
&=
D(b_i,b_j)+D(b_j,b_k).
\end{aligned}
$$

Similarly,

$$
D(b_i,b_j)
=
-aD_1(b_j,b_i)-bD_2(b_j,b_i)
=
-D(b_j,b_i).
$$

Therefore:

### Proposition 3.10

The set of debt functions on $\mathcal B$ is a vector space over $\mathbb R$.

### Remark 3.11

This gives debt a useful algebraic structure.

We can add debt functions, subtract them, and multiply them by real coefficients while remaining inside the class of debt functions.

For a finite belief space with $n$ states, the dimension of this vector space will become important later when we investigate the deeper structure of debt.

---

# 3.6 Debt versus cost asymmetry

We can now state the distinction between the two objects more precisely.

The antisymmetric part of cost is

$$
A(b_i,b_j)
=
\frac12
\left(
d(b_i,b_j)-d(b_j,b_i)
\right).
$$

It is automatically antisymmetric because of how it is defined.

Debt, on the other hand, satisfies the composition law

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

This composition law is substantially stronger.

### Example 3.12 (Antisymmetry without additivity)

Let

$$
\mathcal B=\{b_1,b_2,b_3\}.
$$

Define

$$
A(b_1,b_2)=1,
$$

$$
A(b_2,b_3)=1,
$$

and

$$
A(b_1,b_3)=3.
$$

Extend the function by antisymmetry:

$$
A(b_j,b_i)=-A(b_i,b_j),
$$

and set

$$
A(b_i,b_i)=0.
$$

Then $A$ is antisymmetric.

However,

$$
A(b_1,b_3)=3,
$$

while

$$
A(b_1,b_2)+A(b_2,b_3)=1+1=2.
$$

Therefore,

$$
A(b_1,b_3)
\neq
A(b_1,b_2)+A(b_2,b_3).
$$

So $A$ is not additive.

This gives the important implication

$$
\boxed{
\text{antisymmetry}\not\Rightarrow\text{additivity}.
}
$$

Consequently, not every directional imbalance in cost qualifies as debt.

---

# 3.7 What has been established

At this point, the mathematical structure of debt is deliberately limited to its defining properties and their elementary consequences.

We have established:

1. Debt is a function

$$
D:\mathcal B\times\mathcal B\to\mathbb R.
$$

2. Debt is additive under composition:

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

3. Debt vanishes on the diagonal:

$$
D(b,b)=0.
$$

4. Reversing a transition reverses its debt:

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

5. Debt along a finite sequence is obtained by summing the transition debts:

$$
D(b_0,b_n)
=
\sum_{k=0}^{n-1}D(b_k,b_{k+1}).
$$

6. Debt functions form a vector space.

7. The antisymmetric component of cost $A$ is not automatically a debt function.

The next question is more structural:

> **What does an additive debt function actually look like?**

Is there a scalar quantity associated with each state whose differences generate all debt values?

That question is not answered in this chapter.

It is the subject of the next chapter.

---

# 3.8 Exercises

### Exercise 3.1

Verify directly that if $D$ satisfies (D1), then

$$
D(b,b)=0.
$$

### Exercise 3.2

Show that (D1) implies antisymmetry:

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

Explain why (D2) is therefore mathematically redundant.

### Exercise 3.3

Let

$$
\mathcal B=\{1,2,3\}.
$$

Suppose

$$
D(1,2)=2,
\qquad
D(2,3)=3.
$$

Use additivity to determine $D(1,3)$.

Then determine

$$
D(2,1),\quad D(3,2),\quad D(3,1).
$$

### Exercise 3.4

Let

$$
b_0\rightarrow b_1\rightarrow b_2\rightarrow b_3\rightarrow b_4.
$$

Suppose

$$
D(b_0,b_1)=2,
$$

$$
D(b_1,b_2)=-1,
$$

$$
D(b_2,b_3)=4,
$$

and

$$
D(b_3,b_4)=3.
$$

Calculate the total debt of the sequence and determine $D(b_0,b_4)$.

### Exercise 3.5

Let $D_1$ and $D_2$ be debt functions. Prove that

$$
aD_1+bD_2
$$

is a debt function for any $a,b\in\mathbb R$.

### Exercise 3.6

Construct an antisymmetric function on a three-state space that is not additive.

### Exercise 3.7

Explain in a few lines why the antisymmetric part

$$
A=\frac12(d-d^T)
$$

should not automatically be identified with debt.

### Exercise 3.8

Let $\mathcal B$ contain $n$ states.

Use the defining axioms of debt to determine how many independent values are needed to specify a debt function.

Give your reasoning without using a potential representation.

### Exercise 3.9

Suppose a debt function assigns

$$
D(b_1,b_2)=4,
\qquad
D(b_2,b_3)=-2,
\qquad
D(b_3,b_4)=5.
$$

Determine every value that can be obtained from these transitions using additivity and antisymmetry.

### Exercise 3.10

Let

$$
D(b_i,b_j)=0
$$

for every pair of states connected by a transition.

What does additivity imply about any composed transition?

---

## 3.9 Chapter boundary

This chapter has intentionally stopped before introducing a potential representation.

The next chapter will investigate whether there exists a function

$$
\psi:\mathcal B\to\mathbb R
$$

such that

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

If such a representation exists, it would transform the transition-based description of debt into a state-based description.

That is a deeper structural question.

For now, we only know that debt is an additive and antisymmetric transition quantity.

The transition from **debt** to **potential** belongs to the next chapter.
