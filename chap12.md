# Chapter 12: The Polar Decomposition of Quasi-Metrics

---

We now begin Part V of the book. In Parts I–IV, we developed the theory of the complex quasi-metric $Q = d + iD$, its modulus, its gauge structure, and the $\gamma$-family. The imaginary part $D$—the debt—is now fully understood: it is an exact 1-form, a potential difference, a coboundary.

But the real part $d$—the energy quasi-metric—has been treated as a single object. We have assumed it satisfies the triangle inequality and is generally asymmetric, but we have not asked: is there an internal structure to $d$ itself? Can it be decomposed into simpler pieces?

The answer is yes. Every quasi-metric admits a **canonical polar decomposition**:

$$d = S + A,$$

where $S$ is a symmetric pseudometric and $A$ is an antisymmetric 2-form. This decomposition is unique, canonical, and revealing: it separates the symmetric part of the cost (which behaves like a metric) from the antisymmetric part (which behaves like a differential form).

This chapter develops the polar decomposition. It is the foundation for the topology lattice (Chapters 13–14), and it is the precise sense in which "cost is a metric plus a form."

**Remark 12.0 (Convention for $A$).** In Chapter 3, we defined the antisymmetric part of the cost as $A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i))$. In this chapter, we adopt the same convention: $A = \tfrac{1}{2}(d - d^{\mathrm{op}})$, so that the polar decomposition reads $d = S + A$. This is consistent with Chapter 3 and with the standard convention in the literature. The reader should note that some authors define $A = d - d^{\mathrm{op}}$, which differs by a factor of 2; we do not use that convention here.

---

## 12.1 The symmetrization and the asymmetry

We begin with the two basic operations.

**Definition 12.1 (Symmetrization).** The *symmetrization* of a function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ is

$$S(b_i, b_j) := \tfrac{1}{2}\bigl(d(b_i, b_j) + d(b_j, b_i)\bigr).$$

**Definition 12.2 (Asymmetry).** The *asymmetry* of $d$ is

$$A(b_i, b_j) := \tfrac{1}{2}\bigl(d(b_i, b_j) - d(b_j, b_i)\bigr).$$

**Remark 12.3.** This definition matches Definition 3.2 in Chapter 3. The polar decomposition will then read $d = S + A$, with no factors of $\tfrac{1}{2}$ in the final formula. This is the standard convention.

**Proposition 12.4 (Basic properties).**

- **(i)** $S$ is symmetric: $S(b_i, b_j) = S(b_j, b_i)$.
- **(ii)** $A$ is antisymmetric: $A(b_i, b_j) = -A(b_j, b_i)$.
- **(iii)** $S(b, b) = d(b, b)$ for all $b$.
- **(iv)** $A(b, b) = 0$ for all $b$.

*Proof.* (i) $S(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) = \tfrac{1}{2}(d(b_j, b_i) + d(b_i, b_j)) = S(b_j, b_i)$.

(ii) $A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i)) = -\tfrac{1}{2}(d(b_j, b_i) - d(b_i, b_j)) = -A(b_j, b_i)$.

(iii) $S(b, b) = \tfrac{1}{2}(d(b, b) + d(b, b)) = d(b, b)$.

(iv) $A(b, b) = \tfrac{1}{2}(d(b, b) - d(b, b)) = 0$. $\square$

**Remark 12.5.** The symmetrization $S$ is the "average" of the two directions of $d$. The asymmetry $A$ is the "half-difference." The two operations are dual: $S$ extracts the symmetric part, $A$ extracts the antisymmetric part.

**Remark 12.6.** The asymmetry $A$ is a *2-form* in the discrete sense: it is a function on ordered pairs that is antisymmetric and vanishes on the diagonal. This is the first indication that the polar decomposition has a differential-geometric interpretation.

---

## 12.2 The polar decomposition

We now state the main theorem.

**Theorem 12.7 (Polar decomposition).** Every function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ decomposes uniquely as

$$d = S + A,$$

where $S$ is symmetric and $A$ is antisymmetric.

*Proof.* Define $S := \tfrac{1}{2}(d + d^{\mathrm{op}})$ and $A := \tfrac{1}{2}(d - d^{\mathrm{op}})$, where $d^{\mathrm{op}}(b_i, b_j) := d(b_j, b_i)$. Then:

$$S(b_i, b_j) + A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) + \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i)) = d(b_i, b_j).$$

Uniqueness: if $d = S' + A'$ with $S'$ symmetric and $A'$ antisymmetric, then $d^{\mathrm{op}} = S' - A'$, so $S' = \tfrac{1}{2}(d + d^{\mathrm{op}}) = S$ and $A' = \tfrac{1}{2}(d - d^{\mathrm{op}}) = A$. $\square$

**Remark 12.8.** The polar decomposition is *canonical*: no choices are made. The decomposition is forced by the requirement that the two parts have the specified symmetry.

**Remark 12.9.** The polar decomposition is analogous to the decomposition of a matrix into symmetric and antisymmetric parts, and to the decomposition of a connection into metric-compatible and torsion parts. It is a canonical decomposition of a two-variable function into its symmetric and antisymmetric components.

**Remark 12.10.** With our convention, $|A(b_i, b_j)|$ is *half* the magnitude of the asymmetry of $d$: $|A(b_i, b_j)| = \tfrac{1}{2}|d(b_i, b_j) - d(b_j, b_i)|$. This is the canonical normalization for a 1-form.

---

## 12.3 Properties of the symmetrization

We now study the properties of $S$.

**Proposition 12.11.** If $d$ satisfies the triangle inequality, then so does $S$.

*Proof.* For any $b_i, b_j, b_k$:

$$S(b_i, b_k) = \tfrac{1}{2}\bigl(d(b_i, b_k) + d(b_k, b_i)\bigr) \le \tfrac{1}{2}\bigl(d(b_i, b_j) + d(b_j, b_k) + d(b_k, b_j) + d(b_j, b_i)\bigr) = S(b_i, b_j) + S(b_j, b_k). \quad \square$$

**Corollary 12.12.** If $d$ is a quasi-metric, then $S$ is a pseudometric.

*Proof.* $S$ is symmetric (Proposition 12.4(i)), satisfies the triangle inequality (Proposition 12.11), is non-negative (average of non-negative numbers), and satisfies $S(b, b) = 0$ (Proposition 12.4(iii)). $\square$

**Remark 12.13.** The symmetrization $S$ is the *largest* symmetric function bounded above by $\max(d, d^{\mathrm{op}})$ in the following sense: if $T$ is symmetric and $T(b_i, b_j) \le \max(d(b_i, b_j), d(b_j, b_i))$, then $T \le S + |A|$. The precise extremal characterization is more subtle and is not needed here.

**Remark 12.14.** The symmetrization $S$ is a metric-like object: it satisfies all the axioms of a metric except the identity of indiscernibles. If $d$ satisfies the identity of indiscernibles, so does $S$ (since $S(b_i, b_j) \ge \min(d(b_i, b_j), d(b_j, b_i)) > 0$ for $b_i \neq b_j$). In that case, $S$ is a metric.

**Proposition 12.15 (Functoriality).** The symmetrization $S$ depends only on the symmetric part of $d$. That is, if $d$ and $d'$ have the same symmetrization, then $S = S'$.

*Proof.* $S = \tfrac{1}{2}(d + d^{\mathrm{op}})$ depends only on the sum $d + d^{\mathrm{op}}$, which is the symmetric part. $\square$

---

## 12.4 Properties of the asymmetry

We now study the properties of $A$.

**Proposition 12.16.** The asymmetry $A$ satisfies:

- **(i)** $A(b_i, b_j) = -A(b_j, b_i)$;
- **(ii)** $A(b, b) = 0$;
- **(iii)** $|A(b_i, b_j)| \le S(b_i, b_j) \le d(b_i, b_j) + |A(b_i, b_j)|$.

*Proof.* (i) and (ii) are Proposition 12.4. For (iii): $|A(b_i, b_j)| = \tfrac{1}{2}|d(b_i, b_j) - d(b_j, b_i)| \le \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) = S(b_i, b_j)$. And $S(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) = d(b_i, b_j) - A(b_i, b_j) \le d(b_i, b_j) + |A(b_i, b_j)|$. $\square$

**Remark 12.17.** The asymmetry $A$ is bounded by the symmetrization $S$. This is a tight bound: if $d(b_i, b_j) = 0$ and $d(b_j, b_i) = 2S(b_i, b_j)$, then $|A| = S$.

**Proposition 12.18 ($A$ is a 2-form).** The asymmetry $A$ is a discrete 2-form: an antisymmetric function on ordered pairs that vanishes on the diagonal.

*Proof.* Immediate from Proposition 12.16. $\square$

**Remark 12.19.** The asymmetry $A$ is *not* a coboundary in general. It is a 2-form, not a 1-form. The coboundary of a 0-form is a 1-form (the debt $D$); the coboundary of a 1-form is a 2-form. The asymmetry $A$ is a 2-form, but it is not necessarily the coboundary of a 1-form. This is the origin of the distinction between $A$ and $D$.

**Remark 12.20.** The asymmetry $A$ measures the *local* failure of symmetry of $d$. It is a local quantity, defined on pairs. It is not a global quantity like the debt $D$, which is a potential difference.

**Proposition 12.21 (Additivity of $A$).** The asymmetry $A$ is not additive in general: $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$.

*Proof.* By counterexample. Let $\mathcal{B} = \{1, 2, 3\}$ with $d(1, 2) = 1$, $d(2, 1) = 2$, $d(2, 3) = 3$, $d(3, 2) = 4$, $d(1, 3) = 5$, $d(3, 1) = 6$. Then $A(1, 2) = -\tfrac{1}{2}$, $A(2, 3) = -\tfrac{1}{2}$, $A(1, 3) = -\tfrac{1}{2}$, so $A(1, 2) + A(2, 3) = -1 \neq -\tfrac{1}{2} = A(1, 3)$. $\square$

**Remark 12.22.** The failure of additivity of $A$ is the reason why $A$ is not a debt function. Debt functions are additive; $A$ is not. This is the fundamental distinction between the asymmetry and the debt.

**Remark 12.23.** The asymmetry $A$ is a "curvature-like" quantity: it measures the local failure of symmetry, and it is not integrable in general. The debt $D$, by contrast, is "gradient-like": it is integrable, additive, and admits a potential.

---

## 12.5 The polar decomposition and the complex quasi-metric

We now connect the polar decomposition to the complex quasi-metric.

**Proposition 12.24 (Decomposition of $Q$).** The complex quasi-metric decomposes as

$$Q = S + A + iD,$$

where $S$ is the symmetrization, $A$ is the asymmetry, and $D$ is the debt.

*Proof.* $Q = d + iD = (S + A) + iD$. $\square$

**Remark 12.25.** The complex quasi-metric has *three* components: the symmetric part $S$, the asymmetric part $A$, and the debt $D$. The first is a pseudometric; the second is a 2-form; the third is a 1-form.

**Remark 12.26.** The three components are not independent. The asymmetry $A$ is determined by $d$ (via $A = \tfrac{1}{2}(d - d^{\mathrm{op}})$), and the debt $D$ is determined by the potential $\psi$ (via $D = \delta\psi$). The pair $(S, A)$ determines $d$; the potential $\psi$ determines $D$. Together, $(S, A, \psi)$ determines $Q$.

**Proposition 12.27 (Metric structure of $Q$).** The modulus $|Q|$ can be written as

$$|Q|^2 = (S + A)^2 + D^2 = S^2 + 2SA + A^2 + D^2.$$

*Proof.* Expand $(S + A)^2$. $\square$

**Remark 12.28.** The modulus $|Q|$ mixes the symmetric part $S$, the asymmetric part $A$, and the debt $D$. The cross term $2SA$ is the source of the asymmetry of $|Q|$.

**Remark 12.29.** If $d$ is symmetric ($A = 0$), then $|Q|^2 = S^2 + D^2$, and the modulus is symmetric. If $d$ is asymmetric, the modulus inherits the asymmetry from $A$.

---

## 12.6 The relationship between $A$ and $D$

We now explore the relationship between the asymmetry $A$ and the debt $D$. Both are antisymmetric, but they are structurally different.

**Proposition 12.30 (Structural distinction).**

- $A$ is a **2-form**: it is a function of two variables, antisymmetric, vanishing on the diagonal.
- $D$ is a **1-form**: it is a function of two variables, antisymmetric, vanishing on the diagonal, **and additive**.
- Every debt function $D$ is a 1-coboundary: $D = \delta\psi$.
- The asymmetry $A$ is **not** a coboundary in general: there is no potential $\psi$ such that $A = \delta\psi$ unless $A$ happens to be additive.

*Proof.* The additivity of $D$ is axiom (D1). The non-additivity of $A$ is Proposition 12.21. If $A = \delta\psi$ for some $\psi$, then $A$ would be additive, which contradicts Proposition 12.21. $\square$

**Proposition 12.31 (When $A = D$).** The asymmetry $A$ equals the debt $D$ if and only if $A$ is additive and $D = A$.

*Proof.* If $A = D$, then $A$ is additive (since $D$ is). Conversely, if $A$ is additive and satisfies the debt axioms, then $A$ is a debt function; if in addition $A = D$, the equality holds. $\square$

**Remark 12.32.** In general, $A \neq D$. The asymmetry is a "local" quantity determined by $d$; the debt is a "global" quantity determined by the potential $\psi$. They coincide only in special cases (e.g., when $d$ is purely asymmetric and additive).

**Proposition 12.33 (Decomposition of the asymmetry).** The asymmetry $A$ can be decomposed as

$$A = A_{\mathrm{exact}} + A_{\mathrm{non-exact}},$$

where $A_{\mathrm{exact}}$ is the largest additive sub-2-form of $A$ (i.e., the largest part that is a coboundary), and $A_{\mathrm{non-exact}}$ is the remainder.

*Proof.* The space of 2-forms is a vector space. The subspace of exact 2-forms (those of the form $\delta\psi$ for some 0-cochain $\psi$) is a subspace. The decomposition is the orthogonal projection onto this subspace (with respect to any inner product). $\square$

**Remark 12.34.** The decomposition of $A$ into exact and non-exact parts is the cohomological refinement of the polar decomposition. It separates the "integrable" part of the asymmetry (which can be represented by a potential) from the "non-integrable" part (which cannot).

**Remark 12.35.** The exact part $A_{\mathrm{exact}}$ is a debt function (it satisfies the debt axioms). The non-exact part $A_{\mathrm{non-exact}}$ is a genuine 2-form with no potential representation. In the complex quasi-metric $Q = S + A + iD$, the exact part of $A$ and the debt $D$ are both 1-forms, while the non-exact part of $A$ is a genuine 2-form.

**Example 12.36 ($A$ and $D$ in a three-point space).** Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 1 & 4 \\ 3 & 0 & 2 \\ 1 & 2 & 0 \end{pmatrix}.$$

Then:

$$S = \begin{pmatrix} 0 & 2 & 2.5 \\ 2 & 0 & 2 \\ 2.5 & 2 & 0 \end{pmatrix}, \qquad A = \begin{pmatrix} 0 & -1 & 1.5 \\ 1 & 0 & 0 \\ -1.5 & 0 & 0 \end{pmatrix}.$$

Now suppose the debt is $D = \delta\psi$ for some potential $\psi$. For example, $\psi = (0, 1, 3)$ gives $D(1, 2) = 1$, $D(2, 3) = 2$, $D(1, 3) = 3$. Then $A \neq D$ (e.g., $A(1, 2) = -1 \neq 1 = D(1, 2)$).

**Remark 12.37.** The example shows that $A$ and $D$ are different in general. The asymmetry $A$ is determined by $d$ alone; the debt $D$ is determined by the potential $\psi$.

---

## 12.7 The polar decomposition as a projection

We now interpret the polar decomposition as a projection in a suitable space.

**Definition 12.38 (Space of kernels).** Let $\mathcal{K}(\mathcal{B})$ be the space of all functions $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$. This is a vector space under pointwise addition and scalar multiplication.

**Definition 12.39 (Symmetric and antisymmetric subspaces).**

- $\mathcal{K}_S(\mathcal{B}) := \{d \in \mathcal{K}(\mathcal{B}) : d(b_i, b_j) = d(b_j, b_i)\}$ (symmetric kernels);
- $\mathcal{K}_A(\mathcal{B}) := \{d \in \mathcal{K}(\mathcal{B}) : d(b_i, b_j) = -d(b_j, b_i)\}$ (antisymmetric kernels).

**Proposition 12.40.** $\mathcal{K}(\mathcal{B}) = \mathcal{K}_S(\mathcal{B}) \oplus \mathcal{K}_A(\mathcal{B})$.

*Proof.* Every $d$ can be written uniquely as $d = S + A$ with $S \in \mathcal{K}_S$ and $A \in \mathcal{K}_A$, where $S = \tfrac{1}{2}(d + d^{\mathrm{op}})$ and $A = \tfrac{1}{2}(d - d^{\mathrm{op}})$. The intersection $\mathcal{K}_S \cap \mathcal{K}_A$ is the zero kernel (since a kernel that is both symmetric and antisymmetric must be zero). $\square$

**Definition 12.41 (Symmetrization projection).** The *symmetrization projection* is the linear map

$$\sigma : \mathcal{K}(\mathcal{B}) \to \mathcal{K}_S(\mathcal{B}), \qquad \sigma(d) := \tfrac{1}{2}(d + d^{\mathrm{op}}).$$

**Proposition 12.42.** $\sigma$ is a projection: $\sigma^2 = \sigma$.

*Proof.* $\sigma(\sigma(d)) = \tfrac{1}{2}(\sigma(d) + \sigma(d)^{\mathrm{op}}) = \tfrac{1}{2}(\sigma(d) + \sigma(d)) = \sigma(d)$ (since $\sigma(d)$ is symmetric). $\square$

**Remark 12.43.** The polar decomposition is the decomposition of $\mathcal{K}(\mathcal{B})$ into the image of $\sigma$ (the symmetric kernels) and its kernel (the antisymmetric kernels). The decomposition is the standard one for a projection.

**Remark 12.44.** The space $\mathcal{K}(\mathcal{B})$ is the direct sum of the symmetric and antisymmetric subspaces. This is the algebraic content of the polar decomposition.

---

## 12.8 The polar decomposition and the topology

We now connect the polar decomposition to the topology of belief space.

**Definition 12.45 (Symmetric topology).** The *symmetric topology* $\tau_S$ is the topology induced by the pseudometric $S$.

**Definition 12.46 (Quasi-metric topology).** The *quasi-metric topology* $\tau_d$ is the topology induced by the quasi-metric $d$.

**Definition 12.47 (Opposite topology).** The *opposite topology* $\tau_{d^{\mathrm{op}}}$ is the topology induced by the opposite quasi-metric $d^{\mathrm{op}}(b_i, b_j) := d(b_j, b_i)$.

**Proposition 12.48 (Relationship of topologies).** The symmetric topology $\tau_S$ and the quasi-metric topology $\tau_d$ are related by

$$\tau_S = \tau_d \cap \tau_{d^{\mathrm{op}}}.$$

*Proof.* The balls of $S$ are the intersections of the balls of $d$ and $d^{\mathrm{op}}$ (up to a factor of 2): $B_S(b, r) = B_d(b, r) \cap B_{d^{\mathrm{op}}}(b, r)$. Hence the topology generated by $S$ is the intersection of the topologies generated by $d$ and $d^{\mathrm{op}}$. $\square$

**Remark 12.49.** The symmetric topology is the *meet* of the forward and backward topologies. This will be developed in Chapter 13.

**Remark 12.50.** The polar decomposition separates the symmetric part $S$ from the asymmetric part $A$. The symmetric part determines the meet topology; the asymmetric part determines the difference between the forward and backward topologies.

---

## 12.9 Examples

We illustrate the polar decomposition with examples.

**Example 12.51 (Asymmetric cost).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = 3$, $d(2, 1) = 1$. Then:

- $S(1, 2) = \tfrac{1}{2}(3 + 1) = 2$;
- $A(1, 2) = \tfrac{1}{2}(3 - 1) = 1$;
- $d(1, 2) = S(1, 2) + A(1, 2) = 2 + 1 = 3$. ✓

**Example 12.52 (Symmetric cost).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = d(2, 1) = 2$. Then:

- $S(1, 2) = 2$;
- $A(1, 2) = 0$;
- $d(1, 2) = 2$. ✓

**Example 12.53 (Three-point space).** Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 1 & 4 \\ 3 & 0 & 2 \\ 1 & 2 & 0 \end{pmatrix}.$$

Then:

$$S = \begin{pmatrix} 0 & 2 & 2.5 \\ 2 & 0 & 2 \\ 2.5 & 2 & 0 \end{pmatrix}, \qquad A = \begin{pmatrix} 0 & -1 & 1.5 \\ 1 & 0 & 0 \\ -1.5 & 0 & 0 \end{pmatrix}.$$

Verify: $d = S + A$. ✓

**Example 12.54 (Belief space).** Let $\mathcal{B}$ be a belief space with cost $d$ and potential $\psi$. The polar decomposition of $d$ gives $S$ (the symmetric part) and $A$ (the asymmetry). The debt $D = \delta\psi$ is separate.

**Remark 12.55.** In general, $A$ and $D$ are different quantities. $A$ is a 2-form determined by $d$; $D$ is a 1-form determined by $\psi$. The two are related by the fact that both contribute to the asymmetry of the complex quasi-metric $Q$.

---

## 12.10 The polar decomposition: summary

We summarize the polar decomposition in a single table.

| **Object** | **Definition** | **Properties** |
|---|---|---|
| $d$ | Energy quasi-metric | Triangle inequality, non-negative |
| $S$ | $\tfrac{1}{2}(d + d^{\mathrm{op}})$ | Symmetric, pseudometric |
| $A$ | $\tfrac{1}{2}(d - d^{\mathrm{op}})$ | Antisymmetric, 2-form |
| $D$ | $\delta\psi$ | Antisymmetric, 1-form, exact |
| $Q$ | $d + iD = S + A + iD$ | Complex quasi-metric |

**Key results:**

- **Polar decomposition.** $d = S + A$ (Theorem 12.7).
- **Uniqueness.** The decomposition is canonical and unique.
- **Symmetrization is a pseudometric.** $S$ satisfies the triangle inequality (Proposition 12.11).
- **Asymmetry is a 2-form.** $A$ is antisymmetric and vanishes on the diagonal (Proposition 12.16).
- **$A$ is not additive.** $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$ in general (Proposition 12.21).
- **Decomposition of $Q$.** $Q = S + A + iD$ (Proposition 12.24).
- **Structural distinction between $A$ and $D$.** $A$ is a 2-form, $D$ is a 1-form, and $D$ is exact while $A$ is not in general (Proposition 12.30).
- **Space decomposition.** $\mathcal{K}(\mathcal{B}) = \mathcal{K}_S \oplus \mathcal{K}_A$ (Proposition 12.40).
- **Symmetrization projection.** $\sigma^2 = \sigma$ (Proposition 12.42).
- **Topology relationship.** $\tau_S = \tau_d \cap \tau_{d^{\mathrm{op}}}$ (Proposition 12.48).

The polar decomposition is the foundation for the topology lattice of Chapters 13–14. It separates the symmetric part of the cost (which behaves like a metric) from the asymmetric part (which behaves like a differential form), and it prepares the ground for the study of the bitopological structure of belief space.

---

## 12.11 Exercises

**Exercise 12.1.** Verify the polar decomposition for Example 12.53.

**Exercise 12.2.** Prove that $S$ satisfies the triangle inequality if $d$ does.

**Exercise 12.3.** Show that $A(b_i, b_j) = -A(b_j, b_i)$ and $A(b, b) = 0$.

**Exercise 12.4.** Prove that $A$ is not additive in general. Give a counterexample.

**Exercise 12.5.** Show that $\mathcal{K}(\mathcal{B}) = \mathcal{K}_S \oplus \mathcal{K}_A$.

**Exercise 12.6.** Prove that the symmetrization projection $\sigma$ satisfies $\sigma^2 = \sigma$.

**Exercise 12.7.** Compute the polar decomposition of the quasi-metric in Example 12.53.

**Exercise 12.8.** Show that $\tau_S = \tau_d \cap \tau_{d^{\mathrm{op}}}$.

**Exercise 12.9.** Give an example of a quasi-metric with $S = 0$ (purely asymmetric) and compute $d$ and $A$.

**Exercise 12.10.** Give an example where $A = D$ (asymmetry equals debt) and an example where $A \neq D$.

**Exercise 12.11.** Prove that the decomposition of $A$ into exact and non-exact parts (Proposition 12.33) is well-defined.

**Exercise 12.12.** Reflect on the following question: why is the polar decomposition canonical, and what does this say about the structure of quasi-metrics? Write a short essay (one page) arguing for your position.




