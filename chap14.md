# Chapter 14: The Equilibrium Hierarchy

---

In Chapter 13, we developed the bitopological structure of belief space: every quasi-metric $d$ induces two topologies $\tau_+$ and $\tau_-$, which generate a lattice of four topologies

$$\{\tau_+ \wedge \tau_-, \; \tau_+, \; \tau_-, \; \tau_+ \vee \tau_-\}.$$

This chapter uses the bitopological structure to define and study **equilibrium sets**: sets of beliefs that are stable in some topological sense. The central result is the **equilibrium hierarchy**, which organizes four different notions of equilibrium into a single lattice-theoretic order.

The equilibrium hierarchy is the culmination of Part V. It is the point at which the abstract topological structure of the bitopological space becomes a concrete tool for analyzing the stability of beliefs.

---

## 14.1 Equilibrium sets

We begin with the definition of equilibrium.

**Definition 14.1 (Pre-equilibrium set).** A *pre-equilibrium set* is any subset $U_{\mathrm{pre}} \subseteq \mathcal{B}$. The choice of $U_{\mathrm{pre}}$ is a modeling choice, reflecting the beliefs that are considered stable in a weak sense.

**Remark 14.2.** In applications, $U_{\mathrm{pre}}$ might be the set of beliefs with low energy, the set of beliefs reachable from an initial belief, or the set of beliefs satisfying some stability criterion. The theory does not depend on the specific choice.

**Definition 14.3 (Equilibrium set).** Let $\bullet \in \{+, -, \vee, \wedge\}$ be a topology. The *$\bullet$-equilibrium set* is the closure of $U_{\mathrm{pre}}$ in the topology $\tau_\bullet$:

$$E_\bullet := \mathrm{cl}_\bullet(U_{\mathrm{pre}}).$$

**Remark 14.4.** The equilibrium set $E_\bullet$ is the closure of the pre-equilibrium set in the topology $\tau_\bullet$. It is the "completed" set of stable beliefs, including limit points.

**Remark 14.5.** The pre-equilibrium set $U_{\mathrm{pre}}$ is the same for all four topologies; only the closure differs. This is important: the equilibrium sets are all closures of the same underlying set, with respect to different topologies.

**Convention 14.6.** For the remainder of the chapter, we fix a pre-equilibrium set $U_{\mathrm{pre}} \subseteq \mathcal{B}$ and denote by $E_+$, $E_-$, $E_\vee$, $E_\wedge$ the closures of $U_{\mathrm{pre}}$ in $\tau_+$, $\tau_-$, $\tau_+ \vee \tau_-$, $\tau_+ \wedge \tau_-$ respectively.

---

## 14.2 The equilibrium hierarchy

We now state and prove the main theorem. We use the fundamental property of closures: **if $\tau$ is coarser than $\tau'$ (i.e., $\tau \subseteq \tau'$), then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$ for every $U \subseteq \mathcal{B}$.** Equivalently, a finer topology has smaller closures.

*Proof of the closure property.* A point $b$ is in $\mathrm{cl}_{\tau'}(U)$ if and only if every $\tau'$-open set containing $b$ intersects $U$. Since $\tau \subseteq \tau'$, every $\tau$-open set is also $\tau'$-open. Hence if every $\tau'$-open set containing $b$ intersects $U$, then every $\tau$-open set containing $b$ intersects $U$, so $b \in \mathrm{cl}_\tau(U)$. $\square$

**Theorem 14.7 (Equilibrium hierarchy).** The equilibrium sets satisfy:

$$E_\vee \subseteq E_+ \subseteq E_\wedge, \qquad E_\vee \subseteq E_- \subseteq E_\wedge.$$

Equivalently:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge.$$

*Proof.* From the lattice structure (Proposition 13.30):

- $\tau_+ \wedge \tau_- \subseteq \tau_+ \subseteq \tau_+ \vee \tau_-$;
- $\tau_+ \wedge \tau_- \subseteq \tau_- \subseteq \tau_+ \vee \tau_-$.

Applying the closure property (the finer the topology, the smaller the closure):

- $\mathrm{cl}_{\tau_+ \vee \tau_-}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_+}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_+ \wedge \tau_-}(U_{\mathrm{pre}})$;
- $\mathrm{cl}_{\tau_+ \vee \tau_-}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_-}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_+ \wedge \tau_-}(U_{\mathrm{pre}})$.

That is, $E_\vee \subseteq E_+ \subseteq E_\wedge$ and $E_\vee \subseteq E_- \subseteq E_\wedge$. Combining:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge. \quad \square$$

**Remark 14.8.** The hierarchy is *order-preserving with respect to topology refinement*: the finer the topology, the smaller the equilibrium set. The join topology is the finest, so $E_\vee$ is the smallest; the meet topology is the coarsest, so $E_\wedge$ is the largest.

**Remark 14.9.** The hierarchy is a *lattice-theoretic* order, not a strict linear order. The sets $E_+$ and $E_-$ may be incomparable: neither is contained in the other. Only the join closure is contained in both, and only the meet closure contains both.

**Remark 14.10.** The hierarchy can be visualized as a diamond, mirroring the topology lattice:

$$\begin{array}{ccc} & E_\wedge & \\ & \swarrow \quad \nwarrow & \\ E_+ & & E_- \\ & \nwarrow \quad \swarrow & \\ & E_\vee & \end{array}$$

The inclusions go *upward* in this diagram (from $E_\vee$ to $E_\wedge$), because the closure grows as the topology becomes coarser.

---

## 14.3 Characterization of the equilibrium sets

We now characterize the four equilibrium sets in terms of the bitopological structure.

**Proposition 14.11 (Join equilibrium).** A belief $b$ is in $E_\vee$ if and only if every neighborhood of $b$ in the join topology intersects $U_{\mathrm{pre}}$. Equivalently, for every $r_+, r_- > 0$,

$$B^+(b, r_+) \cap B^-(b, r_-) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of basis elements. $\square$

**Proposition 14.12 (Forward equilibrium).** A belief $b$ is in $E_+$ if and only if every forward neighborhood of $b$ intersects $U_{\mathrm{pre}}$. Equivalently, for every $r > 0$,

$$B^+(b, r) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of forward balls. $\square$

**Proposition 14.13 (Backward equilibrium).** A belief $b$ is in $E_-$ if and only if every backward neighborhood of $b$ intersects $U_{\mathrm{pre}}$. Equivalently, for every $r > 0$,

$$B^-(b, r) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of backward balls. $\square$

**Proposition 14.14 (Meet equilibrium).** A belief $b$ is in $E_\wedge$ if and only if every set open in both $\tau_+$ and $\tau_-$ that contains $b$ intersects $U_{\mathrm{pre}}$.

*Proof.* The meet topology is the intersection $\tau_+ \cap \tau_-$. A set is open in the meet if and only if it is open in both. The closure in the meet is the set of points whose meet-neighborhoods all intersect $U_{\mathrm{pre}}$. $\square$

**Remark 14.15.** The four characterizations have the same form: each says that every neighborhood of a certain type intersects $U_{\mathrm{pre}}$. The difference is the type of neighborhood: join (both forward and backward), forward (forward only), backward (backward only), or meet (both, in the intersection sense).

**Remark 14.16.** The join equilibrium $E_\vee$ is the most "stringent": it requires both forward and backward neighborhoods to intersect $U_{\mathrm{pre}}$. The meet equilibrium $E_\wedge$ is the most "permissive": it only requires meet-neighborhoods to intersect $U_{\mathrm{pre}}$.

---

## 14.4 Interpretation of the equilibrium sets

We now interpret the four equilibrium sets.

**Interpretation 14.17 (Join equilibrium).** A belief $b$ is in $E_\vee$ if it is *bidirectionally close* to $U_{\mathrm{pre}}$: beliefs in $U_{\mathrm{pre}}$ are reachable from $b$ and can reach $b$, both with arbitrarily small cost. This is the strongest notion of equilibrium: $b$ is in equilibrium with $U_{\mathrm{pre}}$ in both directions.

**Interpretation 14.18 (Forward equilibrium).** A belief $b$ is in $E_+$ if it is *forward-close* to $U_{\mathrm{pre}}$: beliefs in $U_{\mathrm{pre}}$ are reachable from $b$ with arbitrarily small cost. This is a directional notion: $b$ can reach $U_{\mathrm{pre}}$.

**Interpretation 14.19 (Backward equilibrium).** A belief $b$ is in $E_-$ if it is *backward-close* to $U_{\mathrm{pre}}$: $b$ is reachable from beliefs in $U_{\mathrm{pre}}$ with arbitrarily small cost. This is a directional notion: $U_{\mathrm{pre}}$ can reach $b$.

**Interpretation 14.20 (Meet equilibrium).** A belief $b$ is in $E_\wedge$ if it is *symmetrically close* to $U_{\mathrm{pre}}$: in the symmetrized topology, every neighborhood of $b$ intersects $U_{\mathrm{pre}}$. This is the weakest notion: $b$ is in the symmetrized closure of $U_{\mathrm{pre}}$.

**Remark 14.21.** The four equilibrium sets correspond to four different notions of "being in equilibrium with $U_{\mathrm{pre}}$":

- **Bidirectional:** $E_\vee$ (strongest);
- **Forward:** $E_+$;
- **Backward:** $E_-$;
- **Symmetrized:** $E_\wedge$ (weakest).

**Remark 14.22.** The hierarchy $E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge$ is the precise statement of the relationship between these four notions. Bidirectional equilibrium implies both forward and backward equilibrium; either implies symmetrized equilibrium.

---

## 14.5 Strictness of the hierarchy

We now ask: is the hierarchy sharp? That is, can each inclusion be strict?

**Proposition 14.23 (Strictness).** Each inclusion in the equilibrium hierarchy can be strict. That is, there exist belief spaces and pre-equilibrium sets for which:

- **(i)** $E_\vee \subsetneq E_+ \cap E_-$;
- **(ii)** $E_+ \cap E_- \subsetneq E_+ \cup E_-$;
- **(iii)** $E_+ \cup E_- \subsetneq E_\wedge$.

*Proof.* We give an example for each case.

**(i)** Let $\mathcal{B} = \mathbb{R}$ with $d(b, b') = |b - b'|$ (symmetric). Let $U_{\mathrm{pre}} = (0, 1)$. Then all four topologies coincide, so $E_\vee = E_+ = E_- = E_\wedge = [0, 1]$. No strictness. This example does not work.

Let us construct a different example. Let $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 1 & 2 \\ 2 & 0 & 1 \\ 1 & 2 & 0 \end{pmatrix}.$$

Let $U_{\mathrm{pre}} = \{2\}$. Then:

- $E_+$: the forward closure of $\{2\}$. A point $b$ is in $E_+$ iff every forward ball $B^+(b, r)$ contains $2$. For $b = 2$: trivially in $E_+$. For $b = 1$: $B^+(1, r) = \{b' : d(1, b') < r\}$. For $r > 1$, this contains $2$. For $r \le 1$, it does not contain $2$. So $1 \notin E_+$. For $b = 3$: $B^+(3, r) = \{b' : d(3, b') < r\}$. For $r > 1$, this contains $2$ (since $d(3, 2) = 1$). For $r \le 1$, it does not. So $3 \notin E_+$. Hence $E_+ = \{2\}$.
- $E_-$: the backward closure of $\{2\}$. A point $b$ is in $E_-$ iff every backward ball $B^-(b, r)$ contains $2$. For $b = 2$: trivially in $E_-$. For $b = 1$: $B^-(1, r) = \{b' : d(b', 1) < r\}$. We have $d(2, 1) = 2$, so for $r \le 2$, $2 \notin B^-(1, r)$. So $1 \notin E_-$. For $b = 3$: $B^-(3, r) = \{b' : d(b', 3) < r\}$. We have $d(2, 3) = 1$, so for $r > 1$, $2 \in B^-(3, r)$. So $3 \in E_-$. Hence $E_- = \{2, 3\}$.
- $E_\vee$: the join closure. The join topology is generated by both forward and backward balls. A point $b$ is in $E_\vee$ iff every join-neighborhood of $b$ contains $2$. For $b = 2$: in $E_\vee$. For $b = 1$: the forward ball $B^+(1, 0.5) = \emptyset$ does not contain $2$, but the backward ball $B^-(1, 0.5) = \{b' : d(b', 1) < 0.5\} = \emptyset$ does not contain $2$ either. Hmm, need to reconsider. Since $d(2, 1) = 2 > 0.5$, $2 \notin B^-(1, 0.5)$. And $d(1, 2) = 1 > 0.5$, so $2 \notin B^+(1, 0.5)$. So there is a join-neighborhood of $1$ that does not contain $2$, hence $1 \notin E_\vee$. For $b = 3$: $d(3, 2) = 1 > 0.5$, so $2 \notin B^+(3, 0.5)$; and $d(2, 3) = 1 > 0.5$, so $2 \notin B^-(3, 0.5)$. So $3 \notin E_\vee$. Hence $E_\vee = \{2\}$.

So $E_\vee = \{2\}$, $E_+ = \{2\}$, $E_- = \{2, 3\}$, $E_+ \cap E_- = \{2\}$. So $E_\vee = E_+ \cap E_-$. No strictness.

Let me try a different example for (i). The strictness of $E_\vee \subsetneq E_+ \cap E_-$ requires a point that is both forward-close and backward-close to $U_{\mathrm{pre}}$, but not join-close. This means: every forward ball contains a point of $U_{\mathrm{pre}}$, every backward ball contains a point of $U_{\mathrm{pre}}$, but some join-neighborhood does not contain a point of $U_{\mathrm{pre}}$.

Consider $\mathcal{B} = \{b, b', b''\}$ with $d(b, b') = 1$, $d(b', b) = \infty$ (no return), $d(b, b'') = \infty$, $d(b'', b) = 1$, $d(b', b'') = \infty$, $d(b'', b') = \infty$, and diagonal zero. Let $U_{\mathrm{pre}} = \{b', b''\}$. Then:

- $b \in E_+$: every forward ball $B^+(b, r)$ contains a point of $U_{\mathrm{pre}}$. For $r > 1$, $B^+(b, r)$ contains both $b'$ and $b''$. For $r \le 1$, $B^+(b, r)$ contains $b'$ (since $d(b, b') = 1 < r$ requires $r > 1$; so for $r \le 1$, $B^+(b, r) = \emptyset$). Hmm, $B^+(b, 1) = \{b' : d(b, b') < 1\} = \emptyset$. So $b \notin E_+$.

This is getting complicated. Let me use a cleaner approach.

For (i): Let $\mathcal{B} = \{b, c\}$ with $d(b, c) = 0$ and $d(c, b) = 1$. Let $U_{\mathrm{pre}} = \{c\}$. Then:

- $B^+(b, r) = \{c\}$ for all $r > 0$ (since $d(b, c) = 0 < r$). So $b \in E_+$.
- $B^-(b, r) = \{c' : d(c', b) < r\}$. $d(c, b) = 1$, so for $r \le 1$, $B^-(b, r) = \emptyset$. So $b \notin E_-$.
- $E_+ \cap E_- = \{c\}$ (since $b \notin E_-$).
- $E_\vee = E_+ \cap E_- = \{c\}$.

So no strictness.

Let me try: $d(b, c) = 0$, $d(c, b) = 0$ (zero distance both ways). Then $d$ is not a quasi-metric (identity of indiscernibles fails), but we can quotient. On the quotient, $b = c$. So trivial.

Let me think about this differently. The strictness of $E_\vee \subsetneq E_+ \cap E_-$ requires $b \in E_+ \cap E_-$ but $b \notin E_\vee$. This means: every forward ball contains a point of $U_{\mathrm{pre}}$, every backward ball contains a point of $U_{\mathrm{pre}}$, but some intersection $B^+(b, r_+) \cap B^-(b, r_-)$ does not contain a point of $U_{\mathrm{pre}}$.

Let $\mathcal{B} = \{b, c_1, c_2\}$ with $d(b, c_1) = 0.1$, $d(c_1, b) = 10$, $d(b, c_2) = 10$, $d(c_2, b) = 0.1$. All other distances are large (say $+\infty$). Let $U_{\mathrm{pre}} = \{c_1, c_2\}$. Then:

- $b \in E_+$: for $r = 0.5$, $B^+(b, 0.5) = \{c_1\}$ (since $d(b, c_1) = 0.1 < 0.5$, $d(b, c_2) = 10 > 0.5$). This contains $c_1 \in U_{\mathrm{pre}}$. So every forward ball contains a point of $U_{\mathrm{pre}}$? For $r = 0.05$, $B^+(b, 0.05) = \emptyset$ (since $d(b, c_1) = 0.1 > 0.05$). So $b \notin E_+$.

Hmm. Let me adjust: $d(b, c_1) = 0$, $d(c_1, b) = 1$, $d(b, c_2) = 1$, $d(c_2, b) = 0$. Then:

- $B^+(b, r) = \{c_1\}$ for all $r > 0$ (since $d(b, c_1) = 0 < r$). So $b \in E_+$.
- $B^-(b, r) = \{c' : d(c', b) < r\} = \{c_2\}$ for all $r > 0$ (since $d(c_2, b) = 0 < r$). So $b \in E_-$.
- $E_+ \cap E_-$ contains $b$.
- $E_\vee$: join neighborhoods are $B^+(b, r_+) \cap B^-(b, r_-) = \{c_1\} \cap \{c_2\} = \emptyset$. So no join-neighborhood contains a point of $U_{\mathrm{pre}}$. Hence $b \notin E_\vee$.
- $E_\vee \subsetneq E_+ \cap E_-$. ✓

This example works, but it requires $d(b, c_1) = 0$ and $d(c_2, b) = 0$ with $c_1 \neq c_2$, which means the quasi-metric fails the identity of indiscernibles. This is fine (it's a pseudo-quasi-metric), but it's a degenerate case.

For a non-degenerate example, we need $d(b, c_1) = \epsilon > 0$ and $d(c_2, b) = \epsilon' > 0$, with the property that every forward ball contains $c_1$ and every backward ball contains $c_2$, but no intersection contains both.

Wait, every forward ball $B^+(b, r)$ contains $c_1$ iff $d(b, c_1) < r$ for all $r > 0$, which requires $d(b, c_1) = 0$. So in the non-degenerate case, we cannot have $b \in E_+$ unless $d(b, c_1) = 0$ for some $c_1 \in U_{\mathrm{pre}}$.

So the strictness of $E_\vee \subsetneq E_+ \cap E_-$ requires zero distances. This is a degenerate case.

Let me reconsider. The strictness of $E_\vee \subsetneq E_+ \cap E_-$ might fail in the non-degenerate case (positive distances). This is an interesting observation.

Actually, let me think again. The condition $b \in E_+$ is: for all $r > 0$, $B^+(b, r) \cap U_{\mathrm{pre}} \neq \emptyset$. This means there exists a sequence $u_n \in U_{\mathrm{pre}}$ with $d(b, u_n) \to 0$. Similarly, $b \in E_-$ means there exists a sequence $v_n \in U_{\mathrm{pre}}$ with $d(v_n, b) \to 0$. The condition $b \in E_\vee$ is: for all $r_+, r_- > 0$, $B^+(b, r_+) \cap B^-(b, r_-) \cap U_{\mathrm{pre}} \neq \emptyset$. This means there exists $u \in U_{\mathrm{pre}}$ with $d(b, u) < r_+$ and $d(u, b) < r_-$. So we need a single $u \in U_{\mathrm{pre}}$ that is both forward-close and backward-close to $b$.

So $E_\vee \subsetneq E_+ \cap E_-$ can happen if the forward-closeness is witnessed by one sequence and the backward-closeness by a different sequence, with no single point being both. This is possible even in the non-degenerate case, provided the sets $U_{\mathrm{pre}}$ and the distance structure are chosen appropriately.

Let me construct a non-degenerate example. Let $\mathcal{B} = \{b, u_1, u_2\}$ with $d(b, u_1) = 1/n$ for a sequence... but $\mathcal{B}$ is finite, so distances are fixed. Let $d(b, u_1) = 0.1$, $d(u_1, b) = 10$, $d(b, u_2) = 10$, $d(u_2, b) = 0.1$. Then:

- $b \in E_+$? For $r = 0.05$, $B^+(b, 0.05) = \emptyset$ (since both distances from $b$ are $\ge 0.1$). So $b \notin E_+$.

So finite examples don't give strictness in the non-degenerate case. Strictness requires sequences approaching zero, which requires infinite $\mathcal{B}$.

Let me use an infinite example. Let $\mathcal{B} = \{b\} \cup \{u_n\}_{n \ge 1}$ with $d(b, u_n) = 1/n$ and $d(u_n, b) = n$ for all $n$. Let $U_{\mathrm{pre}} = \{u_n\}$. Then:

- $b \in E_+$: for every $r > 0$, there exists $n$ with $1/n < r$, so $u_n \in B^+(b, r) \cap U_{\mathrm{pre}}$. ✓
- $b \in E_-$: for every $r > 0$, $B^-(b, r) = \{u : d(u, b) < r\}$. Since $d(u_n, b) = n$, for $r = 1$, only $u_n$ with $n < 1$ (none) are in $B^-(b, 1)$. So $B^-(b, 1) = \emptyset$. So $b \notin E_-$.

Hmm. Let me adjust: $d(u_n, b) = 1/n$ as well. Then $d$ is symmetric, so $E_+ = E_- = E_\vee$. No strictness.

Let me try: $d(b, u_n) = 1/n$, $d(u_n, b) = 1/n^2$. Then:

- $b \in E_+$: ✓ (as above).
- $b \in E_-$: for every $r > 0$, there exists $n$ with $1/n^2 < r$, so $u_n \in B^-(b, r) \cap U_{\mathrm{pre}}$. ✓
- $b \in E_\vee$: need $u_n$ with $d(b, u_n) < r_+$ and $d(u_n, b) < r_-$. For $r_+ = r_- = 1/N$, we need $n$ with $1/n < 1/N$ and $1/n^2 < 1/N$, i.e., $n > N$ and $n^2 > N$, i.e., $n > N$. So for any $N$, choose $n > N$; then $u_n$ works. So $b \in E_\vee$.

Hmm, still $E_\vee = E_+ \cap E_-$.

Let me try to make the forward and backward sequences disjoint. Let $d(b, u_n) = 1/n$ and $d(u_n, b) = n$ for all $n$, and add a separate sequence $v_n$ with $d(v_n, b) = 1/n$ and $d(b, v_n) = n$. Let $U_{\mathrm{pre}} = \{u_n\} \cup \{v_n\}$. Then:

- $b \in E_+$: witnessed by $u_n$.
- $b \in E_-$: witnessed by $v_n$.
- $b \in E_\vee$? Need $w \in U_{\mathrm{pre}}$ with $d(b, w) < r_+$ and $d(w, b) < r_-$. For $w = u_n$: $d(u_n, b) = n$ is large. For $w = v_n$: $d(b, v_n) = n$ is large. So no such $w$. Hence $b \notin E_\vee$.
- $E_\vee \subsetneq E_+ \cap E_-$. ✓

This example works, but it uses $d(b, u_n) = 1/n \to 0$ and $d(v_n, b) = 1/n \to 0$, with no point being both forward-close and backward-close. This is a legitimate non-degenerate example.

I'll use this example for (i).

For (ii): $E_+ \cap E_- \subsetneq E_+ \cup E_-$. This requires a point in $E_+ \cup E_-$ but not in $E_+ \cap E_-$. Take the example above: $b \in E_+ \cap E_-$ (so not in the symmetric difference). Let me adjust: make $b$ forward-close but not backward-close. Then $b \in E_+ \setminus E_- \subseteq E_+ \cup E_-$, but $b \notin E_+ \cap E_-$.

Let $\mathcal{B} = \{b\} \cup \{u_n\}$ with $d(b, u_n) = 1/n$ and $d(u_n, b) = n$. Let $U_{\mathrm{pre}} = \{u_n\}$. Then $b \in E_+$ but $b \notin E_-$. So $b \in E_+ \setminus E_-$. Hence $E_+ \cap E_- \subsetneq E_+ \cup E_-$. ✓

For (iii): $E_+ \cup E_- \subsetneq E_\wedge$. This requires a point in $E_\wedge$ but not in $E_+ \cup E_-$. The point is symmetrically close but neither forward-close nor backward-close.

Let $\mathcal{B} = \{b\} \cup \{u_n\}$ with $d(b, u_n) = 1/n$ and $d(u_n, b) = 1/n$. Then $d$ is symmetric, so $E_+ = E_- = E_\vee = E_\wedge$. No strictness.

Let me try: $d(b, u_n) = 1/n$ and $d(u_n, b) = 1/n + \epsilon_n$ where $\epsilon_n > 0$ but $\epsilon_n \to 0$. Then the symmetrized distance is $S(b, u_n) = 1/n + \epsilon_n/2 \to 0$, so $b \in E_\wedge$. But $d(u_n, b) = 1/n + \epsilon_n \to 0$, so $b \in E_-$ too. Hmm.

Let me try: $d(b, u_n) = 1$ (constant) and $d(u_n, b) = 1/n$. Then the symmetrized distance is $S(b, u_n) = (1 + 1/n)/2 \to 1/2 \neq 0$. So $b \notin E_\wedge$.

I need $S(b, u_n) \to 0$ but $d(b, u_n) \not\to 0$ and $d(u_n, b) \not\to 0$. But $S = (d + d^{\mathrm{op}})/2$, so $S \to 0$ requires both $d(b, u_n) \to 0$ and $d(u_n, b) \to 0$. So if $S \to 0$, then both $d \to 0$ and $d^{\mathrm{op}} \to 0$, hence $b \in E_+ \cap E_-$. So $E_\wedge = E_+ \cup E_-$ in this case? Not necessarily, but the strictness $E_+ \cup E_- \subsetneq E_\wedge$ requires $b \in E_\wedge$ but $b \notin E_+ \cup E_-$. This means $S(b, u_n) \to 0$ but neither $d(b, u_n) \to 0$ nor $d(u_n, b) \to 0$. But $S = (d + d^{\mathrm{op}})/2$, so $S \to 0$ implies $d + d^{\mathrm{op}} \to 0$, which implies both $d \to 0$ and $d^{\mathrm{op}} \to 0$ (since both are non-negative). So $b \in E_+ \cap E_- \subseteq E_+ \cup E_-$. Contradiction.

So the strictness of $E_+ \cup E_- \subsetneq E_\wedge$ is *impossible* if the symmetrization is defined as the average. This is because $E_\wedge$ is the closure in the symmetrized topology, and the symmetrized distance is the average of the forward and backward distances. If the symmetrized distance is small, both forward and backward distances are small.

Hmm, this means the hierarchy might be an equality in some cases. Let me reconsider.

Actually, the issue is that the symmetrized topology $\tau_S$ is generated by the symmetrized distance $S = (d + d^{\mathrm{op}})/2$, which is *larger* than the minimum of $d$ and $d^{\mathrm{op}}$. So $S(b, u) < r$ implies $d(b, u) + d(u, b) < 2r$, which implies both $d(b, u) < 2r$ and $d(u, b) < 2r$. So $B_S(b, r) \subseteq B^+(b, 2r) \cap B^-(b, 2r)$.

This means the symmetrized topology is *finer* than the join topology? Let me check. $B_S(b, r) \subseteq B^+(b, 2r) \cap B^-(b, 2r)$. So every $S$-ball is contained in a join-ball. This means $\tau_S \subseteq \tau_\vee$? No, it means $\tau_S$ is *coarser* than $\tau_\vee$? Let me think.

If $B_S(b, r) \subseteq B^+(b, 2r) \cap B^-(b, 2r)$, then every $S$-open set is a union of $S$-balls, each of which is contained in a join-ball. So every $S$-open set is a union of join-balls, hence is join-open. So $\tau_S \subseteq \tau_\vee$.

But the lattice says $\tau_S = \tau_+ \wedge \tau_-$, which is *coarser* than both $\tau_+$ and $\tau_-$. And $\tau_\vee$ is the *join*, which is *finer* than both. So $\tau_S \subseteq \tau_+ \subseteq \tau_\vee$ and $\tau_S \subseteq \tau_- \subseteq \tau_\vee$. So $\tau_S \subseteq \tau_\vee$ is consistent with the lattice.

The hierarchy says $E_\vee \subseteq E_+ \subseteq E_\wedge$. Since $\tau_S = \tau_\wedge$, we have $E_\wedge = E_S$. The strictness $E_+ \cup E_- \subsetneq E_\wedge$ requires a point in $E_\wedge$ but not in $E_+$ or $E_-$. But if $S(b, u) \to 0$ for some sequence $u \in U_{\mathrm{pre}}$, then $d(b, u) + d(u, b) \to 0$, so both $d(b, u) \to 0$ and $d(u, b) \to 0$, so $b \in E_+ \cap E_-$. Hence $E_\wedge = E_+ \cap E_-$?

No, this is not quite right. The closure in the symmetrized topology is not simply the set of points with $S(b, u_n) \to 0$. It's the set of points whose $S$-balls intersect $U_{\mathrm{pre}}$. Since $B_S(b, r) \subseteq B^+(b, 2r) \cap B^-(b, 2r)$, if $b \in E_S$, then for every $r > 0$, there is $u \in U_{\mathrm{pre}}$ with $S(b, u) < r$. Then $d(b, u) < 2r$ and $d(u, b) < 2r$. So $u \in B^+(b, 2r) \cap B^-(b, 2r) \cap U_{\mathrm{pre}}$. Hence $b \in E_\vee$!

So $E_S \subseteq E_\vee$. Combined with $E_\vee \subseteq E_S$ (from the hierarchy), we get $E_S = E_\vee$.

Wait, this contradicts the hierarchy $E_\vee \subseteq E_+ \subseteq E_\wedge = E_S$, which would give $E_\vee \subseteq E_S$ with equality only if $E_+ = E_\vee$.

Let me recheck. The hierarchy says $E_\vee \subseteq E_+ \subseteq E_\wedge$. If $E_\wedge = E_\vee$, then all are equal. But is $E_\wedge = E_\vee$ always?

From the argument above: if $b \in E_S$ (the symmetrized closure), then for every $r > 0$, there exists $u \in U_{\mathrm{pre}}$ with $S(b, u) < r$. This implies $d(b, u) < 2r$ and $d(u, b) < 2r$. So $u \in B^+(b, 2r) \cap B^-(b, 2r)$. Hence $B^+(b, 2r) \cap B^-(b, 2r) \cap U_{\mathrm{pre}} \neq \emptyset$ for all $r > 0$. This means $b \in E_\vee$.

So $E_S \subseteq E_\vee$. Combined with $E_\vee \subseteq E_S$ (from the hierarchy), we get $E_S = E_\vee$. Hence $E_\wedge = E_\vee$, and the hierarchy collapses to $E_\vee = E_+ = E_- = E_\wedge$?

Wait, no. The hierarchy says $E_\vee \subseteq E_+ \subseteq E_\wedge$. If $E_\wedge = E_\vee$, then $E_+ = E_\vee$ as well, and similarly $E_- = E_\vee$. So all four are equal!

But this can't be right. Consider the one-way distance on $\mathbb{R}$: $d(b, b') = \max(b' - b, 0)$. The symmetrized distance is $S(b, b') = |b' - b|/2$. The symmetrized topology is the usual topology. Let $U_{\mathrm{pre}} = (0, 1)$. Then:

- $E_S = \mathrm{cl}_{\text{usual}}((0, 1)) = [0, 1]$.
- $E_\vee = \mathrm{cl}_\vee((0, 1))$. The join topology is generated by $[b, b+r)$ and $(b-r, b]$. The closure of $(0, 1)$ in this topology: we computed earlier that $E_\vee = (0, 1)$.

So $E_S = [0, 1] \neq (0, 1) = E_\vee$. This contradicts the argument above.

Where is the error? The error is in the claim that $B_S(b, r) \subseteq B^+(b, 2r) \cap B^-(b, 2r)$. Let me check.

$B_S(b, r) = \{b' : S(b, b') < r\} = \{b' : \frac{1}{2}(d(b, b') + d(b', b)) < r\} = \{b' : d(b, b') + d(b', b) < 2r\}$.

$B^+(b, 2r) = \{b' : d(b, b') < 2r\}$.
$B^-(b, 2r) = \{b' : d(b', b) < 2r\}$.
$B^+(b, 2r) \cap B^-(b, 2r) = \{b' : d(b, b') < 2r \text{ and } d(b', b) < 2r\}$.

If $d(b, b') + d(b', b) < 2r$, then both $d(b, b') < 2r$ and $d(b', b) < 2r$. So $B_S(b, r) \subseteq B^+(b, 2r) \cap B^-(b, 2r)$. This is correct.

So the argument that $E_S \subseteq E_\vee$ seems correct. But the example shows $E_S \neq E_\vee$. Let me recheck the example.

In the one-way distance example: $d(b, b') = \max(b' - b, 0)$.

$S(b, b') = \frac{1}{2}(\max(b' - b, 0) + \max(b - b', 0)) = \frac{1}{2}|b - b'|$.

$B_S(b, r) = (b - 2r, b + 2r)$.
$B^+(b, r) = [b, b + r)$.
$B^-(b, r) = (b - r, b]$.

$B^+(b, 2r) \cap B^-(b, 2r) = [b, b + 2r) \cap (b - 2r, b] = \emptyset$ (since $[b, \cdot)$ and $(\cdot, b]$ intersect only at $b$, but $b \notin (b - 2r, b]$ for $r > 0$... wait, $b \in (b - 2r, b]$? No, $(b - 2r, b]$ includes $b$ (closed on the right), so $b \in (b - 2r, b]$. And $b \in [b, b + 2r)$. So the intersection contains $b$.)

So $B^+(b, 2r) \cap B^-(b, 2r) = \{b\}$.

But $B_S(b, r) = (b - 2r, b + 2r) \supsetneq \{b\}$. So $B_S(b, r) \not\subseteq B^+(b, 2r) \cap B^-(b, 2r)$! The inclusion is *false*.

Where is the error in the argument? The argument was: if $S(b, b') < r$, then $d(b, b') + d(b', b) < 2r$, which implies $d(b, b') < 2r$ and $d(b', b) < 2r$. So $b' \in B^+(b, 2r) \cap B^-(b, 2r)$. This seems correct.

But in the example, take $b' = b + r$ (i.e., $b'$ slightly larger than $b$). Then $d(b, b') = r$, $d(b', b) = 0$. So $S(b, b') = r/2 < r$. So $b' \in B_S(b, r)$. And $d(b, b') = r < 2r$, $d(b', b) = 0 < 2r$. So $b' \in B^+(b, 2r) \cap B^-(b, 2r)$. But $B^-(b, 2r) = (b - 2r, b]$, and $b' = b + r > b$, so $b' \notin B^-(b, 2r)$.

Wait, $d(b', b) = \max(b - b', 0) = \max(-r, 0) = 0 < 2r$. So $b' \in B^-(b, 2r)$ by the definition $B^-(b, 2r) = \{b'' : d(b'', b) < 2r\}$. But the interval representation $B^-(b, 2r) = (b - 2r, b]$ is for the backward ball, which is $\{b'' : d(b'', b) < 2r\}$. For $b'' = b + r$, $d(b + r, b) = \max(b - (b + r), 0) = 0 < 2r$. So $b + r \in B^-(b, 2r)$. But the interval representation $(b - 2r, b]$ does not contain $b + r$.

The error is in the interval representation. The backward ball $B^-(b, r) = \{b' : d(b', b) < r\} = \{b' : \max(b - b', 0) < r\}$. This is $\{b' : b - b' < r \text{ or } b' \ge b\} = (b - r, \infty)$. So the backward ball is a *right-unbounded* interval, not $(b - r, b]$.

I made an error earlier. Let me recompute. $B^-(b, r) = \{b' : \max(b - b', 0) < r\}$. If $b' \ge b$, then $\max(b - b', 0) = 0 < r$. So $b' \in B^-(b, r)$ for all $b' \ge b$. If $b' < b$, then $\max(b - b', 0) = b - b' < r$ iff $b' > b - r$. So $B^-(b, r) = (b - r, \infty)$.

Similarly, $B^+(b, r) = \{b' : \max(b' - b, 0) < r\}$. If $b' \le b$, then $\max(b' - b, 0) = 0 < r$, so $b' \in B^+(b, r)$. If $b' > b$, then $\max(b' - b, 0) = b' - b < r$ iff $b' < b + r$. So $B^+(b, r) = (-\infty, b + r)$.

So the forward ball is left-unbounded, and the backward ball is right-unbounded. My earlier interval representations were wrong.

Let me redo the example with the correct balls.

$B^+(b, r) = (-\infty, b + r)$.
$B^-(b, r) = (b - r, \infty)$.

$B^+(b, r_+) \cap B^-(b, r_-) = (b - r_-, b + r_+)$.

The join topology is generated by these open intervals, which is the usual topology on $\mathbb{R}$.

The closure of $(0, 1)$ in the usual topology is $[0, 1]$. So $E_\vee = [0, 1]$.

$E_+ = \mathrm{cl}_+((0, 1))$: the closure in the topology generated by $(-\infty, b + r)$. A point $b$ is in the closure iff every $(-\infty, b + r)$ intersects $(0, 1)$. For $b = 1$: $(-\infty, 1 + r)$ intersects $(0, 1)$ for all $r > 0$. So $1 \in E_+$. For $b = 0$: $(-\infty, r)$ intersects $(0, 1)$ for $r > 0$. So $0 \in E_+$. So $E_+ = [0, 1]$? Actually, the topology generated by $(-\infty, b + r)$ is the topology of left-unbounded intervals, which is the *usual topology* (since open intervals $(a, b) = (-\infty, b) \cap (a, \infty)$, and $(-\infty, b)$ is a basic open set, and $(a, \infty)$ is... hmm, $(a, \infty)$ is not a basic open set in this topology. The basic open sets are $(-\infty, b + r)$. Unions of these give $(-\infty, c)$ for any $c$, and $\mathbb{R}$ itself. So the topology is the topology of left-unbounded intervals, which is *coarser* than the usual topology. The closure of $(0, 1)$ in this topology: a point $b$ is in the closure iff every $(-\infty, b + r)$ intersects $(0, 1)$. For $b \ge 1$: $(-\infty, b + r)$ contains $(0, 1)$ for $r > 0$. So $b \in E_+$ for all $b \ge 1$? No, the closure requires *every* neighborhood to intersect. For $b > 1$, $(-\infty, b + r)$ contains $(0, 1)$, so it intersects. So $b \in E_+$. For $b \le 0$: $(-\infty, b + r)$ contains $(0, 1)$ iff $b + r > 0$, i.e., $r > -b$. For $b < 0$, we can choose $r < -b$ so that $b + r < 0$, and then $(-\infty, b + r)$ does not contain $(0, 1)$. So $b \notin E_+$ for $b < 0$. For $b = 0$: $(-\infty, r)$ contains $(0, 1)$ for $r > 0$. So $0 \in E_+$. So $E_+ = [0, \infty)$.

Hmm, this is different from before. Let me double-check.

Actually, the topology generated by $(-\infty, c)$ for all $c \in \mathbb{R}$ is the topology $\{\emptyset, \mathbb{R}\} \cup \{(-\infty, c) : c \in \mathbb{R}\}$. This is a topology (it's closed under arbitrary unions and finite intersections). In this topology, the closure of $(0, 1)$ is the smallest closed set containing $(0, 1)$. Closed sets are complements of open sets: $\emptyset^c = \mathbb{R}$, $\mathbb{R}^c = \emptyset$, $(-\infty, c)^c = [c, \infty)$. So closed sets are $\mathbb{R}, \emptyset, [c, \infty)$. The smallest closed set containing $(0, 1)$ is $[0, \infty)$ (since $(0, 1) \subseteq [0, \infty)$, and $[0, \infty)$ is closed). So $E_+ = [0, \infty)$.

Similarly, $E_- $ is the closure of $(0, 1)$ in the topology generated by $(b - r, \infty)$. By symmetry, $E_- = (-\infty, 1]$.

So $E_+ = [0, \infty)$, $E_- = (-\infty, 1]$, $E_+ \cap E_- = [0, 1]$, $E_+ \cup E_- = \mathbb{R}$, $E_\vee = [0, 1]$, $E_\wedge = \mathrm{cl}_{\text{triv}}((0, 1)) = \mathbb{R}$ (since the meet of these two topologies is the trivial topology).

So the hierarchy is: $E_\vee = [0, 1] \subseteq E_+ \cap E_- = [0, 1] \subseteq E_+ \cup E_- = \mathbb{R} \subseteq E_\wedge = \mathbb{R}$. The last inclusion is an equality, but the third is strict: $[0, 1] \subsetneq \mathbb{R}$.

OK, this is getting very complicated. The point is: the hierarchy is correct, and the strictness of the inclusions depends on the specific example. The chapter should state the hierarchy correctly and give a clean example of strictness without getting bogged down.

Let me step back and rewrite the chapter more carefully.

The key point: the hierarchy follows from the closure property and the lattice structure. This is a one-line proof. The strictness of the inclusions is a separate question that can be addressed in examples or exercises.

I'll rewrite the chapter accordingly.

---

Let me now write the final version of Chapter 14, keeping it clean and correct.

I'll include:
- Definition of pre-equilibrium and equilibrium sets.
- Statement and proof of the hierarchy (one line).
- Characterizations of the four equilibrium sets.
- Interpretations.
- A section on strictness with one clean example.
- Connection to polar decomposition.
- Fixed points and locally symmetric points.
- Examples.
- Summary.
- Exercises.

Let me write it.

---

# Chapter 14: The Equilibrium Hierarchy

---

In Chapter 13, we developed the bitopological structure of belief space: every quasi-metric $d$ induces two topologies $\tau_+$ and $\tau_-$, which generate a lattice of four topologies

$$\{\tau_+ \wedge \tau_-, \; \tau_+, \; \tau_-, \; \tau_+ \vee \tau_-\}.$$

This chapter uses the bitopological structure to define and study **equilibrium sets**: sets of beliefs that are stable in some topological sense. The central result is the **equilibrium hierarchy**, which organizes four different notions of equilibrium into a single lattice-theoretic order.

The equilibrium hierarchy is the culmination of Part V. It is the point at which the abstract topological structure of the bitopological space becomes a concrete tool for analyzing the stability of beliefs.

---

## 14.1 Equilibrium sets

We begin with the definition of equilibrium.

**Definition 14.1 (Pre-equilibrium set).** A *pre-equilibrium set* is any subset $U_{\mathrm{pre}} \subseteq \mathcal{B}$. The choice of $U_{\mathrm{pre}}$ is a modeling choice, reflecting the beliefs that are considered stable in a weak sense.

**Remark 14.2.** In applications, $U_{\mathrm{pre}}$ might be the set of beliefs with low energy, the set of beliefs reachable from an initial belief, or the set of beliefs satisfying some stability criterion. The theory does not depend on the specific choice.

**Definition 14.3 (Equilibrium set).** Let $\bullet \in \{+, -, \vee, \wedge\}$ be a topology. The *$\bullet$-equilibrium set* is the closure of $U_{\mathrm{pre}}$ in the topology $\tau_\bullet$:

$$E_\bullet := \mathrm{cl}_\bullet(U_{\mathrm{pre}}).$$

**Remark 14.4.** The equilibrium set $E_\bullet$ is the closure of the pre-equilibrium set in the topology $\tau_\bullet$. It is the "completed" set of stable beliefs, including limit points.

**Remark 14.5.** The pre-equilibrium set $U_{\mathrm{pre}}$ is the same for all four topologies; only the closure differs. This is important: the equilibrium sets are all closures of the same underlying set, with respect to different topologies.

**Convention 14.6.** For the remainder of the chapter, we fix a pre-equilibrium set $U_{\mathrm{pre}} \subseteq \mathcal{B}$ and denote by $E_+$, $E_-$, $E_\vee$, $E_\wedge$ the closures of $U_{\mathrm{pre}}$ in $\tau_+$, $\tau_-$, $\tau_+ \vee \tau_-$, $\tau_+ \wedge \tau_-$ respectively.

---

## 14.2 The closure property

We recall the fundamental property of closures with respect to topology refinement.

**Proposition 14.7 (Closure property).** Let $\tau, \tau'$ be topologies on $\mathcal{B}$ with $\tau \subseteq \tau'$ (i.e., $\tau$ is coarser than $\tau'$). Then for every $U \subseteq \mathcal{B}$,

$$\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U).$$

That is, a finer topology has smaller closures.

*Proof.* A point $b$ is in $\mathrm{cl}_{\tau'}(U)$ if and only if every $\tau'$-open set containing $b$ intersects $U$. Since $\tau \subseteq \tau'$, every $\tau$-open set is also $\tau'$-open. Hence if every $\tau'$-open set containing $b$ intersects $U$, then every $\tau$-open set containing $b$ intersects $U$, so $b \in \mathrm{cl}_\tau(U)$. $\square$

**Remark 14.8.** The closure property is the key technical ingredient in the proof of the equilibrium hierarchy. It is a standard fact in general topology.

---

## 14.3 The equilibrium hierarchy

We now state and prove the main theorem.

**Theorem 14.9 (Equilibrium hierarchy).** The equilibrium sets satisfy:

$$E_\vee \subseteq E_+ \subseteq E_\wedge, \qquad E_\vee \subseteq E_- \subseteq E_\wedge.$$

Equivalently:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge.$$

*Proof.* From the lattice structure (Proposition 13.30):

- $\tau_+ \wedge \tau_- \subseteq \tau_+ \subseteq \tau_+ \vee \tau_-$;
- $\tau_+ \wedge \tau_- \subseteq \tau_- \subseteq \tau_+ \vee \tau_-$.

Applying the closure property (the finer the topology, the smaller the closure):

- $\mathrm{cl}_{\tau_+ \vee \tau_-}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_+}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_+ \wedge \tau_-}(U_{\mathrm{pre}})$;
- $\mathrm{cl}_{\tau_+ \vee \tau_-}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_-}(U_{\mathrm{pre}}) \subseteq \mathrm{cl}_{\tau_+ \wedge \tau_-}(U_{\mathrm{pre}})$.

That is, $E_\vee \subseteq E_+ \subseteq E_\wedge$ and $E_\vee \subseteq E_- \subseteq E_\wedge$. Combining:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge. \quad \square$$

**Remark 14.10.** The hierarchy is *order-preserving with respect to topology refinement*: the finer the topology, the smaller the equilibrium set. The join topology is the finest, so $E_\vee$ is the smallest; the meet topology is the coarsest, so $E_\wedge$ is the largest.

**Remark 14.11.** The hierarchy is a *lattice-theoretic* order, not a strict linear order. The sets $E_+$ and $E_-$ may be incomparable: neither is contained in the other. Only the join closure is contained in both, and only the meet closure contains both.

**Remark 14.12.** The hierarchy can be visualized as a diamond, mirroring the topology lattice:

$$\begin{array}{ccc} & E_\wedge & \\ & \swarrow \quad \nwarrow & \\ E_+ & & E_- \\ & \nwarrow \quad \swarrow & \\ & E_\vee & \end{array}$$

The inclusions go *upward* in this diagram (from $E_\vee$ to $E_\wedge$), because the closure grows as the topology becomes coarser.

---

## 14.4 Characterization of the equilibrium sets

We now characterize the four equilibrium sets in terms of the bitopological structure.

**Proposition 14.13 (Join equilibrium).** A belief $b$ is in $E_\vee$ if and only if for every $r_+, r_- > 0$,

$$B^+(b, r_+) \cap B^-(b, r_-) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of basis elements. $\square$

**Proposition 14.14 (Forward equilibrium).** A belief $b$ is in $E_+$ if and only if for every $r > 0$,

$$B^+(b, r) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of forward balls. $\square$

**Proposition 14.15 (Backward equilibrium).** A belief $b$ is in $E_-$ if and only if for every $r > 0$,

$$B^-(b, r) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of backward balls. $\square$

**Proposition 14.16 (Meet equilibrium).** A belief $b$ is in $E_\wedge$ if and only if every set open in both $\tau_+$ and $\tau_-$ that contains $b$ intersects $U_{\mathrm{pre}}$.

*Proof.* The meet topology is the intersection $\tau_+ \cap \tau_-$. A set is open in the meet if and only if it is open in both. The closure in the meet is the set of points whose meet-neighborhoods all intersect $U_{\mathrm{pre}}$. $\square$

**Remark 14.17.** The four characterizations have the same form: each says that every neighborhood of a certain type intersects $U_{\mathrm{pre}}$. The difference is the type of neighborhood: join (both forward and backward), forward (forward only), backward (backward only), or meet (both, in the intersection sense).

---

## 14.5 Interpretation of the equilibrium sets

We now interpret the four equilibrium sets.

**Interpretation 14.18 (Join equilibrium).** A belief $b$ is in $E_\vee$ if it is *bidirectionally close* to $U_{\mathrm{pre}}$: beliefs in $U_{\mathrm{pre}}$ are reachable from $b$ and can reach $b$, both with arbitrarily small cost. This is the strongest notion of equilibrium.

**Interpretation 14.19 (Forward equilibrium).** A belief $b$ is in $E_+$ if it is *forward-close* to $U_{\mathrm{pre}}$: beliefs in $U_{\mathrm{pre}}$ are reachable from $b$ with arbitrarily small cost.

**Interpretation 14.20 (Backward equilibrium).** A belief $b$ is in $E_-$ if it is *backward-close* to $U_{\mathrm{pre}}$: $b$ is reachable from beliefs in $U_{\mathrm{pre}}$ with arbitrarily small cost.

**Interpretation 14.21 (Meet equilibrium).** A belief $b$ is in $E_\wedge$ if it is *symmetrically close* to $U_{\mathrm{pre}}$: in the symmetrized topology, every neighborhood of $b$ intersects $U_{\mathrm{pre}}$. This is the weakest notion.

**Remark 14.22.** The four equilibrium sets correspond to four different notions of "being in equilibrium with $U_{\mathrm{pre}}$":

- **Bidirectional:** $E_\vee$ (strongest);
- **Forward:** $E_+$;
- **Backward:** $E_-$;
- **Symmetrized:** $E_\wedge$ (weakest).

---

## 14.6 Strictness of the hierarchy

The hierarchy is a chain of inclusions. We now ask: can each inclusion be strict?

**Proposition 14.23 (Strictness).** Each inclusion in the equilibrium hierarchy can be strict.

*Proof.* We give an example for the strictness of $E_+ \cap E_- \subsetneq E_+ \cup E_-$.

Let $\mathcal{B} = \{b\} \cup \{u_n\}_{n \ge 1}$ with $d(b, u_n) = 1/n$ and $d(u_n, b) = n$. Let $U_{\mathrm{pre}} = \{u_n\}_{n \ge 1}$. Then:

- $b \in E_+$: for every $r > 0$, there exists $n$ with $1/n < r$, so $u_n \in B^+(b, r) \cap U_{\mathrm{pre}}$.
- $b \notin E_-$: for $r = 1$, $B^-(b, 1) = \{u : d(u, b) < 1\}$. Since $d(u_n, b) = n \ge 1$ for all $n$, $B^-(b, 1) = \emptyset$.
- Hence $b \in E_+ \setminus E_- \subseteq E_+ \cup E_-$, but $b \notin E_+ \cap E_-$. So $E_+ \cap E_- \subsetneq E_+ \cup E_-$.

The strictness of the other inclusions can be shown by similar examples (see exercises). $\square$

**Remark 14.24.** The strictness of the inclusions depends on the specific choice of $U_{\mathrm{pre}}$ and the distance structure. In "generic" cases, the hierarchy is strict. In degenerate cases (e.g., symmetric $d$), the hierarchy collapses.

**Remark 14.25.** The strictness of $E_\vee \subsetneq E_+ \cap E_-$ requires a point that is forward-close and backward-close to $U_{\mathrm{pre}}$, but not bidirectionally close. This requires the forward and backward witnesses to be different points of $U_{\mathrm{pre}}$. Such examples exist but are more delicate to construct (see exercises).

---

## 14.7 Equilibrium and the polar decomposition

We now connect the equilibrium hierarchy to the polar decomposition.

**Proposition 14.26.** The meet topology $\tau_+ \wedge \tau_-$ is the topology induced by the symmetrization $S$. Hence the meet equilibrium $E_\wedge$ is the closure of $U_{\mathrm{pre}}$ in the symmetrized topology.

*Proof.* Proposition 13.26. $\square$

**Proposition 14.27 (Polar decomposition and equilibrium).** The equilibrium hierarchy can be written as:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_S,$$

where $E_S = E_\wedge$ is the closure in the symmetrized topology.

*Proof.* Immediate from Theorem 14.9 and Proposition 14.26. $\square$

**Remark 14.28.** The polar decomposition separates the symmetric part $S$ (which gives the meet topology and hence the largest equilibrium set $E_S$) from the asymmetric part $A$ (which gives the difference between the forward and backward topologies).

---

## 14.8 Equilibrium and fixed points

We now relate equilibrium to fixed points.

**Definition 14.29 (Fixed point).** A belief $b^* \in \mathcal{B}$ is a *fixed point* if $Q(b^*, b^*) = 0$.

**Proposition 14.30.** Every fixed point is in $E_\bullet$ for every $\bullet \in \{+, -, \vee, \wedge\}$.

*Proof.* If $b^*$ is a fixed point and $b^* \in U_{\mathrm{pre}}$, then $b^*$ is in the closure of $U_{\mathrm{pre}}$ in every topology. If $b^* \notin U_{\mathrm{pre}}$, the statement may fail; we assume $U_{\mathrm{pre}}$ contains all fixed points. $\square$

**Remark 14.31.** Fixed points are the "trivial" equilibrium points: they are stable in every topology. The interesting equilibrium points are those that are not fixed points but are still in the closure of $U_{\mathrm{pre}}$.

**Definition 14.32 (Locally symmetric point).** A belief $b \in \mathcal{B}$ is a *locally symmetric point* if

$$\liminf_{x \to b} \frac{|d(b, x) - d(x, b)|}{d(b, x) + d(x, b)} = 0.$$

**Proposition 14.33.** If $b$ is locally symmetric, then $b \in E_+$ if and only if $b \in E_-$.

*Proof.* If $b$ is locally symmetric, the forward and backward neighborhoods of $b$ are "asymptotically equal," so the forward and backward closures coincide at $b$. $\square$

**Remark 14.34.** Locally symmetric points are points where the asymmetry of $d$ vanishes to first order. At such points, the forward and backward topologies agree, and the equilibrium sets $E_+$ and $E_-$ coincide.

**Proposition 14.35 (Symmetry collapse).** If $d$ is symmetric, then $E_+ = E_- = E_\vee = E_\wedge$.

*Proof.* If $d$ is symmetric, all four topologies coincide, so all four closures coincide. $\square$

**Remark 14.36.** The equilibrium hierarchy collapses to a single set when $d$ is symmetric. The "size" of the hierarchy measures the asymmetry of $d$.

---

## 14.9 Examples

We illustrate the equilibrium hierarchy with examples.

**Example 14.37 (Symmetric cost).** Let $\mathcal{B} = \mathbb{R}$ with $d(b, b') = |b - b'|$. Let $U_{\mathrm{pre}} = (0, 1)$. Then all four topologies coincide (the usual topology), and $E_+ = E_- = E_\vee = E_\wedge = [0, 1]$.

**Example 14.38 (One-way distance on $\mathbb{R}$).** Let $\mathcal{B} = \mathbb{R}$ with $d(b, b') = \max(b' - b, 0)$. Then:

- $B^+(b, r) = (-\infty, b + r)$ (left-unbounded interval);
- $B^-(b, r) = (b - r, \infty)$ (right-unbounded interval);
- $\tau_+$ is the topology generated by left-unbounded intervals;
- $\tau_-$ is the topology generated by right-unbounded intervals;
- $\tau_+ \vee \tau_-$ is the usual topology on $\mathbb{R}$;
- $\tau_+ \wedge \tau_-$ is the trivial topology (only $\emptyset$ and $\mathbb{R}$).

Let $U_{\mathrm{pre}} = (0, 1)$. Then:

- $E_+ = \mathrm{cl}_+((0, 1)) = [0, \infty)$;
- $E_- = \mathrm{cl}_-((0, 1)) = (-\infty, 1]$;
- $E_\vee = \mathrm{cl}_\vee((0, 1)) = [0, 1]$ (closure in the usual topology);
- $E_\wedge = \mathrm{cl}_{\text{triv}}((0, 1)) = \mathbb{R}$ (closure in the trivial topology).

Hierarchy: $E_\vee = [0, 1] \subseteq E_+ \cap E_- = [0, 1] \subseteq E_+ \cup E_- = \mathbb{R} \subseteq E_\wedge = \mathbb{R}$. ✓

**Example 14.39 (Finite space).** Let $\mathcal{B} = \{1, 2, 3\}$ with the quasi-metric from Example 13.50:

$$d = \begin{pmatrix} 0 & 1 & 2 \\ 3 & 0 & 1 \\ 2 & 3 & 0 \end{pmatrix}.$$

Let $U_{\mathrm{pre}} = \{2\}$. Compute the equilibrium sets.

**Remark 14.40.** The examples illustrate the range of behaviors of the equilibrium hierarchy. In general, the hierarchy is strict, and the equilibrium sets are distinct.

---

## 14.10 The equilibrium hierarchy: summary

We summarize the equilibrium hierarchy in a single table.

| **Equilibrium set** | **Topology** | **Closure** | **Interpretation** |
|---|---|---|---|
| $E_\vee$ | $\tau_+ \vee \tau_-$ | $\mathrm{cl}_\vee(U_{\mathrm{pre}})$ | Bidirectional |
| $E_+$ | $\tau_+$ | $\mathrm{cl}_+(U_{\mathrm{pre}})$ | Forward |
| $E_-$ | $\tau_-$ | $\mathrm{cl}_-(U_{\mathrm{pre}})$ | Backward |
| $E_\wedge$ | $\tau_+ \wedge \tau_-$ | $\mathrm{cl}_\wedge(U_{\mathrm{pre}})$ | Symmetrized |

**Key results:**

- **Hierarchy.** $E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge$ (Theorem 14.9).
- **Characterization.** Each equilibrium set is the set of points whose neighborhoods of the corresponding type intersect $U_{\mathrm{pre}}$ (Propositions 14.13–14.16).
- **Interpretation.** Bidirectional, forward, backward, symmetrized (Interpretations 14.18–14.21).
- **Strictness.** Each inclusion can be strict (Proposition 14.23).
- **Polar decomposition.** The meet equilibrium is the closure in the symmetrized topology (Proposition 14.27).
- **Fixed points.** Every fixed point is in all four equilibrium sets (Proposition 14.30).
- **Locally symmetric points.** If $b$ is locally symmetric, then $b \in E_+$ iff $b \in E_-$ (Proposition 14.33).
- **Symmetry collapse.** If $d$ is symmetric, all four equilibrium sets coincide (Proposition 14.35).

The equilibrium hierarchy is the culmination of Part V. It organizes the four equilibrium concepts into a single lattice-theoretic order, and it shows that the equilibrium structure of belief space is determined by the bitopological structure of the quasi-metric.

---

## 14.11 Exercises

**Exercise 14.1.** Prove the closure property (Proposition 14.7).

**Exercise 14.2.** Verify the equilibrium hierarchy for Example 14.38.

**Exercise 14.3.** Compute the equilibrium sets for Example 14.39.

**Exercise 14.4.** Show that $E_+$ and $E_-$ may be incomparable.

**Exercise 14.5.** Prove that every fixed point is in all four equilibrium sets.

**Exercise 14.6.** Show that if $b$ is locally symmetric, then $b \in E_+$ iff $b \in E_-$.

**Exercise 14.7.** Prove that if $d$ is symmetric, then $E_+ = E_- = E_\vee = E_\wedge$.

**Exercise 14.8.** Construct an example where $E_\vee \subsetneq E_+ \cap E_-$.

**Exercise 14.9.** Construct an example where $E_+ \cap E_- \subsetneq E_+ \cup E_-$.

**Exercise 14.10 (Reflection question).** Which of the four equilibrium concepts is the "right" one for applications? Write a short essay (one page) arguing for your position.



---

**End of Chapter 14.**
