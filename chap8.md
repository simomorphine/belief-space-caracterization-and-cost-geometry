# Chapter 7: The Modulus is a Metric

---

In Chapter 6, we introduced the complex quasi-metric $Q = d + iD$ and proved that its modulus $|Q|$ satisfies the triangle inequality. This chapter develops the metric properties of $|Q|$ in full.

The central theme is the following: **the modulus repairs what the real part lacks.** The energy quasi-metric $d$ may be asymmetric; the modulus $|Q|$ is symmetric whenever $d$ is symmetric, and satisfies the triangle inequality always. The modulus is the "metric completion" of the complex quasi-metric—the observable that behaves like a genuine distance.

This chapter is the bridge between the complex structure of $Q$ and the geometric/topological structure that follows in Parts IV and V.

---

## 7.1 The triangle inequality in detail

We begin by revisiting the proof of the triangle inequality for $|Q|$, with all details made explicit.

**Theorem 7.1 (Triangle inequality for $|Q|$).** For all $b_i, b_j, b_k \in \mathcal{B}$,

$$|Q(b_i, b_k)| \le |Q(b_i, b_j)| + |Q(b_j, b_k)|.$$

*Proof.* We prove this in three steps.

**Step 1: Reduction to $\mathbb{R}^2$.** Define vectors $u, v, w \in \mathbb{R}^2$ by

$$u := (d(b_i, b_j), D(b_i, b_j)), \quad v := (d(b_j, b_k), D(b_j, b_k)), \quad w := u + v = (d(b_i, b_j) + d(b_j, b_k), D(b_i, b_j) + D(b_j, b_k)).$$

Then $|Q(b_i, b_j)| = \|u\|_2$, $|Q(b_j, b_k)| = \|v\|_2$, and $\|w\|_2 = \sqrt{(d(b_i, b_j) + d(b_j, b_k))^2 + (D(b_i, b_j) + D(b_j, b_k))^2}$.

**Step 2: Comparison with $|Q(b_i, b_k)|$.** We have

$$|Q(b_i, b_k)|^2 = d(b_i, b_k)^2 + D(b_i, b_k)^2.$$

By the triangle inequality for $d$:

$$d(b_i, b_k) \le d(b_i, b_j) + d(b_j, b_k).$$

By additivity of $D$:

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

Both quantities are non-negative (the second after squaring). Hence

$$d(b_i, b_k)^2 \le (d(b_i, b_j) + d(b_j, b_k))^2, \qquad D(b_i, b_k)^2 = (D(b_i, b_j) + D(b_j, b_k))^2.$$

Summing:

$$|Q(b_i, b_k)|^2 \le (d(b_i, b_j) + d(b_j, b_k))^2 + (D(b_i, b_j) + D(b_j, b_k))^2 = \|w\|_2^2.$$

**Step 3: Minkowski.** By Minkowski's inequality in $\mathbb{R}^2$:

$$\|w\|_2 = \|u + v\|_2 \le \|u\|_2 + \|v\|_2 = |Q(b_i, b_j)| + |Q(b_j, b_k)|.$$

Combining steps 2 and 3:

$$|Q(b_i, b_k)| \le \|w\|_2 \le |Q(b_i, b_j)| + |Q(b_j, b_k)|. \quad \square$$

**Remark 7.2.** The proof uses only two properties of the ingredients: the triangle inequality for $d$, and the additivity of $D$. Symmetry of $d$ is *not* used. The modulus satisfies the triangle inequality regardless of whether $d$ is symmetric.

**Remark 7.3.** The proof is the standard proof that a norm on a product is a norm. Specifically, the map $(d, D) \mapsto |Q|$ is the Euclidean norm on $\mathbb{R}^2$, and the triangle inequality for $|Q|$ is the triangle inequality for the Euclidean norm, transported through the map $(b_i, b_j) \mapsto (d(b_i, b_j), D(b_i, b_j))$.

**Remark 7.4.** The triangle inequality for $|Q|$ is *sharp*: equality holds if and only if the vectors $u$ and $v$ are non-negative scalar multiples of each other. In the context of belief space, this means that the path from $b_i$ to $b_k$ through $b_j$ is optimal: the cost and debt of the direct transition equal the sums of the costs and debts of the intermediate transitions.

---

## 7.2 The modulus as a metric: full statement

We now state the full metric properties of $|Q|$.

**Theorem 7.5 (Metric properties of $|Q|$).** Let $|Q| : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ be the modulus of the complex quasi-metric $Q = d + iD$. Then:

- **(M0) Identity.** $|Q|(b, b) = 0$ for all $b \in \mathcal{B}$.
- **(M1) Non-negativity.** $|Q|(b_i, b_j) \ge 0$ for all $b_i, b_j \in \mathcal{B}$.
- **(M2) Triangle inequality.** $|Q|(b_i, b_k) \le |Q|(b_i, b_j) + |Q|(b_j, b_k)$.
- **(M3) Symmetry.** $|Q|(b_i, b_j) = |Q|(b_j, b_i)$ if and only if $d(b_i, b_j) = d(b_j, b_i)$.
- **(M4) Identity of indiscernibles.** $|Q|(b_i, b_j) = 0$ if and only if $d(b_i, b_j) = 0$ and $D(b_i, b_j) = 0$.

*Proof.*

- (M0) $|Q|(b, b) = \sqrt{d(b, b)^2 + D(b, b)^2} = 0$.
- (M1) Square root of a sum of squares.
- (M2) Theorem 7.1.
- (M3) $|Q|(b_i, b_j)^2 - |Q|(b_j, b_i)^2 = [d(b_i, b_j)^2 - d(b_j, b_i)^2] + [D(b_i, b_j)^2 - D(b_j, b_i)^2]$. The second bracket is zero by antisymmetry. So $|Q|(b_i, b_j) = |Q|(b_j, b_i)$ iff $d(b_i, b_j) = d(b_j, b_i)$.
- (M4) $|Q|(b_i, b_j) = 0$ iff $d(b_i, b_j)^2 + D(b_i, b_j)^2 = 0$ iff both terms are zero. $\square$

**Corollary 7.6.** If $d$ is symmetric and satisfies the identity of indiscernibles, then $|Q|$ is a metric on $\mathcal{B}$.

**Corollary 7.7.** If $d$ is symmetric but fails the identity of indiscernibles, then $|Q|$ is a pseudometric on $\mathcal{B}$.

**Corollary 7.8.** If $d$ is asymmetric, then $|Q|$ is a quasi-metric on $\mathcal{B}$ (satisfies the triangle inequality but not necessarily symmetry).

**Remark 7.9.** The modulus $|Q|$ is always *at least* a quasi-metric. It is a metric exactly when $d$ is symmetric and identity-respecting. It is a pseudometric when $d$ is symmetric but not identity-respecting.

**Remark 7.10.** The failure of symmetry of $|Q|$ is *inherited* from the failure of symmetry of $d$. The debt $D$ does not contribute to asymmetry of the modulus, because $D$ enters as $D^2$, which is symmetric. So the modulus is "as symmetric as $d$ is."

---

## 7.3 The metric topology

The modulus $|Q|$ induces a topology on $\mathcal{B}$.

**Definition 7.11 (Metric ball).** The *ball of radius $r$ around $b$* is

$$B(b, r) := \{b' \in \mathcal{B} : |Q|(b, b') < r\}.$$

**Definition 7.12 (Metric topology).** The *metric topology* $\tau_{|Q|}$ is the topology generated by the balls $B(b, r)$ for $b \in \mathcal{B}$ and $r > 0$.

**Proposition 7.13.** If $d$ is symmetric, then $\tau_{|Q|}$ is the topology induced by the pseudometric $|Q|$.

**Proposition 7.14.** If $d$ is asymmetric, then $\tau_{|Q|}$ is the topology induced by the quasi-metric $|Q|$. This topology is not necessarily Hausdorff.

*Proof.* The forward and backward balls $B^+(b, r) = \{b' : |Q|(b, b') < r\}$ and $B^-(b, r) = \{b' : |Q|(b', b) < r\}$ may differ. The topology generated by the forward balls is one topology; the one generated by the backward balls is another. If $d$ is asymmetric, these topologies may differ.

**Remark 7.15.** The metric topology $\tau_{|Q|}$ is the "symmetrized" topology of the complex quasi-metric. It is the topology generated by the modulus, which is the observable that behaves most like a metric.

**Remark 7.16.** In Part V, we will develop a finer topology structure: the *bitopological* structure generated by the forward and backward balls. This structure is richer than $\tau_{|Q|}$ and captures the asymmetry of the complex quasi-metric.

---

## 7.4 Comparison with the energy quasi-metric

The modulus $|Q|$ is related to the energy quasi-metric $d$ by a simple inequality.

**Proposition 7.17.** For all $b_i, b_j \in \mathcal{B}$,

$$d(b_i, b_j) \le |Q|(b_i, b_j) \le d(b_i, b_j) + |D(b_i, b_j)|.$$

*Proof.* The left inequality is immediate from $|Q|^2 = d^2 + D^2 \ge d^2$. For the right inequality:

$$|Q|^2 = d^2 + D^2 \le d^2 + 2d|D| + D^2 = (d + |D|)^2.$$

Taking square roots:

$$|Q| \le d + |D|. \quad \square$$

**Corollary 7.18.** $|Q|(b_i, b_j) = d(b_i, b_j)$ if and only if $D(b_i, b_j) = 0$.

**Corollary 7.19.** $|Q|(b_i, b_j) \le d(b_i, b_j) + |D(b_i, b_j)|$, with equality if and only if $d(b_i, b_j) = 0$ or $D(b_i, b_j) = 0$ or they have the same sign in the sense of the triangle inequality in $\mathbb{R}^2$.

**Remark 7.20.** The modulus $|Q|$ is always *at least* the cost $d$. The debt adds to the cost in the modulus. This is intuitive: a transition with debt is "more costly" in the modulus sense than a transition with the same cost but no debt.

**Remark 7.21.** The modulus is a strictly increasing function of the debt magnitude: for fixed $d$, $|Q|$ increases with $|D|$. So debt always adds to the modulus.

**Proposition 7.22 (Bounded distortion).** For all $b_i, b_j \in \mathcal{B}$ with $|D(b_i, b_j)| \le M$,

$$d(b_i, b_j) \le |Q|(b_i, b_j) \le d(b_i, b_j) + M.$$

So the modulus is within a bounded additive factor of the cost, with the bound controlled by the maximum debt.

---

## 7.5 The modulus and the phase

We now relate the modulus and the phase.

**Proposition 7.23.** For all $b_i, b_j$,

$$d(b_i, b_j) = |Q(b_i, b_j)| \cos \theta(b_i, b_j), \qquad D(b_i, b_j) = |Q(b_i, b_j)| \sin \theta(b_i, b_j).$$

*Proof.* These are the standard trigonometric decompositions of a complex number in polar form. $\square$

**Corollary 7.24.** The cost $d$ is the projection of $Q$ onto the real axis; the debt $D$ is the projection onto the imaginary axis.

**Corollary 7.25.** The phase $\theta$ is the angle between $Q$ and the real axis.

**Remark 7.26.** The modulus $|Q|$ is the "total" magnitude of the transition, combining cost and debt. The phase $\theta$ is the "direction" of the transition, indicating whether it is dominated by cost ($\theta \approx 0$) or debt ($\theta \approx \pm\pi/2$).

**Remark 7.27.** The pair $(|Q|, \theta)$ is the polar coordinate representation of the complex quasi-metric. It is an alternative to the Cartesian representation $(d, D)$. Both are equivalent; the polar representation is more convenient for geometric considerations.

---

## 7.6 The metric completion

The modulus $|Q|$ induces a metric topology, and this topology has a natural completion.

**Definition 7.28 (Cauchy sequence).** A sequence $(b_n)$ in $\mathcal{B}$ is *Cauchy* with respect to $|Q|$ if for every $\epsilon > 0$, there exists $N$ such that $|Q|(b_m, b_n) < \epsilon$ for all $m, n > N$.

**Definition 7.29 (Completion).** The *completion* of $\mathcal{B}$ with respect to $|Q|$ is the set $\overline{\mathcal{B}}$ of equivalence classes of Cauchy sequences, equipped with the extended modulus $|\overline{Q}|$.

**Proposition 7.30.** The completion $\overline{\mathcal{B}}$ is a complete metric space (if $d$ is symmetric) or complete quasi-metric space (if $d$ is asymmetric).

*Proof.* Standard completion construction. $\square$

**Remark 7.31.** The completion may include points that are not in the original belief space. These are "limit beliefs" — beliefs that can be approximated by sequences of reachable beliefs but are not themselves reachable in finite time.

**Remark 7.32.** The completion is not always necessary. In many applications, the belief space is already complete (e.g., if it is a finite set, or if it is closed under limits). But the construction is important for theoretical completeness.

---

## 7.7 The modulus and the triangle inequality: sharpness

We now analyze when the triangle inequality for $|Q|$ is sharp.

**Proposition 7.33 (Equality condition).** For $b_i, b_j, b_k \in \mathcal{B}$, the equality

$$|Q(b_i, b_k)| = |Q(b_i, b_j)| + |Q(b_j, b_k)|$$

holds if and only if the vectors $(d(b_i, b_j), D(b_i, b_j))$ and $(d(b_j, b_k), D(b_j, b_k))$ are non-negative scalar multiples of each other.

*Proof.* This is the equality condition for Minkowski's inequality in $\mathbb{R}^2$. $\square$

**Corollary 7.34.** If $D = 0$ identically, then the triangle inequality for $|Q| = d$ is sharp if and only if the path through $b_j$ is optimal.

**Corollary 7.35.** If $d = 0$ identically, then the triangle inequality for $|Q| = |D|$ is sharp if and only if $D(b_i, b_j)$ and $D(b_j, b_k)$ have the same sign.

**Remark 7.36.** The equality condition is the same as the condition that the path through $b_j$ is "geodesic" in the modulus metric. This connects to the optimization theory of Chapter 10.

**Remark 7.37.** The failure of equality is the *excess* of the modulus over the direct transition. This excess is the "detour cost" in the modulus metric. It is non-negative by the triangle inequality.

---

## 7.8 The metric properties of the modulus

We summarize the metric properties of $|Q|$ in a single theorem.

**Theorem 7.38 (Complete metric properties).** Let $|Q| : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ be the modulus of the complex quasi-metric $Q = d + iD$. Then:

- **(i)** $|Q|$ is a quasi-metric on $\mathcal{B}$, always.
- **(ii)** $|Q|$ is a pseudometric on $\mathcal{B}$ if $d$ is symmetric.
- **(iii)** $|Q|$ is a metric on $\mathcal{B}$ if $d$ is symmetric and satisfies the identity of indiscernibles.
- **(iv)** $|Q|$ is bounded below by $d$: $|Q| \ge d$.
- **(v)** $|Q|$ is bounded above by $d + |D|$: $|Q| \le d + |D|$.
- **(vi)** $|Q| = d$ if and only if $D = 0$ identically.
- **(vii)** The metric topology $\tau_{|Q|}$ is the same as the topology induced by the balls $B(b, r) = \{b' : |Q|(b, b') < r\}$.

*Proof.* Assembled from the propositions and theorems above. $\square$

**Remark 7.39.** The theorem says that the modulus is a "minimal" metric derived from the complex quasi-metric. It is always at least a quasi-metric, and it inherits the symmetry and identity properties of $d$.

**Remark 7.40.** The modulus is the "natural" metric associated with the complex quasi-metric. It is the observable that behaves most like a classical metric, and it is the one that will be used for topological considerations.

---

## 7.9 Examples

We close this chapter with examples illustrating the metric properties of $|Q|$.

**Example 7.41 (Symmetric cost, nonzero debt).** Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 2 & 4 \\ 2 & 0 & 3 \\ 4 & 3 & 0 \end{pmatrix}, \qquad D = \begin{pmatrix} 0 & 1 & 2 \\ -1 & 0 & 1 \\ -2 & -1 & 0 \end{pmatrix}.$$

The modulus is

$$|Q| = \begin{pmatrix} 0 & \sqrt{5} & \sqrt{20} \\ \sqrt{5} & 0 & \sqrt{10} \\ \sqrt{20} & \sqrt{10} & 0 \end{pmatrix} \approx \begin{pmatrix} 0 & 2.236 & 4.472 \\ 2.236 & 0 & 3.162 \\ 4.472 & 3.162 & 0 \end{pmatrix}.$$

Verify: $|Q|(1, 3) = 4.472 \le 2.236 + 3.162 = 5.398$. ✓

**Example 7.42 (Asymmetric cost, nonzero debt).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = 3$, $d(2, 1) = 1$, $D(1, 2) = 2$, $D(2, 1) = -2$. The modulus is $|Q|(1, 2) = \sqrt{9 + 4} = \sqrt{13} \approx 3.606$, $|Q|(2, 1) = \sqrt{1 + 4} = \sqrt{5} \approx 2.236$. The modulus is asymmetric because $d$ is asymmetric.

**Example 7.43 (Pure cost).** If $D = 0$, then $|Q| = d$. The modulus is just the cost.

**Example 7.44 (Pure debt).** If $d = 0$ (all transitions have zero cost), then $|Q| = |D|$. The modulus is the absolute value of the debt. It is symmetric (since $|D|$ is symmetric) even though $D$ is antisymmetric.

**Remark 7.45.** The examples illustrate the range of behaviors of the modulus. In general, $|Q|$ is a metric-like object that combines the asymmetry of $d$ with the symmetry of $D^2$.

---

## 7.10 Summary

We have developed the metric properties of the modulus $|Q| = \sqrt{d^2 + D^2}$.

Key results:

- **Triangle inequality.** $|Q(b_i, b_k)| \le |Q(b_i, b_j)| + |Q(b_j, b_k)|$ (Theorem 7.1).
- **Metric properties.** $|Q|$ is a quasi-metric always; a pseudometric if $d$ is symmetric; a metric if $d$ is symmetric and identity-respecting (Theorem 7.5).
- **Bounded distortion.** $d \le |Q| \le d + |D|$ (Proposition 7.17).
- **Polar form.** $d = |Q| \cos\theta$, $D = |Q| \sin\theta$ (Proposition 7.23).
- **Metric topology.** $\tau_{|Q|}$ is the topology generated by the balls of $|Q|$.
- **Completion.** $\overline{\mathcal{B}}$ is the completion of $\mathcal{B}$ with respect to $|Q|$.
- **Equality condition.** The triangle inequality is sharp iff the vectors $(d, D)$ are colinear and same-sign.

The modulus is the natural metric associated with the complex quasi-metric. It is the observable that behaves most like a classical distance, and it is the one that will be used for topological considerations in Part V.

---

## 7.11 Exercises

**Exercise 7.1.** Verify the triangle inequality for $|Q|$ in Example 7.41 for all triples.

**Exercise 7.2.** Prove that if $d$ is symmetric, then $|Q|$ is symmetric.

**Exercise 7.3.** Show that if $d$ is a metric, then $|Q|$ is a metric if and only if $D = 0$.

**Exercise 7.4.** Compute the modulus $|Q|$ for the pure debt case $d = 0$. Show that $|Q|$ is symmetric.

**Exercise 7.5.** Prove Proposition 7.17 (bounded distortion).

**Exercise 7.6.** Show that the equality condition in Proposition 7.33 is equivalent to the condition that the path through $b_j$ is optimal in the modulus metric.

**Exercise 7.7.** Let $\mathcal{B}$ be a finite set with $n$ elements. Show that $|Q|$ is a metric if and only if $d$ is a metric and $D$ vanishes only on the diagonal.

**Exercise 7.8.** Compute the metric completion of $\mathcal{B}$ for the example in Exercise 7.1. Does it contain any new points?

**Exercise 7.9.** Prove that the metric topology $\tau_{|Q|}$ is Hausdorff if and only if $|Q|$ is a metric.

**Exercise 7.10.** Reflect on the following question: why is the modulus $|Q|$ a metric even when $Q$ itself is not? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we develop the gauge structure of the complex quasi-metric. We introduce the gauge group, describe its action on $Q$, and identify the gauge-invariant observables.*

---

**End of Chapter 7.**
