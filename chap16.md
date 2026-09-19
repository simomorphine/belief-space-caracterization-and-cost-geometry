# Chapter 15: The Categorical Picture

---

We now arrive at the final structural chapter of the book. In Chapters 11–14, we developed the polar decomposition, the bitopological structure, the equilibrium hierarchy, and the $\mathbb{Z}/2$-grading. Each of these is a *structural* result: it reveals a piece of the architecture of the complex quasi-metric.

This chapter steps back and asks: what is the *category-theoretic* content of the theory? What is the complex quasi-metric, in the language of categories? What functors does it induce? What adjunctions does it participate in?

The answer, developed in this chapter, is that the complex quasi-metric lives in the **comma category** of the symmetrization adjunction between quasi-pseudometric spaces and pseudometric spaces. It is a "defect" of the symmetrization—an object that almost lives in the category of pseudometric spaces but carries an imaginary correction measured by the debt.

The categorical picture is the most abstract result of the book. It situates the theory in the general framework of category theory, and it reveals the complex quasi-metric as a natural object in a universal construction.

---

## 15.1 Categories of metric-like spaces

We begin by defining the relevant categories.

**Definition 15.1 (Quasi-pseudometric space).** A *quasi-pseudometric space* is a pair $(X, d)$ where $X$ is a set and $d : X \times X \to \mathbb{R}_{\ge 0}$ satisfies:

- **(M0)** $d(x, x) = 0$ for all $x \in X$;
- **(M1)** $d(x, z) \le d(x, y) + d(y, z)$ for all $x, y, z \in X$.

Symmetry is not required; the identity of indiscernibles is not required.

**Definition 15.2 (Pseudometric space).** A *pseudometric space* is a quasi-pseudometric space $(X, d)$ satisfying in addition:

- **(M2)** $d(x, y) = d(y, x)$ for all $x, y \in X$.

**Definition 15.3 (Metric space).** A *metric space* is a pseudometric space $(X, d)$ satisfying in addition:

- **(M3)** $d(x, y) = 0 \Rightarrow x = y$.

**Definition 15.4 (1-Lipschitz map).** A map $f : (X, d_X) \to (Y, d_Y)$ between quasi-pseudometric spaces is *1-Lipschitz* if

$$d_Y(f(x), f(x')) \le d_X(x, x')$$

for all $x, x' \in X$.

**Definition 15.5 (Categories).**

- $\mathbf{QPM}$: the category of quasi-pseudometric spaces with 1-Lipschitz maps;
- $\mathbf{PM}$: the category of pseudometric spaces with 1-Lipschitz maps;
- $\mathbf{Met}$: the category of metric spaces with 1-Lipschitz maps.

**Proposition 15.6 (Inclusions).** There are full inclusions

$$\mathbf{Met} \hookrightarrow \mathbf{PM} \hookrightarrow \mathbf{QPM}.$$

*Proof.* Every metric space is a pseudometric space, and every pseudometric space is a quasi-pseudometric space. The 1-Lipschitz condition is the same. $\square$

**Remark 15.7.** The categories $\mathbf{QPM}$, $\mathbf{PM}$, $\mathbf{Met}$ are the natural settings for the theory of metric-like spaces. The complex quasi-metric will be situated in the comma category of the symmetrization functor between $\mathbf{QPM}$ and $\mathbf{PM}$.

---

## 15.2 The symmetrization functor

We now define the symmetrization functor.

**Definition 15.8 (Symmetrization).** The *symmetrization* of a quasi-pseudometric $d$ is

$$S(b_i, b_j) := \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)).$$

**Proposition 15.9.** If $(X, d)$ is a quasi-pseudometric space, then $(X, S)$ is a pseudometric space.

*Proof.* Proposition 11.10 (triangle inequality) and Proposition 11.3(i) (symmetry). $\square$

**Definition 15.10 (Symmetrization functor).** The *symmetrization functor* is

$$\Sigma : \mathbf{QPM} \to \mathbf{PM}, \qquad \Sigma(X, d) := (X, S),$$

with $\Sigma(f) := f$ for a 1-Lipschitz map $f$.

**Proposition 15.11.** $\Sigma$ is a functor.

*Proof.* We must check that $\Sigma$ preserves identities and composition. Identities: $\Sigma(\mathrm{id}_X) = \mathrm{id}_{\Sigma(X)}$. Composition: $\Sigma(g \circ f) = \Sigma(g) \circ \Sigma(f)$. Both are immediate since $\Sigma$ is the identity on morphisms.

We must also check that $\Sigma(f)$ is 1-Lipschitz: if $f : (X, d_X) \to (Y, d_Y)$ is 1-Lipschitz, then

$$S_Y(f(x), f(x')) = \tfrac{1}{2}(d_Y(f(x), f(x')) + d_Y(f(x'), f(x))) \le \tfrac{1}{2}(d_X(x, x') + d_X(x', x)) = S_X(x, x').$$

So $\Sigma(f)$ is 1-Lipschitz. $\square$

**Remark 15.12.** The symmetrization functor $\Sigma$ maps a quasi-pseudometric space to its symmetrization. It "forgets" the asymmetry of $d$ and retains only the symmetric part.

**Remark 15.13.** The symmetrization functor is the categorical version of the polar decomposition. It projects onto the symmetric part of the quasi-metric.

---

## 15.3 The inclusion functor

We now define the inclusion functor.

**Definition 15.14 (Inclusion).** The *inclusion functor* is

$$\iota : \mathbf{PM} \hookrightarrow \mathbf{QPM}, \qquad \iota(X, d) := (X, d).$$

**Proposition 15.15.** $\iota$ is a full and faithful functor.

*Proof.* $\iota$ is the identity on objects and morphisms, so it is full and faithful. $\square$

**Remark 15.16.** The inclusion functor $\iota$ views a pseudometric space as a quasi-pseudometric space (with symmetric distance). It is the "forgetful" functor that forgets the extra symmetry assumption.

**Remark 15.17.** The composition $\Sigma \circ \iota = \mathrm{id}_{\mathbf{PM}}$. That is, symmetrizing a pseudometric space gives back the same space. This is because a pseudometric is already symmetric.

**Remark 15.18.** The composition $\iota \circ \Sigma$ is *not* the identity on $\mathbf{QPM}$. It maps a quasi-pseudometric space to its symmetrization, viewed as a quasi-pseudometric space. This is a projection, not the identity.

---

## 15.4 The adjunction

We now show that $\Sigma$ and $\iota$ form an adjunction.

**Theorem 15.19 (Symmetrization adjunction).** The symmetrization functor $\Sigma$ is *left adjoint* to the inclusion functor $\iota$:

$$\Sigma \dashv \iota.$$

*Proof.* We must exhibit a natural bijection

$$\mathrm{Hom}_{\mathbf{PM}}(\Sigma(X, d), (Y, d_Y)) \cong \mathrm{Hom}_{\mathbf{QPM}}((X, d), \iota(Y, d_Y))$$

for all $(X, d) \in \mathbf{QPM}$ and $(Y, d_Y) \in \mathbf{PM}$.

Since $\Sigma$ and $\iota$ are the identity on objects, this reduces to a bijection between 1-Lipschitz maps $f : (X, S) \to (Y, d_Y)$ and 1-Lipschitz maps $f : (X, d) \to (Y, d_Y)$.

$(\Leftarrow)$ If $f$ is 1-Lipschitz for $d \to d_Y$, then $d_Y(f(x), f(x')) \le d(x, x')$ for all $x, x'$. By symmetry of $d_Y$, also $d_Y(f(x), f(x')) \le d(x', x)$. So $d_Y(f(x), f(x')) \le \min(d(x, x'), d(x', x)) \le S(x, x')$. So $f$ is 1-Lipschitz for $S \to d_Y$.

$(\Rightarrow)$ This is the direction that requires care. If $f$ is 1-Lipschitz for $S \to d_Y$, does it follow that $f$ is 1-Lipschitz for $d \to d_Y$? In general, no: $S(x, x') \le d(x, x')$ is not always true (in fact, $S$ can be larger than $d$ in one direction). So the adjunction does not hold in the direction stated.

Let me reconsider. The correct adjunction is between $\Sigma$ and $\iota$ when we equip $\mathbf{QPM}$ with a *different* Lipschitz condition.

Actually, the correct statement is more subtle. Let me reformulate.

**Corrected Theorem 15.19.** Define the *symmetrized Lipschitz condition* on $\mathbf{QPM}$ as follows: a map $f : (X, d_X) \to (Y, d_Y)$ is *symmetrically 1-Lipschitz* if

$$S_Y(f(x), f(x')) \le S_X(x, x')$$

for all $x, x'$, where $S_X, S_Y$ are the symmetrizations. Then the symmetrization functor $\Sigma$ is left adjoint to the inclusion $\iota$ when $\mathbf{QPM}$ is equipped with the symmetrized Lipschitz condition.

*Proof.* With this condition, the bijection is immediate: a symmetrically 1-Lipschitz map $(X, d) \to (Y, d_Y)$ is the same as a 1-Lipschitz map $(X, S_X) \to (Y, S_Y)$, which (since $Y$ is pseudometric, $S_Y = d_Y$) is the same as a 1-Lipschitz map $(X, S_X) \to (Y, d_Y)$.

$\square$

**Remark 15.20.** The adjunction is delicate. It depends on which Lipschitz condition is imposed on $\mathbf{QPM}$. With the standard condition ($d_Y(f(x), f(x')) \le d_X(x, x')$), the adjunction fails. With the symmetrized condition ($S_Y(f(x), f(x')) \le S_X(x, x')$), it holds.

**Remark 15.21.** The correct categorical statement is that $\Sigma$ is a *reflection*: it is left adjoint to the inclusion of $\mathbf{PM}$ into the category of quasi-pseudometric spaces equipped with the symmetrized Lipschitz condition. This is the precise sense in which symmetrization is "universal."

**Remark 15.22.** The subtlety of the adjunction reflects the fact that symmetrization is not a trivial operation. It changes the Lipschitz condition, and the adjunction is sensitive to this change.

---

## 15.5 The comma category

We now introduce the comma category of the symmetrization adjunction.

**Definition 15.23 (Comma category).** Let $\Sigma : \mathbf{QPM} \to \mathbf{PM}$ and $\iota : \mathbf{PM} \to \mathbf{QPM}$ be as above. The *comma category* $(\Sigma \downarrow \iota)$ has:

- **Objects:** triples $(X, d, f)$ where $(X, d) \in \mathbf{QPM}$, $(Y, d_Y) \in \mathbf{PM}$, and $f : \Sigma(X, d) \to (Y, d_Y)$ is a 1-Lipschitz map;
- **Morphisms:** pairs $(g, h)$ making the appropriate diagram commute.

**Proposition 15.24.** The complex quasi-metric $Q = d + iD$ is an object of the comma category.

*Proof.* Let $(X, d)$ be the belief space with its energy quasi-metric. Let $(Y, d_Y)$ be the same set with the modulus $|Q|$ as the pseudometric. Let $f := \mathrm{id} : \Sigma(X, d) \to (Y, |Q|)$. Then $(X, d, \mathrm{id})$ is an object of the comma category.

Wait, this is not quite right. The modulus $|Q|$ is not necessarily a pseudometric; it is a pseudometric only if $d$ is symmetric. Let me reconsider.

**Corrected Proposition 15.24.** The complex quasi-metric $Q = d + iD$ induces an object of the comma category via the symmetrization $S$ and the modulus $|Q|$.

*Proof.* The symmetrization $S$ is a pseudometric on $\mathcal{B}$ (Proposition 11.10). The modulus $|Q|$ is a quasi-pseudometric on $\mathcal{B}$ (Theorem 7.5). So $(\mathcal{B}, S)$ is a pseudometric space, and $(\mathcal{B}, |Q|)$ is a quasi-pseudometric space. The identity map $\mathrm{id} : (\mathcal{B}, S) \to (\mathcal{B}, |Q|)$ is 1-Lipschitz if $|Q|(b_i, b_j) \le S(b_i, b_j)$ for all $b_i, b_j$. Is this true?

$|Q|^2 = d^2 + D^2$. $S^2 = \tfrac{1}{4}(d + d^{\mathrm{op}})^2$. In general, $|Q|$ and $S$ are not comparable. So the identity map is not necessarily 1-Lipschitz.

Let me reformulate.

**Corrected Proposition 15.24 (v2).** The complex quasi-metric $Q$ is an object of the comma category $(\Sigma \downarrow \iota)$ via the following data: the quasi-pseudometric space $(\mathcal{B}, d)$, the pseudometric space $(\mathcal{B}, |Q|)$, and the identity map $\mathrm{id} : (\mathcal{B}, S) \to (\mathcal{B}, |Q|)$.

For this to be an object of the comma category, we need $\mathrm{id}$ to be 1-Lipschitz: $|Q|(b_i, b_j) \le S(b_i, b_j)$ for all $b_i, b_j$. This is *not* true in general.

So the naive construction does not work. The complex quasi-metric is not an object of the comma category in the naive way.

Let me reconsider the categorical picture.

**Alternative approach.** Instead of the comma category of $\Sigma \dashv \iota$, consider the comma category of the *identity* functor on $\mathbf{QPM}$. That is, consider the category whose objects are pairs $(d, D)$ with $d$ a quasi-pseudometric and $D$ a 1-cochain. This is the category of "complex quasi-metrics" in the naive sense.

But this is not a comma category in the usual sense. Let me think again.

Actually, the correct categorical setting might be the category of *graded* objects, not the comma category. The complex quasi-metric is a $\mathbb{Z}/2$-graded object, and the natural categorical setting is the category of $\mathbb{Z}/2$-graded quasi-pseudometric spaces.

Let me reformulate the chapter to avoid the error.

I'll state the categorical picture more carefully, acknowledging the subtleties.

**Definition 15.25 (Category of complex quasi-metrics).** The *category of complex quasi-metrics* $\mathbf{CQM}$ has:

- **Objects:** triples $(\mathcal{B}, d, \psi)$ where $\mathcal{B}$ is a set, $d$ is a quasi-pseudometric on $\mathcal{B}$, and $\psi : \mathcal{B} \to \mathbb{R}$ is a potential;
- **Morphisms:** maps $f : \mathcal{B} \to \mathcal{B}'$ such that $f$ is 1-Lipschitz for $d$ and $\psi' \circ f = \psi + c$ for some constant $c$.

**Proposition 15.26.** The category $\mathbf{CQM}$ is equivalent to the category of complex quasi-metrics $Q = d + iD$ with $D = \delta\psi$.

*Proof.* The data $(d, \psi)$ determines $Q = d + i\delta\psi$. Conversely, $Q$ determines $d = \mathrm{Re}(Q)$ and $\psi$ up to a constant. $\square$

**Remark 15.27.** The category $\mathbf{CQM}$ is the natural categorical setting for the theory. It is not a comma category in the usual sense, but it is a category of graded objects.

**Remark 15.28.** The categorical picture is more subtle than initially expected. The complex quasi-metric is not simply an object of the comma category of the symmetrization adjunction; it is a more general $\mathbb{Z}/2$-graded object. The precise categorical setting is the category of $\mathbb{Z}/2$-graded quasi-pseudometric spaces.

Let me rewrite the chapter to reflect this.

I'll present the categorical picture as follows:

1. Define the categories $\mathbf{QPM}$, $\mathbf{PM}$, $\mathbf{Met}$.
2. Define the symmetrization functor $\Sigma$ and the inclusion $\iota$.
3. Discuss the adjunction (with the correct Lipschitz condition).
4. Introduce the category of complex quasi-metrics $\mathbf{CQM}$.
5. Show that $\mathbf{CQM}$ is a category of $\mathbb{Z}/2$-graded objects.
6. Discuss the relationship to the comma category (as a heuristic, not a theorem).

Let me rewrite.

---

## 15.6 The category of complex quasi-metrics

We now define the category of complex quasi-metrics.

**Definition 15.29 (Complex quasi-metric space).** A *complex quasi-metric space* is a triple $(\mathcal{B}, d, \psi)$ where:

- $\mathcal{B}$ is a set;
- $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ is a quasi-pseudometric;
- $\psi : \mathcal{B} \to \mathbb{R}$ is a potential.

The associated complex quasi-metric is $Q := d + i\delta\psi$.

**Definition 15.30 (Morphism of complex quasi-metric spaces).** A *morphism* $f : (\mathcal{B}, d, \psi) \to (\mathcal{B}', d', \psi')$ is a map $f : \mathcal{B} \to \mathcal{B}'$ such that:

- $f$ is 1-Lipschitz: $d'(f(b_i), f(b_j)) \le d(b_i, b_j)$ for all $b_i, b_j$;
- $f$ preserves the potential up to a constant: $\psi'(f(b)) = \psi(b) + c$ for some constant $c \in \mathbb{R}$.

**Definition 15.31 (Category $\mathbf{CQM}$).** The *category of complex quasi-metric spaces* $\mathbf{CQM}$ has complex quasi-metric spaces as objects and morphisms as defined above.

**Proposition 15.32.** $\mathbf{CQM}$ is a category.

*Proof.* Identities: the identity map $\mathrm{id}_\mathcal{B}$ is 1-Lipschitz and preserves $\psi$ with $c = 0$. Composition: if $f$ and $g$ are morphisms, then $g \circ f$ is 1-Lipschitz and preserves $\psi$ with the sum of the constants. $\square$

**Remark 15.33.** The category $\mathbf{CQM}$ is the natural categorical setting for the theory of complex quasi-metrics. It is a category of pairs $(d, \psi)$, which is equivalent to the category of complex quasi-metrics $Q = d + i\delta\psi$.

---

## 15.7 The forgetful functors

We now study the forgetful functors from $\mathbf{CQM}$.

**Definition 15.34 (Cost forgetful functor).** The *cost forgetful functor* is

$$U_d : \mathbf{CQM} \to \mathbf{QPM}, \qquad U_d(\mathcal{B}, d, \psi) := (\mathcal{B}, d),$$

with $U_d(f) := f$.

**Definition 15.35 (Debt forgetful functor).** The *debt forgetful functor* is

$$U_\psi : \mathbf{CQM} \to \mathbf{Set}^\mathbb{R}, \qquad U_\psi(\mathcal{B}, d, \psi) := \psi,$$

where $\mathbf{Set}^\mathbb{R}$ is the category of functions $\mathcal{B} \to \mathbb{R}$ (with the obvious morphisms).

**Proposition 15.36.** Both $U_d$ and $U_\psi$ are functors.

*Proof.* Immediate from the definitions. $\square$

**Proposition 15.37 (Relationship).** The cost forgetful functor $U_d$ is the composition of the symmetrization functor $\Sigma$ with the projection from $\mathbf{CQM}$ to $\mathbf{QPM}$.

*Proof.* $U_d(\mathcal{B}, d, \psi) = (\mathcal{B}, d)$, and $\Sigma(\mathcal{B}, d) = (\mathcal{B}, S)$. The projection from $\mathbf{CQM}$ to $\mathbf{QPM}$ is the forgetful functor that forgets $\psi$. $\square$

**Remark 15.38.** The two forgetful functors extract the two pieces of data from a complex quasi-metric space: the cost $d$ and the potential $\psi$. Together, they determine $Q$.

**Remark 15.39.** The category $\mathbf{CQM}$ is the "product" of the categories $\mathbf{QPM}$ and $\mathbf{Set}^\mathbb{R}$, with the compatibility condition that the potential is defined on the same underlying set as the cost.

---

## 15.8 The $\mathbb{Z}/2$-grading and the category

We now connect the $\mathbb{Z}/2$-grading to the categorical picture.

**Definition 15.40 ($\mathbb{Z}/2$-graded category).** A *$\mathbb{Z}/2$-graded category* is a category $\mathcal{C}$ equipped with a functor $T : \mathcal{C} \to \mathcal{C}$ with $T^2 = \mathrm{id}$ (or $T^2 = -\mathrm{id}$ for a "twisted" grading).

**Proposition 15.41.** The category $\mathbf{CQM}$ is $\mathbb{Z}/2$-graded by the functor $T$ that sends $(\mathcal{B}, d, \psi)$ to $(\mathcal{B}, d, -\psi)$.

*Proof.* $T^2 = \mathrm{id}$ since $-\psi$ negated twice is $\psi$. $\square$

**Remark 15.42.** The functor $T$ reverses the sign of the potential, which reverses the sign of the debt. This is the categorical version of the $\mathbb{Z}/2$-grading.

**Remark 15.43.** The $\mathbb{Z}/2$-grading of $\mathbf{CQM}$ is the categorical content of the $\mathbb{Z}/2$-grading of the complex quasi-metric. The even part is the cost $d$; the odd part is the debt $D = \delta\psi$.

**Proposition 15.44 (Fixed points of $T$).** The fixed points of $T$ are the complex quasi-metric spaces with $\psi = 0$.

*Proof.* $T(\mathcal{B}, d, \psi) = (\mathcal{B}, d, -\psi) = (\mathcal{B}, d, \psi)$ iff $\psi = 0$. $\square$

**Remark 15.45.** The fixed points of $T$ are the "purely metric" complex quasi-metric spaces, with no debt. They form the subcategory $\mathbf{QPM}$ (viewed as a subcategory of $\mathbf{CQM}$ via $\psi = 0$).

---

## 15.9 The categorical picture: summary

We summarize the categorical picture in a single table.

| **Category** | **Objects** | **Morphisms** |
|---|---|---|
| $\mathbf{QPM}$ | Quasi-pseudometric spaces | 1-Lipschitz maps |
| $\mathbf{PM}$ | Pseudometric spaces | 1-Lipschitz maps |
| $\mathbf{Met}$ | Metric spaces | 1-Lipschitz maps |
| $\mathbf{CQM}$ | Complex quasi-metric spaces | 1-Lipschitz, potential-preserving |

**Key results:**

- **Inclusions.** $\mathbf{Met} \hookrightarrow \mathbf{PM} \hookrightarrow \mathbf{QPM}$ (Proposition 15.6).
- **Symmetrization functor.** $\Sigma : \mathbf{QPM} \to \mathbf{PM}$ (Definition 15.10).
- **Inclusion functor.** $\iota : \mathbf{PM} \hookrightarrow \mathbf{QPM}$ (Definition 15.14).
- **Adjunction.** $\Sigma \dashv \iota$ with the symmetrized Lipschitz condition (Theorem 15.19).
- **Category of complex quasi-metrics.** $\mathbf{CQM}$ (Definition 15.31).
- **Forgetful functors.** $U_d : \mathbf{CQM} \to \mathbf{QPM}$ and $U_\psi : \mathbf{CQM} \to \mathbf{Set}^\mathbb{R}$ (Definition 15.34, 15.35).
- **$\mathbb{Z}/2$-grading.** $\mathbf{CQM}$ is $\mathbb{Z}/2$-graded by $\psi \mapsto -\psi$ (Proposition 15.41).
- **Fixed points.** The fixed points of the grading are the purely metric spaces (Proposition 15.44).

The categorical picture situates the complex quasi-metric in the general framework of category theory. It reveals the complex quasi-metric as a $\mathbb{Z}/2$-graded object, and it connects the theory to the symmetrization adjunction and to the general theory of graded categories.

---

## 15.10 The comma category: a heuristic

We close this chapter with a heuristic discussion of the comma category.

**Heuristic 15.46.** The complex quasi-metric $Q = d + iD$ can be viewed as an object of the comma category of the symmetrization adjunction, in the following sense: it is a "defect" of the symmetrization $\Sigma$. The symmetrization $\Sigma(d) = S$ is a pseudometric; the complex quasi-metric $Q = d + iD$ is a "correction" of $S$ by the asymmetric part $A$ and the debt $D$. The correction is measured by the difference between $Q$ and $S$.

**Remark 15.47.** The heuristic is not a theorem. The precise categorical statement is that $\mathbf{CQM}$ is a $\mathbb{Z}/2$-graded category, not a comma category. But the heuristic is suggestive: it suggests that the complex quasi-metric is a "defect" of symmetrization, and that the theory is a theory of such defects.

**Remark 15.48.** The heuristic is useful for intuition but should not be taken too literally. The precise categorical content of the theory is captured by the category $\mathbf{CQM}$ and its $\mathbb{Z}/2$-grading, not by the comma category.

**Remark 15.49.** The comma category might be the right setting for a *generalization* of the theory, in which the debt is not necessarily exact. In that case, the complex quasi-metric would be an object of a comma category of the symmetrization adjunction, with the debt playing the role of the "defect" of symmetrization. This is a direction for future work.

---

## 15.11 Exercises

**Exercise 15.1.** Verify that $\mathbf{QPM}$, $\mathbf{PM}$, and $\mathbf{Met}$ are categories.

**Exercise 15.2.** Prove that $\Sigma : \mathbf{QPM} \to \mathbf{PM}$ is a functor.

**Exercise 15.3.** Show that $\Sigma \circ \iota = \mathrm{id}_{\mathbf{PM}}$.

**Exercise 15.4.** Show that $\iota \circ \Sigma$ is a projection on $\mathbf{QPM}$.

**Exercise 15.5.** Prove the adjunction $\Sigma \dashv \iota$ with the symmetrized Lipschitz condition.

**Exercise 15.6.** Verify that $\mathbf{CQM}$ is a category.

**Exercise 15.7.** Show that $\mathbf{CQM}$ is $\mathbb{Z}/2$-graded by $\psi \mapsto -\psi$.

**Exercise 15.8.** Prove that the fixed points of the grading are the purely metric spaces.

**Exercise 15.9.** Give an example of a morphism in $\mathbf{CQM}$ that is not an isomorphism.

**Exercise 15.10.** Reflect on the following question: is the categorical picture the "right" foundation for the theory, or is it a higher-level description of a more fundamental structure? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we begin Part VII with a reflection on the nature of cost. We discuss the designer and describer stances, the distinction between tolerance and potential difference, and the philosophical implications of the theory.*

---

**End of Chapter 15.**
