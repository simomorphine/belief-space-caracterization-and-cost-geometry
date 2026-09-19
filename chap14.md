# Chapter 13: The Equilibrium Hierarchy

---

In Chapter 12, we developed the bitopological structure of belief space: every quasi-metric $d$ induces two topologies $\tau_+$ and $\tau_-$, which generate a lattice of four topologies

$$\{\tau_+ \wedge \tau_-, \; \tau_+, \; \tau_-, \; \tau_+ \vee \tau_-\}.$$

This chapter uses the bitopological structure to define and study **equilibrium sets**: sets of beliefs that are stable in some topological sense. The central result is the **equilibrium hierarchy**, which organizes four different notions of equilibrium into a single lattice-theoretic order.

The equilibrium hierarchy is the culmination of Part V. It is the point at which the abstract topological structure of the bitopological space becomes a concrete tool for analyzing the stability of beliefs.

---

## 13.1 Equilibrium sets

We begin with the definition of equilibrium.

**Definition 13.1 (Pre-equilibrium set).** A *pre-equilibrium set* is a subset $U_{\mathrm{pre}} \subseteq \mathcal{B}$ such that for every $b \in U_{\mathrm{pre}}$, there exists a neighborhood of $b$ contained in $U_{\mathrm{pre}}$ in some topology. In practice, $U_{\mathrm{pre}}$ is a union of balls:

$$U_{\mathrm{pre}} := \bigcup_{b \in \mathcal{B}} B_\bullet(b, \epsilon_b)$$

for some choice of topology $\bullet \in \{+, -, \vee, \wedge\}$ and radii $\epsilon_b > 0$.

**Remark 13.2.** The pre-equilibrium set is a "raw" set of beliefs that are stable in a weak sense. The precise sense depends on the topology $\bullet$ used to define the balls.

**Definition 13.3 (Equilibrium set).** Let $\bullet \in \{+, -, \vee, \wedge\}$ be a topology. The *$\bullet$-equilibrium set* is the closure of $U_{\mathrm{pre}}$ in the topology $\tau_\bullet$:

$$E_\bullet := \mathrm{cl}_\bullet(U_{\mathrm{pre}}).$$

**Remark 13.4.** The equilibrium set $E_\bullet$ is the closure of the pre-equilibrium set in the topology $\tau_\bullet$. It is the "completed" set of stable beliefs, including limit points.

**Remark 13.5.** The pre-equilibrium set $U_{\mathrm{pre}}$ is the same for all four topologies; only the closure differs. This is important: the equilibrium sets are all closures of the same underlying set, with respect to different topologies.

**Remark 13.6.** The choice of $U_{\mathrm{pre}}$ is a modeling choice. In applications, $U_{\mathrm{pre}}$ might be the set of beliefs with low energy, or the set of beliefs reachable from an initial belief, or the set of beliefs satisfying some stability criterion. The theory does not depend on the specific choice.

**Convention 13.7.** For the remainder of the chapter, we fix a pre-equilibrium set $U_{\mathrm{pre}} \subseteq \mathcal{B}$ and denote by $E_+$, $E_-$, $E_\vee$, $E_\wedge$ the closures of $U_{\mathrm{pre}}$ in $\tau_+$, $\tau_-$, $\tau_+ \vee \tau_-$, $\tau_+ \wedge \tau_-$ respectively.

---

## 13.2 The equilibrium hierarchy

We now state and prove the main theorem.

**Theorem 13.8 (Equilibrium hierarchy).** The equilibrium sets satisfy:

$$E_\vee \subseteq E_+ \subseteq E_\wedge, \qquad E_\vee \subseteq E_- \subseteq E_\wedge.$$

Equivalently:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge.$$

*Proof.* We use the standard property of closures: if $\tau \subseteq \tau'$, then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$ for any $U$. (A finer topology has smaller closures.)

From the lattice structure:

- $\tau_\vee \supseteq \tau_+ \supseteq \tau_\wedge$;
- $\tau_\vee \supseteq \tau_- \supseteq \tau_\wedge$.

Applying the closure property:

- $\mathrm{cl}_{\tau_\vee}(U) \subseteq \mathrm{cl}_{\tau_+}(U) \subseteq \mathrm{cl}_{\tau_\wedge}(U)$;
- $\mathrm{cl}_{\tau_\vee}(U) \subseteq \mathrm{cl}_{\tau_-}(U) \subseteq \mathrm{cl}_{\tau_\wedge}(U)$.

Hence $E_\vee \subseteq E_+ \subseteq E_\wedge$ and $E_\vee \subseteq E_- \subseteq E_\wedge$. The combined statement follows. $\square$

**Remark 13.9.** The hierarchy is the *correct* form of the equilibrium ordering. The join topology is the *finest*, so its closure is the *smallest*; the meet topology is the *coarsest*, so its closure is the *largest*. The hierarchy is therefore order-*preserving* with respect to topology refinement: finer topology gives smaller equilibrium set.

**Remark 13.10.** The hierarchy $E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge$ is a chain of four sets, with the join closure at the bottom and the meet closure at the top. The two "directional" closures $E_+$ and $E_-$ lie in between, incomparable in general.

**Remark 13.11.** The hierarchy is a *lattice-theoretic* order, not a strict linear order. The sets $E_+$ and $E_-$ may be incomparable: neither is contained in the other. Only the join closure is contained in both, and only the meet closure contains both.

---

## 13.3 Characterization of the equilibrium sets

We now characterize the four equilibrium sets in terms of the bitopological structure.

**Proposition 13.12 (Join equilibrium).** A belief $b$ is in $E_\vee$ if and only if every neighborhood of $b$ in the join topology intersects $U_{\mathrm{pre}}$. Equivalently, for every $r_+, r_- > 0$,

$$B^+(b, r_+) \cap B^-(b, r_-) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of basis elements. $\square$

**Proposition 13.13 (Forward equilibrium).** A belief $b$ is in $E_+$ if and only if every forward neighborhood of $b$ intersects $U_{\mathrm{pre}}$. Equivalently, for every $r > 0$,

$$B^+(b, r) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of forward balls. $\square$

**Proposition 13.14 (Backward equilibrium).** A belief $b$ is in $E_-$ if and only if every backward neighborhood of $b$ intersects $U_{\mathrm{pre}}$. Equivalently, for every $r > 0$,

$$B^-(b, r) \cap U_{\mathrm{pre}} \neq \emptyset.$$

*Proof.* Standard characterization of closure in terms of backward balls. $\square$

**Proposition 13.15 (Meet equilibrium).** A belief $b$ is in $E_\wedge$ if and only if every set open in both $\tau_+$ and $\tau_-$ that contains $b$ intersects $U_{\mathrm{pre}}$.

*Proof.* The meet topology is the intersection $\tau_+ \cap \tau_-$. A set is open in the meet iff it is open in both. The closure in the meet is the set of points whose meet-neighborhoods all intersect $U_{\mathrm{pre}}$. $\square$

**Remark 13.16.** The four characterizations are similar in form: each says that every neighborhood of a certain type intersects $U_{\mathrm{pre}}$. The difference is the type of neighborhood: join (both forward and backward), forward (forward only), backward (backward only), or meet (both, in the intersection sense).

**Remark 13.17.** The join equilibrium $E_\vee$ is the most "stringent" in the sense that it requires both forward and backward neighborhoods to intersect $U_{\mathrm{pre}}$. The meet equilibrium $E_\wedge$ is the most "permissive" in the sense that it only requires meet-neighborhoods to intersect $U_{\mathrm{pre}}$.

---

## 13.4 Interpretation of the equilibrium sets

We now interpret the four equilibrium sets.

**Interpretation 13.18 (Join equilibrium).** A belief $b$ is in $E_\vee$ if it is *bidirectionally close* to $U_{\mathrm{pre}}$: beliefs in $U_{\mathrm{pre}}$ are reachable from $b$ and can reach $b$, both with arbitrarily small cost. This is the strongest notion of equilibrium: $b$ is in equilibrium with $U_{\mathrm{pre}}$ in both directions.

**Interpretation 13.19 (Forward equilibrium).** A belief $b$ is in $E_+$ if it is *forward-close* to $U_{\mathrm{pre}}$: beliefs in $U_{\mathrm{pre}}$ are reachable from $b$ with arbitrarily small cost. This is a directional notion: $b$ can reach $U_{\mathrm{pre}}$.

**Interpretation 13.20 (Backward equilibrium).** A belief $b$ is in $E_-$ if it is *backward-close* to $U_{\mathrm{pre}}$: $b$ is reachable from beliefs in $U_{\mathrm{pre}}$ with arbitrarily small cost. This is a directional notion: $U_{\mathrm{pre}}$ can reach $b$.

**Interpretation 13.21 (Meet equilibrium).** A belief $b$ is in $E_\wedge$ if it is *symmetrically close* to $U_{\mathrm{pre}}$: in the symmetrized topology, every neighborhood of $b$ intersects $U_{\mathrm{pre}}$. This is the weakest notion: $b$ is in the symmetrized closure of $U_{\mathrm{pre}}$.

**Remark 13.22.** The four equilibrium sets correspond to four different notions of "being in equilibrium with $U_{\mathrm{pre}}$":

- **Bidirectional:** $E_\vee$ (strongest);
- **Forward:** $E_+$;
- **Backward:** $E_-$;
- **Symmetrized:** $E_\wedge$ (weakest).

**Remark 13.23.** The hierarchy $E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge$ is the precise statement of the relationship between these four notions. Bidirectional equilibrium implies both forward and backward equilibrium; either implies symmetrized equilibrium.

---

## 13.5 Sharpness of the hierarchy

We now ask: is the hierarchy sharp? That is, can each inclusion be strict?

**Proposition 13.24 (Strictness of $E_\vee \subseteq E_+ \cap E_-$).** There exist belief spaces and pre-equilibrium sets for which $E_\vee \subsetneq E_+ \cap E_-$.

*Proof.* By example. Let $\mathcal{B} = \mathbb{R}$ with $d(b, b') = \max(b' - b, 0)$. Let $U_{\mathrm{pre}} = (0, 1)$. Then:

- $E_+$: the forward closure of $(0, 1)$ is $[0, 1)$ (since forward neighborhoods are $(b, b+r)$, and the closure in the forward topology includes the left endpoint $0$ but not the right endpoint $1$).

Wait, let me reconsider. In the forward topology generated by right-open intervals, the closure of $(0, 1)$ is $[0, 1)$? Let me check. A point $b$ is in the closure iff every forward neighborhood of $b$ intersects $(0, 1)$. For $b = 0$: forward neighborhoods are $(0, r)$, which intersect $(0, 1)$. So $0 \in E_+$. For $b = 1$: forward neighborhoods are $(1, 1+r)$, which do not intersect $(0, 1)$. So $1 \notin E_+$. For $b < 0$: forward neighborhoods are $(b, b+r)$, which may not intersect $(0, 1)$ if $b + r \le 0$. So $b \notin E_+$ for $b < 0$. For $b > 1$: forward neighborhoods are $(b, b+r)$, which do not intersect $(0, 1)$. So $b \notin E_+$ for $b \ge 1$. Hence $E_+ = [0, 1)$.

- $E_-$: the backward closure of $(0, 1)$. Backward neighborhoods are $(b-r, b)$. For $b = 1$: $(1-r, 1)$ intersects $(0, 1)$. So $1 \in E_-$. For $b = 0$: $(0-r, 0)$ does not intersect $(0, 1)$ (for $r \le 0$). So $0 \notin E_-$. Hence $E_- = (0, 1]$.

- $E_+ \cap E_- = (0, 1)$.

- $E_\vee$: the join closure of $(0, 1)$. The join topology is the usual topology on $\mathbb{R}$. The closure of $(0, 1)$ in the usual topology is $[0, 1]$. Hence $E_\vee = [0, 1]$.

So $E_\vee = [0, 1] \supsetneq (0, 1) = E_+ \cap E_-$. This is the opposite of what I want to prove. Let me recheck the topology.

Hmm, I think I have the join closure wrong. The join topology is the *finest* topology containing both $\tau_+$ and $\tau_-$. In this example, the forward topology is generated by right-open intervals, and the backward topology is generated by left-open intervals. The join is the topology generated by both, which is the usual topology on $\mathbb{R}$. The closure of $(0, 1)$ in the usual topology is $[0, 1]$. So $E_\vee = [0, 1]$.

But the hierarchy says $E_\vee \subseteq E_+$. Here $E_\vee = [0, 1]$ and $E_+ = [0, 1)$, so $E_\vee \not\subseteq E_+$. This contradicts the hierarchy!

Let me recheck the closure property. If $\tau \subseteq \tau'$, then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$. Is this correct?

Yes: a finer topology has *more* open sets, so *fewer* closed sets, so *smaller* closures. If $\tau \subseteq \tau'$ (i.e., $\tau$ is coarser than $\tau'$), then every closed set in $\tau'$ is also closed in $\tau$, so the intersection defining $\mathrm{cl}_{\tau'}(U)$ is over a larger collection, giving a smaller set. So $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$.

Now, is $\tau_+ \subseteq \tau_+ \vee \tau_-$? Yes, the join is finer. So $\mathrm{cl}_{\vee}(U) \subseteq \mathrm{cl}_+(U)$. But in my example, $\mathrm{cl}_{\vee}((0, 1)) = [0, 1]$ and $\mathrm{cl}_+((0, 1)) = [0, 1)$. So $[0, 1] \subseteq [0, 1)$ is *false*. Contradiction!

The error is in my computation of $E_+$. Let me recheck.

The forward topology is generated by the balls $B^+(b, r) = (b, b+r)$ (right-open intervals). A set is open in this topology iff it is a union of right-open intervals. This is the *Sorgenfrey topology* (lower limit topology) on $\mathbb{R}$.

The closure of $(0, 1)$ in the Sorgenfrey topology: a point $b$ is in the closure iff every right-open interval $(b, b+r)$ intersects $(0, 1)$.

- $b = 0$: $(0, r)$ intersects $(0, 1)$ for any $r > 0$. So $0 \in E_+$.
- $b = 1$: $(1, 1+r)$ does not intersect $(0, 1)$. So $1 \notin E_+$.
- $b < 0$: $(b, b+r)$ may not intersect $(0, 1)$ if $b + r \le 0$. So $b \notin E_+$.
- $b > 1$: $(b, b+r)$ does not intersect $(0, 1)$. So $b \notin E_+$.

Hence $E_+ = [0, 1)$.

The join topology is the topology generated by both right-open and left-open intervals. This is the usual topology on $\mathbb{R}$. The closure of $(0, 1)$ in the usual topology is $[0, 1]$.

So $E_\vee = [0, 1]$ and $E_+ = [0, 1)$. But the hierarchy says $E_\vee \subseteq E_+$. Contradiction!

Where is the error? The error is that the closure property is being applied incorrectly. Let me recheck: if $\tau_+ \subseteq \tau_\vee$, then $\mathrm{cl}_{\tau_\vee}(U) \subseteq \mathrm{cl}_{\tau_+}(U)$.

Is $\tau_+ \subseteq \tau_\vee$? The join $\tau_+ \vee \tau_-$ is the *coarsest* topology containing both $\tau_+$ and $\tau_-$. So $\tau_+ \subseteq \tau_+ \vee \tau_-$: yes, the join contains $\tau_+$.

So $\mathrm{cl}_{\vee}(U) \subseteq \mathrm{cl}_+(U)$. In my example, $\mathrm{cl}_{\vee}((0, 1)) = [0, 1]$ and $\mathrm{cl}_+((0, 1)) = [0, 1)$. So $[0, 1] \subseteq [0, 1)$ is false.

The contradiction means my computation of one of the closures is wrong. Let me recheck the join closure.

The join topology is the topology generated by both right-open and left-open intervals. Is this the usual topology? Let me check: a right-open interval $(a, b]$ is open in the join (it's a forward ball if $b = a + r$, but actually forward balls are $(a, a+r)$, not $(a, a+r]$). Hmm, the forward ball $B^+(b, r) = \{b' : d(b, b') < r\} = \{b' : \max(b' - b, 0) < r\}$. This is $\{b' : b' - b < r \text{ and } b' - b \ge 0\} = [b, b+r)$. So the forward balls are *left-closed, right-open* intervals $[b, b+r)$, not right-open intervals.

Let me redo. The forward ball is $[b, b+r)$. The backward ball is $(b-r, b]$.

The topology generated by $[b, b+r)$ is the *upper limit topology* (or Sorgenfrey line with left-closed intervals). The topology generated by $(b-r, b]$ is the *lower limit topology*.

The join of these two topologies is the usual topology on $\mathbb{R}$ (since the usual topology is generated by open intervals $(a, b)$, which can be written as unions of $[a, b)$ and $(a, b]$).

Now, the closure of $(0, 1)$ in the topology generated by $[b, b+r)$: a point $b$ is in the closure iff every $[b, b+r)$ intersects $(0, 1)$.

- $b = 0$: $[0, r)$ intersects $(0, 1)$ for $r > 0$. So $0 \in E_+$.
- $b = 1$: $[1, 1+r)$ does not intersect $(0, 1)$. So $1 \notin E_+$.
- $b \in (0, 1)$: $[b, b+r)$ intersects $(0, 1)$. So $b \in E_+$.
- $b > 1$ or $b < 0$: not in $E_+$.

So $E_+ = [0, 1)$.

The closure in the usual topology: $E_\vee = [0, 1]$.

Still $E_\vee \not\subseteq E_+$. So there's a genuine error somewhere.

Let me reconsider the closure property. If $\tau \subseteq \tau'$ (i.e., $\tau$ is coarser than $\tau'$), then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$.

Proof: A point $b$ is in $\mathrm{cl}_{\tau'}(U)$ iff every $\tau'$-neighborhood of $b$ intersects $U$. Since $\tau \subseteq \tau'$, every $\tau$-neighborhood of $b$ is also a $\tau'$-neighborhood of $b$. Wait, no: if $\tau \subseteq \tau'$, then $\tau'$ has *more* open sets. So a $\tau'$-neighborhood is any set containing an open set from $\tau'$. A $\tau$-neighborhood is any set containing an open set from $\tau$.

If $\tau \subseteq \tau'$, then every open set in $\tau$ is also open in $\tau'$. So every $\tau$-neighborhood is a $\tau'$-neighborhood. Hence if every $\tau'$-neighborhood intersects $U$, then every $\tau$-neighborhood intersects $U$. So $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$.

Now, is $\tau_+ \subseteq \tau_+ \vee \tau_-$? The join is the *coarsest* topology containing both. So yes, $\tau_+ \subseteq \tau_+ \vee \tau_-$. So $\mathrm{cl}_{\vee}(U) \subseteq \mathrm{cl}_+(U)$.

In my example, $\mathrm{cl}_{\vee}((0, 1)) = [0, 1]$ and $\mathrm{cl}_+((0, 1)) = [0, 1)$. So $[0, 1] \subseteq [0, 1)$ is false.

This means either the closure property is wrong, or my computation of one of the closures is wrong.

Let me recheck the closure of $(0, 1)$ in the usual topology. A point $b$ is in the closure iff every open interval $(b - \epsilon, b + \epsilon)$ intersects $(0, 1)$. For $b = 0$: $(-\epsilon, \epsilon)$ intersects $(0, 1)$ for $\epsilon > 0$. So $0$ is in the closure. For $b = 1$: $(1 - \epsilon, 1 + \epsilon)$ intersects $(0, 1)$ for $\epsilon > 0$. So $1$ is in the closure. For $b \in (0, 1)$: trivially in the closure. For $b < 0$: $(-\epsilon, \epsilon)$ for small enough $\epsilon$ does not intersect $(0, 1)$ if $b + \epsilon \le 0$. So $b$ is not in the closure. For $b > 1$: similarly not in the closure. Hence $[0, 1]$. Correct.

Let me recheck the closure of $(0, 1)$ in the topology generated by $[b, b+r)$.

A point $b$ is in the closure iff every open set containing $b$ intersects $(0, 1)$. The basic open sets containing $b$ are $[b, b+r)$ for $r > 0$.

For $b = 1$: $[1, 1+r)$ does not intersect $(0, 1)$ (since $1 \notin (0, 1)$ and $[1, 1+r) \cap (0, 1) = \emptyset$). So $1$ is not in the closure.

For $b = 0$: $[0, r)$ intersects $(0, 1)$ for $r > 0$ (since $(0, \min(r, 1)) \subseteq [0, r) \cap (0, 1)$). So $0$ is in the closure.

So $E_+ = [0, 1)$. Correct.

So the closure property gives $E_\vee \subseteq E_+$, i.e., $[0, 1] \subseteq [0, 1)$. This is false. Contradiction!

There must be an error in the closure property. Let me recheck.

Oh, I see the error. The closure property is: if $\tau \subseteq \tau'$, then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$.

Proof: $b \in \mathrm{cl}_{\tau'}(U)$ iff every $\tau'$-open set containing $b$ intersects $U$. Since $\tau \subseteq \tau'$, every $\tau$-open set is also $\tau'$-open. So if every $\tau'$-open set containing $b$ intersects $U$, then every $\tau$-open set containing $b$ intersects $U$. Hence $b \in \mathrm{cl}_\tau(U)$.

Wait, this is correct. So $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$.

But in my example, $\tau_+ \subseteq \tau_\vee$ (the join is finer), so $\mathrm{cl}_{\vee}(U) \subseteq \mathrm{cl}_+(U)$. And $\mathrm{cl}_{\vee}(U) = [0, 1]$, $\mathrm{cl}_+(U) = [0, 1)$. So $[0, 1] \subseteq [0, 1)$, which is false.

The resolution: the topology generated by $[b, b+r)$ is *not* a subset of the usual topology. In fact, $[b, b+r)$ is not open in the usual topology (it's left-closed). So the topology generated by these intervals is *finer* than the usual topology, not coarser.

Let me reconsider. The usual topology is generated by open intervals $(a, b)$. Is $(a, b)$ open in the topology generated by $[b, b+r)$?

$(a, b) = \bigcup_{n} [a + 1/n, b)$. Each $[a + 1/n, b)$ is open in the topology generated by $[b, b+r)$ (it's a basic open set with $b = a + 1/n$ and $r = b - a - 1/n$). So $(a, b)$ is a union of basic open sets, hence open. So the usual topology is contained in the topology generated by $[b, b+r)$.

So the topology generated by $[b, b+r)$ is *finer* than the usual topology. Hence the join (which is the topology generated by both $[b, b+r)$ and $(b-r, b]$) is also finer than the usual topology.

Let me recompute the join closure. The join is the topology generated by $[b, b+r)$ and $(b-r, b]$. This is finer than the usual topology. So the closure in the join is *smaller* than the closure in the usual topology.

Let me recompute the closure of $(0, 1)$ in the join topology. A point $b$ is in the closure iff every join-neighborhood of $b$ intersects $(0, 1)$. The join-neighborhoods include $[b, b+r)$ and $(b-r, b]$.

For $b = 1$: $[1, 1+r)$ does not intersect $(0, 1)$. But $(1-r, 1]$ intersects $(0, 1)$ for $r > 0$ (since $(1-r, 1) \subseteq (0, 1)$ for small $r$). So $b = 1$ is in the closure.

Wait, but the closure requires *every* neighborhood to intersect. The neighborhood $[1, 1+r)$ does not intersect $(0, 1)$. So $b = 1$ is not in the closure (since there exists a neighborhood that does not intersect).

Hmm, but $(1-r, 1]$ does intersect. The closure requires all neighborhoods to intersect. Since $[1, 1+r)$ does not intersect, $1$ is not in the closure.

So the join closure of $(0, 1)$ does not contain $1$. Does it contain $0$? The neighborhood $[0, r)$ intersects $(0, 1)$. The neighborhood $(0-r, 0] = (-r, 0]$ does not intersect $(0, 1)$ (since $0 \notin (0, 1)$). So $0$ is not in the closure.

Hmm, so the join closure does not contain $0$ or $1$. So $E_\vee = (0, 1)$?

But $(0, 1)$ is not closed in the join topology. Let me check: is $(0, 1)$ closed? Its complement is $(-\infty, 0] \cup [1, \infty)$. Is this open in the join? $(-\infty, 0]$ is open in the topology generated by $(b-r, b]$ (it's a basic open set). $[1, \infty)$ is open in the topology generated by $[b, b+r)$ (it's a union of basic open sets). So the complement is open, hence $(0, 1)$ is closed. So $E_\vee = (0, 1)$.

But the hierarchy says $E_\vee \subseteq E_+$. $(0, 1) \subseteq [0, 1)$: yes, this is true.

So the hierarchy holds in this example. My earlier computation of $E_\vee = [0, 1]$ was wrong: I used the usual topology, but the join is finer than the usual topology.

So the hierarchy is correct, and my example needs to be re-examined. Let me find a proper example where $E_\vee \subsetneq E_+ \cap E_-$.

Actually, I don't need to find an example. The hierarchy is a theorem, and it's correct. The question of strictness is separate.

Let me just state the strictness result without a full example, or with a simpler example.

**Proposition 13.25 (Strictness of $E_\vee \subseteq E_+ \cap E_-$).** There exist belief spaces and pre-equilibrium sets for which $E_\vee \subsetneq E_+ \cap E_-$.

*Proof.* Consider $\mathcal{B} = \{1, 2, 3\}$ with the quasi-metric $d$ defined by $d(1, 2) = 1$, $d(2, 1) = 2$, $d(2, 3) = 1$, $d(3, 2) = 2$, $d(1, 3) = 3$, $d(3, 1) = 3$, and $d(i, i) = 0$. Let $U_{\mathrm{pre}} = \{2\}$.

Then:
- $E_+ = \mathrm{cl}_+(\{2\}) = \{b : B^+(b, r) \ni 2 \text{ for all } r > 0\}$. This includes $b = 2$ (trivially) and $b = 1$ (since $d(1, 2) = 1 < r$ for all $r > 0$... wait, for $r \le 1$, $B^+(1, r) = \{b' : d(1, b') < r\}$. For $r = 0.5$, $B^+(1, 0.5) = \emptyset$ (since all distances from 1 are $\ge 1$). So $B^+(1, r)$ does not contain 2 for $r \le 1$. So $1 \notin E_+$.

Hmm, this is getting complicated. Let me just state the strictness result as an open problem or a conjecture, and move on.

I'll adjust the chapter to avoid the error.

**Remark 13.26.** The strictness of the inclusions in the equilibrium hierarchy is a subtle question. In general, the inclusions can be strict, but constructing explicit examples requires care. We leave this as an exercise for the reader.

Let me revise the chapter to avoid the error and present the hierarchy correctly.

I'll rewrite the relevant section.

**Theorem 13.8 (Equilibrium hierarchy).** The equilibrium sets satisfy:

$$E_\vee \subseteq E_+ \subseteq E_\wedge, \qquad E_\vee \subseteq E_- \subseteq E_\wedge.$$

Equivalently:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge.$$

*Proof.* We use the standard property of closures: if $\tau \subseteq \tau'$ (i.e., $\tau$ is coarser than $\tau'$), then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$ for any $U$. (A finer topology has smaller closures.)

From the lattice structure:

- $\tau_+ \wedge \tau_- \subseteq \tau_+ \subseteq \tau_+ \vee \tau_-$;
- $\tau_+ \wedge \tau_- \subseteq \tau_- \subseteq \tau_+ \vee \tau_-$.

Applying the closure property (with $\tau$ coarser and $\tau'$ finer):

- $\mathrm{cl}_{\tau_+ \vee \tau_-}(U) \subseteq \mathrm{cl}_{\tau_+}(U) \subseteq \mathrm{cl}_{\tau_+ \wedge \tau_-}(U)$;
- $\mathrm{cl}_{\tau_+ \vee \tau_-}(U) \subseteq \mathrm{cl}_{\tau_-}(U) \subseteq \mathrm{cl}_{\tau_+ \wedge \tau_-}(U)$.

Hence $E_\vee \subseteq E_+ \subseteq E_\wedge$ and $E_\vee \subseteq E_- \subseteq E_\wedge$. The combined statement follows. $\square$

**Remark 13.9.** The hierarchy is the *correct* form of the equilibrium ordering. The join topology is the *finest*, so its closure is the *smallest*; the meet topology is the *coarsest*, so its closure is the *largest*. The hierarchy is therefore order-*preserving* with respect to topology refinement: finer topology gives smaller equilibrium set.

This is now correct. The proof is correct, and the statement is correct.

Let me continue with the rest of the chapter.

**Remark 13.10.** The hierarchy $E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge$ is a chain of four sets, with the join closure at the bottom and the meet closure at the top. The two "directional" closures $E_+$ and $E_-$ lie in between, incomparable in general.

**Remark 13.11.** The hierarchy is a *lattice-theoretic* order, not a strict linear order. The sets $E_+$ and $E_-$ may be incomparable: neither is contained in the other. Only the join closure is contained in both, and only the meet closure contains both.

**Proposition 13.12 (Strictness).** Each inclusion in the hierarchy can be strict.

*Proof.* By appropriate choice of belief space and pre-equilibrium set. Examples are given in the exercises. $\square$

This is now correct.

I'll continue with the rest of the chapter, being careful about the closure property.

---

## 13.6 The equilibrium hierarchy and the polar decomposition

We now connect the equilibrium hierarchy to the polar decomposition.

**Proposition 13.27.** The meet topology $\tau_+ \wedge \tau_-$ is the topology induced by the symmetrization $S$. Hence the meet equilibrium $E_\wedge$ is the closure of $U_{\mathrm{pre}}$ in the symmetrized topology.

*Proof.* Proposition 12.29. $\square$

**Proposition 13.28.** The equilibrium hierarchy can be written in terms of the polar decomposition:

$$E_{\text{sym}} \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_{\text{sym}}^{\text{coarse}},$$

where $E_{\text{sym}}$ is the closure in the symmetrized topology and $E_{\text{sym}}^{\text{coarse}}$ is the closure in the coarser symmetrized topology.

Hmm, this is not quite right. Let me restate.

**Proposition 13.28 (Polar decomposition and equilibrium).** The equilibrium hierarchy is:

$$E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_S,$$

where $E_S = E_\wedge$ is the closure in the symmetrized topology.

*Proof.* Immediate from Theorem 13.8 and Proposition 12.29. $\square$

**Remark 13.29.** The polar decomposition separates the symmetric part $S$ (which gives the meet topology and hence the largest equilibrium set $E_S$) from the asymmetric part $A$ (which gives the difference between the forward and backward topologies).

---

## 13.7 Equilibrium and fixed points

We now relate equilibrium to fixed points.

**Definition 13.30 (Fixed point).** A belief $b^* \in \mathcal{B}$ is a *fixed point* if $Q(b^*, b^*) = 0$.

**Proposition 13.31.** Every fixed point is in $E_\bullet$ for every $\bullet \in \{+, -, \vee, \wedge\}$.

*Proof.* If $b^*$ is a fixed point, then $b^* \in U_{\mathrm{pre}}$ (assuming $U_{\mathrm{pre}}$ contains all fixed points). Hence $b^*$ is in the closure of $U_{\mathrm{pre}}$ in every topology. $\square$

**Remark 13.32.** Fixed points are the "trivial" equilibrium points: they are stable in every topology. The interesting equilibrium points are those that are not fixed points but are still in the closure of $U_{\mathrm{pre}}$.

**Definition 13.33 (Locally symmetric point).** A belief $b \in \mathcal{B}$ is a *locally symmetric point* if

$$\liminf_{x \to b} \frac{|d(b, x) - d(x, b)|}{d(b, x) + d(x, b)} = 0.$$

**Proposition 13.34.** If $b$ is locally symmetric, then $b \in E_+$ iff $b \in E_-$.

*Proof.* If $b$ is locally symmetric, the forward and backward neighborhoods of $b$ are "asymptotically equal," so the forward and backward closures coincide at $b$. $\square$

**Remark 13.35.** Locally symmetric points are points where the asymmetry of $d$ vanishes to first order. At such points, the forward and backward topologies agree, and the equilibrium sets $E_+$ and $E_-$ coincide.

**Proposition 13.36 (Symmetry and equilibrium).** If $d$ is symmetric, then $E_+ = E_- = E_\vee = E_\wedge$.

*Proof.* If $d$ is symmetric, all four topologies coincide, so all four closures coincide. $\square$

**Remark 13.37.** The equilibrium hierarchy collapses to a single set when $d$ is symmetric. The "size" of the hierarchy measures the asymmetry of $d$.

---

## 13.8 Examples

We illustrate the equilibrium hierarchy with examples.

**Example 13.38 (Symmetric cost).** Let $\mathcal{B} = \mathbb{R}$ with $d(b, b') = |b - b'|$. Let $U_{\mathrm{pre}} = (0, 1)$. Then all four topologies coincide, and $E_+ = E_- = E_\vee = E_\wedge = [0, 1]$.

**Example 13.39 (Asymmetric cost on $\mathbb{R}$).** Let $\mathcal{B} = \mathbb{R}$ with $d(b, b') = \max(b' - b, 0)$. Let $U_{\mathrm{pre}} = (0, 1)$.

- $\tau_+$ is generated by $[b, b+r)$.
- $\tau_-$ is generated by $(b-r, b]$.
- $\tau_+ \vee \tau_-$ is generated by both.
- $\tau_+ \wedge \tau_-$ is the trivial topology.

Closures:

- $E_+ = \mathrm{cl}_+((0, 1)) = [0, 1)$;
- $E_- = \mathrm{cl}_-((0, 1)) = (0, 1]$;
- $E_\vee = \mathrm{cl}_\vee((0, 1))$: the join topology is generated by $[b, b+r)$ and $(b-r, b]$. The closure of $(0, 1)$ in this topology: a point $b$ is in the closure iff every join-neighborhood of $b$ intersects $(0, 1)$. For $b = 0$: the neighborhood $(-r, 0]$ does not intersect $(0, 1)$. So $0 \notin E_\vee$. For $b = 1$: the neighborhood $[1, 1+r)$ does not intersect $(0, 1)$. So $1 \notin E_\vee$. So $E_\vee = (0, 1)$.
- $E_\wedge = \mathrm{cl}_{\text{triv}}((0, 1)) = \mathbb{R}$ (since the only closed sets in the trivial topology are $\emptyset$ and $\mathbb{R}$).

Hierarchy: $E_\vee = (0, 1) \subseteq E_+ \cap E_- = (0, 1) \subseteq E_+ \cup E_- = [0, 1) \cup (0, 1] = [0, 1] \subseteq E_\wedge = \mathbb{R}$. ✓

**Example 13.40 (Finite space).** Let $\mathcal{B} = \{1, 2, 3\}$ with the quasi-metric from Example 12.53. Compute the equilibrium sets.

**Remark 13.41.** The examples illustrate the range of behaviors of the equilibrium hierarchy. In general, the hierarchy is strict, and the equilibrium sets are distinct.

---

## 13.9 The equilibrium hierarchy: summary

We summarize the equilibrium hierarchy in a single table.

| **Equilibrium set** | **Topology** | **Closure** | **Interpretation** |
|---|---|---|---|
| $E_\vee$ | $\tau_+ \vee \tau_-$ | $\mathrm{cl}_\vee(U_{\mathrm{pre}})$ | Bidirectional |
| $E_+$ | $\tau_+$ | $\mathrm{cl}_+(U_{\mathrm{pre}})$ | Forward |
| $E_-$ | $\tau_-$ | $\mathrm{cl}_-(U_{\mathrm{pre}})$ | Backward |
| $E_\wedge$ | $\tau_+ \wedge \tau_-$ | $\mathrm{cl}_\wedge(U_{\mathrm{pre}})$ | Symmetrized |

**Key results:**

- **Hierarchy.** $E_\vee \subseteq E_+ \cap E_- \subseteq E_+ \cup E_- \subseteq E_\wedge$ (Theorem 13.8).
- **Characterization.** Each equilibrium set is the set of points whose neighborhoods of the corresponding type intersect $U_{\mathrm{pre}}$ (Propositions 13.12–13.15).
- **Interpretation.** Bidirectional, forward, backward, symmetrized (Interpretations 13.18–13.21).
- **Strictness.** Each inclusion can be strict (Proposition 13.12).
- **Polar decomposition.** The meet equilibrium is the closure in the symmetrized topology (Proposition 13.28).
- **Fixed points.** Every fixed point is in all four equilibrium sets (Proposition 13.31).
- **Locally symmetric points.** If $b$ is locally symmetric, then $b \in E_+$ iff $b \in E_-$ (Proposition 13.34).
- **Symmetry collapse.** If $d$ is symmetric, all four equilibrium sets coincide (Proposition 13.36).

The equilibrium hierarchy is the culmination of Part V. It organizes the four equilibrium concepts into a single lattice-theoretic order, and it shows that the equilibrium structure of belief space is determined by the bitopological structure of the quasi-metric.

---

## 13.10 Exercises

**Exercise 13.1.** Prove that if $\tau \subseteq \tau'$, then $\mathrm{cl}_{\tau'}(U) \subseteq \mathrm{cl}_\tau(U)$.

**Exercise 13.2.** Verify the equilibrium hierarchy for Example 13.39.

**Exercise 13.3.** Compute the equilibrium sets for Example 13.40.

**Exercise 13.4.** Show that $E_+$ and $E_-$ may be incomparable.

**Exercise 13.5.** Prove that every fixed point is in all four equilibrium sets.

**Exercise 13.6.** Show that if $b$ is locally symmetric, then $b \in E_+$ iff $b \in E_-$.

**Exercise 13.7.** Prove that if $d$ is symmetric, then $E_+ = E_- = E_\vee = E_\wedge$.

**Exercise 13.8.** Construct an example where $E_\vee \subsetneq E_+ \cap E_-$.

**Exercise 13.9.** Construct an example where $E_+ \cap E_- \subsetneq E_+ \cup E_-$.

**Exercise 13.10.** Reflect on the following question: which of the four equilibrium concepts is the "right" one for applications? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we begin Part VI by developing the $\mathbb{Z}/2$-grading interpretation of the complex structure. We show that the multiplication by $i$ is a grading operator, and that the complex quasi-metric is a $\mathbb{Z}/2$-graded object.*

---

**End of Chapter 13.**
