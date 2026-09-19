# Chapter 7: The Complex Quasi-Metric

---

We now arrive at the central object of the book. In Chapters 3–5, we developed the debt function $D$ and proved that it is exact: $D = \delta\psi$ for some potential $\psi$. In Chapter 2, we established the energy quasi-metric $d$. Now we combine them into a single complex object.

The **complex quasi-metric** is defined by

$$Q(b_i, b_j) := d(b_i, b_j) + i \cdot D(b_i, b_j).$$

Its real part is the cost; its imaginary part is the debt. Its modulus is a metric; its argument is a phase. The complex structure is not decoration—it is the canonical way to encode a two-part structure, and it will turn out to be a $\mathbb{Z}/2$-grading.

This chapter develops the basic theory of $Q$: its definition, its algebraic properties, its modulus, its argument, and its geometric interpretation.

---

## 6.1 Definition and basic properties

**Definition 6.1 (Complex quasi-metric).** Let $\mathcal{B}$ be a belief space with energy quasi-metric $d$ and debt function $D = \delta\psi$. The *complex quasi-metric* is the function $Q : \mathcal{B} \times \mathcal{B} \to \mathbb{C}$ defined by

$$Q(b_i, b_j) := d(b_i, b_j) + i \cdot D(b_i, b_j),$$

where $i^2 = -1$.

**Remark 6.2.** The notation $Q$ is chosen for "quasi-metric," but also for "quantity," "quotient," and "charge." The reader should not read too much into the letter; it is simply a name.

**Proposition 6.3 (Basic properties).** The complex quasi-metric satisfies:

- **(i) Identity.** $Q(b, b) = 0$ for all $b \in \mathcal{B}$.
- **(ii) Non-negative real part.** $\mathrm{Re}\, Q(b_i, b_j) = d(b_i, b_j) \ge 0$.
- **(iii) Antisymmetric imaginary part.** $\mathrm{Im}\, Q(b_i, b_j) = -\mathrm{Im}\, Q(b_j, b_i)$.
- **(iv) Exact imaginary part.** $\mathrm{Im}\, Q = \delta\psi$ for some $\psi : \mathcal{B} \to \mathbb{R}$.

*Proof.* (i) $d(b, b) = 0$ and $D(b, b) = 0$, so $Q(b, b) = 0$.

(ii) By definition of $d$.

(iii) $D$ is antisymmetric by (D2).

(iv) By the basepoint theorem (Theorem 4.1). $\square$

**Remark 6.4.** The properties (i)–(iv) are the defining properties of the complex quasi-metric. They are not independent: (iv) implies (iii), and (i) follows from (ii) and (iii) if we also assume $D(b, b) = 0$. But it is convenient to list them separately.

**Remark 6.5.** The complex quasi-metric is *not* a metric in the usual sense. It is complex-valued, and its real part is not symmetric. However, its modulus *is* a metric (Theorem 6.12), and its imaginary part is exact. This is the precise sense in which $Q$ "packages" cost and debt into a single object.

**Convention 6.6.** For the remainder of the book, we write $Q_{ij}$ for $Q(b_i, b_j)$, $d_{ij}$ for $d(b_i, b_j)$, and $D_{ij}$ for $D(b_i, b_j)$ when the context is clear.

---

## 6.2 Modulus and phase

The complex quasi-metric has two natural real-valued components: the modulus and the phase.

**Definition 6.7 (Modulus).** The *modulus* of $Q$ is

$$|Q(b_i, b_j)| := \sqrt{d(b_i, b_j)^2 + D(b_i, b_j)^2}.$$

**Definition 6.8 (Phase).** The *phase* of $Q$ is

$$\theta(b_i, b_j) := \arg Q(b_i, b_j) = \arctan\!\left(\frac{D(b_i, b_j)}{d(b_i, b_j)}\right),$$

with the convention that $\theta = \pm\pi/2$ when $d(b_i, b_j) = 0$ and $D(b_i, b_j) \neq 0$.

**Proposition 6.9 (Polar form).** Every complex quasi-metric can be written as

$$Q(b_i, b_j) = |Q(b_i, b_j)| \, e^{i\theta(b_i, b_j)}.$$

*Proof.* This is the polar form of a complex number. $\square$

**Proposition 6.10 (Properties of the phase).**

- **(i)** $\theta(b, b) = 0$;
- **(ii)** $\theta(b_i, b_j) = -\theta(b_j, b_i) + \pi$ if $d(b_i, b_j) = d(b_j, b_i)$ (i.e., if the cost is symmetric) — but in general the relationship is more subtle;
- **(iii)** $\theta$ is gauge-invariant;
- **(iv)** $\theta \in (-\pi/2, \pi/2)$ when $d > 0$.

*Proof.* (i) $D(b, b) = 0$ and $d(b, b) = 0$, so $\theta = 0$.

(ii) If $d$ is symmetric, then $Q(b_j, b_i) = d(b_j, b_i) + iD(b_j, b_i) = d(b_i, b_j) - iD(b_i, b_j) = \overline{Q(b_i, b_j)}$. Hence $\theta(b_j, b_i) = -\theta(b_i, b_j)$.

(iii) $D$ is gauge-invariant; $d$ is independent of $\psi$.

(iv) Since $d \ge 0$ and $\arctan$ maps $\mathbb{R}$ to $(-\pi/2, \pi/2)$. $\square$

**Remark 6.11.** The phase $\theta$ is the *debt-to-cost angle*. It measures the relative importance of debt and cost for a given transition. When $\theta = 0$, the transition is pure cost (no debt). When $\theta = \pm\pi/2$, the transition is pure debt (no cost). When $\theta \in (0, \pi/2)$, the transition has both cost and debt, with debt dominating if $\theta > \pi/4$ and cost dominating if $\theta < \pi/4$.

**Remark 6.12.** The phase $\theta$ is related to the debt-to-cost ratio $r$ by $\theta = \arctan(r)$. This will be used in Chapter 9 to define the $\gamma$-family.

---

## 6.3 The modulus is a metric

The central result of this chapter is that the modulus $|Q|$ is a metric.

**Theorem 6.13 (Modulus is a metric).** The function $|Q| : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ defined by

$$|Q|(b_i, b_j) := \sqrt{d(b_i, b_j)^2 + D(b_i, b_j)^2}$$

satisfies:

- **(i) Identity.** $|Q|(b, b) = 0$ for all $b \in \mathcal{B}$.
- **(ii) Non-negativity.** $|Q|(b_i, b_j) \ge 0$ for all $b_i, b_j \in \mathcal{B}$.
- **(iii) Symmetry.** $|Q|(b_i, b_j) = |Q|(b_j, b_i)$ if $d$ is symmetric.
- **(iv) Triangle inequality.** $|Q|(b_i, b_k) \le |Q|(b_i, b_j) + |Q|(b_j, b_k)$ for all $b_i, b_j, b_k \in \mathcal{B}$.

*Proof.* (i) $d(b, b) = 0$ and $D(b, b) = 0$, so $|Q|(b, b) = 0$.

(ii) Square root of a sum of squares.

(iii) $|Q|(b_i, b_j)^2 = d(b_i, b_j)^2 + D(b_i, b_j)^2$. If $d$ is symmetric, then $d(b_i, b_j) = d(b_j, b_i)$, and $D(b_i, b_j)^2 = D(b_j, b_i)^2$ (since $D$ is antisymmetric). Hence $|Q|(b_i, b_j) = |Q|(b_j, b_i)$.

(iv) Compute:

$$|Q|(b_i, b_k)^2 = d(b_i, b_k)^2 + D(b_i, b_k)^2.$$

By the triangle inequality for $d$ and the additivity of $D$:

$$d(b_i, b_k) \le d(b_i, b_j) + d(b_j, b_k), \qquad D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

Hence

$$|Q|(b_i, b_k)^2 \le [d(b_i, b_j) + d(b_j, b_k)]^2 + [D(b_i, b_j) + D(b_j, b_k)]^2.$$

By Minkowski's inequality in $\mathbb{R}^2$:

$$\sqrt{(a_1 + a_2)^2 + (b_1 + b_2)^2} \le \sqrt{a_1^2 + b_1^2} + \sqrt{a_2^2 + b_2^2},$$

with $a_1 = d(b_i, b_j)$, $b_1 = D(b_i, b_j)$, $a_2 = d(b_j, b_k)$, $b_2 = D(b_j, b_k)$. Hence

$$|Q|(b_i, b_k) \le |Q|(b_i, b_j) + |Q|(b_j, b_k).$$

This proves the triangle inequality. $\square$

**Remark 6.14.** The theorem is the key structural result of the chapter. It says that even though $Q$ itself is not a metric (it is complex-valued, and its real part is not symmetric), its modulus is a genuine metric (or pseudometric, if $d$ is symmetric but not identity-respecting). This is the precise sense in which $Q$ "contains" a metric.

**Remark 6.15.** The proof uses two key facts: the triangle inequality for $d$ (which holds by construction, since $d$ is an energy quasi-metric) and the additivity of $D$ (which holds by axiom D1). These two facts, combined with Minkowski's inequality in $\mathbb{R}^2$, give the triangle inequality for $|Q|$.

**Remark 6.16.** The triangle inequality for $|Q|$ holds *regardless* of whether $d$ is symmetric. The modulus is a metric (or pseudometric) as long as $d$ satisfies the triangle inequality. This is important: the modulus "repairs" the asymmetry of $d$ to the extent that it becomes symmetric *only if $d$ was symmetric to begin with*. If $d$ is asymmetric, $|Q|$ is also asymmetric in general, and is only a quasi-metric.

**Corollary 6.17.** If $d$ is symmetric, then $|Q|$ is a metric (or pseudometric) on $\mathcal{B}$.

**Corollary 6.18.** If $d$ is asymmetric, then $|Q|$ is a quasi-metric on $\mathcal{B}$, but not necessarily symmetric.

**Remark 6.19.** The modulus $|Q|$ is a metric in a *stronger* sense than $d$: it incorporates the debt $D$, which is symmetric in a certain sense (the *square* $D^2$ is symmetric). This is why the modulus is "more symmetric" than $d$ itself.

---

## 6.4 The phase as a geometric quantity

The phase $\theta$ is not just an algebraic artifact. It has a geometric interpretation.

**Definition 6.20 (Phase angle).** The phase $\theta(b_i, b_j)$ is the angle between the positive real axis and the vector $(d(b_i, b_j), D(b_i, b_j))$ in $\mathbb{R}^2$.

**Proposition 6.21 (Geometric interpretation).**

- $\theta = 0$: the transition is pure cost. The vector points along the real axis.
- $\theta = \pi/4$: cost and debt are equal in magnitude. The vector points along the diagonal.
- $\theta = \pi/2$: the transition is pure debt. The vector points along the imaginary axis.
- $\theta = -\pi/4$: cost and debt are equal in magnitude but opposite in sign. The vector points along the anti-diagonal.
- $\theta = -\pi/2$: the transition is pure negative debt. The vector points along the negative imaginary axis.

**Remark 6.22.** The phase $\theta$ is a *local* quantity: it depends on the pair $(b_i, b_j)$. It is not a global property of the belief space. Different transitions have different phases.

**Remark 6.23.** The phase is *gauge-invariant*: it depends only on $D$ and $d$, not on the choice of potential $\psi$. This is important: the phase is an observable.

**Definition 6.24 (Phase field).** The *phase field* on $\mathcal{B} \times \mathcal{B}$ is the function $\theta : \mathcal{B} \times \mathcal{B} \to (-\pi/2, \pi/2)$ defined by $\theta(b_i, b_j) := \arg Q(b_i, b_j)$.

**Proposition 6.25.** The phase field satisfies:

- **(i)** $\theta(b, b) = 0$;
- **(ii)** $\theta(b_i, b_j) = -\theta(b_j, b_i)$ if $d$ is symmetric;
- **(iii)** $\theta$ is gauge-invariant;
- **(iv)** $\theta$ is bounded in $(-\pi/2, \pi/2)$.

*Proof.* (i) $Q(b, b) = 0$, so the phase is defined as $0$.

(ii) If $d$ is symmetric, $Q(b_j, b_i) = \overline{Q(b_i, b_j)}$, so the phases are negatives.

(iii) $D$ is gauge-invariant; $d$ is independent of gauge.

(iv) $\arctan$ maps $\mathbb{R}$ to $(-\pi/2, \pi/2)$. $\square$

**Remark 6.26.** The phase field is the natural "angular coordinate" on the space of transitions. It measures the relative importance of cost and debt. It is the second fundamental quantity of the theory, alongside the modulus.

---

## 6.5 The complex quasi-metric as a section

The complex quasi-metric can be viewed as a section of a bundle over $\mathcal{B} \times \mathcal{B}$.

**Definition 6.27 (Trivial bundle).** Let $\mathcal{B} \times \mathcal{B} \times \mathbb{C} \to \mathcal{B} \times \mathcal{B}$ be the trivial complex line bundle over $\mathcal{B} \times \mathcal{B}$.

**Definition 6.28 (Section).** The complex quasi-metric $Q$ is a section of this bundle: it assigns to each pair $(b_i, b_j)$ a complex number $Q(b_i, b_j) \in \mathbb{C}$.

**Proposition 6.29 (Gauge action on the bundle).** The gauge transformation $\psi \mapsto \psi + \chi$ acts on the section $Q$ by

$$Q(b_i, b_j) \mapsto Q(b_i, b_j) + i \cdot (\chi(b_j) - \chi(b_i)).$$

This is a *vertical* translation in the bundle, in the imaginary direction.

*Proof.* Immediate from the definition of $Q$ and the gauge transformation of $D$. $\square$

**Remark 6.30.** The gauge action is a translation in the imaginary direction, with the amount of translation depending on the pair $(b_i, b_j)$. This is the precise sense in which the gauge group acts on the complex quasi-metric.

**Remark 6.31.** The real part $d$ is gauge-invariant; the imaginary part $D$ shifts by a coboundary. This is the origin of the gauge structure. It will be developed in detail in Chapter 8.

---

## 6.6 The algebra of complex quasi-metrics

We now consider algebraic operations on complex quasi-metrics.

**Definition 6.32 (Addition).** If $Q_1 = d_1 + iD_1$ and $Q_2 = d_2 + iD_2$ are complex quasi-metrics, their *sum* is

$$Q_1 + Q_2 := (d_1 + d_2) + i(D_1 + D_2).$$

**Proposition 6.33.** The sum of two complex quasi-metrics is a complex quasi-metric.

*Proof.* The real part $d_1 + d_2$ satisfies the triangle inequality (sum of quasi-metrics), and the imaginary part $D_1 + D_2$ satisfies (D1) and (D2). $\square$

**Definition 6.34 (Scalar multiplication).** If $Q = d + iD$ is a complex quasi-metric and $\alpha \in \mathbb{R}$, the *scalar multiple* is

$$\alpha Q := (\alpha d) + i(\alpha D).$$

**Proposition 6.35.** The scalar multiple of a complex quasi-metric is a complex quasi-metric if $\alpha \ge 0$.

*Proof.* The real part $\alpha d$ satisfies the triangle inequality if $\alpha \ge 0$. The imaginary part $\alpha D$ satisfies (D1) and (D2). $\square$

**Remark 6.36.** If $\alpha < 0$, then $\alpha d$ is negative, violating the non-negativity of the real part. So scalar multiplication is only defined for $\alpha \ge 0$.

**Definition 6.37 (Conjugation).** The *conjugate* of $Q = d + iD$ is

$$\overline{Q} := d - iD.$$

**Proposition 6.38.** The conjugate $\overline{Q}$ satisfies:

- $\mathrm{Re}\, \overline{Q} = \mathrm{Re}\, Q$;
- $\mathrm{Im}\, \overline{Q} = -\mathrm{Im}\, Q$;
- $|\overline{Q}| = |Q|$;
- $\arg \overline{Q} = -\arg Q$.

*Proof.* Immediate. $\square$

**Remark 6.39.** The conjugation operation reverses the sign of the debt but leaves the cost unchanged. This corresponds to reversing the "direction" of the debt (positive becomes negative, and vice versa).

**Definition 6.40 (Product).** The *product* of two complex quasi-metrics is defined by

$$Q_1 Q_2 := (d_1 d_2 - D_1 D_2) + i(d_1 D_2 + d_2 D_1).$$

**Proposition 6.41.** The product of two complex quasi-metrics is *not* in general a complex quasi-metric.

*Proof.* The real part $d_1 d_2 - D_1 D_2$ may be negative, violating non-negativity. Additionally, the product may not satisfy the triangle inequality. $\square$

**Remark 6.42.** The product is defined for algebraic completeness, but it does not preserve the structure of complex quasi-metrics. This is an important point: the complex quasi-metric is not closed under multiplication. The natural operations are addition and scalar multiplication, not multiplication.

**Remark 6.43.** The failure of closure under multiplication is the reason the theory is developed in the *additive* regime. The multiplicative regime (where $Q_1 Q_2$ is meaningful) is a different theory, developed in Chapter 16.

---

## 6.7 The complex quasi-metric and the basepoint

We now make explicit the dependence of $Q$ on the basepoint.

**Proposition 6.44.** Let $s_0 \in \mathcal{B}$ be a basepoint. Then for all $b_i, b_j \in \mathcal{B}$,

$$Q(b_i, b_j) = d(b_i, b_j) + i \cdot (\psi_{s_0}(b_j) - \psi_{s_0}(b_i)),$$

where $\psi_{s_0}(b) := D(s_0, b)$.

*Proof.* By the basepoint theorem, $D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)$. $\square$

**Corollary 6.45.** The complex quasi-metric is independent of the choice of basepoint $s_0$. That is, $Q$ is the same regardless of which $s_0$ is used to define $\psi$.

*Proof.* Different basepoints give potentials that differ by constants, and constants cancel in differences. $\square$

**Remark 6.46.** The basepoint is a *computational device*: it allows us to compute $Q$ without reference to paths. The complex quasi-metric itself is basepoint-independent.

---

## 6.8 The complex quasi-metric as a 1-cochain

The complex quasi-metric can be interpreted as a complex-valued 1-cochain.

**Definition 6.47 (Complex 1-cochain).** A *complex 1-cochain* on $\mathcal{B}$ is a function $Q : \mathcal{B} \times \mathcal{B} \to \mathbb{C}$.

**Proposition 6.48.** The complex quasi-metric $Q$ satisfies:

- **(i)** $Q(b, b) = 0$;
- **(ii)** $\mathrm{Re}\, Q \ge 0$;
- **(iii)** $\mathrm{Im}\, Q$ is a real 1-coboundary.

*Proof.* Immediate from the definitions. $\square$

**Remark 6.49.** The complex quasi-metric is a complex 1-cochain with a special structure: its real part is non-negative, and its imaginary part is exact. This is the cohomological characterization of the complex quasi-metric.

**Remark 6.50.** The condition that $\mathrm{Im}\, Q$ is a coboundary is what distinguishes the complex quasi-metric from a general complex 1-cochain. It is a strong condition: it says that the imaginary part is *integrable*, i.e., it is the coboundary of a 0-cochain.

---

## 6.9 The complex quasi-metric as a metric-like object

We close this chapter by summarizing the sense in which the complex quasi-metric is "metric-like."

**The complex quasi-metric is not a metric.** It is complex-valued, its real part is not symmetric, and it does not satisfy the triangle inequality in the usual sense.

**But its modulus is a metric.** The quantity $|Q(b_i, b_j)| = \sqrt{d^2 + D^2}$ satisfies the triangle inequality, symmetry (if $d$ is symmetric), and non-negativity. It is a genuine metric (or pseudometric).

**And its imaginary part is exact.** The debt $D = \mathrm{Im}\, Q$ is a coboundary, so it is path-independent, cycle-invariant, and admits a potential.

**So the complex quasi-metric is a "metric-like" object:** it is a complex-valued function that "contains" a metric (its modulus) and an exact 1-form (its imaginary part). The complex structure is the natural way to package these two pieces of information into a single object.

**Remark 6.51.** The phrase "complex quasi-metric" is therefore a *portmanteau*: it combines "complex" (the codomain is $\mathbb{C}$) and "quasi-metric" (the real part is a quasi-metric). It is not a metric in the classical sense, but it is a natural generalization.

**Remark 6.52.** The complex quasi-metric is the central object of the book. Its modulus is a metric; its phase is a geometric quantity; its imaginary part is exact. These three properties—metric modulus, geometric phase, exact imaginary part—are the defining features of the theory.

---

## 6.10 Summary

We have introduced the complex quasi-metric $Q = d + iD$, where $d$ is the energy quasi-metric and $D = \delta\psi$ is the debt function.

Key results:

- **Definition.** $Q(b_i, b_j) = d(b_i, b_j) + i \cdot D(b_i, b_j)$.
- **Basic properties.** $Q(b, b) = 0$, $\mathrm{Re}\, Q \ge 0$, $\mathrm{Im}\, Q$ is antisymmetric and exact.
- **Modulus.** $|Q| = \sqrt{d^2 + D^2}$ is a metric (Theorem 6.13).
- **Phase.** $\theta = \arg Q$ is a geometric quantity in $(-\pi/2, \pi/2)$.
- **Polar form.** $Q = |Q| e^{i\theta}$.
- **Gauge action.** $Q \mapsto Q + i \delta\chi$ under a gauge transformation.
- **Algebra.** $Q$ is closed under addition and scalar multiplication, but not under multiplication.
- **Basepoint independence.** $Q$ is independent of the basepoint used to define $\psi$.
- **Cohomological characterization.** $Q$ is a complex 1-cochain with non-negative real part and exact imaginary part.

The complex quasi-metric is the central object of the book. Everything that follows—the $\gamma$-family, the polar decomposition, the topology lattice, the grading, the categorical picture—is a consequence or elaboration of this object.

---

## 6.11 Exercises

**Exercise 6.1.** Let $\mathcal{B} = \{1, 2, 3\}$ with $d$ and $D$ given by

$$d = \begin{pmatrix} 0 & 2 & 5 \\ 1 & 0 & 3 \\ 4 & 1 & 0 \end{pmatrix}, \qquad D = \begin{pmatrix} 0 & 1 & 3 \\ -1 & 0 & 2 \\ -3 & -2 & 0 \end{pmatrix}.$$

Compute $Q$, $|Q|$, and $\theta$ for all pairs.

**Exercise 6.2.** Verify that $|Q|$ satisfies the triangle inequality in the example above.

**Exercise 6.3.** Prove that if $d$ is symmetric, then $|Q|$ is symmetric.

**Exercise 6.4.** Show that the phase $\theta$ is gauge-invariant.

**Exercise 6.5.** Compute the polar form $Q = |Q| e^{i\theta}$ for a pure cost transition ($D = 0$) and a pure debt transition ($d = 0$).

**Exercise 6.6.** Prove that the product of two complex quasi-metrics is not in general a complex quasi-metric. Give a counterexample.

**Exercise 6.7.** Show that $Q$ is independent of the choice of basepoint $s_0$.

**Exercise 6.8.** Let $Q_1$ and $Q_2$ be complex quasi-metrics. Show that $Q_1 + Q_2$ is a complex quasi-metric.

**Exercise 6.9.** Prove that the modulus $|Q|$ is a pseudometric if $d$ is a pseudometric, and a metric if $d$ is a metric.

**Exercise 6.10.** Reflect on the following question: why is the modulus $|Q|$ a metric even though $Q$ itself is not? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we develop the metric properties of the modulus $|Q|$ in detail. We prove that it satisfies the triangle inequality, characterize its metric structure, and connect it to the energy quasi-metric $d$.*

---

**End of Chapter 6.**
