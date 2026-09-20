# Chapter 10: The γ-Family

---

In Chapters 7–9, we developed the complex quasi-metric $Q = d + iD$, studied the metric properties of its modulus $|Q|$, and characterized its gauge structure. The modulus is the "full" metric that incorporates both cost and debt.

But the modulus is not the only metric-like object we can form from $d$ and $D$. There is a whole *one-parameter family* of quasi-metrics, interpolating between the pure cost $d$ (at one extreme) and the full modulus $|Q|$ (at the other).

This family, called the **$\gamma$-family**, is the subject of this chapter. It is defined by

$$d_\gamma(b_i, b_j) := \sqrt{d(b_i, b_j)^2 + \gamma^2 D(b_i, b_j)^2}, \qquad \gamma \in [0, 1].$$

At $\gamma = 0$, we recover the energy quasi-metric $d$. At $\gamma = 1$, we recover the modulus $|Q|$. For intermediate $\gamma$, we get a quasi-metric that interpolates between the two.

The $\gamma$-family is a natural one-parameter deformation of the energy quasi-metric by the debt. It shows that the complex quasi-metric is not just a single object, but a *family* of quasi-metrics parameterized by a continuous parameter.

**Remark 10.0 (Scope of this chapter).** This chapter develops the definition and basic properties of the $\gamma$-family. The topological properties of the family—the dependence of the topology $\tau_\gamma$ on $\gamma$, and the phase transitions that occur at critical values of $\gamma$—are developed in Chapter 11. The reader who wants only the algebraic and metric properties can read this chapter; the reader who wants the topological structure should read both.

---

## 10.1 Definition and basic properties

We begin with the definition.

**Definition 10.1 ($\gamma$-distance).** Let $Q = d + iD$ be a complex quasi-metric on $\mathcal{B}$. For $\gamma \in [0, 1]$, the *$\gamma$-distance* is

$$d_\gamma(b_i, b_j) := \sqrt{d(b_i, b_j)^2 + \gamma^2 D(b_i, b_j)^2}.$$

**Remark 10.2.** The parameter $\gamma$ controls the relative weight of cost and debt in the quasi-metric. At $\gamma = 0$, debt is ignored; at $\gamma = 1$, debt is fully incorporated. Intermediate values of $\gamma$ correspond to partial incorporation.

**Proposition 10.3 (Extremes).**

- $d_0(b_i, b_j) = d(b_i, b_j)$ (pure cost);
- $d_1(b_i, b_j) = |Q(b_i, b_j)|$ (full modulus).

*Proof.* Immediate from the definition. $\square$

**Proposition 10.4 (Non-negativity).** $d_\gamma(b_i, b_j) \ge 0$ for all $\gamma \in [0, 1]$ and all $b_i, b_j$.

*Proof.* Sum of squares. $\square$

**Proposition 10.5 (Identity).** $d_\gamma(b, b) = 0$ for all $\gamma$ and all $b$.

*Proof.* $d(b, b) = 0$ and $D(b, b) = 0$, so $d_\gamma(b, b) = 0$. $\square$

**Proposition 10.6 (Monotonicity in $\gamma$).** For fixed $b_i, b_j$, the function $\gamma \mapsto d_\gamma(b_i, b_j)$ is non-decreasing on $[0, 1]$.

*Proof.* $d_\gamma^2 = d^2 + \gamma^2 D^2$, which is non-decreasing in $\gamma$ since $D^2 \ge 0$. $\square$

**Remark 10.7.** The monotonicity says that increasing $\gamma$ can only increase distances (or leave them unchanged). Debt never decreases the $\gamma$-distance; it only adds to it.

**Proposition 10.8 (Strict monotonicity).** If $D(b_i, b_j) \neq 0$, then $\gamma \mapsto d_\gamma(b_i, b_j)$ is strictly increasing on $[0, 1]$.

*Proof.* $\frac{d}{d\gamma} d_\gamma = \frac{\gamma D^2}{d_\gamma} > 0$ when $\gamma > 0$ and $D \neq 0$. $\square$

---

## 10.2 The triangle inequality for $d_\gamma$

The central result of this chapter is that $d_\gamma$ satisfies the triangle inequality for every $\gamma$.

**Theorem 10.9 (Triangle inequality for $d_\gamma$).** For every $\gamma \in [0, 1]$ and all $b_i, b_j, b_k \in \mathcal{B}$,

$$d_\gamma(b_i, b_k) \le d_\gamma(b_i, b_j) + d_\gamma(b_j, b_k).$$

*Proof.* We prove this using the norm-space interpretation.

**Step 1: Reduction to a norm.** Define the linear map $L_\gamma : \mathbb{R}^2 \to \mathbb{R}^2$ by

$$L_\gamma(x, y) := (x, \gamma y).$$

Then $d_\gamma(b_i, b_j) = \|L_\gamma(d(b_i, b_j), D(b_i, b_j))\|_2$, where $\|\cdot\|_2$ is the Euclidean norm on $\mathbb{R}^2$.

**Step 2: Minkowski.** By the triangle inequality for $d$ and the additivity of $D$:

$$d(b_i, b_k) \le d(b_i, b_j) + d(b_j, b_k), \qquad D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

Applying $L_\gamma$:

$$L_\gamma(d(b_i, b_k), D(b_i, b_k)) = (d(b_i, b_k), \gamma D(b_i, b_k)).$$

The first coordinate is bounded by the sum of first coordinates of $L_\gamma(d(b_i, b_j), D(b_i, b_j))$ and $L_\gamma(d(b_j, b_k), D(b_j, b_k))$; the second coordinate is *equal* to the sum of second coordinates.

By Minkowski's inequality in $\mathbb{R}^2$:

$$\|L_\gamma(d(b_i, b_k), D(b_i, b_k))\|_2 \le \|L_\gamma(d(b_i, b_j), D(b_i, b_j))\|_2 + \|L_\gamma(d(b_j, b_k), D(b_j, b_k))\|_2.$$

This is exactly the triangle inequality for $d_\gamma$. $\square$

**Remark 10.10.** The proof is a direct application of Minkowski's inequality in $\mathbb{R}^2$, transported through the linear map $L_\gamma$. The key observation is that $L_\gamma$ preserves the additivity of the second coordinate (since it just scales it by $\gamma$), and the first coordinate satisfies the triangle inequality by hypothesis.

**Remark 10.11.** The triangle inequality holds for every $\gamma \in [0, 1]$, not just the endpoints. This is because Minkowski's inequality holds for every norm, and $L_\gamma$ is a linear map for every $\gamma$. There is nothing special about the endpoints.

**Remark 10.12.** The parameter $\gamma$ can in fact be any real number $\ge 0$. The range $[0, 1]$ is chosen for normalization: $\gamma = 0$ is pure cost, $\gamma = 1$ is full modulus. Values $\gamma > 1$ correspond to over-weighting the debt.

**Corollary 10.13 (Symmetry).** $d_\gamma(b_i, b_j) = d_\gamma(b_j, b_i)$ if and only if $d(b_i, b_j) = d(b_j, b_i)$.

*Proof.* $d_\gamma^2 = d^2 + \gamma^2 D^2$. The second term is symmetric (since $D^2$ is symmetric). The first term is symmetric iff $d$ is symmetric. $\square$

**Corollary 10.14 (Quasi-metric).** $d_\gamma$ is a quasi-metric on $\mathcal{B}$ for every $\gamma \in [0, 1]$.

*Proof.* Combine Theorem 10.9 with Corollary 10.13. $\square$

**Corollary 10.15 (Metric).** $d_\gamma$ is a metric on $\mathcal{B}$ if and only if:

1. $d$ is symmetric, and
2. $d_\gamma(b_i, b_j) = 0 \Rightarrow b_i = b_j$.

The second condition is equivalent to: $d(b_i, b_j) = 0$ and $D(b_i, b_j) = 0$ imply $b_i = b_j$.

*Proof.* If $d$ is symmetric, then $d_\gamma$ is symmetric. The triangle inequality holds by Theorem 10.9. The identity of indiscernibles holds iff $d_\gamma(b_i, b_j) = 0 \Rightarrow b_i = b_j$, which is equivalent to the stated condition. Conversely, if $d_\gamma$ is a metric, then it is symmetric, which forces $d$ to be symmetric, and the identity of indiscernibles forces the stated condition. $\square$

**Remark 10.16.** Note that $d_\gamma$ can be a metric even when $D \neq 0$. For example, if $d$ is a metric and $D(b_i, b_j) = 0$ whenever $d(b_i, b_j) = 0$, then $d_\gamma$ is a metric. The condition is not "$\gamma = 0$ or $D = 0$"; it is that $D$ does not vanish on any pair where $d$ is already zero and the points are distinct.

---

## 10.3 The norm-space interpretation

The $\gamma$-family has a clean geometric interpretation.

**Definition 10.17 (Norm-space).** The *norm-space* of the complex quasi-metric is the space $\mathbb{R}^2$ equipped with the Euclidean norm $\|\cdot\|_2$.

**Construction 10.18 (Embedding).** Define the map $\Phi : \mathcal{B} \times \mathcal{B} \to \mathbb{R}^2$ by

$$\Phi(b_i, b_j) := (d(b_i, b_j), D(b_i, b_j)).$$

Then $\Phi$ embeds the pairs of beliefs into $\mathbb{R}^2$.

**Proposition 10.19.** The modulus is the composition

$$|Q| = \|\cdot\|_2 \circ \Phi.$$

**Proposition 10.20.** The $\gamma$-distance is the composition

$$d_\gamma = \|\cdot\|_2 \circ L_\gamma \circ \Phi,$$

where $L_\gamma(x, y) = (x, \gamma y)$.

*Proof.* Direct computation. $\square$

**Remark 10.21.** The $\gamma$-family is the image of the *straight line* in norm-space under the map $L_\gamma$. As $\gamma$ varies from $0$ to $1$, the image of $\Phi$ is scaled vertically by $\gamma$. At $\gamma = 0$, the image is projected onto the $x$-axis (pure cost). At $\gamma = 1$, the image is unchanged (full modulus).

**Remark 10.22.** The norm-space interpretation shows that the $\gamma$-family is *natural*: it is not an arbitrary interpolation, but the result of a linear deformation of the Euclidean norm. The family is the "geodesic" in the space of norms on $\mathbb{R}^2$, restricted to the image of $\Phi$.

**Remark 10.23.** The norm-space interpretation also shows why the triangle inequality holds for every $\gamma$: the Euclidean norm satisfies the triangle inequality, and $L_\gamma$ is linear, so the composition satisfies the triangle inequality.

---

## 10.4 The $\gamma$-family as a deformation

We now interpret the $\gamma$-family as a deformation of the energy quasi-metric.

**Definition 10.24 (Deformation path).** The *deformation path* of the complex quasi-metric is the map $\gamma \mapsto d_\gamma$.

**Proposition 10.25.** The deformation path is continuous in $\gamma$ with respect to the topology of pointwise convergence.

*Proof.* $d_\gamma^2 = d^2 + \gamma^2 D^2$ is continuous in $\gamma$, so $d_\gamma$ is continuous. $\square$

**Proposition 10.26.** The deformation path is *monotone*: $d_\gamma \le d_{\gamma'}$ pointwise for $\gamma \le \gamma'$.

*Proof.* Proposition 10.6. $\square$

**Proposition 10.27.** The deformation path is *strictly monotone* at each pair with $D \neq 0$.

*Proof.* Proposition 10.8. $\square$

**Remark 10.28.** The deformation path is a one-parameter family of quasi-metrics, all on the same underlying set $\mathcal{B}$, continuously deforming from $d$ to $|Q|$. This is a "homotopy" of quasi-metrics.

**Remark 10.29.** The deformation is *not* a homotopy in the usual topological sense, because the topology induced by $d_\gamma$ may change discontinuously even when $d_\gamma$ varies continuously. Topological changes require a finer analysis, which is developed in Chapter 11.

---

## 10.5 The geometry of the $\gamma$-family

We now study the geometry of the $\gamma$-family.

**Definition 10.30 ($\gamma$-ball).** The *$\gamma$-ball of radius $r$ around $b$* is

$$B_\gamma(b, r) := \{b' \in \mathcal{B} : d_\gamma(b, b') < r\}.$$

**Proposition 10.31 (Nesting of balls).** For $\gamma \le \gamma'$ and fixed $r > 0$,

$$B_{\gamma'}(b, r) \subseteq B_\gamma(b, r).$$

*Proof.* If $d_{\gamma'}(b, b') < r$, then $d_\gamma(b, b') \le d_{\gamma'}(b, b') < r$. $\square$

**Remark 10.32.** Increasing $\gamma$ shrinks the balls. This is because increasing $\gamma$ increases the distances (by monotonicity), so the set of points at distance less than $r$ shrinks.

**Proposition 10.33 (Topology monotonicity).** The topology $\tau_\gamma$ induced by $d_\gamma$ is *coarser* for larger $\gamma$: $\tau_{\gamma'} \subseteq \tau_\gamma$ for $\gamma \le \gamma'$.

*Proof.* The balls $B_{\gamma'}(b, r)$ are subsets of $B_\gamma(b, r)$. So a set that is open in $\tau_{\gamma'}$ is open in $\tau_\gamma$. $\square$

**Remark 10.34.** Larger $\gamma$ gives a coarser topology. At $\gamma = 0$, the topology is the finest (the topology of $d$); at $\gamma = 1$, the topology is the coarsest (the topology of $|Q|$).

**Remark 10.35 (Forward reference).** The topology $\tau_\gamma$ can change discontinuously as $\gamma$ varies: there may be values of $\gamma$ at which the topology changes abruptly. This is the origin of the "phase transitions" mentioned in the introduction. A finer analysis of these transitions is the subject of Chapter 11, where we show that the topology $\tau_\gamma$ depends only on the *asymptotic behavior* of the ratio $D/d$, and identify the critical values of $\gamma$ at which the topology changes.

---

## 10.6 The $\gamma$-family and the phase

We now relate the $\gamma$-family to the phase $\theta$ of the complex quasi-metric.

**Proposition 10.36.** The $\gamma$-distance can be written in terms of the modulus and phase as

$$d_\gamma(b_i, b_j) = |Q(b_i, b_j)| \sqrt{\cos^2\theta(b_i, b_j) + \gamma^2 \sin^2\theta(b_i, b_j)}.$$

*Proof.* $d = |Q| \cos\theta$ and $D = |Q| \sin\theta$. Substituting:

$$d_\gamma^2 = |Q|^2 \cos^2\theta + \gamma^2 |Q|^2 \sin^2\theta = |Q|^2 (\cos^2\theta + \gamma^2 \sin^2\theta). \quad \square$$

**Corollary 10.37.** The ratio $d_\gamma / |Q|$ depends only on $\gamma$ and the phase $\theta$:

$$\frac{d_\gamma}{|Q|} = \sqrt{\cos^2\theta + \gamma^2 \sin^2\theta}.$$

**Remark 10.38.** The $\gamma$-family is a *phase-dependent* rescaling of the modulus. For a transition with phase $\theta = 0$ (pure cost), $d_\gamma = |Q|$ for all $\gamma$. For a transition with phase $\theta = \pm \pi/2$ (pure debt), $d_\gamma = \gamma |Q|$. For intermediate phases, $d_\gamma$ interpolates between these extremes.

**Remark 10.39.** The phase $\theta$ determines how much the $\gamma$-deformation affects a given transition. Transitions with large $|\theta|$ (debt-dominated) are strongly affected; transitions with small $|\theta|$ (cost-dominated) are weakly affected.

**Proposition 10.40 (Extreme phases).**

- If $\theta = 0$: $d_\gamma = |Q| = d$ for all $\gamma$.
- If $\theta = \pm \pi/2$: $d_\gamma = \gamma |Q| = \gamma |D|$ for all $\gamma$.
- If $\theta = \pm \pi/4$: $d_\gamma = |Q| \sqrt{(1 + \gamma^2)/2}$.

*Proof.* Direct computation. $\square$

**Remark 10.41.** The $\gamma$-family is "invisible" at $\theta = 0$ and "maximally visible" at $\theta = \pm \pi/2$. This is intuitive: debt-only transitions are most affected by the debt-weighting parameter.

---

## 10.7 The $\gamma$-family as a linear path in norm-space

We now make the norm-space interpretation more precise.

**Definition 10.42 (Norm-space path).** The *norm-space path* of the $\gamma$-family is the path

$$\gamma \mapsto L_\gamma = \begin{pmatrix} 1 & 0 \\ 0 & \gamma \end{pmatrix}$$

in the space of linear maps $\mathbb{R}^2 \to \mathbb{R}^2$.

**Proposition 10.43.** The norm-space path is a straight line in the space of linear maps, from the projection onto the $x$-axis ($\gamma = 0$) to the identity ($\gamma = 1$).

*Proof.* $L_\gamma = (1 - \gamma) L_0 + \gamma L_1$, where $L_0 = \mathrm{diag}(1, 0)$ and $L_1 = \mathrm{Id}$. $\square$

**Remark 10.44.** The norm-space path is a *linear interpolation* between the projection and the identity. This is the sense in which the $\gamma$-family is "natural": it is the simplest possible path between the two extremes.

**Remark 10.45.** The norm-space path can be generalized to any path $\gamma \mapsto L_\gamma$ in the space of linear maps. The $\gamma$-family corresponds to the linear path. Other paths would give other families of quasi-metrics, with different geometric properties. The linear path is the canonical choice.

**Remark 10.46.** The norm-space interpretation is the "correct" way to think about the $\gamma$-family. The family is not an arbitrary interpolation; it is the image of a straight line in norm-space, transported through the embedding $\Phi : \mathcal{B} \times \mathcal{B} \to \mathbb{R}^2$.

---

## 10.8 The $\gamma$-family and the basepoint

We close this section by noting the relationship between the $\gamma$-family and the basepoint.

**Proposition 10.47.** The $\gamma$-distance $d_\gamma$ is independent of the choice of basepoint $s_0$ used to define the potential $\psi$.

*Proof.* $d$ is independent of $\psi$, and $D$ is independent of the choice of basepoint (by the basepoint theorem). Hence $d_\gamma$ is independent. $\square$

**Remark 10.48.** The $\gamma$-family is basepoint-independent, like the complex quasi-metric $Q$ itself. The basepoint is a computational convenience, not a structural component.

**Remark 10.49.** The basepoint independence of the $\gamma$-family is another manifestation of the gauge invariance of the theory. The $\gamma$-family is defined in terms of $d$ and $D$, both of which are gauge-invariant in the appropriate sense ($d$ fully, $D$ up to coboundary).

---

## 10.9 Examples

We illustrate the $\gamma$-family with examples.

**Example 10.50 (Two-point space).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = 3$, $d(2, 1) = 1$, $D(1, 2) = 2$. Compute:

- $d_0(1, 2) = 3$, $d_0(2, 1) = 1$.
- $d_{0.5}(1, 2) = \sqrt{9 + 0.25 \cdot 4} = \sqrt{10} \approx 3.162$, $d_{0.5}(2, 1) = \sqrt{1 + 0.25 \cdot 4} = \sqrt{2} \approx 1.414$.
- $d_1(1, 2) = \sqrt{9 + 4} = \sqrt{13} \approx 3.606$, $d_1(2, 1) = \sqrt{1 + 4} = \sqrt{5} \approx 2.236$.

Note that $d_\gamma$ is asymmetric for all $\gamma$, because $d$ is asymmetric.

**Example 10.51 (Symmetric cost, nonzero debt).** Let $\mathcal{B} = \{1, 2\}$ with $d(1, 2) = d(2, 1) = 3$, $D(1, 2) = 2$. Then $d_\gamma(1, 2) = d_\gamma(2, 1) = \sqrt{9 + 4\gamma^2}$. The $\gamma$-family is symmetric for all $\gamma$, and increases from $3$ at $\gamma = 0$ to $\sqrt{13} \approx 3.606$ at $\gamma = 1$.

**Example 10.52 (Pure debt).** Let $d = 0$ and $D(1, 2) = 2$, $D(2, 1) = -2$. Then $d_\gamma(1, 2) = d_\gamma(2, 1) = 2\gamma$. At $\gamma = 0$, $d_\gamma = 0$ (all transitions have zero distance); at $\gamma = 1$, $d_\gamma = 2$. The $\gamma$-family interpolates between the trivial metric and the debt magnitude.

**Example 10.53 (Three-point space).** Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 2 & 5 \\ 1 & 0 & 3 \\ 4 & 1 & 0 \end{pmatrix}, \qquad D = \begin{pmatrix} 0 & 1 & 3 \\ -1 & 0 & 2 \\ -3 & -2 & 0 \end{pmatrix}.$$

Compute $d_\gamma(i, j)$ for all pairs and for several values of $\gamma$:

- $\gamma = 0$: $d_0 = d$.
- $\gamma = 0.5$: $d_{0.5}(1, 2) = \sqrt{4 + 0.25} = \sqrt{4.25} \approx 2.062$, etc.
- $\gamma = 1$: $d_1 = |Q|$.

---

## 10.10 The $\gamma$-family: summary

We summarize the $\gamma$-family in a single table.

| **$\gamma$** | **$d_\gamma$** | **Interpretation** |
|---|---|---|
| 0 | $d$ | Pure cost |
| 1/2 | $\sqrt{d^2 + D^2/4}$ | Half-weighted debt |
| 1 | $\sqrt{d^2 + D^2} = |Q|$ | Full modulus |
| $> 1$ | $\sqrt{d^2 + \gamma^2 D^2}$ | Over-weighted debt |

**Key properties:**

- **Non-negativity and identity:** $d_\gamma \ge 0$, $d_\gamma(b, b) = 0$.
- **Triangle inequality:** $d_\gamma(b_i, b_k) \le d_\gamma(b_i, b_j) + d_\gamma(b_j, b_k)$ for all $\gamma$ (Theorem 10.9).
- **Monotonicity:** $d_\gamma \le d_{\gamma'}$ for $\gamma \le \gamma'$ (Proposition 10.6).
- **Strict monotonicity:** strict when $D \neq 0$ (Proposition 10.8).
- **Norm-space interpretation:** $d_\gamma = \|L_\gamma \circ \Phi\|_2$ with $L_\gamma(x, y) = (x, \gamma y)$ (Proposition 10.20).
- **Phase dependence:** $d_\gamma = |Q| \sqrt{\cos^2\theta + \gamma^2 \sin^2\theta}$ (Proposition 10.36).
- **Basepoint independence:** $d_\gamma$ does not depend on the choice of basepoint (Proposition 10.47).
- **Topology monotonicity:** $\tau_{\gamma'} \subseteq \tau_\gamma$ for $\gamma \le \gamma'$ (Proposition 10.33).

The $\gamma$-family is the natural one-parameter deformation of the energy quasi-metric by the debt. It interpolates continuously between the pure cost and the full modulus, and it satisfies the triangle inequality for every value of $\gamma$.

---

## 10.11 Exercises

**Exercise 10.1.** Compute $d_\gamma(1, 2)$ for $\gamma \in \{0, 0.25, 0.5, 0.75, 1\}$ in Example 10.50.

**Exercise 10.2.** Prove that $d_\gamma$ is a quasi-metric for every $\gamma \in [0, 1]$.

**Exercise 10.3.** Show that the balls $B_\gamma(b, r)$ are nested: $B_{\gamma'}(b, r) \subseteq B_\gamma(b, r)$ for $\gamma \le \gamma'$.

**Exercise 10.4.** Prove the phase formula $d_\gamma = |Q| \sqrt{\cos^2\theta + \gamma^2 \sin^2\theta}$.

**Exercise 10.5.** Compute $d_\gamma$ for a pure debt transition ($d = 0$) and a pure cost transition ($D = 0$).

**Exercise 10.6.** Show that the norm-space path $L_\gamma$ is a straight line between the projection $L_0 = \mathrm{diag}(1, 0)$ and the identity $L_1 = \mathrm{Id}$.

**Exercise 10.7.** Prove that $d_\gamma$ is basepoint-independent.

**Exercise 10.8.** Verify that the triangle inequality holds for $d_\gamma$ in Example 10.53.

**Exercise 10.9.** Show that $d_\gamma$ is a metric if and only if $d$ is symmetric and $d_\gamma(b_i, b_j) = 0 \Rightarrow b_i = b_j$. Give an example where $d$ is a metric, $D \neq 0$, and $d_\gamma$ is still a metric for all $\gamma$.

**Exercise 10.10.** Prove that $\tau_{\gamma'} \subseteq \tau_\gamma$ for $\gamma \le \gamma'$. Give an example where the inclusion is strict.

**Exercise 10.11 (Reflection question).** Is the $\gamma$-family the *unique* natural interpolation between $d$ and $|Q|$? Write a short essay (one page) arguing for your position.




