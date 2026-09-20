# Chapter 9: Gauge Structure

---

In Chapter 7, we introduced the complex quasi-metric $Q = d + iD$ and noted that its imaginary part $D = \delta\psi$ is a coboundary. The potential $\psi$ is not unique: it is defined only up to an additive constant. This non-uniqueness is the origin of the **gauge structure** of the theory.

In this chapter, we develop the gauge structure in full. We introduce the gauge group, describe its action on $Q$, characterize the gauge-invariant observables, and interpret the gauge action as a connection on a trivial bundle. We also study the consequences of the fact that the gauge action is transitive on the space of debt functions, and we connect the gauge structure to the metric properties of $|Q|$.

The gauge structure is not an add-on to the theory; it is a fundamental aspect of the complex quasi-metric, and it will play a central role in the categorical picture of Chapter 15.

**Remark 9.0 (Relation to Chapter 8).** Chapter 8 developed the metric properties of the modulus $|Q|$. This chapter studies the gauge structure of $Q$ itself. The reader who wants only the metric theory can read Chapter 8; the reader who wants the full structure of $Q$ should read both.

---

## 9.1 The gauge group

We begin with the definition of the gauge group.

**Definition 9.1 (Gauge transformation).** A *gauge transformation* of the potential is a map $\psi \mapsto \psi + \chi$, where $\chi : \mathcal{B} \to \mathbb{R}$ is any function.

**Definition 9.2 (Gauge group).** The *gauge group* of the belief space $\mathcal{B}$ is the additive group

$$\mathcal{G} := \mathbb{R}^{\mathcal{B}} = \{\chi : \mathcal{B} \to \mathbb{R}\},$$

with group operation pointwise addition.

**Proposition 9.3.** The gauge group $\mathcal{G}$ is an abelian group. It is isomorphic to $\mathbb{R}^{\mathcal{B}}$.

*Proof.* Pointwise addition of functions is commutative and associative, with identity the zero function and inverse the negation. $\square$

**Remark 9.4.** The gauge group is *huge*: it is the space of all functions from $\mathcal{B}$ to $\mathbb{R}$. For a finite belief space with $n$ elements, $\mathcal{G} \cong \mathbb{R}^n$. For an infinite belief space, $\mathcal{G}$ is infinite-dimensional.

**Remark 9.5.** The gauge group is abelian. This is important: it means the gauge transformations commute, and the gauge structure is "abelian" in the sense of gauge theory. Non-abelian gauge groups would arise if the potential took values in a non-abelian group, which is not the case here.

---

## 9.2 The gauge action on the debt

We now describe how the gauge group acts on the debt.

**Definition 9.6 (Gauge action on debt).** For $\chi \in \mathcal{G}$, the *gauge action* of $\chi$ on $D$ is

$$(\chi \cdot D)(b_i, b_j) := D(b_i, b_j) + \chi(b_j) - \chi(b_i).$$

Equivalently, $(\chi \cdot D) = D + \delta\chi$.

**Proposition 9.7 (Properties of the gauge action).**

- **(i) Group action.** $\chi_1 \cdot (\chi_2 \cdot D) = (\chi_1 + \chi_2) \cdot D$ for all $\chi_1, \chi_2 \in \mathcal{G}$.
- **(ii) Identity.** $0 \cdot D = D$.
- **(iii) Inverse.** $\chi \cdot (\chi^{-1} \cdot D) = D$.
- **(iv) Additivity preservation.** $\chi \cdot D$ satisfies (D1) and (D2) for all $\chi$.

*Proof.* (i) $(\chi_1 \cdot (\chi_2 \cdot D))(b_i, b_j) = \chi_2 \cdot D(b_i, b_j) + \chi_1(b_j) - \chi_1(b_i) = D(b_i, b_j) + \chi_2(b_j) - \chi_2(b_i) + \chi_1(b_j) - \chi_1(b_i) = D(b_i, b_j) + (\chi_1 + \chi_2)(b_j) - (\chi_1 + \chi_2)(b_i) = ((\chi_1 + \chi_2) \cdot D)(b_i, b_j)$.

(ii) Immediate.

(iii) Immediate.

(iv) The gauge action shifts $D$ by a coboundary $\delta\chi$, which satisfies (D1) and (D2). The sum of two functions satisfying (D1) and (D2) satisfies (D1) and (D2). $\square$

**Remark 9.8.** The gauge action is a *translation* of $D$ by a coboundary. It is a group action of $\mathcal{G}$ on the space of debt functions. The orbits of this action are the equivalence classes of debt functions that differ by coboundaries.

**Remark 9.9.** The gauge action is *not* trivial: different $\chi$ give different $D$. However, the *debt* is invariant under *constant* gauge transformations (i.e., $\chi = c$ constant), because $\delta c = 0$. The subgroup of constant functions acts trivially.

**Definition 9.10 (Gauge orbit).** The *gauge orbit* of $D$ is the set

$$\mathcal{O}_D := \{\chi \cdot D : \chi \in \mathcal{G}\}.$$

**Proposition 9.11.** The gauge orbit of $D$ is an affine subspace of the space of 1-cochains, consisting of $D$ plus the image of $\delta : \mathbb{R}^\mathcal{B} \to C^1(\mathcal{B})$.

*Proof.* Immediate from the definition. $\square$

---

## 9.3 The gauge action on the complex quasi-metric

We now extend the gauge action to the complex quasi-metric.

**Definition 9.12 (Gauge action on $Q$).** For $\chi \in \mathcal{G}$, the *gauge action* of $\chi$ on $Q$ is

$$(\chi \cdot Q)(b_i, b_j) := Q(b_i, b_j) + i(\chi(b_j) - \chi(b_i)) = Q(b_i, b_j) + i \cdot \delta\chi(b_i, b_j).$$

**Proposition 9.13 (Properties of the gauge action on $Q$).**

- **(i) Group action.** $\chi_1 \cdot (\chi_2 \cdot Q) = (\chi_1 + \chi_2) \cdot Q$.
- **(ii) Identity.** $0 \cdot Q = Q$.
- **(iii) Real part invariant.** $\mathrm{Re}(\chi \cdot Q) = \mathrm{Re}(Q) = d$.
- **(iv) Imaginary part shifts.** $\mathrm{Im}(\chi \cdot Q) = \mathrm{Im}(Q) + \delta\chi = D + \delta\chi$.
- **(v) Modulus changes.** $|\chi \cdot Q| \neq |Q|$ in general.

*Proof.* (i)–(iv) are immediate from the definitions. For (v):

$$|\chi \cdot Q|^2 = d^2 + (D + \delta\chi)^2 = d^2 + D^2 + 2D\delta\chi + (\delta\chi)^2 = |Q|^2 + 2D\delta\chi + (\delta\chi)^2.$$

This differs from $|Q|^2$ unless $\delta\chi = 0$ or $2D + \delta\chi = 0$. $\square$

**Remark 9.14.** The gauge action leaves the real part invariant and shifts the imaginary part by a coboundary. The modulus is *not* gauge-invariant in general—it changes by a term quadratic in $\delta\chi$ plus a cross term.

**Remark 9.15.** The failure of gauge invariance of $|Q|$ is important. It means that the modulus is not an observable in the gauge-theoretic sense; it depends on the choice of gauge. The genuine gauge-invariant observables are $d$ and the *cohomology class* of $D$ (which is trivial in the present setting, since $H^1 = 0$).

**Remark 9.16.** In the special case where $\chi$ is constant, $\delta\chi = 0$, and the gauge action is trivial. So the subgroup of constant functions acts trivially on $Q$. This is the "stabilizer" of the gauge action.

---

## 9.4 Gauge-invariant observables

We now identify the quantities that are invariant under gauge transformations.

**Definition 9.17 (Gauge-invariant quantity).** A quantity $F(Q)$ is *gauge-invariant* if $F(\chi \cdot Q) = F(Q)$ for all $\chi \in \mathcal{G}$.

**Proposition 9.18 (Gauge-invariant quantities).** The following are gauge-invariant:

- **(i)** The real part $d(b_i, b_j)$.
- **(ii)** The asymmetry $A(b_i, b_j) = d(b_i, b_j) - d(b_j, b_i)$.
- **(iii)** The cohomology class of $D$ in $H^1(\mathcal{B}; \mathbb{R})$. In the present setting, this is trivial, so this condition is vacuous.
- **(iv)** The cycle sums $\sum_{\text{cycle}} D$, which are all zero.

*Proof.* (i) $d$ is independent of $\psi$.

(ii) $A$ is defined in terms of $d$ only.

(iii) The cohomology class of $D$ is invariant under $D \mapsto D + \delta\chi$ by definition of cohomology. In the present setting, $H^1 = 0$, so the class is always trivial.

(iv) The cycle sums are zero by the basepoint theorem, and this is independent of gauge. $\square$

**Remark 9.19.** The list of gauge-invariant quantities is surprisingly short. The real part $d$ is gauge-invariant, but the debt $D$ is not. This is because the debt is a coboundary, and coboundaries are not gauge-invariant (they shift by coboundaries).

**Remark 9.20 (Gauge-invariance vs. observability).** It is important to distinguish between *gauge-invariance* and *observability*. A quantity is gauge-invariant if it is unchanged by gauge transformations. A quantity is observable if it can be measured in principle. These are not the same.

The debt $D$ is not gauge-invariant, but it is still an observable: it is the imaginary part of $Q$, and $Q$ is the fundamental object of the theory. The gauge transformation is a change of *description* of $Q$, not a change of $Q$ itself. Different gauges give different descriptions of the same $Q$, and the debt is part of the description.

The correct statement is: **gauge-invariance is a mathematical property, not a criterion for physicality.** The debt is gauge-dependent but physically meaningful. The cost is gauge-invariant and physically meaningful. Both are part of $Q$.

**Remark 9.21.** The fact that so few quantities are gauge-invariant is a reflection of the fact that the gauge group is huge. The gauge orbit of $D$ is an affine subspace of dimension $\dim(\mathcal{G}) = \dim(\mathbb{R}^\mathcal{B})$, which is large. So most quantities are not gauge-invariant.

**Remark 9.22.** In physics, the gauge-invariant quantities are often called the *observables*. The fact that $d$ is gauge-invariant and $D$ is not means that $d$ is the "physical" quantity in the strict gauge-theoretic sense, and $D$ is a "gauge artifact." But this is misleading: $D$ is not an artifact; it is a genuine quantity that happens to transform nontrivially under gauge. The gauge-invariant content of $D$ is its cohomology class, which is trivial here. So in some sense, $D$ contains no gauge-invariant information. But this is only true because the basepoint theorem says $D$ is always a coboundary. In more general settings (with non-trivial cohomology), $D$ would have gauge-invariant content.

---

## 9.5 The gauge action as a connection

The gauge action has a natural interpretation as a *connection* on a trivial bundle.

**Definition 9.23 (Trivial bundle).** Let $\mathcal{B} \times \mathbb{R} \to \mathcal{B}$ be the trivial real line bundle over $\mathcal{B}$.

**Definition 9.24 (Connection).** A *connection* on the trivial bundle is a 1-form $\omega : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ satisfying $\omega(b_i, b_j) = -\omega(b_j, b_i)$.

**Proposition 9.25.** The debt $D$ is a connection on the trivial bundle.

*Proof.* $D$ is antisymmetric (D2), so it is a 1-form. $\square$

**Proposition 9.26.** The gauge action $\chi \cdot D = D + \delta\chi$ is the standard transformation law for a connection under a change of trivialization.

*Proof.* In gauge theory, a connection $A$ transforms as $A \mapsto A + d\chi$ under a gauge transformation $\chi$. Here $D$ plays the role of $A$, and $\delta$ plays the role of $d$. $\square$

**Remark 9.27.** This is a precise analogy. The debt $D$ is a connection on a trivial $\mathbb{R}$-bundle over $\mathcal{B}$. The gauge group is the group of sections of the bundle (i.e., functions $\mathcal{B} \to \mathbb{R}$). The gauge action is the standard action of the gauge group on connections.

**Remark 9.28 (Flatness).** The *curvature* of the connection $D$ is the 2-form $\delta D$. By Proposition 6.16, $\delta D = 0$ for any debt function. So the connection $D$ is **flat**. This is a reflection of the fact that $D$ is a coboundary, i.e., pure gauge. In more general settings (with non-trivial cohomology), $D$ could have non-zero curvature, corresponding to non-trivial holonomy.

**Remark 9.29.** The flatness of $D$ is the gauge-theoretic statement of the basepoint theorem. It says that the connection $D$ is trivializable: there exists a gauge in which $D = 0$ (namely, the gauge where $\psi = 0$). This is the sense in which debt is "pure gauge."

**Remark 9.30 (Comparison with electromagnetism).** The analogy to electromagnetism is suggestive but should be stated carefully. In electromagnetism:

- The connection is $A$ (a 1-form).
- The curvature is $F = dA$ (a 2-form).
- Gauge transformations are $A \mapsto A + d\chi$.
- The curvature is gauge-invariant: $F \mapsto F$.
- $F$ can be nonzero (and is gauge-invariant).

In our case:

- The connection is $D$ (a 1-cochain).
- The curvature is $\delta D = 0$ (always zero).
- Gauge transformations are $D \mapsto D + \delta\chi$.
- The "curvature" is trivially gauge-invariant.
- $D$ is always flat (because $D$ is a coboundary).

The difference is that in electromagnetism, the curvature $F$ can be nonzero (and is gauge-invariant). In our case, the curvature is always zero. This is because $D$ is a coboundary, which is the statement that the connection is trivializable. In more general settings (with non-trivial cohomology), the curvature could be nonzero, and the theory would be richer.

---

## 9.6 The gauge orbit and its geometry

We now study the geometry of the gauge orbit.

**Definition 9.31 (Gauge orbit).** The *gauge orbit* of $D$ is

$$\mathcal{O}_D := \{D + \delta\chi : \chi \in \mathcal{G}\}.$$

**Proposition 9.32.** The gauge orbit $\mathcal{O}_D$ is an affine subspace of the space of 1-cochains, of dimension $\dim(\mathcal{G}) - 1 = \dim(\mathbb{R}^\mathcal{B}) - 1$.

*Proof.* The map $\chi \mapsto \delta\chi$ has kernel the constant functions, of dimension 1. So the image has dimension $\dim(\mathcal{G}) - 1$. $\square$

**Proposition 9.33.** The gauge orbit $\mathcal{O}_D$ is contained in the space of debt functions $\mathcal{D}(\mathcal{B})$.

*Proof.* $D + \delta\chi$ satisfies (D1) and (D2) for all $\chi$. $\square$

**Corollary 9.34 (Transitivity).** The gauge orbit is a subset of $\mathcal{D}(\mathcal{B})$, and in fact $\mathcal{O}_D = \mathcal{D}(\mathcal{B})$ for any $D \in \mathcal{D}(\mathcal{B})$.

*Proof.* Every debt function is a coboundary (basepoint theorem), so $\mathcal{D}(\mathcal{B}) = \mathrm{im}(\delta)$. Hence the gauge orbit of any $D$ is all of $\mathcal{D}(\mathcal{B})$. $\square$

**Remark 9.35.** The gauge orbit is the entire space of debt functions. There is only *one* gauge orbit. This is a consequence of the fact that $H^1 = 0$: every debt function is gauge-equivalent to every other.

**Remark 9.36.** The fact that there is only one gauge orbit means that the space of debt functions is *homogeneous* under the gauge group. The gauge group acts transitively. This is a strong statement: all debt functions are gauge-equivalent.

**Remark 9.37 (Consequences of transitivity).** The transitivity of the gauge action has several important consequences:

1. **Moduli space.** The moduli space of complex quasi-metrics (modulo gauge) is the space of costs $d$. The debt contributes no moduli: all debt functions are gauge-equivalent.

2. **No debt invariants.** There are no gauge-invariant functions of $D$ alone (other than constants), because any such function would be constant on the entire gauge orbit, which is all of $\mathcal{D}(\mathcal{B})$.

3. **Pure gauge.** The debt is "pure gauge" in the sense that it contains no gauge-invariant information. This is a reflection of the fact that $D$ is always a coboundary.

4. **Trivializability.** The flat connection $D$ is trivializable: there exists a gauge in which $D = 0$. This is the gauge where $\psi = 0$.

**Remark 9.38.** In more general settings (with non-trivial cohomology), there would be multiple gauge orbits, corresponding to different cohomology classes. The gauge orbits would be the fibers of the map $D \mapsto [D] \in H^1$. The moduli space would then include the cohomology $H^1$, and the debt would have gauge-invariant content.

---

## 9.7 The gauge-invariant content of $Q$

We now address the question: what is the gauge-invariant content of the complex quasi-metric?

**Theorem 9.39 (Gauge-invariant content).** The gauge-invariant content of $Q = d + iD$ is precisely the real part $d$, together with the trivial cohomology class of $D$.

*Proof.* The real part $d$ is gauge-invariant. The imaginary part $D$ is a coboundary, so its cohomology class is zero (trivial). Any gauge-invariant function of $D$ must depend only on its cohomology class, which is zero, so it is constant. Hence the only gauge-invariant content of $Q$ is $d$. $\square$

**Remark 9.40.** This is a striking conclusion: the gauge-invariant content of the complex quasi-metric is *just the cost*. The debt is entirely gauge-dependent. This means that, from a gauge-theoretic perspective, the debt contains no "invariant" information—it is pure gauge.

**Remark 9.41.** But this conclusion should not be overinterpreted. The debt is not "unphysical"—it is part of the complex quasi-metric $Q$, which is the fundamental object. The gauge transformation is a change of *description*, not a change of $Q$ itself. Different gauges give different descriptions of the same $Q$, and the debt is part of the description. The correct interpretation is that the complex quasi-metric $Q$ is the fundamental object, and the gauge group acts on its *descriptions*. The gauge-invariant content is $d$; the gauge-dependent content is $D$. Both are part of $Q$.

**Remark 9.42.** The situation is analogous to electromagnetism, but with an important difference. In electromagnetism, the vector potential $A$ is gauge-dependent, but the electromagnetic field $F = dA$ is gauge-invariant. The field $F$ is the physically observable quantity, and $A$ is a mathematical convenience. In our case, the "field" is $d$ (the real part), and the "potential" is $D$ (the imaginary part). But there is a crucial difference: in electromagnetism, $F$ is the physically observable field, and $A$ is a mathematical convenience. In our case, $d$ is the cost, which is observable, and $D$ is the debt, which is also observable (it is the imaginary part of $Q$). The gauge-dependence of $D$ does not make it unobservable; it makes it *gauge-dependent observable*.

---

## 9.8 Gauge transformations and the modulus

We now study the effect of gauge transformations on the modulus and on the metric properties of $|Q|$.

**Proposition 9.43.** Under a gauge transformation $\chi$, the modulus transforms as

$$|\chi \cdot Q|^2 = |Q|^2 + 2D \cdot \delta\chi + (\delta\chi)^2.$$

*Proof.* Direct computation:

$$|\chi \cdot Q|^2 = d^2 + (D + \delta\chi)^2 = d^2 + D^2 + 2D\delta\chi + (\delta\chi)^2 = |Q|^2 + 2D\delta\chi + (\delta\chi)^2. \quad \square$$

**Corollary 9.44.** The modulus is gauge-invariant if and only if $\delta\chi = 0$ or $2D + \delta\chi = 0$.

**Remark 9.45.** The modulus is not gauge-invariant in general. This means that different gauges give different moduli. The modulus is a *gauge-dependent* quantity.

**Remark 9.46.** The gauge-dependence of the modulus is a reflection of the fact that the modulus is a function of both $d$ and $D$, and $D$ is gauge-dependent. The gauge-invariant content of the modulus is $d$; the gauge-dependent content is the debt contribution.

**Proposition 9.47 (Bounded gauge variation).** If $|\delta\chi| \le M$ and $|D| \le N$ for all pairs, then

$$\bigl||\chi \cdot Q| - |Q|\bigr| \le M + 2N.$$

*Proof.* From Proposition 9.43:

$$\bigl||\chi \cdot Q|^2 - |Q|^2\bigr| = |2D\delta\chi + (\delta\chi)^2| \le 2NM + M^2.$$

Hence $\bigl||\chi \cdot Q| - |Q|\bigr| \le \sqrt{2NM + M^2} \le M + 2N$ (for appropriate bounds). $\square$

**Remark 9.48.** The gauge variation of the modulus is bounded by the magnitudes of the debt and the gauge transformation. If both are small, the modulus is approximately gauge-invariant.

**Remark 9.49 (Gauge transformations and the metric topology).** Since the modulus is not gauge-invariant, the metric topology $\tau_{|Q|}$ is not gauge-invariant either. Different gauges can give different topologies. The gauge-invariant topology is the one induced by $d$, which is coarser than $\tau_{|Q|}$ in general.

---

## 9.9 The stabilizer of the gauge action

We now study the subgroup of the gauge group that acts trivially.

**Definition 9.50 (Stabilizer).** The *stabilizer* of $Q$ is the subgroup

$$\mathrm{Stab}(Q) := \{\chi \in \mathcal{G} : \chi \cdot Q = Q\}.$$

**Proposition 9.51.** $\mathrm{Stab}(Q) = \{\chi \in \mathcal{G} : \delta\chi = 0\}$ = the constant functions.

*Proof.* $\chi \cdot Q = Q$ iff $i \cdot \delta\chi = 0$ iff $\delta\chi = 0$ iff $\chi$ is constant. $\square$

**Corollary 9.52.** The stabilizer of $Q$ is isomorphic to $\mathbb{R}$ (the constant functions).

**Remark 9.53.** The stabilizer is the group of gauge transformations that leave $Q$ invariant. It is the subgroup of constant functions. This is the "trivial" part of the gauge group—the part that does nothing.

**Remark 9.54.** The quotient $\mathcal{G}/\mathrm{Stab}(Q) = \mathbb{R}^\mathcal{B}/\mathbb{R}$ is the *effective* gauge group, which acts faithfully on $Q$. This is the same as the space of debt functions $\mathcal{D}(\mathcal{B})$, by the isomorphism of Chapter 5.

---

## 9.10 The gauge structure: summary

We summarize the gauge structure in a single table.

| **Object** | **Definition** | **Gauge transformation** |
|---|---|---|
| Potential $\psi$ | $\psi : \mathcal{B} \to \mathbb{R}$ | $\psi \mapsto \psi + \chi$ |
| Debt $D$ | $D = \delta\psi$ | $D \mapsto D + \delta\chi$ |
| Complex quasi-metric $Q$ | $Q = d + iD$ | $Q \mapsto Q + i\delta\chi$ |
| Modulus $|Q|$ | $|Q| = \sqrt{d^2 + D^2}$ | $|Q|^2 \mapsto |Q|^2 + 2D\delta\chi + (\delta\chi)^2$ |
| Gauge group $\mathcal{G}$ | $\mathbb{R}^\mathcal{B}$ | — |
| Stabilizer | Constant functions | Acts trivially |

**Remark 9.55.** The gauge structure is abelian, because the gauge group is abelian. The gauge action is a translation of $D$ by a coboundary. The real part $d$ is gauge-invariant; the imaginary part $D$ is not; the modulus $|Q|$ is not; the cohomology class of $D$ is trivial.

**Remark 9.56.** The gauge structure is the foundation for the categorical picture of Chapter 15. The complex quasi-metric $Q$ is a section of a trivial bundle, and the gauge group is the group of sections of the associated principal bundle. The gauge action is the standard action of the gauge group on sections.

---

## 9.11 The gauge structure and the basepoint theorem

We close this chapter by connecting the gauge structure to the basepoint theorem.

**Theorem 9.57 (Basepoint and gauge).** The basepoint theorem says that every debt function is a coboundary. The gauge structure says that the coboundary is determined only up to a constant. Together, these two results characterize the debt completely: the debt is a coboundary, and the potential is unique up to a constant.

*Proof.* Combine Theorem 4.1 and Proposition 9.51. $\square$

**Remark 9.58.** The basepoint theorem and the gauge structure are two sides of the same coin. The basepoint theorem says that debt is exact; the gauge structure says that the potential is not unique. Both are reflections of the fact that $H^1(\mathcal{B}; \mathbb{R}) = 0$: the first cohomology is trivial, so every 1-cocycle is a coboundary, and the space of coboundaries is the space of potentials modulo constants.

**Remark 9.59.** The gauge structure is the "fine structure" of the basepoint theorem. The basepoint theorem says that $D = \delta\psi$ for some $\psi$; the gauge structure says that $\psi$ is unique up to a constant. The constant is the gauge freedom.

**Remark 9.60.** The gauge structure is the last ingredient needed for the complex quasi-metric to be a complete object. The real part $d$ is the cost; the imaginary part $D$ is the debt, which is exact; the gauge group is the group of constants. Everything else—the modulus, the phase, the $\gamma$-family, the polar decomposition, the topology lattice, the grading, the categorical picture—follows from these ingredients.

---

## 9.12 Summary

We have developed the gauge structure of the complex quasi-metric.

Key results:

- **Gauge group.** $\mathcal{G} = \mathbb{R}^\mathcal{B}$, the group of functions $\chi : \mathcal{B} \to \mathbb{R}$.
- **Gauge action on $D$.** $D \mapsto D + \delta\chi$.
- **Gauge action on $Q$.** $Q \mapsto Q + i\delta\chi$.
- **Real part invariant.** $\mathrm{Re}(\chi \cdot Q) = d$.
- **Imaginary part shifts.** $\mathrm{Im}(\chi \cdot Q) = D + \delta\chi$.
- **Modulus changes.** $|\chi \cdot Q|^2 = |Q|^2 + 2D\delta\chi + (\delta\chi)^2$.
- **Gauge-invariant quantities.** $d$, $A$, the cohomology class of $D$ (trivial), and the cycle sums (zero).
- **Connection interpretation.** $D$ is a flat connection on the trivial bundle.
- **Gauge orbit.** The gauge orbit of $D$ is all of $\mathcal{D}(\mathcal{B})$; the gauge action is transitive.
- **Stabilizer.** The constant functions; $\mathrm{Stab}(Q) \cong \mathbb{R}$.
- **Gauge-invariant content.** The gauge-invariant content of $Q$ is precisely $d$.
- **Metric topology.** $\tau_{|Q|}$ is not gauge-invariant; the gauge-invariant topology is the one induced by $d$.

The gauge structure is a fundamental aspect of the complex quasi-metric. It is the origin of the "gauge freedom" of the potential, and it will play a central role in the categorical picture of Chapter 15.

---

## 9.13 Exercises

**Exercise 9.1.** Verify that the gauge action on $D$ satisfies the group action axioms.

**Exercise 9.2.** Show that the gauge action on $Q$ leaves the real part invariant and shifts the imaginary part by a coboundary.

**Exercise 9.3.** Prove that the modulus $|Q|$ is gauge-invariant if and only if $\delta\chi = 0$ or $2D + \delta\chi = 0$.

**Exercise 9.4.** Compute the gauge variation of the modulus for a specific example.

**Exercise 9.5.** Show that the gauge orbit of $D$ is all of $\mathcal{D}(\mathcal{B})$.

**Exercise 9.6.** Prove that the stabilizer of $Q$ is the constant functions.

**Exercise 9.7.** Show that $D$ is a flat connection: $\delta D = 0$.

**Exercise 9.8.** Prove that the gauge-invariant content of $Q$ is precisely $d$.

**Exercise 9.9.** Let $\chi : \mathcal{B} \to \mathbb{R}$ be a gauge transformation. Show that $\chi \cdot Q$ is a complex quasi-metric.

**Exercise 9.10.** Discuss the consequences of the transitivity of the gauge action. In particular, explain why there are no gauge-invariant functions of $D$ alone (other than constants).

**Exercise 9.11.** Explain how gauge transformations affect the metric topology $\tau_{|Q|}$. Is $\tau_{|Q|}$ gauge-invariant? What is the gauge-invariant topology?

**Exercise 9.12.** Reflect on the following question: is the gauge structure a *feature* or a *bug* of the theory? Write a short essay (one page) arguing for your position.



---

**End of Chapter 9**
