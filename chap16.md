# Chapter 16: The Categorical Picture

---

We now arrive at the final structural chapter of the book. In Chapters 12–15, we developed the polar decomposition, the bitopological structure, the equilibrium hierarchy, and the $\mathbb{Z}/2$-grading. Each of these is a *structural* result: it reveals a piece of the architecture of the complex quasi-metric.

This chapter steps back and asks: what is the *category-theoretic* content of the theory? What is the complex quasi-metric, in the language of categories? What functors does it induce? What adjunctions does it participate in?

The answer, developed in this chapter, is that the complex quasi-metric lives in a **$\mathbb{Z}/2$-graded category** $\mathbf{CQM}$ of cost-potential pairs. This category is related to the categories of quasi-pseudometric and pseudometric spaces by forgetful functors, and it is compatible with the symmetrization adjunction. The comma category of the symmetrization adjunction provides a useful heuristic, but the precise categorical setting is $\mathbf{CQM}$.

The categorical picture is the most abstract result of the book. It situates the theory in the general framework of category theory, and it reveals the complex quasi-metric as a natural object in a universal construction.

---

## 16.1 Categories of metric-like spaces

We begin by defining the relevant categories.

**Definition 16.1 (Quasi-pseudometric space).** A *quasi-pseudometric space* is a pair $(X, d)$ where $X$ is a set and $d : X \times X \to \mathbb{R}_{\ge 0}$ satisfies:

- **(M0)** $d(x, x) = 0$ for all $x \in X$;
- **(M1)** $d(x, z) \le d(x, y) + d(y, z)$ for all $x, y, z \in X$.

Symmetry is not required; the identity of indiscernibles is not required.

**Definition 16.2 (Pseudometric space).** A *pseudometric space* is a quasi-pseudometric space $(X, d)$ satisfying in addition:

- **(M2)** $d(x, y) = d(y, x)$ for all $x, y \in X$.

**Definition 16.3 (Metric space).** A *metric space* is a pseudometric space $(X, d)$ satisfying in addition:

- **(M3)** $d(x, y) = 0 \Rightarrow x = y$.

**Definition 16.4 (1-Lipschitz map).** A map $f : (X, d_X) \to (Y, d_Y)$ between quasi-pseudometric spaces is *1-Lipschitz* if

$$d_Y(f(x), f(x')) \le d_X(x, x')$$

for all $x, x' \in X$.

**Definition 16.5 (Categories).**

- $\mathbf{QPM}$: the category of quasi-pseudometric spaces with 1-Lipschitz maps;
- $\mathbf{PM}$: the category of pseudometric spaces with 1-Lipschitz maps;
- $\mathbf{Met}$: the category of metric spaces with 1-Lipschitz maps.

**Proposition 16.6 (Inclusions).** There are full inclusions

$$\mathbf{Met} \hookrightarrow \mathbf{PM} \hookrightarrow \mathbf{QPM}.$$

*Proof.* Every metric space is a pseudometric space, and every pseudometric space is a quasi-pseudometric space. The 1-Lipschitz condition is the same. $\square$

**Remark 16.7.** The categories $\mathbf{QPM}$, $\mathbf{PM}$, $\mathbf{Met}$ are the natural settings for the theory of metric-like spaces. The complex quasi-metric will be situated in the category $\mathbf{CQM}$ of cost-potential pairs, which is related to these categories by forgetful functors.

---

## 16.2 The symmetrization functor

We now define the symmetrization functor.

**Definition 16.8 (Symmetrization).** The *symmetrization* of a quasi-pseudometric $d$ is

$$S(b_i, b_j) := \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)).$$

**Proposition 16.9.** If $(X, d)$ is a quasi-pseudometric space, then $(X, S)$ is a pseudometric space.

*Proof.* Proposition 12.11 (triangle inequality) and Proposition 12.4(i) (symmetry). $\square$

**Definition 16.10 (Symmetrization functor).** The *symmetrization functor* is

$$\Sigma : \mathbf{QPM} \to \mathbf{PM}, \qquad \Sigma(X, d) := (X, S),$$

with $\Sigma(f) := f$ for a 1-Lipschitz map $f$.

**Proposition 16.11.** $\Sigma$ is a functor.

*Proof.* We must check that $\Sigma$ preserves identities and composition. Identities: $\Sigma(\mathrm{id}_X) = \mathrm{id}_{\Sigma(X)}$. Composition: $\Sigma(g \circ f) = \Sigma(g) \circ \Sigma(f)$. Both are immediate since $\Sigma$ is the identity on morphisms.

We must also check that $\Sigma(f)$ is 1-Lipschitz: if $f : (X, d_X) \to (Y, d_Y)$ is 1-Lipschitz, then

$$S_Y(f(x), f(x')) = \tfrac{1}{2}(d_Y(f(x), f(x')) + d_Y(f(x'), f(x))) \le \tfrac{1}{2}(d_X(x, x') + d_X(x', x)) = S_X(x, x').$$

So $\Sigma(f)$ is 1-Lipschitz. $\square$

**Remark 16.12.** The symmetrization functor $\Sigma$ maps a quasi-pseudometric space to its symmetrization. It "forgets" the asymmetry of $d$ and retains only the symmetric part.

**Remark 16.13.** The symmetrization functor is the categorical version of the polar decomposition. It projects onto the symmetric part of the quasi-metric.

---

## 16.3 The inclusion functor

We now define the inclusion functor.

**Definition 16.14 (Inclusion).** The *inclusion functor* is

$$\iota : \mathbf{PM} \hookrightarrow \mathbf{QPM}, \qquad \iota(X, d) := (X, d).$$

**Proposition 16.15.** $\iota$ is a full and faithful functor.

*Proof.* $\iota$ is the identity on objects and morphisms, so it is full and faithful. $\square$

**Remark 16.16.** The inclusion functor $\iota$ views a pseudometric space as a quasi-pseudometric space (with symmetric distance). It is the "forgetful" functor that forgets the extra symmetry assumption.

**Remark 16.17.** The composition $\Sigma \circ \iota = \mathrm{id}_{\mathbf{PM}}$. That is, symmetrizing a pseudometric space gives back the same space. This is because a pseudometric is already symmetric.

**Remark 16.18.** The composition $\iota \circ \Sigma$ is *not* the identity on $\mathbf{QPM}$. It maps a quasi-pseudometric space to its symmetrization, viewed as a quasi-pseudometric space. This is a projection, not the identity.

---

## 16.4 The symmetrized Lipschitz condition

The naive adjunction between $\Sigma$ and $\iota$ fails with the standard Lipschitz condition. We introduce a modified condition under which it holds.

**Definition 16.19 (Symmetrically 1-Lipschitz map).** A map $f : (X, d_X) \to (Y, d_Y)$ between quasi-pseudometric spaces is *symmetrically 1-Lipschitz* if

$$S_Y(f(x), f(x')) \le S_X(x, x')$$

for all $x, x' \in X$, where $S_X, S_Y$ are the symmetrizations.

**Definition 16.20 (Category $\mathbf{QPM}_S$).** The category $\mathbf{QPM}_S$ has quasi-pseudometric spaces as objects and symmetrically 1-Lipschitz maps as morphisms.

**Proposition 16.21.** $\mathbf{QPM}_S$ is a category.

*Proof.* Identities are symmetrically 1-Lipschitz. Composition of symmetrically 1-Lipschitz maps is symmetrically 1-Lipschitz (since the symmetrized Lipschitz condition is preserved under composition). $\square$

**Remark 16.22.** The category $\mathbf{QPM}_S$ is the "symmetrized" version of $\mathbf{QPM}$. It is the natural setting for the adjunction $\Sigma \dashv \iota$.

**Remark 16.23 (Why the naive adjunction fails).** With the standard Lipschitz condition ($d_Y(f(x), f(x')) \le d_X(x, x')$), the adjunction fails because $S(x, x')$ is not always $\le d(x, x')$. In fact, $S$ can be *larger* than $d$ in one direction: if $d(b_i, b_j) < d(b_j, b_i)$, then $S(b_i, b_j) > d(b_i, b_j)$. So a map that is 1-Lipschitz for $S$ need not be 1-Lipschitz for $d$. The symmetrized condition fixes this by using $S$ on both sides.

---

## 16.5 The adjunction

We now state and prove the adjunction.

**Theorem 16.24 (Symmetrization adjunction).** The symmetrization functor $\Sigma : \mathbf{QPM}_S \to \mathbf{PM}$ is *left adjoint* to the inclusion functor $\iota : \mathbf{PM} \hookrightarrow \mathbf{QPM}_S$:

$$\Sigma \dashv \iota.$$

*Proof.* We exhibit a natural bijection

$$\mathrm{Hom}_{\mathbf{PM}}(\Sigma(X, d), (Y, d_Y)) \cong \mathrm{Hom}_{\mathbf{QPM}_S}((X, d), \iota(Y, d_Y))$$

for all $(X, d) \in \mathbf{QPM}_S$ and $(Y, d_Y) \in \mathbf{PM}$.

Since $\Sigma$ and $\iota$ are the identity on objects, this reduces to a bijection between 1-Lipschitz maps $f : (X, S) \to (Y, d_Y)$ and symmetrically 1-Lipschitz maps $f : (X, d) \to (Y, d_Y)$.

A map $f$ is symmetrically 1-Lipschitz for $(X, d) \to (Y, d_Y)$ iff $S_Y(f(x), f(x')) \le S_X(x, x')$ for all $x, x'$. Since $Y$ is pseudometric, $S_Y = d_Y$. So this is equivalent to $d_Y(f(x), f(x')) \le S_X(x, x')$, which is exactly the condition that $f$ is 1-Lipschitz for $(X, S) \to (Y, d_Y)$.

Hence the bijection. Naturality in $(X, d)$ and $(Y, d_Y)$ is immediate. $\square$

**Remark 16.25.** The adjunction $\Sigma \dashv \iota$ is the precise sense in which symmetrization is "universal." It says that mapping out of a symmetrized space is the same as mapping out of the original space with the symmetrized Lipschitz condition.

**Remark 16.26.** The adjunction $\Sigma \dashv \iota$ is a *reflection*: the inclusion $\iota$ has a left adjoint. The category $\mathbf{PM}$ is a reflective subcategory of $\mathbf{QPM}_S$. This is the categorical content of symmetrization.

**Remark 16.27.** The adjunction is sensitive to the choice of morphisms. With the standard condition, it fails; with the symmetrized condition, it holds. This reflects the fact that symmetrization is not a trivial operation: it changes the Lipschitz condition.

---

## 16.6 The category of complex quasi-metrics

We now define the category of complex quasi-metrics, which is the natural categorical setting for the theory.

**Definition 16.28 (Complex quasi-metric space).** A *complex quasi-metric space* is a triple $(\mathcal{B}, d, \psi)$ where:

- $\mathcal{B}$ is a set;
- $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ is a quasi-pseudometric;
- $\psi : \mathcal{B} \to \mathbb{R}$ is a potential.

The associated complex quasi-metric is $Q := d + i\delta\psi$.

**Definition 16.29 (Morphism of complex quasi-metric spaces).** A *morphism* $f : (\mathcal{B}, d, \psi) \to (\mathcal{B}', d', \psi')$ is a map $f : \mathcal{B} \to \mathcal{B}'$ such that:

- $f$ is symmetrically 1-Lipschitz: $S'(f(b_i), f(b_j)) \le S(b_i, b_j)$ for all $b_i, b_j$, where $S$ and $S'$ are the symmetrizations of $d$ and $d'$;
- $f$ preserves the potential up to a constant: $\psi'(f(b)) = \psi(b) + c$ for some constant $c \in \mathbb{R}$.

**Definition 16.30 (Category $\mathbf{CQM}$).** The *category of complex quasi-metric spaces* $\mathbf{CQM}$ has complex quasi-metric spaces as objects and morphisms as defined above.

**Proposition 16.31.** $\mathbf{CQM}$ is a category.

*Proof.* Identities: the identity map $\mathrm{id}_\mathcal{B}$ is symmetrically 1-Lipschitz and preserves $\psi$ with $c = 0$. Composition: if $f$ and $g$ are morphisms, then $g \circ f$ is symmetrically 1-Lipschitz (composition of symmetrically 1-Lipschitz maps) and preserves $\psi$ with the sum of the constants. $\square$

**Remark 16.32.** The category $\mathbf{CQM}$ is the natural categorical setting for the theory of complex quasi-metrics. It is a category of triples $(\mathcal{B}, d, \psi)$, which is equivalent to the category of complex quasi-metrics $Q = d + i\delta\psi$ (since $\psi$ is determined up to a constant).

**Remark 16.33.** The symmetrized Lipschitz condition is the natural one for $\mathbf{CQM}$, because the complex quasi-metric involves both $d$ and $\psi$, and the symmetrized condition is the one compatible with the adjunction $\Sigma \dashv \iota$.

**Remark 16.34 (Why not the comma category).** The naive attempt to situate $Q$ in the comma category of the symmetrization adjunction fails because the modulus $|Q|$ and the symmetrization $S$ are not comparable in general. The correct categorical setting is the $\mathbb{Z}/2$-graded category $\mathbf{CQM}$, which encodes both the cost $d$ and the potential $\psi$ as separate data. The comma category provides a useful heuristic (§16.9), but the precise setting is $\mathbf{CQM}$.

---

## 16.7 The forgetful functors

We now study the forgetful functors from $\mathbf{CQM}$.

**Definition 16.35 (Cost forgetful functor).** The *cost forgetful functor* is

$$U_d : \mathbf{CQM} \to \mathbf{QPM}_S, \qquad U_d(\mathcal{B}, d, \psi) := (\mathcal{B}, d),$$

with $U_d(f) := f$.

**Definition 16.36 (Debt forgetful functor).** The *debt forgetful functor* is

$$U_\psi : \mathbf{CQM} \to \mathbf{Set}^\mathbb{R}, \qquad U_\psi(\mathcal{B}, d, \psi) := \psi,$$

where $\mathbf{Set}^\mathbb{R}$ is the category of functions $\mathcal{B} \to \mathbb{R}$ (with the obvious morphisms).

**Proposition 16.37.** Both $U_d$ and $U_\psi$ are functors.

*Proof.* Immediate from the definitions. $\square$

**Proposition 16.38 (Relationship to symmetrization).** The composition $\Sigma \circ U_d : \mathbf{CQM} \to \mathbf{PM}$ sends a complex quasi-metric space $(\mathcal{B}, d, \psi)$ to its symmetrized space $(\mathcal{B}, S)$.

*Proof.* $\Sigma(U_d(\mathcal{B}, d, \psi)) = \Sigma(\mathcal{B}, d) = (\mathcal{B}, S)$. $\square$

**Remark 16.39.** The two forgetful functors extract the two pieces of data from a complex quasi-metric space: the cost $d$ and the potential $\psi$. Together, they determine $Q$.

**Remark 16.40.** The category $\mathbf{CQM}$ is the "product" of the categories $\mathbf{QPM}_S$ and $\mathbf{Set}^\mathbb{R}$, with the compatibility condition that the potential is defined on the same underlying set as the cost. This is a *fibered product*, not a direct product: the two functors share the underlying set.

---

## 16.8 The $\mathbb{Z}/2$-grading and the category

We now connect the $\mathbb{Z}/2$-grading to the categorical picture.

**Definition 16.41 ($\mathbb{Z}/2$-graded category).** A *$\mathbb{Z}/2$-graded category* is a category $\mathcal{C}$ equipped with a functor $T : \mathcal{C} \to \mathcal{C}$ with $T^2 = \mathrm{id}$.

**Proposition 16.42.** The category $\mathbf{CQM}$ is $\mathbb{Z}/2$-graded by the functor $T$ that sends $(\mathcal{B}, d, \psi)$ to $(\mathcal{B}, d, -\psi)$.

*Proof.* $T^2 = \mathrm{id}$ since $-\psi$ negated twice is $\psi$. We must check that $T$ is a functor: if $f : (\mathcal{B}, d, \psi) \to (\mathcal{B}', d', \psi')$ is a morphism with $\psi'(f(b)) = \psi(b) + c$, then $f : (\mathcal{B}, d, -\psi) \to (\mathcal{B}', d', -\psi')$ is a morphism with $-\psi'(f(b)) = -\psi(b) - c$, which is of the form $(-\psi)(b) + c'$ with $c' = -c$. So $T(f) := f$ is a morphism. $\square$

**Remark 16.43.** The functor $T$ reverses the sign of the potential, which reverses the sign of the debt. This is the categorical version of the $\mathbb{Z}/2$-grading.

**Remark 16.44.** The $\mathbb{Z}/2$-grading of $\mathbf{CQM}$ is the categorical content of the $\mathbb{Z}/2$-grading of the complex quasi-metric. The even part is the cost $d$; the odd part is the debt $D = \delta\psi$.

**Proposition 16.45 (Fixed points of $T$).** The fixed points of $T$ are the complex quasi-metric spaces with $\psi = 0$ (constant potential).

*Proof.* $T(\mathcal{B}, d, \psi) = (\mathcal{B}, d, -\psi) = (\mathcal{B}, d, \psi)$ iff $\psi = -\psi$ iff $\psi = 0$ (up to a constant). $\square$

**Remark 16.46.** The fixed points of $T$ are the "purely metric" complex quasi-metric spaces, with no debt. They form the subcategory $\mathbf{QPM}_S$ (viewed as a subcategory of $\mathbf{CQM}$ via $\psi = 0$).

**Proposition 16.47 (Orbits of $T$).** The orbits of $T$ are the pairs $\{(\mathcal{B}, d, \psi), (\mathcal{B}, d, -\psi)\}$. The orbit has size 1 if $\psi$ is constant, and size 2 otherwise.

*Proof.* Immediate. $\square$

**Remark 16.48.** The orbits of $T$ are the "gauge orbits" of the $\mathbb{Z}/2$-grading. They are the categorical version of the sign ambiguity of the debt.

---

## 16.9 The categorical picture: summary

We summarize the categorical picture in a single table.

| **Category** | **Objects** | **Morphisms** |
|---|---|---|
| $\mathbf{QPM}$ | Quasi-pseudometric spaces | 1-Lipschitz maps |
| $\mathbf{QPM}_S$ | Quasi-pseudometric spaces | Symmetrically 1-Lipschitz maps |
| $\mathbf{PM}$ | Pseudometric spaces | 1-Lipschitz maps |
| $\mathbf{Met}$ | Metric spaces | 1-Lipschitz maps |
| $\mathbf{CQM}$ | Complex quasi-metric spaces | Symmetrically 1-Lipschitz, potential-preserving |

**Key results:**

- **Inclusions.** $\mathbf{Met} \hookrightarrow \mathbf{PM} \hookrightarrow \mathbf{QPM}_S$ (Proposition 16.6).
- **Symmetrization functor.** $\Sigma : \mathbf{QPM}_S \to \mathbf{PM}$ (Definition 16.10).
- **Inclusion functor.** $\iota : \mathbf{PM} \hookrightarrow \mathbf{QPM}_S$ (Definition 16.14).
- **Adjunction.** $\Sigma \dashv \iota$ (Theorem 16.24). The symmetrization functor is left adjoint to the inclusion.
- **Category of complex quasi-metrics.** $\mathbf{CQM}$ (Definition 16.30).
- **Forgetful functors.** $U_d : \mathbf{CQM} \to \mathbf{QPM}_S$ and $U_\psi : \mathbf{CQM} \to \mathbf{Set}^\mathbb{R}$ (Definitions 16.35, 16.36).
- **$\mathbb{Z}/2$-grading.** $\mathbf{CQM}$ is $\mathbb{Z}/2$-graded by $\psi \mapsto -\psi$ (Proposition 16.42).
- **Fixed points.** The fixed points of the grading are the purely metric spaces (Proposition 16.45).
- **Orbits.** The orbits of the grading are the pairs $\{(\mathcal{B}, d, \psi), (\mathcal{B}, d, -\psi)\}$ (Proposition 16.47).

The categorical picture situates the complex quasi-metric in the general framework of category theory. It reveals the complex quasi-metric as a $\mathbb{Z}/2$-graded object in the category $\mathbf{CQM}$, and it connects the theory to the symmetrization adjunction and to the general theory of graded categories.

---

## 16.10 The comma category: a heuristic

We close this chapter with a heuristic discussion of the comma category.

**Heuristic 16.49.** The complex quasi-metric $Q = d + iD$ can be viewed as an object of the comma category of the symmetrization adjunction, in the following sense: it is a "defect" of the symmetrization $\Sigma$. The symmetrization $\Sigma(d) = S$ is a pseudometric; the complex quasi-metric $Q = d + iD$ is a "correction" of $S$ by the asymmetric part $A$ and the debt $D$. The correction is measured by the difference between $Q$ and $S$.

**Remark 16.50.** The heuristic is not a theorem. The precise categorical statement is that $\mathbf{CQM}$ is a $\mathbb{Z}/2$-graded category, not a comma category. But the heuristic is suggestive: it suggests that the complex quasi-metric is a "defect" of symmetrization, and that the theory is a theory of such defects.

**Remark 16.51.** The heuristic is useful for intuition but should not be taken too literally. The precise categorical content of the theory is captured by the category $\mathbf{CQM}$ and its $\mathbb{Z}/2$-grading, not by the comma category.

**Remark 16.52.** The comma category might be the right setting for a *generalization* of the theory, in which the debt is not necessarily exact. In that case, the complex quasi-metric would be an object of a comma category of the symmetrization adjunction, with the debt playing the role of the "defect" of symmetrization. This is a direction for future work.

---

## 16.11 Exercises

**Exercise 16.1.** Verify that $\mathbf{QPM}$, $\mathbf{PM}$, and $\mathbf{Met}$ are categories.

**Exercise 16.2.** Prove that $\Sigma : \mathbf{QPM}_S \to \mathbf{PM}$ is a functor.

**Exercise 16.3.** Show that $\Sigma \circ \iota = \mathrm{id}_{\mathbf{PM}}$.

**Exercise 16.4.** Show that $\iota \circ \Sigma$ is a projection on $\mathbf{QPM}_S$.

**Exercise 16.5.** Prove the adjunction $\Sigma \dashv \iota$.

**Exercise 16.6.** Verify that $\mathbf{CQM}$ is a category.

**Exercise 16.7.** Show that $\mathbf{CQM}$ is $\mathbb{Z}/2$-graded by $\psi \mapsto -\psi$.

**Exercise 16.8.** Prove that the fixed points of the grading are the purely metric spaces.

**Exercise 16.9.** Give an example of a morphism in $\mathbf{CQM}$ that is not an isomorphism.

**Exercise 16.10 (Reflection question).** Is the categorical picture the "right" foundation for the theory, or is it a higher-level description of a more fundamental structure? Write a short essay (one page) arguing for your position.


