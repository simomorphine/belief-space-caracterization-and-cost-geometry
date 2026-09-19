# Chapter 4: Exactness

---

In Chapter 3, we introduced the debt function $D$ via two axioms: additivity and antisymmetry. We showed that these axioms imply identity, cycle invariance, path independence, and gauge invariance. We also noted that every potential difference $\psi(b_j) - \psi(b_i)$ satisfies the axioms.

The central question of this chapter is the converse: does *every* debt function arise from a potential? The answer is yes, and the proof is the content of the **basepoint theorem**. This theorem is the foundational result of the entire theory. It says that debt is always exact—always a coboundary, always integrable, always a gradient.

---

## 4.1 The basepoint theorem

Let us state the theorem precisely.

**Theorem 4.1 (Basepoint theorem).** Let $\mathcal{B}$ be a set and let $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ satisfy:

- **(D1) Additivity.** $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$ for all $b_i, b_j, b_k \in \mathcal{B}$;
- **(D2) Antisymmetry.** $D(b_i, b_j) = -D(b_j, b_i)$ for all $b_i, b_j \in \mathcal{B}$.

Then for any choice of basepoint $s_0 \in \mathcal{B}$, the function

$$\psi_{s_0}(b) := D(s_0, b)$$

satisfies

$$D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)$$

for all $b_i, b_j \in \mathcal{B}$. Moreover, $\psi_{s_0}$ is unique up to an additive constant: if $\psi$ also satisfies $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$, then $\psi = \psi_{s_0} + c$ for some $c \in \mathbb{R}$.

**Remark 4.2.** The theorem says three things. First, the function $\psi_{s_0}(b) := D(s_0, b)$ is a valid potential. Second, it represents $D$ as a potential difference. Third, any other potential differs from $\psi_{s_0}$ by a constant. The basepoint $s_0$ is arbitrary; different choices of $s_0$ give potentials that differ by constants.

**Remark 4.3.** The theorem is constructive. Given $D$ and a basepoint $s_0$, the potential is computed by a single evaluation per point: $\psi_{s_0}(b) = D(s_0, b)$. No integration, no path-independence argument, no choice of paths. This is the discrete analogue of the fundamental theorem of calculus.

---

## 4.2 Proof of the basepoint theorem

We prove the theorem in three steps.

**Step 1: Construction.** Fix a basepoint $s_0 \in \mathcal{B}$. Define $\psi_{s_0}(b) := D(s_0, b)$ for all $b \in \mathcal{B}$.

**Step 2: Representation.** We claim that $\psi_{s_0}(b_j) - \psi_{s_0}(b_i) = D(b_i, b_j)$ for all $b_i, b_j \in \mathcal{B}$.

Compute:

$$\psi_{s_0}(b_j) - \psi_{s_0}(b_i) = D(s_0, b_j) - D(s_0, b_i).$$

By (D2), $D(s_0, b_i) = -D(b_i, s_0)$. Hence

$$D(s_0, b_j) - D(s_0, b_i) = D(s_0, b_j) + D(b_i, s_0).$$

By (D1) applied to the triple $(b_i, s_0, b_j)$:

$$D(b_i, b_j) = D(b_i, s_0) + D(s_0, b_j).$$

Comparing the two expressions:

$$\psi_{s_0}(b_j) - \psi_{s_0}(b_i) = D(b_i, s_0) + D(s_0, b_j) = D(b_i, b_j).$$

This proves the representation.

**Step 3: Uniqueness up to constant.** Suppose $\psi$ and $\psi'$ both satisfy $D(b_i, b_j) = \psi(b_j) - \psi(b_i) = \psi'(b_j) - \psi'(b_i)$ for all $b_i, b_j$.

Then for all $b_i, b_j$:

$$\psi(b_j) - \psi'(b_j) = \psi(b_i) - \psi'(b_i).$$

Rearranging:

$$(\psi - \psi')(b_j) = (\psi - \psi')(b_i).$$

Since $b_i$ and $b_j$ are arbitrary, the function $\psi - \psi'$ is constant on $\mathcal{B}$. Hence $\psi = \psi' + c$ for some $c \in \mathbb{R}$.

This completes the proof. $\square$

**Remark 4.4.** The proof uses only the two axioms (D1) and (D2). No topology, no metric, no additional structure. The theorem is purely combinatorial. It applies to any set $\mathcal{B}$, finite or infinite, discrete or continuous, with or without a topology.

**Remark 4.5.** The key step is the identity

$$D(b_i, b_j) = D(b_i, s_0) + D(s_0, b_j),$$

which is (D1) with the middle point $s_0$. This identity says that the debt from $b_i$ to $b_j$ factors through any intermediate point, and in particular through the basepoint. This is what makes the potential $\psi_{s_0}$ well-defined.

---

## 4.3 The basepoint is a gauge choice

The basepoint theorem shows that the potential $\psi$ is unique up to an additive constant. This means that the choice of basepoint is a **gauge choice**.

**Proposition 4.6 (Change of basepoint).** Let $s_0, s_0' \in \mathcal{B}$ be two basepoints. Then

$$\psi_{s_0'}(b) = \psi_{s_0}(b) + D(s_0', s_0)$$

for all $b \in \mathcal{B}$.

*Proof.* Compute:

$$\psi_{s_0'}(b) = D(s_0', b) = D(s_0', s_0) + D(s_0, b) = D(s_0', s_0) + \psi_{s_0}(b).$$

The constant $D(s_0', s_0)$ depends only on the two basepoints, not on $b$. $\square$

**Corollary 4.7.** The set of potentials representing a given debt function $D$ is an affine space of dimension $1$: $\{\psi_{s_0} + c : c \in \mathbb{R}\}$.

**Definition 4.8 (Gauge group).** The *gauge group* of the debt function $D$ is the additive group $\mathbb{R}$, acting on potentials by $\psi \mapsto \psi + c$.

**Remark 4.9.** The gauge group is $\mathbb{R}$, not $\mathbb{R}^\mathcal{B}$ or anything larger. This is because the only freedom in the potential is the addition of a constant. The potential is otherwise determined by $D$. This is a strong statement: the potential is essentially unique.

**Remark 4.10.** The gauge group $\mathbb{R}$ is the same as the group of real numbers under addition. It acts on the space of potentials by translation. The quotient of the space of potentials by this action is the space of debt functions. In symbols:

$$\{\text{debt functions}\} \cong \{\text{potentials}\} / \mathbb{R}.$$

This is the precise statement of the relationship between potentials and debt.

---

## 4.4 The discrete fundamental theorem of calculus

The basepoint theorem has a natural interpretation as the discrete analogue of the fundamental theorem of calculus.

**The fundamental theorem of calculus.** If $f : [a, b] \to \mathbb{R}$ is differentiable and $F(x) := \int_a^x f(t) \, dt$, then $F'(x) = f(x)$.

**The discrete analogue.** If $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ satisfies (D1) and (D2), and $\psi_{s_0}(b) := D(s_0, b)$, then $D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)$.

The correspondence is:

| Continuous | Discrete |
|---|---|
| $f(x)$ | $D(b_i, b_j)$ |
| $F(x) = \int_a^x f(t) \, dt$ | $\psi_{s_0}(b) = D(s_0, b)$ |
| $F'(x) = f(x)$ | $\psi_{s_0}(b_j) - \psi_{s_0}(b_i) = D(b_i, b_j)$ |
| Integration | Summation (evaluation at basepoint) |
| Fundamental theorem | Basepoint theorem |

**Remark 4.11.** The discrete analogue is *simpler* than the continuous version. In the continuous case, the fundamental theorem requires differentiability of $F$ and integrability of $f$. In the discrete case, the basepoint theorem requires only the two axioms (D1) and (D2). No regularity conditions, no measurability, no topology. The discrete case is purely algebraic.

**Remark 4.12.** The basepoint theorem is also the discrete analogue of the statement that on a simply connected space, every closed 1-form is exact. In the discrete setting, the "space" is the complete directed graph on $\mathcal{B}$, which is simply connected in the appropriate sense. Hence every closed 1-form (i.e., every 1-cocycle) is exact (i.e., a coboundary).

---

## 4.5 The cohomological interpretation

The basepoint theorem has a clean interpretation in cohomology.

**Definition 4.13 (Cohomology of the discrete de Rham complex).** Let $\mathcal{B}$ be a set, viewed as a simplicial complex in which every finite subset is a simplex. The *k-th cohomology* of $\mathcal{B}$ with coefficients in $\mathbb{R}$ is

$$H^k(\mathcal{B}; \mathbb{R}) := \frac{\ker(\delta : C^k \to C^{k+1})}{\mathrm{im}(\delta : C^{k-1} \to C^k)}.$$

**Proposition 4.14.** $H^1(\mathcal{B}; \mathbb{R}) = 0$.

*Proof.* Let $D \in \ker(\delta : C^1 \to C^2)$ be a 1-cocycle. By Proposition 3.19, $D$ satisfies (D1). If $D$ also satisfies (D2), then by the basepoint theorem, $D = \delta\psi$ for some $\psi \in C^0$. Hence every 1-cocycle is a coboundary, so $H^1 = 0$.

(If $D$ does not satisfy (D2), then $D$ is not a debt function, but the cohomology computation still holds: every 1-cocycle is a coboundary because the underlying complex is the full simplicial complex, which is contractible.)

$\square$

**Corollary 4.15.** Debt functions are exactly the 1-coboundaries of the discrete de Rham complex on $\mathcal{B}$.

**Remark 4.16.** The vanishing of $H^1$ is a strong statement. It says that the discrete de Rham complex on a complete simplicial complex is *acyclic*. There is no obstruction to integrability. Every closed 1-form is exact.

**Remark 4.17.** This is in contrast to the continuous case, where $H^1$ can be nontrivial (e.g., on a circle, $H^1 = \mathbb{R}$). The difference is that the discrete complex on $\mathcal{B}$ is the full simplicial complex, which is contractible. If we restricted to a subcomplex (e.g., a graph with cycles), $H^1$ could be nontrivial, and there would be non-exact 1-cocycles. This is the origin of the "holonomy" discussed in Chapter 16.

---

## 4.6 The minimal axiom set

The basepoint theorem allows us to sharpen the axiom set for debt functions.

**Theorem 4.18 (Minimal axioms).** The following are equivalent for a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$:

1. $D$ satisfies (D1) and (D2).
2. $D$ is a coboundary: $D = \delta\psi$ for some $\psi : \mathcal{B} \to \mathbb{R}$.
3. $D$ is a potential difference: $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ for some $\psi$.
4. $D$ vanishes on every closed loop.
5. $D$ is path-independent: the debt of a path depends only on the endpoints.

*Proof.* The equivalence of (1) and (2) is the basepoint theorem (in one direction) and Proposition 3.14 (in the other). The equivalence of (2) and (3) is the definition of the coboundary. The equivalence of (3) and (4) follows from telescoping. The equivalence of (4) and (5) is immediate.

$\square$

**Remark 4.19.** The theorem says that the four properties—additivity, exactness, potential difference, and cycle invariance—are not four independent axioms. They are four faces of one fact: **debt is exact.** Any one of them implies all the others.

**Remark 4.20.** In Chapter 3, we listed five properties of debt (identity, additivity, antisymmetry, cycle invariance, gauge invariance). The basepoint theorem shows that all five are consequences of just two: additivity and antisymmetry. The other three are theorems.

**Convention 4.21.** For the remainder of the book, we take (D1) and (D2) as the *only* axioms of the debt function. All other properties are consequences.

---

## 4.7 Explicit potentials

The basepoint theorem gives an explicit construction of the potential: $\psi_{s_0}(b) = D(s_0, b)$. Let us compute this potential in several examples.

**Example 4.22 (Three-point space).** Let $\mathcal{B} = \{1, 2, 3\}$ and let $D$ be defined by

$$D(1, 2) = 2, \quad D(2, 3) = 3, \quad D(1, 3) = 5,$$

with $D$ extended by antisymmetry and $D(i, i) = 0$. Choose $s_0 = 1$. Then:

$$\psi_{s_0}(1) = D(1, 1) = 0, \quad \psi_{s_0}(2) = D(1, 2) = 2, \quad \psi_{s_0}(3) = D(1, 3) = 5.$$

Verify: $D(2, 3) = \psi(3) - \psi(2) = 5 - 2 = 3$. ✓

**Example 4.23 (Four-point space).** Let $\mathcal{B} = \{1, 2, 3, 4\}$ and let $D$ be defined by

$$D(i, j) = j - i$$

for all $i, j$. Choose $s_0 = 1$. Then $\psi_{s_0}(i) = D(1, i) = i - 1$. Verify: $D(i, j) = \psi(j) - \psi(i) = (j - 1) - (i - 1) = j - i$. ✓

**Example 4.24 (Belief space).** Let $\mathcal{B}$ be a belief space with potential $\psi(b) = -\log p(b)$, where $p$ is a probability distribution. Then $D(b_i, b_j) = \psi(b_j) - \psi(b_i) = \log p(b_i) - \log p(b_j) = \log(p(b_i)/p(b_j))$. The debt from $b_i$ to $b_j$ is the log-ratio of the probabilities. This is the *information gain* or *surprisal* of the transition.

**Example 4.25 (Energy landscape).** Let $\mathcal{B}$ be the configuration space of a physical system and let $\psi(b)$ be the energy of configuration $b$. Then $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ is the change in energy. The debt is the energy difference.

**Remark 4.26.** In each example, the potential $\psi$ has a natural interpretation: probability (negative log), energy, information, etc. The theory does not depend on the interpretation. What matters is that the potential exists and is unique up to a constant.

---

## 4.8 The debt as a derived quantity

We emphasize a subtle but important point: the debt is a *derived* quantity. It is not given a priori; it is constructed from the potential.

**Construction 4.27.** Given a set $\mathcal{B}$ and a function $\psi : \mathcal{B} \to \mathbb{R}$, define $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ by

$$D(b_i, b_j) := \psi(b_j) - \psi(b_i).$$

Then $D$ is a debt function.

**Theorem 4.28.** Every debt function arises this way. That is, the map

$$\{\psi : \mathcal{B} \to \mathbb{R}\} \to \{\text{debt functions on } \mathcal{B}\}, \qquad \psi \mapsto \delta\psi$$

is surjective, with kernel the constant functions.

*Proof.* Surjectivity is the basepoint theorem. The kernel is the set of $\psi$ with $\delta\psi = 0$, i.e., $\psi(b_j) - \psi(b_i) = 0$ for all $b_i, b_j$, i.e., $\psi$ is constant. $\square$

**Corollary 4.29.** The space of debt functions on $\mathcal{B}$ is isomorphic to the space of potentials modulo constants:

$$\{\text{debt functions}\} \cong \mathbb{R}^\mathcal{B} / \mathbb{R}.$$

**Remark 4.30.** This is a clean characterization. The debt function is not a primitive object; it is the derivative of a potential. The potential is the primitive object, and the debt is its coboundary.

**Remark 4.31.** In the context of belief space, this means that the debt between two beliefs is determined by a potential function on beliefs. The potential is the fundamental quantity; the debt is derived from it. This is analogous to the relationship between energy and force in physics: energy is the fundamental quantity, force is the gradient of energy.

---

## 4.9 The basepoint theorem and the complex quasi-metric

We close this chapter by connecting the basepoint theorem to the complex quasi-metric.

**Definition 4.32 (Complex quasi-metric, revisited).** Let $\mathcal{B}$ be a belief space with energy quasi-metric $d$ and potential $\psi$. The *complex quasi-metric* is

$$Q(b_i, b_j) := d(b_i, b_j) + i \cdot D(b_i, b_j),$$

where $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$.

**Proposition 4.33.** The complex quasi-metric satisfies:

- **(i)** $Q(b, b) = 0$;
- **(ii)** $\mathrm{Re}\, Q(b_i, b_j) \ge 0$;
- **(iii)** $\mathrm{Im}\, Q(b_i, b_j) = -\mathrm{Im}\, Q(b_j, b_i)$;
- **(iv)** $\mathrm{Im}\, Q$ is a coboundary.

*Proof.* Immediate from the definitions and the basepoint theorem. $\square$

**Remark 4.34.** The basepoint theorem is what makes the complex quasi-metric well-defined. Without it, the imaginary part $D$ would be an arbitrary antisymmetric function, not necessarily a potential difference. The theorem guarantees that $D$ has the structure of a coboundary, which is what allows the entire theory to work.

**Remark 4.35.** The complex quasi-metric $Q$ is the central object of the book. Its real part is the energy quasi-metric $d$; its imaginary part is the debt $D$, which is exact by the basepoint theorem. The modulus $|Q|$ is a metric; the argument $\arg Q$ is a phase. These will be developed in Chapters 6–8.

---

## 4.10 Summary

We have proven the **basepoint theorem**: every debt function is a potential difference. Specifically, given $D$ satisfying (D1) and (D2), and any basepoint $s_0 \in \mathcal{B}$, the function $\psi_{s_0}(b) := D(s_0, b)$ satisfies

$$D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i).$$

The potential is unique up to an additive constant, and the choice of basepoint is a gauge choice.

Consequences:

- **Minimal axioms.** Debt functions are exactly the functions satisfying (D1) and (D2). All other properties (identity, cycle invariance, path independence, gauge invariance) are theorems.
- **Discrete fundamental theorem of calculus.** The basepoint theorem is the discrete analogue of the fundamental theorem of calculus.
- **Cohomological interpretation.** $H^1(\mathcal{B}; \mathbb{R}) = 0$; every closed 1-form is exact.
- **Derived nature of debt.** Debt is not primitive; it is the coboundary of a potential.
- **Complex quasi-metric.** The basepoint theorem makes the complex quasi-metric $Q = d + iD$ well-defined.

The basepoint theorem is the foundational result of the theory. Everything that follows—the modulus, the phase, the $\gamma$-family, the polar decomposition, the topology lattice, the grading, the categorical picture—depends on it.

---

## 4.11 Exercises

**Exercise 4.1.** Prove the basepoint theorem directly from the definitions, without referring to Chapter 3.

**Exercise 4.2.** Let $\mathcal{B} = \{1, 2, 3, 4\}$ and let $D$ be defined by

$$D(i, j) = i^2 - j^2.$$

Verify that $D$ satisfies (D1) and (D2). Find the potential $\psi$ with basepoint $s_0 = 1$.

**Exercise 4.3.** Show that the set of debt functions on a finite set $\mathcal{B}$ with $n$ elements is a vector space of dimension $n - 1$.

**Exercise 4.4.** Let $D$ be a debt function and let $D' := cD$ for $c \in \mathbb{R}$. Show that $D'$ is a debt function. What is the corresponding potential?

**Exercise 4.5.** Prove that the basepoint theorem holds for any set $\mathcal{B}$, finite or infinite. (The proof is the same; just verify that no finiteness is used.)

**Exercise 4.6.** Let $\mathcal{B}$ be a set with three elements $\{1, 2, 3\}$. How many debt functions are there on $\mathcal{B}$? (Hint: the space is isomorphic to $\mathbb{R}^2$.)

**Exercise 4.7.** Let $D$ be a debt function on $\mathcal{B}$ and let $s_0, s_0' \in \mathcal{B}$. Show that $\psi_{s_0'}(b) = \psi_{s_0}(b) + D(s_0', s_0)$ for all $b \in \mathcal{B}$.

**Exercise 4.8.** Prove that the map $\psi \mapsto \delta\psi$ from potentials to debt functions is linear and surjective, with kernel the constant functions.

**Exercise 4.9.** Let $\mathcal{B}$ be a belief space with potential $\psi(b) = -\log p(b)$. Compute the debt $D(b_i, b_j)$ and interpret it in terms of information theory.

**Exercise 4.10.** Reflect on the following question: why is the basepoint theorem true for *any* set $\mathcal{B}$, without any topological or metric assumptions? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we consolidate the theory of debt by stating the minimal axiom set and exploring its consequences. We also introduce the debt-to-cost ratio and prepare for the complex quasi-metric.*

---

**End of Chapter 4.**
