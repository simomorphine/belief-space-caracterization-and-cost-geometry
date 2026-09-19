# Chapter 7: The Complex Quasi-Metric

---

In the previous chapters, we developed the two fundamental components of the geometric structure.

The first is the **energy quasi-metric**

$$
d:\mathcal B\times\mathcal B\to [0,+\infty],
$$

which measures the cost of moving from one belief state to another.

The second is the **debt function**

$$
D:\mathcal B\times\mathcal B\to\mathbb R,
$$

which, under the additivity axiom, admits a potential representation

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

The cost and debt therefore describe two different aspects of a transition.

The cost is nonnegative and may be asymmetric:

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

The debt is signed and antisymmetric:

$$
D(b_i,b_j)=-D(b_j,b_i).
$$

This chapter combines these two quantities into a single object.

We define

$$
\boxed{
Q(b_i,b_j)=d(b_i,b_j)+iD(b_i,b_j)
}
$$

and call $Q$ the **complex quasi-metric**.

The purpose of this construction is not merely to introduce complex numbers. The complex representation allows us to keep the magnitude of a transition and its signed debt information in the same mathematical object.

We will study three associated quantities:

1. the real part, which records cost;
2. the imaginary part, which records debt;
3. the modulus and phase, which provide a geometric representation of the pair.

---

## 7.1 Motivation

Suppose an information-processing system moves from $b_i$ to $b_j$.

The transition may require energy:

$$
d(b_i,b_j).
$$

At the same time, the transition may change the system's epistemic state in a direction represented by

$$
D(b_i,b_j).
$$

These quantities have different mathematical roles.

The cost satisfies

$$
d(b_i,b_j)\geq 0,
$$

while debt can have either sign:

$$
D(b_i,b_j)\in\mathbb R.
$$

It is therefore natural to place them in orthogonal components of a complex number:

$$
Q(b_i,b_j)=d(b_i,b_j)+iD(b_i,b_j).
$$

The real axis represents cost.

The imaginary axis represents debt.

Thus a transition becomes a point in the complex plane.

---

## 7.2 Definition of the complex quasi-metric

**Definition 7.1 (Complex quasi-metric).**

Let $\mathcal B$ be a belief space equipped with an energy quasi-metric $d$ and a debt function $D$.

For every pair for which $d(b_i,b_j)<+\infty$, define

$$
Q(b_i,b_j)
:=
d(b_i,b_j)+iD(b_i,b_j).
$$

We call $Q$ the **complex quasi-metric**.

The decomposition

$$
Q=d+iD
$$

will be called the **cost-debt decomposition**.

The real and imaginary parts are therefore

$$
\operatorname{Re}Q(b_i,b_j)=d(b_i,b_j),
$$

and

$$
\operatorname{Im}Q(b_i,b_j)=D(b_i,b_j).
$$

---

## 7.3 The zero transition

Because the cost satisfies

$$
d(b,b)=0
$$

and debt satisfies

$$
D(b,b)=0,
$$

we immediately obtain:

**Proposition 7.2.**

For every $b\in\mathcal B$,

$$
Q(b,b)=0.
$$

### Proof

We have

$$
Q(b,b)
=
d(b,b)+iD(b,b).
$$

Since both terms vanish,

$$
Q(b,b)=0.
$$

$\square$

Thus the diagonal of the complex quasi-metric is zero.

---

## 7.4 The complex plane representation

For a transition $b_i\to b_j$, define

$$
x=d(b_i,b_j),
$$

and

$$
y=D(b_i,b_j).
$$

Then

$$
Q(b_i,b_j)=x+iy.
$$

The transition can therefore be represented by the point

$$
(x,y)
$$

in the complex plane.

The horizontal coordinate represents energy cost.

The vertical coordinate represents debt.

Since

$$
d(b_i,b_j)\geq0,
$$

all finite transitions lie in the closed right half-plane:

$$
\operatorname{Re}Q\geq0.
$$

The debt may be positive or negative, so transitions can lie above or below the real axis.

---

## 7.5 The modulus

The most immediate scalar quantity associated with a complex number is its modulus.

**Definition 7.3 (Complex transition magnitude).**

For a finite transition, define

$$
\rho(b_i,b_j)
:=
|Q(b_i,b_j)|.
$$

Since

$$
Q=d+iD,
$$

we have

$$
\boxed{
\rho(b_i,b_j)
=
\sqrt{
d(b_i,b_j)^2+D(b_i,b_j)^2
}.
}
$$

The quantity $\rho$ combines cost and debt into a single nonnegative magnitude.

It measures the Euclidean magnitude of the cost-debt pair.

---

## 7.6 Basic properties of the modulus

**Proposition 7.4.**

For every finite transition,

$$
\rho(b_i,b_j)\geq0.
$$

Moreover,

$$
\rho(b,b)=0.
$$

### Proof

Both terms inside the square root are nonnegative:

$$
d(b_i,b_j)^2\geq0,
$$

and

$$
D(b_i,b_j)^2\geq0.
$$

Therefore

$$
\rho(b_i,b_j)\geq0.
$$

For $b_i=b_j=b$,

$$
d(b,b)=D(b,b)=0,
$$

so

$$
\rho(b,b)=0.
$$

$\square$

---

## 7.7 Does the modulus define a metric?

It is tempting to immediately call $\rho$ a metric.

We must be more careful.

The original cost $d$ is allowed to be asymmetric. Therefore

$$
d(b_i,b_j)
\neq
d(b_j,b_i)
$$

in general.

Since

$$
D(b_j,b_i)=-D(b_i,b_j),
$$

we obtain

$$
\rho(b_j,b_i)
=
\sqrt{
d(b_j,b_i)^2+D(b_i,b_j)^2
}.
$$

Therefore, in general,

$$
\rho(b_i,b_j)
\neq
\rho(b_j,b_i).
$$

So the modulus is **not automatically a metric**.

It is more generally a quasi-metric.

---

## 7.8 Triangle inequality for the modulus

Although symmetry may fail, the modulus inherits a triangle inequality from the cost and debt structures.

Suppose

$$
d(b_i,b_k)
\leq
d(b_i,b_j)+d(b_j,b_k).
$$

Since debt is additive,

$$
D(b_i,b_k)
=
D(b_i,b_j)+D(b_j,b_k).
$$

Therefore

$$
\rho(b_i,b_k)
=
\sqrt{
d(b_i,b_k)^2+
D(b_i,b_k)^2
}.
$$

Using the triangle inequality for $d$,

$$
\rho(b_i,b_k)
\leq
\sqrt{
(d(b_i,b_j)+d(b_j,b_k))^2
+
(D(b_i,b_j)+D(b_j,b_k))^2
}.
$$

Now apply the Euclidean triangle inequality in $\mathbb R^2$:

$$
\sqrt{
(x_1+x_2)^2+(y_1+y_2)^2
}
\leq
\sqrt{x_1^2+y_1^2}
+
\sqrt{x_2^2+y_2^2}.
$$

Hence

$$
\boxed{
\rho(b_i,b_k)
\leq
\rho(b_i,b_j)+\rho(b_j,b_k).
}
$$

**Proposition 7.5.**

The modulus $\rho=|Q|$ satisfies the triangle inequality whenever $d$ satisfies the quasi-metric triangle inequality.

Thus $\rho$ is a **quasi-metric** under the corresponding separation assumptions.

---

## 7.9 When does the modulus become a metric?

The remaining issue is symmetry.

Suppose that $d$ is symmetric:

$$
d(b_i,b_j)=d(b_j,b_i).
$$

Since

$$
D(b_j,b_i)^2=D(b_i,b_j)^2,
$$

we obtain

$$
\rho(b_i,b_j)
=
\rho(b_j,b_i).
$$

Therefore:

**Proposition 7.6.**

If $d$ is symmetric, then $\rho$ is symmetric.

If, in addition,

$$
\rho(b_i,b_j)=0
\quad\Longrightarrow\quad
b_i=b_j,
$$

then $\rho$ is a metric.

Thus the modulus becomes an ordinary metric when the underlying cost loses its directional asymmetry and satisfies the appropriate separation property.

This distinction will be important later.

---

## 7.10 The phase

The modulus describes the magnitude of the transition.

The next quantity describes its direction in the cost-debt plane.

**Definition 7.7 (Phase).**

For

$$
Q(b_i,b_j)\neq0,
$$

define the phase

$$
\theta(b_i,b_j)
:=
\arg Q(b_i,b_j).
$$

Equivalently,

$$
\theta(b_i,b_j)
=
\operatorname{atan2}
\left(
D(b_i,b_j),
d(b_i,b_j)
\right).
$$

Because

$$
d(b_i,b_j)\geq0,
$$

the phase lies in the interval

$$
-\frac{\pi}{2}
\leq
\theta(b_i,b_j)
\leq
\frac{\pi}{2}.
$$

The phase is undefined when

$$
Q(b_i,b_j)=0.
$$

---

## 7.11 Geometric meaning of the phase

The complex number can be written in polar form:

$$
Q(b_i,b_j)
=
\rho(b_i,b_j)e^{i\theta(b_i,b_j)}.
$$

Therefore

$$
d(b_i,b_j)
=
\rho(b_i,b_j)\cos\theta(b_i,b_j),
$$

and

$$
D(b_i,b_j)
=
\rho(b_i,b_j)\sin\theta(b_i,b_j).
$$

Consequently,

$$
\boxed{
\frac{D(b_i,b_j)}
{\rho(b_i,b_j)}
=
\sin\theta(b_i,b_j)
}
$$

and, whenever $d(b_i,b_j)>0$,

$$
\boxed{
\frac{D(b_i,b_j)}
{d(b_i,b_j)}
=
\tan\theta(b_i,b_j).
}
$$

The debt-to-cost ratio introduced earlier is therefore related to the phase by

$$
r(b_i,b_j)=\tan\theta(b_i,b_j).
$$

The ratio and the phase encode the same directional information when $d>0$.

---

## 7.12 Interpreting special cases

Several limiting cases are particularly simple.

### Pure cost

If

$$
D(b_i,b_j)=0
$$

and

$$
d(b_i,b_j)>0,
$$

then

$$
Q(b_i,b_j)=d(b_i,b_j),
$$

so

$$
\theta(b_i,b_j)=0.
$$

The transition lies entirely on the real axis.

---

### Positive debt

If

$$
D(b_i,b_j)>0,
$$

then

$$
\theta(b_i,b_j)>0.
$$

The transition lies above the real axis.

---

### Negative debt

If

$$
D(b_i,b_j)<0,
$$

then

$$
\theta(b_i,b_j)<0.
$$

The transition lies below the real axis.

---

### Pure debt

If

$$
d(b_i,b_j)=0
$$

and

$$
D(b_i,b_j)\neq0,
$$

then

$$
Q(b_i,b_j)=iD(b_i,b_j).
$$

Consequently,

$$
\theta(b_i,b_j)
=
\begin{cases}
\frac{\pi}{2}, & D(b_i,b_j)>0,\\[4pt]
-\frac{\pi}{2}, & D(b_i,b_j)<0.
\end{cases}
$$

---

## 7.13 The reverse transition

The debt changes sign when a transition is reversed:

$$
D(b_j,b_i)=-D(b_i,b_j).
$$

However, the cost need not change sign:

$$
d(b_j,b_i)\neq d(b_i,b_j)
$$

in general.

Therefore

$$
Q(b_j,b_i)
=
d(b_j,b_i)-iD(b_i,b_j).
$$

Compare this with the complex conjugate:

$$
\overline{Q(b_i,b_j)}
=
d(b_i,b_j)-iD(b_i,b_j).
$$

Hence

$$
\boxed{
Q(b_j,b_i)=\overline{Q(b_i,b_j)}
}
$$

if and only if

$$
d(b_j,b_i)=d(b_i,b_j).
$$

Thus complex conjugation corresponds to reversing a transition **only when the cost is symmetric**.

This is an important structural distinction.

---

## 7.14 Reverse transitions and phase

If the cost is symmetric, then

$$
Q(b_j,b_i)=\overline{Q(b_i,b_j)}.
$$

Therefore

$$
\theta(b_j,b_i)
=
-\theta(b_i,b_j).
$$

When the cost is asymmetric, this relation generally fails.

The debt remains antisymmetric, but the cost component carries its own directional information.

Thus the phase contains information from **both**:

1. the signed debt;
2. the asymmetry of the cost geometry.

---

## 7.15 Cost-debt coordinates

Every transition can therefore be represented by the pair

$$
\left(
d(b_i,b_j),
D(b_i,b_j)
\right).
$$

The complex notation simply packages this pair:

$$
(d,D)
\longleftrightarrow
d+iD.
$$

The polar representation provides a second description:

$$
(d,D)
\longleftrightarrow
(\rho,\theta).
$$

Thus we have two coordinate systems:

### Cartesian coordinates

$$
(d,D).
$$

### Polar coordinates

$$
(\rho,\theta).
$$

The conversion is

$$
\rho=\sqrt{d^2+D^2},
$$

and

$$
\theta=\operatorname{atan2}(D,d).
$$

Conversely,

$$
d=\rho\cos\theta,
$$

and

$$
D=\rho\sin\theta.
$$

---

## 7.16 The phase as a relative quantity

The phase should not be interpreted as an independent physical quantity.

It is derived from the pair $(d,D)$.

In particular,

$$
\theta
=
\operatorname{atan2}(D,d).
$$

Therefore a change in either cost or debt changes the phase.

For example, increasing $D$ while keeping $d$ fixed moves the transition upward in the complex plane and increases the phase.

Increasing $d$ while keeping $D$ fixed moves the transition toward the real axis and decreases the absolute phase.

The phase therefore measures the relative orientation of cost and debt.

---

## 7.17 Scaling

Suppose both cost and debt are multiplied by the same positive constant $\lambda$:

$$
d'=\lambda d,
$$

and

$$
D'=\lambda D.
$$

Then

$$
Q'
=
\lambda d+i\lambda D
=
\lambda Q.
$$

Consequently,

$$
|Q'|
=
\lambda |Q|.
$$

But the phase remains unchanged:

$$
\arg Q'
=
\arg Q
$$

for $\lambda>0$.

Thus:

* the modulus measures scale;
* the phase measures relative orientation.

This separation will be useful when interpreting geometric structure.

---

## 7.18 The role of the potential

Recall that debt is exact:

$$
D(b_i,b_j)
=
\psi(b_j)-\psi(b_i).
$$

Therefore

$$
Q(b_i,b_j)
=
d(b_i,b_j)
+
i\bigl(\psi(b_j)-\psi(b_i)\bigr).
$$

The complex quasi-metric can therefore be written directly in terms of the cost and a potential:

$$
\boxed{
Q(b_i,b_j)
=
d(b_i,b_j)
+
i\bigl(\psi(b_j)-\psi(b_i)\bigr).
}
$$

This expression makes the structure transparent.

The real component describes the energetic geometry.

The imaginary component describes the potential difference.

---

## 7.19 Debt along a path

Consider a path

$$
\gamma=(b_0,b_1,\ldots,b_n).
$$

The total debt is

$$
\sum_{k=0}^{n-1}D(b_k,b_{k+1}).
$$

Since $D=\delta\psi$,

$$
\sum_{k=0}^{n-1}
D(b_k,b_{k+1})
=
\psi(b_n)-\psi(b_0).
$$

Thus the imaginary component of the path sum is completely determined by its endpoints.

The cost behaves differently.

In general,

$$
\sum_{k=0}^{n-1}d(b_k,b_{k+1})
$$

depends on the chosen path.

Therefore the two components of $Q$ have fundamentally different behavior along paths:

* debt telescopes;
* cost generally accumulates.

This asymmetry is one of the central features of the construction.

---

## 7.20 A two-state example

Let

$$
\mathcal B=\{b_1,b_2\}.
$$

Suppose

$$
d(b_1,b_2)=3,
$$

and

$$
D(b_1,b_2)=2.
$$

Then

$$
Q(b_1,b_2)=3+2i.
$$

Its modulus is

$$
|Q(b_1,b_2)|
=
\sqrt{3^2+2^2}
=
\sqrt{13}.
$$

Its phase is

$$
\theta(b_1,b_2)
=
\operatorname{atan2}(2,3).
$$

For the reverse transition, suppose

$$
d(b_2,b_1)=5.
$$

Then

$$
D(b_2,b_1)=-2,
$$

and therefore

$$
Q(b_2,b_1)=5-2i.
$$

Notice that

$$
Q(b_2,b_1)\neq\overline{Q(b_1,b_2)}
$$

because

$$
5\neq3.
$$

The asymmetry of the cost survives in the complex representation.

---

## 7.21 A symmetric-cost example

Suppose instead that

$$
d(b_1,b_2)=d(b_2,b_1)=3.
$$

Then

$$
Q(b_1,b_2)=3+2i,
$$

while

$$
Q(b_2,b_1)=3-2i.
$$

Therefore

$$
Q(b_2,b_1)=\overline{Q(b_1,b_2)}.
$$

Moreover,

$$
|Q(b_1,b_2)|
=
|Q(b_2,b_1)|
=
\sqrt{13},
$$

and

$$
\theta(b_2,b_1)
=
-\theta(b_1,b_2).
$$

This illustrates the additional symmetry obtained when the underlying cost becomes symmetric.

---

## 7.22 What the complex structure does not imply

The introduction of $Q$ does not automatically imply that cost and debt have the same mathematical properties.

They do not.

The cost may be:

* nonnegative;
* asymmetric;
* extended-valued;
* subject to a triangle inequality.

The debt is:

* signed;
* antisymmetric;
* additive;
* exact under our assumptions.

Packaging them into

$$
Q=d+iD
$$

does not erase these differences.

The complex number is a representation of the pair; it does not make the two components identical.

---

## 7.23 A useful distinction: structure versus representation

The complex quasi-metric should therefore be viewed at two levels.

### Structural level

We have two objects:

$$
d
\qquad\text{and}\qquad
D.
$$

They have different axioms and different interpretations.

### Representational level

We combine them into

$$
Q=d+iD.
$$

The complex number provides a convenient geometric representation of the pair.

This distinction prevents us from attributing properties of one component to the other.

---

## 7.24 The cost-debt plane

The construction suggests a simple geometric picture.

Each transition corresponds to a point

$$
(d,D)\in[0,+\infty)\times\mathbb R.
$$

The horizontal direction represents cost.

The vertical direction represents debt.

The distance from the origin is

$$
\rho=\sqrt{d^2+D^2},
$$

and the angle from the positive cost axis is

$$
\theta=\operatorname{atan2}(D,d).
$$

Thus the complex quasi-metric gives a **cost-debt geometry**.

The magnitude tells us how large the combined transition is.

The phase tells us how that magnitude is distributed between cost and debt.

---

## 7.25 Summary of the main relations

The central relations of this chapter are

$$
\boxed{
Q=d+iD
}
$$

with

$$
\boxed{
|Q|=\sqrt{d^2+D^2}
}
$$

and

$$
\boxed{
\arg Q=\operatorname{atan2}(D,d).
}
$$

Equivalently,

$$
\boxed{
d=|Q|\cos(\arg Q)
}
$$

and

$$
\boxed{
D=|Q|\sin(\arg Q).
}
$$

When $d>0$,

$$
\boxed{
\frac{D}{d}=\tan(\arg Q).
}
$$

These relations give three equivalent descriptions of a transition:

$$
(d,D),
$$

$$
(Q),
$$

and

$$
(|Q|,\arg Q).
$$

---

## 7.26 What we have established

The complex quasi-metric packages the energy cost and debt into one object:

$$
Q(b_i,b_j)=d(b_i,b_j)+iD(b_i,b_j).
$$

Its real and imaginary components retain their original meanings:

$$
\operatorname{Re}Q=d,
$$

and

$$
\operatorname{Im}Q=D.
$$

Its modulus satisfies a triangle inequality whenever the cost satisfies one, but it is not automatically symmetric.

Therefore the modulus is generally a **quasi-metric**, becoming a metric under additional symmetry and separation assumptions.

The phase provides a geometric measure of the relative contribution of debt to cost.

Finally, reversing a transition reverses the debt but does not necessarily reverse the cost:

$$
D(b_j,b_i)=-D(b_i,b_j),
$$

while generally

$$
d(b_j,b_i)\neq d(b_i,b_j).
$$

This distinction is essential to the geometry.

---

## 7.27 Exercises

**Exercise 7.1.** Let

$$
d(b_i,b_j)=4
$$

and

$$
D(b_i,b_j)=3.
$$

Compute $Q$, $|Q|$, and $\arg Q$.

---

**Exercise 7.2.** Suppose

$$
Q=5+12i.
$$

Compute its modulus and phase. Verify that

$$
d=|Q|\cos\theta
$$

and

$$
D=|Q|\sin\theta.
$$

---

**Exercise 7.3.** Prove that

$$
|Q(b_i,b_j)|
\leq
|Q(b_i,b_k)|+|Q(b_k,b_j)|
$$

using the triangle inequality for $d$ and the additivity of $D$.

---

**Exercise 7.4.** Construct an example where

$$
|Q(b_i,b_j)|
\neq
|Q(b_j,b_i)|.
$$

Explain why this does not contradict the antisymmetry of debt.

---

**Exercise 7.5.** Prove that if $d$ is symmetric, then

$$
Q(b_j,b_i)=\overline{Q(b_i,b_j)}.
$$

---

**Exercise 7.6.** Suppose that

$$
d(b_i,b_j)=d(b_j,b_i)
$$

for every pair of states. Prove that

$$
\arg Q(b_j,b_i)
=
-\arg Q(b_i,b_j)
$$

whenever $Q(b_i,b_j)\neq0$.

---

**Exercise 7.7.** Give an example where $d(b_i,b_j)>0$ but $D(b_i,b_j)=0$. What are the modulus and phase?

---

**Exercise 7.8.** Give an example where $d(b_i,b_j)=0$ but $D(b_i,b_j)\neq0$. What is the phase?

---

**Exercise 7.9.** Let

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i).
$$

Show directly that the debt accumulated along any path depends only on its endpoints.

---

**Exercise 7.10.** Explain why the modulus of the complex quasi-metric is not necessarily a metric when the underlying cost is asymmetric.

---

## 7.28 Final perspective

The complex quasi-metric does not introduce a new independent quantity.

It packages two quantities that were already present:

$$
\boxed{
\text{cost}
\quad+\quad
i\,\text{debt}.
}
$$

The resulting complex representation gives us a geometric language in which magnitude and direction can be studied simultaneously.

At this stage, however, we should resist interpreting the phase too strongly.

We have established the mathematics of the representation.

Its deeper interpretation remains an open question.

That distinction will become important as the theory develops.

---

**End of Chapter 7.**
