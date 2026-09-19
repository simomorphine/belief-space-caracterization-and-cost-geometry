# Chapter 11: The Polar Decomposition of Quasi-Metrics

---

We now begin Part V of the book. In Parts I–IV, we developed the theory of the complex quasi-metric $Q = d + iD$, its modulus, its gauge structure, and the $\gamma$-family. The imaginary part $D$—the debt—is now fully understood: it is an exact 1-form, a potential difference, a coboundary.

But the real part $d$—the energy quasi-metric—has been treated as a single object. We have assumed it satisfies the triangle inequality and is generally asymmetric, but we have not asked: is there an internal structure to $d$ itself? Can it be decomposed into simpler pieces?

The answer is yes. Every quasi-metric admits a **canonical polar decomposition**:

$$d = S + \tfrac{1}{2}A,$$

where $S$ is a symmetric pseudometric and $A$ is an antisymmetric 2-form. This decomposition is unique, canonical, and revealing: it separates the symmetric part of the cost (which behaves like a metric) from the antisymmetric part (which behaves like a differential form).

This chapter develops the polar decomposition. It is the foundation for the topology lattice (Chapters 12–13), and it is the precise sense in which "cost is a metric plus a form."

---

## 11.1 The symmetrization and the asymmetry

We begin with the two basic operations.

**Definition 11.1 (Symmetrization).** The *symmetrization* of a function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ is

$$S(b_i, b_j) := \tfrac{1}{2}\bigl(d(b_i, b_j) + d(b_j, b_i)\bigr).$$

**Definition 11.2 (Asymmetry).** The *asymmetry* of $d$ is

$$A(b_i, b_j) := d(b_i, b_j) - d(b_j, b_i).$$

**Proposition 11.3 (Basic properties).**

- **(i)** $S$ is symmetric: $S(b_i, b_j) = S(b_j, b_i)$.
- **(ii)** $A$ is antisymmetric: $A(b_i, b_j) = -A(b_j, b_i)$.
- **(iii)** $S(b, b) = d(b, b)$ for all $b$.
- **(iv)** $A(b, b) = 0$ for all $b$.

*Proof.* (i) $S(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) = \tfrac{1}{2}(d(b_j, b_i) + d(b_i, b_j)) = S(b_j, b_i)$.

(ii) $A(b_i, b_j) = d(b_i, b_j) - d(b_j, b_i) = -(d(b_j, b_i) - d(b_i, b_j)) = -A(b_j, b_i)$.

(iii) $S(b, b) = \tfrac{1}{2}(d(b, b) + d(b, b)) = d(b, b)$.

(iv) $A(b, b) = d(b, b) - d(b, b) = 0$. $\square$

**Remark 11.4.** The symmetrization $S$ is the "average" of the two directions of $d$. The asymmetry $A$ is the "difference." The two operations are dual: $S$ extracts the symmetric part, $A$ extracts the antisymmetric part.

**Remark 11.5.** The asymmetry $A$ is a *2-form* in the discrete sense: it is a function on ordered pairs that is antisymmetric and vanishes on the diagonal. This is the first indication that the polar decomposition has a differential-geometric interpretation.

---

## 11.2 The polar decomposition

We now state the main theorem.

**Theorem 11.6 (Polar decomposition).** Every function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ decomposes uniquely as

$$d = S + \tfrac{1}{2}A,$$

where $S$ is symmetric and $A$ is antisymmetric.

*Proof.* Define $S := \tfrac{1}{2}(d + d^{\mathrm{op}})$ and $A := d - d^{\mathrm{op}}$, where $d^{\mathrm{op}}(b_i, b_j) := d(b_j, b_i)$. Then:

$$S(b_i, b_j) + \tfrac{1}{2}A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) + \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i)) = d(b_i, b_j).$$

Uniqueness: if $d = S' + T'$ with $S'$ symmetric and $T'$ antisymmetric, then $d^{\mathrm{op}} = S' - T'$, so $S' = \tfrac{1}{2}(d + d^{\mathrm{op}}) = S$ and $T' = \tfrac{1}{2}(d - d^{\mathrm{op}}) = \tfrac{1}{2}A$. $\square$

**Remark 11.7.** The polar decomposition is *canonical*: no choices are made. The decomposition is forced by the requirement that the two parts have the specified symmetry.

**Remark 11.8.** The factor of $\tfrac{1}{2}$ in the $A$-term is a normalization convention. Some authors write $d = S + A$ with $A$ defined as $\tfrac{1}{2}(d - d^{\mathrm{op}})$. We follow the convention $A = d - d^{\mathrm{op}}$, so that $A(b_i, b_j)$ has the same magnitude as the asymmetry of $d$.

**Remark 11.9.** The polar decomposition is analogous to the decomposition of a matrix into symmetric and antisymmetric parts, and to the decomposition of a connection into metric-compatible and torsion parts. It is a canonical decomposition of a two-variable function into its symmetric and antisymmetric components.

---

## 11.3 Properties of the symmetrization

We now study the properties of $S$.

**Proposition 11.10.** If $d$ satisfies the triangle inequality, then so does $S$.

*Proof.* For any $b_i, b_j, b_k$:

$$S(b_i, b_k) = \tfrac{1}{2}\bigl(d(b_i, b_k) + d(b_k, b_i)\bigr) \le \tfrac{1}{2}\bigl(d(b_i, b_j) + d(b_j, b_k) + d(b_k, b_j) + d(b_j, b_i)\bigr) = S(b_i, b_j) + S(b_j, b_k). \quad \square$$

**Corollary 11.11.** If $d$ is a quasi-metric, then $S$ is a pseudometric.

*Proof.* $S$ is symmetric (Proposition 11.3(i)), satisfies the triangle inequality (Proposition 11.10), is non-negative (average of non-negative numbers), and satisfies $S(b, b) = 0$ (Proposition 11.3(iii)). $\square$

**Remark 11.12.** The symmetrization $S$ is the *largest* symmetric function bounded above by $d$ in the following sense: if $T$ is symmetric and $T \le d$ pointwise, then $T \le S$. This is because $T(b_i, b_j) = T(b_j, b_i) \le d(b_j, b_i)$, so $T(b_i, b_j) \le \min(d(b_i, b_j), d(b_j, b_i)) \le S(b_i, b_j)$.

**Remark 11.13.** The symmetrization $S$ is a metric-like object: it satisfies all the axioms of a metric except the identity of indiscernibles. If $d$ satisfies the identity of indiscernibles, so does $S$ (since $S(b_i, b_j) \ge \min(d(b_i, b_j), d(b_j, b_i)) > 0$ for $b_i \neq b_j$). In that case, $S$ is a metric.

**Proposition 11.14 (Functoriality).** The symmetrization $S$ depends only on the symmetric part of $d$. That is, if $d$ and $d'$ have the same symmetrization, then $S = S'$.

*Proof.* $S = \tfrac{1}{2}(d + d^{\mathrm{op}})$ depends only on the sum $d + d^{\mathrm{op}}$, which is the symmetric part. $\square$

---

## 11.4 Properties of the asymmetry

We now study the properties of $A$.

**Proposition 11.15.** The asymmetry $A$ satisfies:

- **(i)** $A(b_i, b_j) = -A(b_j, b_i)$;
- **(ii)** $A(b, b) = 0$;
- **(iii)** $|A(b_i, b_j)| \le d(b_i, b_j) + d(b_j, b_i) = 2S(b_i, b_j)$.

*Proof.* (i) and (ii) are Proposition 11.3. For (iii): $|A(b_i, b_j)| = |d(b_i, b_j) - d(b_j, b_i)| \le d(b_i, b_j) + d(b_j, b_i) = 2S(b_i, b_j)$. $\square$

**Remark 11.16.** The asymmetry $A$ is bounded by twice the symmetrization $S$. This is a tight bound: if $d(b_i, b_j) = 0$ and $d(b_j, b_i) = 2S(b_i, b_j)$, then $|A| = 2S$.

**Proposition 11.17 (A is a 2-form).** The asymmetry $A$ is a discrete 2-form: an antisymmetric function on ordered pairs that vanishes on the diagonal.

*Proof.* Immediate from Proposition 11.15. $\square$

**Remark 11.18.** The asymmetry $A$ is *not* a coboundary in general. It is a 2-form, not a 1-form. The coboundary of a 0-form is a 1-form (the debt $D$); the coboundary of a 1-form is a 2-form. The asymmetry $A$ is a 2-form, but it is not necessarily the coboundary of a 1-form. This is the origin of the distinction between $A$ and $D$.

**Remark 11.19.** The asymmetry $A$ measures the *local* failure of symmetry of $d$. It is a local quantity, defined on pairs. It is not a global quantity like the debt $D$, which is a potential difference.

**Proposition 11.20 (Additivity of $A$).** The asymmetry $A$ is not additive in general: $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$.

*Proof.* By counterexample. Let $\mathcal{B} = \{1, 2, 3\}$ with $d(1, 2) = 1$, $d(2, 1) = 2$, $d(2, 3) = 3$, $d(3, 2) = 4$, $d(1, 3) = 5$, $d(3, 1) = 6$. Then $A(1, 2) = -1$, $A(2, 3) = -1$, $A(1, 3) = -1$, so $A(1, 2) + A(2, 3) = -2 \neq -1 = A(1, 3)$. $\square$

**Remark 11.21.** The failure of additivity of $A$ is the reason why $A$ is not a debt function. Debt functions are additive; $A$ is not. This is the fundamental distinction between the asymmetry and the debt.

**Remark 11.22.** The asymmetry $A$ is a "curvature-like" quantity: it measures the local failure of symmetry, and it is not integrable in general. The debt $D$, by contrast, is "gradient-like": it is integrable, additive, and admits a potential.

---

## 11.5 The polar decomposition and the complex quasi-metric

We now connect the polar decomposition to the complex quasi-metric.

**Proposition 11.23 (Decomposition of $Q$).** The complex quasi-metric decomposes as

$$Q = S + \tfrac{1}{2}A + iD,$$

where $S$ is the symmetrization, $A$ is the asymmetry, and $D$ is the debt.

*Proof.* $Q = d + iD = (S + \tfrac{1}{2}A) + iD$. $\square$

**Remark 11.24.** The complex quasi-metric has *three* components: the symmetric part $S$, the asymmetric part $\tfrac{1}{2}A$, and the debt $D$. The first is a pseudometric; the second is a 2-form; the third is a 1-form.

**Remark 11.25.** The three components are not independent. The asymmetry $A$ is determined by $d$ (via $A = d - d^{\mathrm{op}}$), and the debt $D$ is determined by the potential $\psi$ (via $D = \delta\psi$). The pair $(S, A)$ determines $d$; the potential $\psi$ determines $D$. Together, $(S, A, \psi)$ determines $Q$.

**Proposition 11.26 (Metric structure of $Q$).** The modulus $|Q|$ can be written as

$$|Q|^2 = (S + \tfrac{1}{2}A)^2 + D^2 = S^2 + S \cdot A + \tfrac{1}{4}A^2 + D^2.$$

*Proof.* Expand $(S + \tfrac{1}{2}A)^2$. $\square$

**Remark 11.27.** The modulus $|Q|$ mixes the symmetric part $S$, the asymmetric part $A$, and the debt $D$. The cross term $S \cdot A$ is the source of the asymmetry of $|Q|$.

**Remark 11.28.** If $d$ is symmetric ($A = 0$), then $|Q|^2 = S^2 + D^2$, and the modulus is symmetric. If $d$ is asymmetric, the modulus inherits the asymmetry from $A$.

---

## 11.6 The polar decomposition and the debt

We now relate the polar decomposition to the debt.

**Proposition 11.29.** The debt $D$ and the asymmetry $A$ are related by

$$A(b_i, b_j) = D(b_i, b_j) - D(b_j, b_i) + [d(b_i, b_j) - d(b_j, b_i) - D(b_i, b_j) + D(b_j, b_i)].$$

This is a tautology. The meaningful statement is that $A$ and $D$ are *not* the same.

**Proposition 11.30.** If $d$ is *purely asymmetric* (i.e., $S = 0$), then $d = \tfrac{1}{2}A$, and the debt $D$ is a separate quantity.

**Proposition 11.31.** If $d$ is *symmetric* (i.e., $A = 0$), then $d = S$, and the only source of asymmetry in $Q$ is the debt $D$.

*Proof.* If $A = 0$, then $d = S$, and $Q = S + iD$. The imaginary part $D$ is antisymmetric, so it is the only source of asymmetry. $\square$

**Remark 11.32.** The polar decomposition separates the asymmetry of $d$ (captured by $A$) from the asymmetry of $Q$ (captured by $D$). In general, both contribute to the asymmetry of $Q$.

**Remark 11.33.** The distinction between $A$ and $D$ is fundamental. $A$ is a 2-form (curvature-like), while $D$ is a 1-form (gradient-like). $A$ is not additive, while $D$ is additive. $A$ does not admit a potential, while $D$ does. The two quantities are structurally different.

---

## 11.7 The polar decomposition as a projection

We now interpret the polar decomposition as a projection in a suitable space.

**Definition 11.34 (Space of kernels).** Let $\mathcal{K}(\mathcal{B})$ be the space of all functions $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$. This is a vector space under pointwise addition and scalar multiplication.

**Definition 11.35 (Symmetric and antisymmetric subspaces).**

- $\mathcal{K}_S(\mathcal{B}) := \{d \in \mathcal{K}(\mathcal{B}) : d(b_i, b_j) = d(b_j, b_i)\}$ (symmetric kernels);
- $\mathcal{K}_A(\mathcal{B}) := \{d \in \mathcal{K}(\mathcal{B}) : d(b_i, b_j) = -d(b_j, b_i)\}$ (antisymmetric kernels).

**Proposition 11.36.** $\mathcal{K}(\mathcal{B}) = \mathcal{K}_S(\mathcal{B}) \oplus \mathcal{K}_A(\mathcal{B})$.

*Proof.* Every $d$ can be written uniquely as $d = S + T$ with $S \in \mathcal{K}_S$ and $T \in \mathcal{K}_A$, where $S = \tfrac{1}{2}(d + d^{\mathrm{op}})$ and $T = \tfrac{1}{2}(d - d^{\mathrm{op}})$. The intersection $\mathcal{K}_S \cap \mathcal{K}_A$ is the zero kernel (since a kernel that is both symmetric and antisymmetric must be zero). $\square$

**Definition 11.37 (Symmetrization projection).** The *symmetrization projection* is the linear map

$$\sigma : \mathcal{K}(\mathcal{B}) \to \mathcal{K}_S(\mathcal{B}), \qquad \sigma(d) := \tfrac{1}{2}(d + d^{\mathrm{op}}).$$

**Proposition 11.38.** $\sigma$ is a projection: $\sigma^2 = \sigma$.

*Proof.* $\sigma(\sigma(d)) = \tfrac{1}{2}(\sigma(d) + \sigma(d)^{\mathrm{op}}) = \tfrac{1}{2}(\sigma(d) + \sigma(d)) = \sigma(d)$ (since $\sigma(d)$ is symmetric). $\square$

**Remark 11.39.** The polar decomposition is the decomposition of $\mathcal{K}(\mathcal{B})$ into the image of $\sigma$ (the symmetric kernels) and its kernel (the antisymmetric kernels). The decomposition is the standard one for a projection.

**Remark 11.40.** The space $\mathcal{K}(\mathcal{B})$ is the direct sum of the symmetric and antisymmetric subspaces. This is the algebraic content of the polar decomposition.

---

## 11.8 The polar decomposition and the topology

We now connect the polar decomposition to the topology of belief space.

**Definition 11.41 (Symmetric topology).** The *symmetric topology* $\tau_S$ is the topology induced by the pseudometric $S$.

**Definition 11.42 (Quasi-metric topology).** The *quasi-metric topology* $\tau_d$ is the topology induced by the quasi-metric $d$.

**Proposition 11.43.** $\tau_S \subseteq \tau_d$.

*Proof.* Since $S \le d$ pointwise (because $S(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) \le \max(d(b_i, b_j), d(b_j, b_i))$ and similarly for the other direction), the balls of $S$ are contained in the balls of $d$. Hence $\tau_S \subseteq \tau_d$. $\square$

Wait, this is not quite right. Let me reconsider.

$S(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i))$. This is *at least* $\min(d(b_i, b_j), d(b_j, b_i))$ and *at most* $\max(d(b_i, b_j), d(b_j, b_i))$. So $S$ is not necessarily $\le d$ pointwise. In fact, if $d(b_i, b_j) < d(b_j, b_i)$, then $S(b_i, b_j) > d(b_i, b_j)$.

So the relationship between $\tau_S$ and $\tau_d$ is more subtle.

Let me correct.

**Proposition 11.44 (Relationship of topologies).** The symmetric topology $\tau_S$ and the quasi-metric topology $\tau_d$ are related by

$$\tau_S = \tau_d \cap \tau_{d^{\mathrm{op}}},$$

where $\tau_{d^{\mathrm{op}}}$ is the topology induced by the opposite quasi-metric $d^{\mathrm{op}}$.

*Proof.* The balls of $S$ are the intersections of the balls of $d$ and $d^{\mathrm{op}}$ (up to a factor of 2): $B_S(b, r) = B_d(b, r) \cap B_{d^{\mathrm{op}}}(b, r)$. Hence the topology generated by $S$ is the intersection of the topologies generated by $d$ and $d^{\mathrm{op}}$. $\square$

**Remark 11.45.** The symmetric topology is the *meet* of the forward and backward topologies. This will be developed in Chapter 12.

**Remark 11.46.** The polar decomposition separates the symmetric part $S$ from the asymmetric part $A$. The symmetric part determines the meet topology; the asymmetric part determines the difference between the forward and backward topologies.

---

## 11.9 Examples

We illustrate the polar decomposition with examples.

**Example 11.47 (Asymmetric cost).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = 3$, $d(2, 1) = 1$. Then:

- $S(1, 2) = \tfrac{1}{2}(3 + 1) = 2$;
- $A(1, 2) = 3 - 1 = 2$;
- $d(1, 2) = S(1, 2) + \tfrac{1}{2}A(1, 2) = 2 + 1 = 3$. ✓

**Example 11.48 (Symmetric cost).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = d(2, 1) = 2$. Then:

- $S(1, 2) = 2$;
- $A(1, 2) = 0$;
- $d(1, 2) = 2$. ✓

**Example 11.49 (Three-point space).** Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 1 & 4 \\ 3 & 0 & 2 \\ 1 & 2 & 0 \end{pmatrix}.$$

Then:

$$S = \begin{pmatrix} 0 & 2 & 2.5 \\ 2 & 0 & 2 \\ 2.5 & 2 & 0 \end{pmatrix}, \qquad A = \begin{pmatrix} 0 & -2 & 3 \\ 2 & 0 & 0 \\ -3 & 0 & 0 \end{pmatrix}.$$

Verify: $d = S + \tfrac{1}{2}A$. ✓

**Example 11.50 (Belief space).** Let $\mathcal{B}$ be a belief space with cost $d$ and potential $\psi$. The polar decomposition of $d$ gives $S$ (the symmetric part) and $A$ (the asymmetry). The debt $D = \delta\psi$ is separate.

**Remark 11.51.** In general, $A$ and $D$ are different quantities. $A$ is a 2-form determined by $d$; $D$ is a 1-form determined by $\psi$. The two are related by the fact that both contribute to the asymmetry of the complex quasi-metric $Q$.

---

## 11.10 The polar decomposition: summary

We summarize the polar decomposition in a single table.

| **Object** | **Definition** | **Properties** |
|---|---|---|
| $d$ | Energy quasi-metric | Triangle inequality, non-negative |
| $S$ | $\tfrac{1}{2}(d + d^{\mathrm{op}})$ | Symmetric, pseudometric |
| $A$ | $d - d^{\mathrm{op}}$ | Antisymmetric, 2-form |
| $D$ | $\delta\psi$ | Antisymmetric, 1-form, exact |
| $Q$ | $d + iD$ | Complex quasi-metric |

**Key results:**

- **Polar decomposition.** $d = S + \tfrac{1}{2}A$ (Theorem 11.6).
- **Uniqueness.** The decomposition is canonical and unique.
- **Symmetrization is a pseudometric.** $S$ satisfies the triangle inequality (Proposition 11.10).
- **Asymmetry is a 2-form.** $A$ is antisymmetric and vanishes on the diagonal (Proposition 11.15).
- **$A$ is not additive.** $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$ in general (Proposition 11.20).
- **Decomposition of $Q$.** $Q = S + \tfrac{1}{2}A + iD$ (Proposition 11.23).
- **Space decomposition.** $\mathcal{K}(\mathcal{B}) = \mathcal{K}_S \oplus \mathcal{K}_A$ (Proposition 11.36).
- **Symmetrization projection.** $\sigma^2 = \sigma$ (Proposition 11.38).
- **Topology relationship.** $\tau_S = \tau_d \cap \tau_{d^{\mathrm{op}}}$ (Proposition 11.44).

The polar decomposition is the foundation for the topology lattice of Chapters 12–13. It separates the symmetric part of the cost (which behaves like a metric) from the asymmetric part (which behaves like a differential form), and it prepares the ground for the study of the bitopological structure of belief space.

---

## 11.11 Exercises

**Exercise 11.1.** Verify the polar decomposition for Example 11.49.

**Exercise 11.2.** Prove that $S$ satisfies the triangle inequality if $d$ does.

**Exercise 11.3.** Show that $A(b_i, b_j) = -A(b_j, b_i)$ and $A(b, b) = 0$.

**Exercise 11.4.** Prove that $A$ is not additive in general. Give a counterexample.

**Exercise 11.5.** Show that $\mathcal{K}(\mathcal{B}) = \mathcal{K}_S \oplus \mathcal{K}_A$.

**Exercise 11.6.** Prove that the symmetrization projection $\sigma$ satisfies $\sigma^2 = \sigma$.

**Exercise 11.7.** Compute the polar decomposition of the quasi-metric in Example 11.49.

**Exercise 11.8.** Show that $\tau_S = \tau_d \cap \tau_{d^{\mathrm{op}}}$.

**Exercise 11.9.** Give an example of a quasi-metric with $S = 0$ (purely asymmetric) and compute $d$, $A$, and $D$.

**Exercise 11.10.** Reflect on the following question: why is the polar decomposition canonical, and what does this say about the structure of quasi-metrics? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we develop the bitopological structure of belief space. We introduce the forward and backward topologies $\tau_+$ and $\tau_-$, show that they form a lattice, and study the associated equilibrium concepts.*

---

**End of Chapter 11.**
