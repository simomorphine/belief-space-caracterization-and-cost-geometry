# Chapter 8: The Modulus as a Quasi-Metric

---

In Chapter 7, we introduced the complex quasi-metric $Q = d + iD$ and proved that its modulus $|Q|$ satisfies the triangle inequality. This chapter develops the metric properties of $|Q|$ in full and introduces the topological structure it induces.

The central theme is the following: **the modulus repairs what the real part lacks—but only partially.** The energy quasi-metric $d$ may be asymmetric; the modulus $|Q|$ is symmetric whenever $d$ is symmetric, and satisfies the triangle inequality always. But the modulus does *not* repair the asymmetry of $d$: if $d$ is asymmetric, then $|Q|$ is a quasi-metric, not a metric.

This chapter is the bridge between the complex structure of $Q$ and the topological structure that follows in Parts IV and V. The main new contributions are:

1. The bounded distortion inequality: $d \le |Q| \le d + |D|$.
2. The metric topology $\tau_{|Q|}$.
3. The metric completion $\overline{\mathcal{B}}$.
4. The sharpness/equality condition for the triangle inequality.
5. The systematic statement of metric properties.

**Remark 8.0 (Relation to Chapter 7).** Chapter 7 already established the triangle inequality for $|Q|$ and the conditions under which $|Q|$ is a metric. This chapter does not repeat those proofs in full; it cross-references them and focuses on the new content. The reader who wants only the triangle inequality can read Chapter 7, Theorem 7.8. The reader who wants the full metric structure should read both chapters.

---

## 8.1 The triangle inequality: summary

We begin by recalling the triangle inequality for $|Q|$ and stating the equality condition, which is new.

**Theorem 8.1 (Triangle inequality for $|Q|$).** For all $b_i, b_j, b_k \in \mathcal{B}$,

$$|Q(b_i, b_k)| \le |Q(b_i, b_j)| + |Q(b_j, b_k)|.$$

*Proof.* See Chapter 7, Theorem 7.8. The proof uses the triangle inequality for $d$, the additivity of $D$, and Minkowski's inequality in $\mathbb{R}^2$. $\square$

**Remark 8.2.** The triangle inequality for $|Q|$ uses only two properties: the triangle inequality for $d$ and the additivity of $D$. Symmetry of $d$ is *not* used. The modulus satisfies the triangle inequality regardless of whether $d$ is symmetric.

**Remark 8.3.** The proof is the standard proof that a norm on a product is a norm. Specifically, the map $(d, D) \mapsto |Q|$ is the Euclidean norm on $\mathbb{R}^2$, and the triangle inequality for $|Q|$ is the triangle inequality for the Euclidean norm, transported through the map $(b_i, b_j) \mapsto (d(b_i, b_j), D(b_i, b_j))$.

### The equality condition

We now analyze when the triangle inequality is sharp.

**Theorem 8.4 (Equality condition).** For $b_i, b_j, b_k \in \mathcal{B}$ with $Q(b_i, b_j) \neq 0$ and $Q(b_j, b_k) \neq 0$, the equality

$$|Q(b_i, b_k)| = |Q(b_i, b_j)| + |Q(b_j, b_k)|$$

holds if and only if there exists $\lambda > 0$ such that

$$d(b_i, b_j) = \lambda \, d(b_j, b_k) \quad \text{and} \quad D(b_i, b_j) = \lambda \, D(b_j, b_k).$$

Equivalently, the vectors $(d(b_i, b_j), D(b_i, b_j))$ and $(d(b_j, b_k), D(b_j, b_k))$ are non-negative scalar multiples of each other.

*Proof.* This is the equality condition for Minkowski's inequality in $\mathbb{R}^2$. Equality holds if and only if the two vectors are non-negative scalar multiples of each other. $\square$

**Corollary 8.5 (Equality in the pure-cost case).** If $D = 0$ identically, then the triangle inequality for $|Q| = d$ is sharp if and only if the path through $b_j$ is optimal:

$$d(b_i, b_k) = d(b_i, b_j) + d(b_j, b_k).$$

**Corollary 8.6 (Equality in the pure-debt case).** If $d = 0$ identically, then $|Q| = |D|$, and the triangle inequality is sharp if and only if $D(b_i, b_j)$ and $D(b_j, b_k)$ have the same sign.

**Corollary 8.7 (Equality in the general case).** In general, the triangle inequality is sharp if and only if the phase $\theta$ is the same for both transitions:

$$\theta(b_i, b_j) = \theta(b_j, b_k).$$

*Proof.* The vectors $(d(b_i, b_j), D(b_i, b_j))$ and $(d(b_j, b_k), D(b_j, b_k))$ are non-negative scalar multiples of each other if and only if they have the same phase. $\square$

**Remark 8.8.** The equality condition says that the triangle inequality is sharp precisely when the two transitions lie on the same ray in the cost-debt plane. This is the discrete analogue of the statement that the Euclidean triangle inequality is sharp if and only if the two vectors are colinear and same-signed.

**Remark 8.9 (Path optimality).** The equality condition can be interpreted as a statement about path optimality: the path through $b_j$ is optimal in the modulus metric if and only if the phases of the two transitions agree. This connects to the optimization theory of Chapter 10.

---

## 8.2 The modulus as a metric: full statement

We now state the full metric properties of $|Q|$ systematically. The proofs are assembled from results in Chapter 7 and the new results above.

**Theorem 8.10 (Metric properties of $|Q|$).** Let $|Q| : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ be the modulus of the complex quasi-metric $Q = d + iD$. Then:

- **(M0) Identity.** $|Q|(b, b) = 0$ for all $b \in \mathcal{B}$.
- **(M1) Non-negativity.** $|Q|(b_i, b_j) \ge 0$ for all $b_i, b_j \in \mathcal{B}$.
- **(M2) Triangle inequality.** $|Q|(b_i, b_k) \le |Q|(b_i, b_j) + |Q|(b_j, b_k)$.
- **(M3) Symmetry.** $|Q|(b_i, b_j) = |Q|(b_j, b_i)$ if and only if $d(b_i, b_j) = d(b_j, b_i)$.
- **(M4) Identity of indiscernibles.** $|Q|(b_i, b_j) = 0$ if and only if $d(b_i, b_j) = 0$ and $D(b_i, b_j) = 0$.

*Proof.*

- (M0) $|Q|(b, b) = \sqrt{d(b, b)^2 + D(b, b)^2} = 0$.
- (M1) Square root of a sum of squares.
- (M2) Theorem 8.1.
- (M3) $|Q|(b_i, b_j)^2 - |Q|(b_j, b_i)^2 = [d(b_i, b_j)^2 - d(b_j, b_i)^2] + [D(b_i, b_j)^2 - D(b_j, b_i)^2]$. The second bracket is zero by antisymmetry. So $|Q|(b_i, b_j) = |Q|(b_j, b_i)$ iff $d(b_i, b_j) = d(b_j, b_i)$.
- (M4) $|Q|(b_i, b_j) = 0$ iff $d(b_i, b_j)^2 + D(b_i, b_j)^2 = 0$ iff both terms are zero. $\square$

**Corollary 8.11.** If $d$ is symmetric and satisfies the identity of indiscernibles, then $|Q|$ is a metric on $\mathcal{B}$.

**Corollary 8.12.** If $d$ is symmetric but fails the identity of indiscernibles, then $|Q|$ is a pseudometric on $\mathcal{B}$.

**Corollary 8.13.** If $d$ is asymmetric, then $|Q|$ is a quasi-metric on $\mathcal{B}$ (satisfies the triangle inequality but not necessarily symmetry).

**Remark 8.14.** The modulus $|Q|$ is always *at least* a quasi-metric. It is a metric exactly when $d$ is symmetric and identity-respecting. It is a pseudometric when $d$ is symmetric but not identity-respecting.

**Remark 8.15.** The failure of symmetry of $|Q|$ is *inherited* from the failure of symmetry of $d$. The debt $D$ does not contribute to asymmetry of the modulus, because $D$ enters as $D^2$, which is symmetric. So the modulus is "as symmetric as $d$ is."

**Remark 8.16 (The title of this chapter).** The chapter is titled "The Modulus as a Quasi-Metric" rather than "The Modulus is a Metric" because the latter would suggest an unconditional result. In fact, $|Q|$ is a metric only under additional hypotheses on $d$. The unconditional statement is that $|Q|$ is a quasi-metric.

---

## 8.3 Bounded distortion

The modulus $|Q|$ is related to the energy quasi-metric $d$ by a simple inequality.

**Proposition 8.17 (Bounded distortion).** For all $b_i, b_j \in \mathcal{B}$,

$$d(b_i, b_j) \le |Q|(b_i, b_j) \le d(b_i, b_j) + |D(b_i, b_j)|.$$

*Proof.* The left inequality is immediate from $|Q|^2 = d^2 + D^2 \ge d^2$. For the right inequality:

$$|Q|^2 = d^2 + D^2 \le d^2 + 2d|D| + D^2 = (d + |D|)^2.$$

Taking square roots: $|Q| \le d + |D|$. $\square$

**Corollary 8.18.** $|Q|(b_i, b_j) = d(b_i, b_j)$ if and only if $D(b_i, b_j) = 0$.

**Corollary 8.19.** $|Q|(b_i, b_j) = d(b_i, b_j) + |D(b_i, b_j)|$ if and only if $d(b_i, b_j) = 0$ or $D(b_i, b_j) = 0$.

*Proof.* From the proof of Proposition 8.17, equality holds if and only if $d|D| = 0$. So $d = 0$ or $D = 0$. $\square$

**Remark 8.20.** The modulus $|Q|$ is always *at least* the cost $d$. The debt adds to the cost in the modulus. This is intuitive: a transition with debt is "more costly" in the modulus sense than a transition with the same cost but no debt.

**Remark 8.21.** The modulus is a strictly increasing function of the debt magnitude: for fixed $d$, $|Q|$ increases with $|D|$. So debt always adds to the modulus.

**Proposition 8.22 (Bounded distortion with phase).** For all $b_i, b_j \in \mathcal{B}$ with $Q(b_i, b_j) \neq 0$,

$$|Q|(b_i, b_j) = d(b_i, b_j) \sec \theta(b_i, b_j),$$

where $\theta$ is the phase. In particular:

- $|Q| = d$ if and only if $\theta = 0$.
- $|Q| \to +\infty$ relative to $d$ as $\theta \to \pm\pi/2$.

*Proof.* Since $d = |Q| \cos\theta$, we have $|Q| = d / \cos\theta = d \sec\theta$. $\square$

**Remark 8.23.** The phase $\theta$ measures the "distortion" of the modulus relative to the cost. When $\theta = 0$, the modulus equals the cost. As $|\theta| \to \pi/2$, the modulus becomes much larger than the cost.

---

## 8.4 The metric topology

The modulus $|Q|$ induces a topology on $\mathcal{B}$.

**Definition 8.24 (Metric ball).** The *ball of radius $r$ around $b$* is

$$B(b, r) := \lbrace b' \in \mathcal{B} : |Q|(b, b') < r \rbrace.$$

**Definition 8.25 (Metric topology).** The *metric topology* $\tau_{|Q|}$ is the topology generated by the balls $B(b, r)$ for $b \in \mathcal{B}$ and $r > 0$.

**Proposition 8.26.** The metric topology $\tau_{|Q|}$ is the topology induced by the quasi-metric $|Q|$.

**Proposition 8.27.** If $d$ is symmetric, then $\tau_{|Q|}$ is Hausdorff if and only if $|Q|$ is a metric (i.e., $|Q|$ satisfies the identity of indiscernibles).

*Proof.* If $|Q|$ is a metric, then distinct points have positive distance, so the topology is Hausdorff. Conversely, if $|Q|$ is not a metric, then there exist distinct $b_i \neq b_j$ with $|Q|(b_i, b_j) = 0$, so every neighborhood of $b_i$ contains $b_j$ and vice versa, and the topology is not Hausdorff. $\square$

**Proposition 8.28.** If $d$ is asymmetric, then $\tau_{|Q|}$ is not necessarily Hausdorff.

*Proof.* The forward and backward balls $B^+(b, r) = \{b' : |Q|(b, b') < r\}$ and $B^-(b, r) = \{b' : |Q|(b', b) < r\}$ may differ. The topology generated by the forward balls is one topology; the one generated by the backward balls is another. If $d$ is asymmetric, these topologies may differ, and the resulting topology may not be Hausdorff. $\square$

**Remark 8.29.** The metric topology $\tau_{|Q|}$ is the "symmetrized" topology of the complex quasi-metric. It is the topology generated by the modulus, which is the observable that behaves most like a metric.

**Remark 8.30.** In Part V, we will develop a finer topology structure: the *bitopological* structure generated by the forward and backward balls. This structure is richer than $\tau_{|Q|}$ and captures the asymmetry of the complex quasi-metric.

**Proposition 8.31 (Comparison with the $d$-topology).** If $D = 0$ identically, then $\tau_{|Q|} = \tau_d$, the topology induced by the energy quasi-metric $d$.

*Proof.* If $D = 0$, then $|Q| = d$, so the balls of $|Q|$ coincide with the balls of $d$. $\square$

**Remark 8.32.** When $D \neq 0$, the topology $\tau_{|Q|}$ may differ from $\tau_d$. In general, $\tau_{|Q|}$ is finer than $\tau_d$ in the sense that the balls of $|Q|$ are "larger" (since $|Q| \ge d$).

---

## 8.5 The metric completion

The modulus $|Q|$ induces a metric topology, and this topology has a natural completion.

**Definition 8.33 (Cauchy sequence).** A sequence $(b_n)$ in $\mathcal{B}$ is *Cauchy* with respect to $|Q|$ if for every $\epsilon > 0$, there exists $N$ such that $|Q|(b_m, b_n) < \epsilon$ for all $m, n > N$.

**Definition 8.34 (Completion).** The *completion* of $\mathcal{B}$ with respect to $|Q|$ is the set $\overline{\mathcal{B}}$ of equivalence classes of Cauchy sequences, equipped with the extended modulus $|\overline{Q}|$.

**Proposition 8.35.** The completion $\overline{\mathcal{B}}$ is a complete metric space (if $d$ is symmetric) or complete quasi-metric space (if $d$ is asymmetric).

*Proof.* Standard completion construction: define the distance between two Cauchy sequences $(b_n)$ and $(c_n)$ as $\lim_{n \to \infty} |Q|(b_n, c_n)$, verify that this is well-defined and satisfies the metric axioms, and show that $\mathcal{B}$ embeds densely in $\overline{\mathcal{B}}$. $\square$

**Remark 8.36.** The completion may include points that are not in the original belief space. These are "limit beliefs"—beliefs that can be approximated by sequences of reachable beliefs but are not themselves reachable in finite time.

**Remark 8.37.** The completion is not always necessary. In many applications, the belief space is already complete (e.g., if it is a finite set, or if it is closed under limits). But the construction is important for theoretical completeness.

**Example 8.38 (Completion of a finite space).** If $\mathcal{B}$ is finite, then every Cauchy sequence is eventually constant, so $\overline{\mathcal{B}} = \mathcal{B}$. The completion adds no new points.

**Example 8.39 (Completion of $\mathbb{Q}$ with respect to the Euclidean metric).** If $\mathcal{B} = \mathbb{Q}$ with $d(q_1, q_2) = |q_1 - q_2|$ and $D = 0$, then $\overline{\mathcal{B}} = \mathbb{R}$. The completion adds the irrational numbers as limit points.

---

## 8.6 Summary

We have developed the metric properties of the modulus $|Q| = \sqrt{d^2 + D^2}$.

Key results:

- **Triangle inequality.** $|Q(b_i, b_k)| \le |Q(b_i, b_j)| + |Q(b_j, b_k)|$ (Theorem 8.1, proved in Chapter 7).
- **Equality condition.** The triangle inequality is sharp if and only if the vectors $(d, D)$ are non-negative scalar multiples of each other (Theorem 8.4).
- **Metric properties.** $|Q|$ is a quasi-metric always; a pseudometric if $d$ is symmetric; a metric if $d$ is symmetric and identity-respecting (Theorem 8.10).
- **Bounded distortion.** $d \le |Q| \le d + |D|$ (Proposition 8.17).
- **Phase distortion.** $|Q| = d \sec\theta$ (Proposition 8.22).
- **Metric topology.** $\tau_{|Q|}$ is the topology generated by the balls of $|Q|$ (Definition 8.25).
- **Hausdorff condition.** $\tau_{|Q|}$ is Hausdorff if and only if $|Q|$ is a metric (Proposition 8.27).
- **Completion.** $\overline{\mathcal{B}}$ is the completion of $\mathcal{B}$ with respect to $|Q|$ (Definition 8.34).

The modulus is the natural quasi-metric associated with the complex quasi-metric. It is the observable that behaves most like a classical distance, and it is the one that will be used for topological considerations in Part V.

---

## 8.7 Exercises

**Exercise 8.1.** Verify the triangle inequality for $|Q|$ in the following example. Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 2 & 4 \\ 2 & 0 & 3 \\ 4 & 3 & 0 \end{pmatrix}, \qquad D = \begin{pmatrix} 0 & 1 & 2 \\ -1 & 0 & 1 \\ -2 & -1 & 0 \end{pmatrix}.$$

Compute $|Q|$ for all pairs and verify the triangle inequality for all triples.

**Exercise 8.2.** Prove that if $d$ is symmetric, then $|Q|$ is symmetric. Give an example where $d$ is asymmetric and $|Q|$ is also asymmetric.

**Exercise 8.3.** Show that if $d$ is a metric, then $|Q|$ is a metric, regardless of $D$. Give an example where $D \neq 0$ and $|Q|$ is still a metric.

**Exercise 8.4.** Compute the modulus $|Q|$ for the pure debt case $d = 0$. Show that $|Q|$ is symmetric even though $D$ is antisymmetric.

**Exercise 8.5.** Prove Proposition 8.17 (bounded distortion).

**Exercise 8.6.** Prove Corollary 8.19: $|Q| = d + |D|$ if and only if $d = 0$ or $D = 0$.

**Exercise 8.7.** Show that the equality condition in Theorem 8.4 is equivalent to the condition that the phases of the two transitions agree.

**Exercise 8.8.** Let $\mathcal{B}$ be a finite set with $n$ elements. Show that $|Q|$ is a metric if and only if $d$ is a metric (i.e., $d$ is symmetric and identity-respecting). Does $D$ play any role in this condition?

**Exercise 8.9.** Compute the metric completion of $\mathcal{B} = \mathbb{Q}$ with $d(q_1, q_2) = |q_1 - q_2|$ and $D = 0$. What is the completion?

**Exercise 8.10.** Prove that the metric topology $\tau_{|Q|}$ is Hausdorff if and only if $|Q|$ is a metric.

**Exercise 8.11.** Let $D = 0$ identically. Show that $\tau_{|Q|} = \tau_d$.

**Exercise 8.12.** Let $d = 0$ identically. Show that $|Q| = |D|$ and that $\tau_{|Q|}$ is the discrete topology if $D$ separates points.

**Exercise 8.13.** Reflect on the following question: why is the modulus $|Q|$ a quasi-metric even when $Q$ itself is not? Write a short essay (one page) arguing for your position.

