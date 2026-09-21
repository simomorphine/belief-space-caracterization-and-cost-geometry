# Chapter 7: The Complex Quasi-Metric

---

In the previous chapters we developed the two fundamental components of the geometric structure.

The first is the **energy quasi-metric**

$$d : \mathcal{B} \times \mathcal{B} \to [0, +\infty],$$

which measures the cost of moving from one belief state to another.

The second is the **debt function**

$$D : \mathcal{B} \times \mathcal{B} \to \mathbb{R},$$

which, under the additivity axiom, admits a potential representation

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

Cost and debt describe two different aspects of a transition.

The cost is nonnegative and may be asymmetric:

$$d(b_i, b_j) \neq d(b_j, b_i).$$

The debt is signed and antisymmetric:

$$D(b_i, b_j) = -D(b_j, b_i).$$

This chapter combines the two quantities into a single object:

$$\boxed{Q(b_i, b_j) = d(b_i, b_j) + iD(b_i, b_j)}$$

which we call the **complex quasi-metric**.

The purpose of this construction is not merely to introduce complex numbers. The complex representation keeps the magnitude of a transition and its signed debt in one mathematical object.

We study three associated quantities:

1. the real part, which records cost;
2. the imaginary part, which records debt;
3. the modulus and phase, which give a geometric representation of the pair.

**Convention 7.0 (Finiteness).** Throughout this chapter, we assume $d(b_i, b_j) < +\infty$ unless otherwise stated. When $d(b_i, b_j) = +\infty$, we define $Q(b_i, b_j) := +\infty$ (an extended value) and exclude such pairs from the domain of the modulus and phase. The case $+\infty$ can be handled by working in the extended complex plane or by excluding such pairs from the domain of $Q$. We adopt the latter convention: $Q$ is defined on the set of pairs with finite cost.

---

## 7.1 Motivation

Suppose an information-processing system moves from $b_i$ to $b_j$.

The transition may require energy:

$$d(b_i, b_j).$$

At the same time, it may change the system's epistemic state in a direction represented by

$$D(b_i, b_j).$$

These quantities have different mathematical roles:

$$d(b_i, b_j) \geq 0, \qquad D(b_i, b_j) \in \mathbb{R}.$$

It is therefore natural to place them in orthogonal components of a complex number. The real axis represents cost; the imaginary axis represents debt. A transition becomes a point in the complex plane.

---

## 7.2 Definition of the complex quasi-metric

**Definition 7.1 (Complex quasi-metric).** Let $\mathcal{B}$ be a belief space equipped with an energy quasi-metric $d$ and a debt function $D = \delta\psi$. For every pair with $d(b_i, b_j) < +\infty$, define

$$Q(b_i, b_j) := d(b_i, b_j) + iD(b_i, b_j).$$

We call $Q$ the **complex quasi-metric**, and the decomposition $Q = d + iD$ the **cost-debt decomposition**.

The real and imaginary parts are

$$\mathrm{Re} Q(b_i, b_j) = d(b_i, b_j), \qquad \mathrm{Im} Q(b_i, b_j) = D(b_i, b_j).$$

**Convention 7.2.** When the context is clear we write $Q_{ij}$, $d_{ij}$ and $D_{ij}$ for $Q(b_i, b_j)$, $d(b_i, b_j)$ and $D(b_i, b_j)$.

**Remark 7.3.** The letter $Q$ is simply a name, chosen for "quasi-metric." No further meaning should be read into it.

---

## 7.3 Basic properties

**Proposition 7.4 (Basic properties).** For all $b, b_i, b_j \in \mathcal{B}$ (with $d(b_i, b_j) < +\infty$):

1. **Identity.** $Q(b, b) = 0$.
2. **Nonnegative real part.** $\mathrm{Re} Q(b_i, b_j) \geq 0$.
3. **Antisymmetric imaginary part.** $\mathrm{Im} Q(b_i, b_j) = -\mathrm{Im} Q(b_j, b_i)$.
4. **Exact imaginary part.** $\mathrm{Im} Q = \delta\psi$ for some $\psi : \mathcal{B} \to \mathbb{R}$.

*Proof.*

1. $d(b, b) = 0$ and $D(b, b) = 0$, so $Q(b, b) = 0$.
2. This is nonnegativity of $d$.
3. This is antisymmetry of $D$.
4. This is the potential representation of the debt. $\square$

**Remark 7.5.** Property 4 implies property 3, since $\psi(b_j) - \psi(b_i)$ is automatically antisymmetric in $(b_i, b_j)$. They are listed separately for convenience.

Thus the diagonal of $Q$ is zero, and all finite transitions lie in the closed right half-plane $\mathrm{Re} Q \geq 0$.

---

## 7.4 The complex plane representation

For a transition $b_i \to b_j$ set

$$x = d(b_i, b_j), \qquad y = D(b_i, b_j),$$

so that $Q(b_i, b_j) = x + iy$.

The transition is represented by the point $(x, y)$: the horizontal coordinate is energy cost, the vertical coordinate is debt. Since $x \geq 0$, all finite transitions lie in the closed right half-plane. Debt may be positive or negative, so transitions can lie above or below the real axis.

The pair $(d, D)$ can also be written in polar coordinates $(\rho, \theta)$, where

$$\rho = \sqrt{d^2 + D^2}, \qquad \theta = \mathrm{atan2}(D, d).$$

Conversely,

$$d = \rho \cos\theta, \qquad D = \rho \sin\theta.$$

Geometrically, each transition is a point $(d, D) \in [0, +\infty) \times \mathbb{R}$. The distance from the origin is $\rho$; the angle from the positive cost axis is $\theta$. The complex quasi-metric thus gives a **cost-debt geometry**: the magnitude tells us how large the combined transition is, and the phase tells us how that magnitude is distributed between cost and debt.

---

## 7.5 The modulus

**Definition 7.6 (Complex transition magnitude).** For a finite transition define

$$\rho(b_i, b_j) := |Q(b_i, b_j)|.$$

Explicitly,

$$\boxed{\rho(b_i, b_j) = \sqrt{d(b_i, b_j)^2 + D(b_i, b_j)^2}.}$$

The quantity $\rho$ combines cost and debt into a single nonnegative magnitude: the Euclidean size of the cost-debt pair.

**Proposition 7.7.** For every finite transition, $\rho(b_i, b_j) \geq 0$ and $\rho(b, b) = 0$. Moreover,

$$\rho(b_i, b_j) = 0 \iff d(b_i, b_j) = 0 \text{ and } D(b_i, b_j) = 0.$$

*Proof.* Both $d^2$ and $D^2$ are nonnegative, so their sum has a nonnegative square root, which vanishes exactly when both terms vanish. On the diagonal, $d(b, b) = D(b, b) = 0$.

When $d(b_i, b_j) = +\infty$, we define $\rho(b_i, b_j) = +\infty$; since $+\infty \neq 0$, the equivalence still holds. $\square$

---

## 7.6 Is the modulus a metric?

It is tempting to call $\rho$ a metric immediately. We must be more careful.

The cost $d$ is allowed to be asymmetric. Since $D(b_j, b_i) = -D(b_i, b_j)$,

$$\rho(b_j, b_i) = \sqrt{d(b_j, b_i)^2 + D(b_i, b_j)^2}.$$

Therefore, in general,

$$\rho(b_i, b_j) \neq \rho(b_j, b_i).$$

The modulus is **not automatically a metric**. It is, more generally, a quasi-metric.

---

## 7.7 Triangle inequality for the modulus

Although symmetry may fail, the modulus inherits a triangle inequality from the cost and debt structures.

**Theorem 7.8 (Triangle inequality for the modulus).** If $d$ satisfies the quasi-metric triangle inequality, then for all $b_i, b_j, b_k$ with finite costs,

$$\boxed{\rho(b_i, b_k) \leq \rho(b_i, b_j) + \rho(b_j, b_k).}$$

*Proof.* By the triangle inequality for $d$,

$$d(b_i, b_k) \leq d(b_i, b_j) + d(b_j, b_k),$$

and by additivity of debt,

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

Since $0 \leq d(b_i, b_k)$, squaring preserves the inequality, so

$$\rho(b_i, b_k) \leq \sqrt{\bigl(d(b_i, b_j) + d(b_j, b_k)\bigr)^2 + \bigl(D(b_i, b_j) + D(b_j, b_k)\bigr)^2}.$$

Now apply the Euclidean triangle (Minkowski) inequality in $\mathbb{R}^2$,

$$\sqrt{(x_1 + x_2)^2 + (y_1 + y_2)^2} \leq \sqrt{x_1^2 + y_1^2} + \sqrt{x_2^2 + y_2^2},$$

with $x_1 = d(b_i, b_j)$, $y_1 = D(b_i, b_j)$, $x_2 = d(b_j, b_k)$, $y_2 = D(b_j, b_k)$. This gives

$$\rho(b_i, b_k) \leq \rho(b_i, b_j) + \rho(b_j, b_k). \quad \square$$

**Remark 7.9.** The proof uses exactly two facts: the triangle inequality for $d$ and the additivity of $D$, combined with the Euclidean triangle inequality. No symmetry is used. Hence $\rho$ satisfies the triangle inequality even when $d$ is asymmetric.

---

## 7.8 When does the modulus become a metric?

The remaining issue is symmetry.

**Proposition 7.10.** If $d$ is symmetric, then $\rho$ is symmetric. If, in addition, $\rho(b_i, b_j) = 0 \Rightarrow b_i = b_j$, then $\rho$ is a metric.

*Proof.* If $d(b_i, b_j) = d(b_j, b_i)$, then since $D(b_j, b_i)^2 = D(b_i, b_j)^2$,

$$\rho(b_i, b_j)^2 = d(b_i, b_j)^2 + D(b_i, b_j)^2 = d(b_j, b_i)^2 + D(b_j, b_i)^2 = \rho(b_j, b_i)^2.$$

Non-negativity, the identity $\rho(b, b) = 0$, the triangle inequality (Theorem 7.8) and the assumed separation property then give the axioms of a metric. $\square$

**Corollary 7.11.**

- If $d$ is symmetric and satisfies the triangle inequality, then $\rho$ is a **pseudometric**, and a **metric** if it separates points.
- If $d$ is asymmetric, then $\rho$ is in general a **quasi-metric**, not a metric.

**Remark 7.12.** If $d$ separates points (that is, $d(b_i, b_j) = 0 \Rightarrow b_i = b_j$), then so does $\rho$, because $\rho = 0$ forces $d = 0$. The modulus can only have *more* separating power than $d$, never less.

**Remark 7.13.** The modulus does not "repair" the asymmetry of $d$. The debt contributes a symmetric term $D^2$, but the asymmetry of $d$ passes through unchanged. A metric modulus requires a symmetric cost.

---

## 7.9 The phase

The modulus describes the magnitude of a transition. The next quantity describes its direction in the cost-debt plane.

**Definition 7.14 (Phase).** For $Q(b_i, b_j) \neq 0$ define the phase

$$\theta(b_i, b_j) := \arg Q(b_i, b_j) = \mathrm{atan2}\bigl(D(b_i, b_j),\, d(b_i, b_j)\bigr).$$

Because $d(b_i, b_j) \geq 0$,

$$-\frac{\pi}{2} \leq \theta(b_i, b_j) \leq \frac{\pi}{2},$$

with $\theta = \pm\pi/2$ exactly when $d = 0$ and $D \neq 0$. The phase is undefined when $Q(b_i, b_j) = 0$.

**Remark 7.15.** When $d > 0$ the phase lies in the *open* interval $(-\pi/2, \pi/2)$ and equals $\arctan(D/d)$.

**Remark 7.16 (The case $d = 0$, $D \neq 0$).** When $d = 0$ and $D \neq 0$, the transition has zero cost but nonzero debt. In the complex plane, $Q = iD$ lies on the imaginary axis, and the phase is $\pm\pi/2$. This case is unusual but not impossible. It occurs when a transition is free in terms of cost but changes the potential. For example, a reversible computation might have zero cost in one direction but nonzero debt; or a gauge transformation might be costless but shift the potential. The phase $\pm\pi/2$ signals that the transition is purely debt-driven.

---

## 7.10 Geometric meaning of the phase

In polar form,

$$Q(b_i, b_j) = \rho(b_i, b_j) \, e^{i\theta(b_i, b_j)},$$

so

$$d = \rho \cos\theta, \qquad D = \rho \sin\theta.$$

Consequently,

$$\boxed{\frac{D}{\rho} = \sin\theta}$$

and, whenever $d > 0$,

$$\boxed{\frac{D}{d} = \tan\theta.}$$

The debt-to-cost ratio $r(b_i, b_j) = D/d$ is therefore related to the phase by

$$r(b_i, b_j) = \tan\theta(b_i, b_j).$$

When $d > 0$, the ratio and the phase encode the same directional information.

---

## 7.11 Interpreting special cases

| Phase $\theta$ | Meaning | Position of $Q$ |
|---|---|---|
| $0$ | Pure cost ($D = 0$, $d > 0$) | Positive real axis |
| $0 < \theta < \pi/4$ | Cost dominates positive debt | Above axis, below diagonal |
| $\pi/4$ | $d = D > 0$ | Diagonal |
| $\pi/4 < \theta < \pi/2$ | Positive debt dominates | Above diagonal |
| $\pi/2$ | Pure positive debt ($d = 0$, $D > 0$) | Positive imaginary axis |
| $-\pi/4$ | $d = -D > 0$ | Anti-diagonal |
| $-\pi/2$ | Pure negative debt ($d = 0$, $D < 0$) | Negative imaginary axis |

In particular:

- **Pure cost.** If $D = 0$ and $d > 0$, then $Q = d$ and $\theta = 0$.
- **Positive debt.** If $D > 0$ then $\theta > 0$.
- **Negative debt.** If $D < 0$ then $\theta < 0$.
- **Pure debt.** If $d = 0$ and $D \neq 0$, then $Q = iD$ and

$$\theta = \begin{cases} \dfrac{\pi}{2}, & D > 0, \\[6pt] -\dfrac{\pi}{2}, & D < 0. \end{cases}$$

---

## 7.12 The reverse transition

The debt changes sign when a transition is reversed:

$$D(b_j, b_i) = -D(b_i, b_j).$$

The cost need not:

$$d(b_j, b_i) \neq d(b_i, b_j) \quad \text{in general.}$$

Therefore

$$Q(b_j, b_i) = d(b_j, b_i) - iD(b_i, b_j),$$

whereas the complex conjugate is

$$\overline{Q(b_i, b_j)} = d(b_i, b_j) - iD(b_i, b_j).$$

Hence

$$\boxed{Q(b_j, b_i) = \overline{Q(b_i, b_j)} \iff d(b_j, b_i) = d(b_i, b_j).}$$

Complex conjugation corresponds to reversing a transition **only when the cost is symmetric**. This is an important structural distinction.

**Proposition 7.17 (Phase of the reverse transition).** If $d$ is symmetric, then

$$\theta(b_j, b_i) = -\theta(b_i, b_j)$$

whenever $Q(b_i, b_j) \neq 0$.

*Proof.* If $d$ is symmetric, $Q(b_j, b_i) = \overline{Q(b_i, b_j)}$, and conjugation negates the argument. $\square$

When the cost is asymmetric this relation generally fails. The debt remains antisymmetric, but the cost carries its own directional information. The phase therefore contains information from **both**:

1. the signed debt;
2. the asymmetry of the cost geometry.

---

## 7.13 Cost-debt coordinates and scaling

Every transition is described by the pair $(d, D)$, and the complex notation packages it:

$$(d, D) \longleftrightarrow d + iD.$$

The polar representation gives a second description $(\rho, \theta)$. The two coordinate systems are related by

$$\rho = \sqrt{d^2 + D^2}, \qquad \theta = \mathrm{atan2}(D, d),$$

and conversely

$$d = \rho \cos\theta, \qquad D = \rho \sin\theta.$$

Suppose cost and debt are both multiplied by the same constant $\lambda > 0$:

$$d' = \lambda d, \qquad D' = \lambda D.$$

Then $Q' = \lambda Q$, so

$$|Q'| = \lambda |Q|, \qquad \arg Q' = \arg Q.$$

Thus:

- the modulus measures **scale**;
- the phase measures **relative orientation**.

Conversely, the phase is a relative quantity, derived from $(d, D)$. Increasing $D$ with $d$ fixed moves the transition upward and increases $\theta$; increasing $d$ with $D$ fixed moves it toward the real axis and decreases $|\theta|$.

---

## 7.14 The role of the potential and the basepoint

Since debt is exact,

$$Q(b_i, b_j) = d(b_i, b_j) + i\bigl(\psi(b_j) - \psi(b_i)\bigr).$$

This makes the structure transparent: the real component describes the energetic geometry, and the imaginary component describes a potential difference.

**Proposition 7.18 (Basepoint form).** Let $s_0 \in \mathcal{B}$ be a basepoint and define $\psi_{s_0}(b) := D(s_0, b)$. Then

$$Q(b_i, b_j) = d(b_i, b_j) + i\bigl(\psi_{s_0}(b_j) - \psi_{s_0}(b_i)\bigr).$$

*Proof.* By additivity and antisymmetry of $D$,

$$D(b_i, b_j) = D(b_i, s_0) + D(s_0, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i). \quad \square$$

**Corollary 7.19 (Basepoint independence).** $Q$ does not depend on the choice of basepoint $s_0$.

*Proof.* Two basepoints give potentials differing by a constant, and constants cancel in differences. $\square$

**Remark 7.20.** The basepoint is a computational device: it lets us compute $Q$ without reference to paths. The object $Q$, and therefore $\rho$ and $\theta$, is basepoint-independent.

**Remark 7.21 (Gauge transformations vs. potential shifts).** The term *gauge transformation* is reserved for the transformation

$$\psi \mapsto \psi + c, \qquad c \in \mathbb{R} \text{ constant},$$

which leaves $D$, $Q$, $\rho$, and $\theta$ invariant. This is the genuine gauge freedom of the theory.

A non-constant shift $\psi \mapsto \psi + \chi$ is not a gauge transformation. It produces a **different** debt function

$$D'(b_i, b_j) = D(b_i, b_j) + \bigl(\chi(b_j) - \chi(b_i)\bigr),$$

and therefore a different complex quasi-metric

$$Q'(b_i, b_j) = Q(b_i, b_j) + i\bigl(\chi(b_j) - \chi(b_i)\bigr).$$

This is a translation of $Q$ in the imaginary direction that depends on the pair $(b_i, b_j)$. The real part $d$ is unchanged, but the modulus and phase are **not** invariant under such a shift. Only $d$ and the constant-shift class of $\psi$ are canonical. The gauge structure is developed systematically in Chapter 8.

---

## 7.15 Debt along a path

Consider a path $\gamma = (b_0, b_1, \ldots, b_n)$. The total debt is

$$\sum_{k=0}^{n-1} D(b_k, b_{k+1}) = \psi(b_n) - \psi(b_0),$$

so the imaginary component of the path sum depends only on the endpoints. The cost behaves differently:

$$\sum_{k=0}^{n-1} d(b_k, b_{k+1})$$

in general depends on the chosen path.

Therefore the two components of $Q$ behave fundamentally differently along paths:

- debt **telescopes**;
- cost generally **accumulates**.

This asymmetry is one of the central features of the construction.

---

## 7.16 Algebra of complex quasi-metrics

We now consider algebraic operations.

**Definition 7.22 (Addition).** For $Q_1 = d_1 + iD_1$ and $Q_2 = d_2 + iD_2$ defined on the same domain,

$$Q_1 + Q_2 := (d_1 + d_2) + i(D_1 + D_2).$$

**Proposition 7.23.** The sum of two complex quasi-metrics on the same domain is a complex quasi-metric.

*Proof.* Since both $Q_1$ and $Q_2$ are defined on $\mathcal{B} \times \mathcal{B}$, the sum is well-defined. The real part $d_1 + d_2$ is a sum of quasi-metrics, hence a quasi-metric. The imaginary part $D_1 + D_2$ is additive and antisymmetric, and $D_1 + D_2 = \delta(\psi_1 + \psi_2)$ is exact. $\square$

**Definition 7.24 (Scalar multiplication).** For $\alpha \geq 0$,

$$\alpha Q := (\alpha d) + i(\alpha D).$$

**Proposition 7.25.** If $\alpha \geq 0$, then $\alpha Q$ is a complex quasi-metric.

*Proof.* $\alpha d$ is a quasi-metric for $\alpha \geq 0$, and $\alpha D = \delta(\alpha\psi)$ is exact. $\square$

**Remark 7.26.** For $\alpha < 0$ the real part $\alpha d$ becomes negative, so scalar multiplication is only defined for $\alpha \geq 0$.

**Definition 7.27 (Conjugation).** $\overline{Q} := d - iD$.

**Proposition 7.28.** The conjugate satisfies

$$\mathrm{Re}\overline{Q} = \mathrm{Re}Q, \quad \mathrm{Im}\overline{Q} = -\mathrm{Im}Q, \quad |\overline{Q}| = |Q|, \quad \arg\overline{Q} = -\arg Q.$$

*Proof.* Immediate. $\square$

**Remark 7.29.** Conjugation reverses the sign of the debt and leaves the cost unchanged. It is the complex quasi-metric of the pair $(d, -D)$, with potential $-\psi$. As Section 7.12 shows, it coincides with *reversing the transition* only when $d$ is symmetric.

**Definition 7.30 (Product).**

$$Q_1 Q_2 := (d_1 d_2 - D_1 D_2) + i(d_1 D_2 + d_2 D_1).$$

**Proposition 7.31.** The product of two complex quasi-metrics is in general **not** a complex quasi-metric.

*Proof.* The real part $d_1 d_2 - D_1 D_2$ may be negative, violating nonnegativity.

For example, take $Q_1 = Q_2 = 1 + 2i$. Then

$$Q_1 Q_2 = (1 \cdot 1 - 2 \cdot 2) + i(1 \cdot 2 + 2 \cdot 1) = -3 + 4i,$$

whose real part is negative. $\square$

**Remark 7.32.** The complex quasi-metric is closed under addition and nonnegative scaling, but not under multiplication. The theory is therefore developed in the *additive* regime.

---

## 7.17 Complex quasi-metrics as 1-cochains

A **complex 1-cochain** on $\mathcal{B}$ is a function $Q : \mathcal{B} \times \mathcal{B} \to \mathbb{C}$.

**Proposition 7.33.** The complex quasi-metric is a complex 1-cochain satisfying

1. $Q(b, b) = 0$;
2. $\mathrm{Re}Q \geq 0$;
3. $\mathrm{Im}Q$ is a real 1-coboundary, $\mathrm{Im}Q = \delta\psi$.

*Proof.* Immediate from the definitions. $\square$

**Remark 7.34.** Condition 3 distinguishes $Q$ from a general complex 1-cochain. It says that the imaginary part is *integrable*: it is the coboundary of a 0-cochain.

---

## 7.18 A two-state example

Let $\mathcal{B} = \{b_1, b_2\}$ with

$$d(b_1, b_2) = 3, \qquad D(b_1, b_2) = 2.$$

Then

$$Q(b_1, b_2) = 3 + 2i, \qquad |Q(b_1, b_2)| = \sqrt{13}, \qquad \theta(b_1, b_2) = \mathrm{atan2}(2, 3).$$

For the reverse transition suppose $d(b_2, b_1) = 5$. Then $D(b_2, b_1) = -2$, so

$$Q(b_2, b_1) = 5 - 2i, \qquad |Q(b_2, b_1)| = \sqrt{29}.$$

Notice that $Q(b_2, b_1) \neq \overline{Q(b_1, b_2)}$ because $5 \neq 3$, and $\rho(b_2, b_1) \neq \rho(b_1, b_2)$. The asymmetry of the cost survives in the complex representation.

---

## 7.19 A symmetric-cost example

Suppose instead that

$$d(b_1, b_2) = d(b_2, b_1) = 3.$$

Then

$$Q(b_1, b_2) = 3 + 2i, \qquad Q(b_2, b_1) = 3 - 2i = \overline{Q(b_1, b_2)}.$$

Moreover

$$|Q(b_1, b_2)| = |Q(b_2, b_1)| = \sqrt{13}, \qquad \theta(b_2, b_1) = -\theta(b_1, b_2).$$

This illustrates the additional symmetry obtained when the underlying cost is symmetric.

---

## 7.20 Structure versus representation

Introducing $Q$ does not mean that cost and debt have the same mathematical properties. They do not.

The cost may be

- nonnegative,
- asymmetric,
- extended-valued,
- subject to a triangle inequality.

The debt is

- signed,
- antisymmetric,
- additive,
- exact under our assumptions.

The complex quasi-metric should therefore be viewed at two levels:

| Level | Objects | Role |
|---|---|---|
| **Structural** | $d$ and $D$ | Different axioms and interpretations |
| **Representational** | $Q = d + iD$ | Convenient geometric packaging of the pair |

This distinction prevents us from attributing properties of one component to the other.

---

## 7.21 Summary of the main relations

The central relations of this chapter are

$$\boxed{Q = d + iD}, \qquad \boxed{|Q| = \sqrt{d^2 + D^2}}, \qquad \boxed{\arg Q = \mathrm{atan2}(D, d)},$$

equivalently

$$\boxed{d = |Q|\cos(\arg Q)}, \qquad \boxed{D = |Q|\sin(\arg Q)},$$

and, when $d > 0$,

$$\boxed{\frac{D}{d} = \tan(\arg Q).}$$

These give three equivalent descriptions of a transition: $(d, D)$, $Q$, and $(|Q|, \arg Q)$.

---

## 7.22 What we have established

- **Definition.** $Q(b_i, b_j) = d(b_i, b_j) + iD(b_i, b_j)$, with $\mathrm{Re}Q = d$ and $\mathrm{Im}Q = D = \delta\psi$.
- **Basic properties.** $Q(b, b) = 0$, $\mathrm{Re}Q \geq 0$, and $\mathrm{Im}Q$ is antisymmetric and exact.
- **Modulus.** $|Q|$ satisfies the triangle inequality whenever $d$ does (Theorem 7.8). It is symmetric, and a pseudometric or metric, only when $d$ is symmetric (and separating); otherwise it is a quasi-metric.
- **Phase.** $\theta = \arg Q \in [-\pi/2, \pi/2]$ measures the relative orientation of cost and debt, with $D/d = \tan\theta$.
- **Reversal.** Reversing a transition negates the debt but not necessarily the cost, so $Q(b_j, b_i) = \overline{Q(b_i, b_j)}$ iff $d$ is symmetric.
- **Basepoint independence.** $Q$, $\rho$ and $\theta$ do not depend on the basepoint.
- **Path behavior.** Debt telescopes along paths; cost accumulates.
- **Algebra.** $Q$ is closed under addition and nonnegative scaling, but not multiplication.

---

## 7.23 Exercises

**Exercise 7.1.** Let $d(b_i, b_j) = 4$ and $D(b_i, b_j) = 3$. Compute $Q$, $|Q|$, and $\arg Q$.

**Exercise 7.2.** Suppose $Q = 5 + 12i$. Compute its modulus and phase. Verify that $d = |Q|\cos\theta$ and $D = |Q|\sin\theta$.

**Exercise 7.3.** Prove that

$$|Q(b_i, b_j)| \leq |Q(b_i, b_k)| + |Q(b_k, b_j)|$$

using the triangle inequality for $d$ and the additivity of $D$.

**Exercise 7.4.** Construct an example where $|Q(b_i, b_j)| \neq |Q(b_j, b_i)|$. Explain why this does not contradict the antisymmetry of debt.

**Exercise 7.5.** Prove that if $d$ is symmetric, then $Q(b_j, b_i) = \overline{Q(b_i, b_j)}$.

**Exercise 7.6.** Suppose $d(b_i, b_j) = d(b_j, b_i)$ for every pair of states. Prove that

$$\arg Q(b_j, b_i) = -\arg Q(b_i, b_j)$$

whenever $Q(b_i, b_j) \neq 0$.

**Exercise 7.7.** Give an example where $d(b_i, b_j) > 0$ but $D(b_i, b_j) = 0$. What are the modulus and phase?

**Exercise 7.8.** Give an example where $d(b_i, b_j) = 0$ but $D(b_i, b_j) \neq 0$. What is the phase? Explain in one sentence why this case is unusual.

**Exercise 7.9.** Let $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Show directly that the debt accumulated along any path depends only on its endpoints.

**Exercise 7.10.** Explain why the modulus of the complex quasi-metric is not necessarily a metric when the underlying cost is asymmetric.

**Exercise 7.11.** Let

$$d = \begin{pmatrix} 0 & 2 & 5 \\ 1 & 0 & 3 \\ 4 & 1 & 0 \end{pmatrix}, \qquad D = \begin{pmatrix} 0 & 1 & 3 \\ -1 & 0 & 2 \\ -3 & -2 & 0 \end{pmatrix}.$$

Compute $Q$, $|Q|$ and $\theta$ for all pairs. Verify that $D$ satisfies additivity for all triples $(b_i, b_j, b_k)$ and is therefore exact. Verify the triangle inequality for $|Q|$ on all triples.

**Exercise 7.12.** Show that $Q$ is independent of the choice of basepoint $s_0$.

**Exercise 7.13.** Show that the phase $\theta$ is invariant under $\psi \mapsto \psi + c$ for constant $c$, and give an example of a non-constant $\chi$ for which $\theta$ changes under $\psi \mapsto \psi + \chi$.

**Exercise 7.14.** Give a counterexample showing that the product $Q_1 Q_2$ of two complex quasi-metrics need not be a complex quasi-metric.

**Exercise 7.15.** Let $Q_1 = 1 + 2i$ and $Q_2 = 1 + 2i$. Compute $Q_1 Q_2$ and verify that its real part is negative. Explain why this shows that the product of two complex quasi-metrics is not necessarily a complex quasi-metric.

---

## 7.24 Final perspective

The complex quasi-metric does not introduce a new independent quantity. It packages two quantities that were already present:

$$\boxed{\text{cost} \quad + \quad i\,\text{debt}.}$$

The resulting complex representation gives a geometric language in which magnitude and direction can be studied simultaneously.

At this stage, however, we should resist interpreting the phase too strongly. We have established the mathematics of the representation; its deeper interpretation remains an open question. That distinction will become important as the theory develops.
