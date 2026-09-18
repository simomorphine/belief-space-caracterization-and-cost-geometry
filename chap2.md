# Chapter 2: Belief Space

---

A theory needs a stage. For the theory of cost and debt, the stage is **belief space**: the set of configurations that an information processing system can occupy, together with the transitions between them.

This chapter defines belief space, introduces the energy quasi-metric, and establishes the conventions that will be used throughout the book. It is deliberately spare. The interesting structure—debt, the complex quasi-metric, the γ-family—comes later. Here we set the stage.

---

## 2.1 States and configurations

Let us begin with the primitive notion.

**Definition 2.1 (Information processing system).** An *information processing system* is a triple $(\mathcal{S}, \mathcal{T}, \mathcal{C})$ consisting of:

- A set $\mathcal{S}$ of *states*;
- A set $\mathcal{T} \subseteq \mathcal{S} \times \mathcal{S}$ of *transitions*;
- A function $\mathcal{C} : \mathcal{T} \to \mathbb{R}_{\ge 0}$ assigning a *cost* to each transition.

A *state* $s \in \mathcal{S}$ is a complete specification of the system's configuration at a moment in time. A *transition* $(s_i, s_j) \in \mathcal{T}$ is a permissible move from state $s_i$ to state $s_j$. The *cost* $\mathcal{C}(s_i, s_j)$ is the resource—energy, time, money, information—required to perform the transition.

**Remark 2.2.** The set $\mathcal{T}$ need not be symmetric. If $(s_i, s_j) \in \mathcal{T}$, it does not follow that $(s_j, s_i) \in \mathcal{T}$. Transitions may be irreversible. This is the first place where the metric assumption fails.

**Remark 2.3.** The cost function $\mathcal{C}$ is defined only on $\mathcal{T}$. If $(s_i, s_j) \notin \mathcal{T}$, the cost is undefined—not infinite, but absent. This distinction matters: an undefined cost is not the same as an infinite cost. The former means the transition is not permitted; the latter means it is permitted but prohibitively expensive.

**Example 2.4 (Finite automaton).** Let $\mathcal{S}$ be the set of states of a finite automaton, $\mathcal{T}$ the transition relation, and $\mathcal{C}(s_i, s_j) = 1$ for all permitted transitions. Then $(\mathcal{S}, \mathcal{T}, \mathcal{C})$ is an information processing system. The cost is uniform: every transition costs one unit.

**Example 2.5 (Belief update).** Let $\mathcal{S}$ be the set of probability distributions over some outcome space $\Omega$. Let $\mathcal{T}$ be the set of pairs $(\mu, \nu)$ such that $\nu$ is absolutely continuous with respect to $\mu$. Let $\mathcal{C}(\mu, \nu) = D_{\mathrm{KL}}(\nu \| \mu)$, the Kullback–Leibler divergence. Then $(\mathcal{S}, \mathcal{T}, \mathcal{C})$ is an information processing system. The cost is the information gained by the update.

**Example 2.6 (Computation).** Let $\mathcal{S}$ be the set of configurations of a Turing machine, $\mathcal{T}$ the transition relation, and $\mathcal{C}(s_i, s_j)$ the number of steps required to go from $s_i$ to $s_j$. Then $(\mathcal{S}, \mathcal{T}, \mathcal{C})$ is an information processing system. The cost is time.

Each example exhibits a different notion of cost. The theory developed in this book applies to all of them, provided certain structural conditions are met.

---

## 2.2 Reachability and belief space

Not every state is reachable from every other. The set of reachable states, starting from a given state and with a bounded budget, is the natural domain of the theory.

**Definition 2.7 (Path).** A *path* in an information processing system is a finite sequence

$$\gamma = (s_0, s_1, \dots, s_n)$$

with $(s_k, s_{k+1}) \in \mathcal{T}$ for all $k = 0, \dots, n-1$. The *length* of the path is $n$. The *endpoints* are $s_0$ and $s_n$. The *cost* of the path is

$$\mathcal{C}(\gamma) := \sum_{k=0}^{n-1} \mathcal{C}(s_k, s_{k+1}).$$

**Definition 2.8 (Reachability).** A state $s_j$ is *reachable* from a state $s_i$ if there exists a path from $s_i$ to $s_j$. The *reachability relation* is the transitive closure of $\mathcal{T}$.

**Definition 2.9 (Bounded reachability).** A state $s_j$ is *reachable from $s_i$ with budget $B$* if there exists a path from $s_i$ to $s_j$ with cost at most $B$.

**Definition 2.10 (Belief space).** Let $(\mathcal{S}, \mathcal{T}, \mathcal{C})$ be an information processing system and let $s_0 \in \mathcal{S}$ be a distinguished *initial state*. The *belief space* is

$$\mathcal{B} := \{s \in \mathcal{S} : s \text{ is reachable from } s_0 \text{ with finite budget}\}.$$

The elements of $\mathcal{B}$ are called *beliefs*.

**Remark 2.11.** The term "belief" is deliberately broad. A belief may be a probability distribution, a computational configuration, a memory state, or anything else. The theory does not depend on the interpretation. What matters is that $\mathcal{B}$ is a set equipped with a cost function, and that every element is reachable from a common origin.

**Remark 2.12.** The choice of initial state $s_0$ is a gauge choice. Different initial states give different belief spaces, related by translation. The theory is invariant under this choice. This will be made precise in Chapter 4.

**Convention 2.13.** For the remainder of the book, we fix an information processing system, an initial state $s_0$, and the associated belief space $\mathcal{B}$. All constructions are relative to this data. We write $b, b_i, b_j, \dots$ for elements of $\mathcal{B}$.

---

## 2.3 The energy quasi-metric

The cost of moving between beliefs extends from paths to pairs by minimization.

**Definition 2.14 (Energy quasi-metric).** The *energy quasi-metric* is the function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0} \cup \{+\infty\}$ defined by

$$d(b_i, b_j) := \inf_{\gamma : b_i \to b_j} \mathcal{C}(\gamma),$$

where the infimum is over all paths from $b_i$ to $b_j$. If no path exists, $d(b_i, b_j) := +\infty$.

**Proposition 2.15.** The energy quasi-metric satisfies:

- **(i) Identity.** $d(b, b) = 0$ for all $b \in \mathcal{B}$.
- **(ii) Non-negativity.** $d(b_i, b_j) \ge 0$ for all $b_i, b_j \in \mathcal{B}$.
- **(iii) Triangle inequality.** $d(b_i, b_k) \le d(b_i, b_j) + d(b_j, b_k)$ for all $b_i, b_j, b_k \in \mathcal{B}$.

*Proof.* (i) The empty path from $b$ to $b$ has cost zero. Since costs are non-negative, no path has cost less than zero. Hence $d(b, b) = 0$.

(ii) Immediate from the non-negativity of $\mathcal{C}$.

(iii) Let $\gamma_1$ be a path from $b_i$ to $b_j$ with cost $C_1$, and let $\gamma_2$ be a path from $b_j$ to $b_k$ with cost $C_2$. The concatenation $\gamma_1 \cdot \gamma_2$ is a path from $b_i$ to $b_k$ with cost $C_1 + C_2$. Hence

$$d(b_i, b_k) \le \inf_{\gamma_1} \mathcal{C}(\gamma_1) + \inf_{\gamma_2} \mathcal{C}(\gamma_2) = d(b_i, b_j) + d(b_j, b_k).$$

Taking infima over all such decompositions gives the result. $\square$

**Remark 2.16.** The triangle inequality for $d$ is *automatic*: it follows from the definition of $d$ as a minimum over paths. This is a crucial point. The energy quasi-metric always satisfies the triangle inequality, by construction. What it does *not* automatically satisfy is symmetry. The asymmetry is the genuine content.

**Remark 2.17.** The notation "quasi-metric" reflects the fact that $d$ satisfies the triangle inequality but need not be symmetric. If $d$ is also symmetric, it is a pseudometric (or a metric, if the identity of indiscernibles also holds).

**Proposition 2.18 (Path-independence of $d$).** The energy quasi-metric $d$ depends only on the endpoints, not on the path. That is, if $\gamma_1$ and $\gamma_2$ are two paths from $b_i$ to $b_j$, then $d(b_i, b_j) \le \mathcal{C}(\gamma_1)$ and $d(b_i, b_j) \le \mathcal{C}(\gamma_2)$, with equality if and only if both paths are optimal.

*Proof.* Immediate from the definition of $d$ as an infimum. $\square$

**Remark 2.19.** The energy quasi-metric $d$ is an *emergent* quantity. It is not given; it is derived from the underlying cost function $\mathcal{C}$ by minimization. This is the standard move in shortest-path theory, and it is what makes $d$ well-behaved even when $\mathcal{C}$ is not.

---

## 2.4 The failure of symmetry

We now come to the central point.

**Proposition 2.20.** The energy quasi-metric $d$ need not be symmetric. That is, there may exist $b_i, b_j \in \mathcal{B}$ with $d(b_i, b_j) \neq d(b_j, b_i)$.

*Proof.* By construction. Consider an information processing system in which the transition $(s_i, s_j)$ is permitted but $(s_j, s_i)$ is not. Then $d(s_i, s_j)$ is finite but $d(s_j, s_i) = +\infty$. More subtly, even if both transitions are permitted, their costs may differ.

**Example 2.21 (Asymmetric network).** Let $\mathcal{B}$ be a set of nodes in a directed graph, with edge weights representing transmission costs. Let $d(b_i, b_j)$ be the shortest-path cost from $b_i$ to $b_j$. If the graph is directed and the weights are asymmetric, then $d$ is asymmetric.

**Example 2.22 (Reversible computation).** Let $\mathcal{B}$ be the set of configurations of a reversible computer. Forward transitions have cost $1$; backward transitions have cost $0$ (since they are reversible). Then $d(b_i, b_j) = 1$ and $d(b_j, b_i) = 0$, so $d$ is asymmetric.

**Example 2.23 (Belief update).** Let $\mathcal{B}$ be the set of probability distributions, and let $\mathcal{C}(\mu, \nu) = D_{\mathrm{KL}}(\nu \| \mu)$. Then

$$d(\mu, \nu) = D_{\mathrm{KL}}(\nu \| \mu), \qquad d(\nu, \mu) = D_{\mathrm{KL}}(\mu \| \nu).$$

Since KL divergence is asymmetric, so is $d$.

**Remark 2.24.** Asymmetry is not a defect. It is a feature. A system in which all transitions cost the same in both directions is a special case—an idealization. Real systems are asymmetric. The theory must accommodate this, not assume it away.

---

## 2.5 The failure of identity

The energy quasi-metric may also fail the identity of indiscernibles.

**Proposition 2.25.** There may exist distinct $b_i, b_j \in \mathcal{B}$ with $d(b_i, b_j) = 0$.

*Proof.* Suppose there is a transition $(b_i, b_j) \in \mathcal{T}$ with $\mathcal{C}(b_i, b_j) = 0$. Then $d(b_i, b_j) = 0$. If $b_i \neq b_j$, the identity of indiscernibles fails.

**Example 2.26 (Computational equivalence).** Let $\mathcal{B}$ be the set of configurations of a computer, and let $b_i \sim b_j$ if they compute the same function. Then $d(b_i, b_j) = 0$ for $b_i \sim b_j$, even though $b_i \neq b_j$.

**Example 2.27 (Gauge equivalence).** Let $\mathcal{B}$ be the set of states of a gauge theory, and let $b_i \sim b_j$ if they are related by a gauge transformation. Then $d(b_i, b_j) = 0$ for gauge-equivalent states.

**Remark 2.28.** When the identity of indiscernibles fails, $d$ is a *pseudometric* rather than a metric. The equivalence classes of zero-cost transitions are the "true" states; the individual elements of $\mathcal{B}$ are representatives.

**Definition 2.29 (Quotient belief space).** Let $\sim$ be the equivalence relation $b_i \sim b_j \iff d(b_i, b_j) = d(b_j, b_i) = 0$. The *quotient belief space* is $\mathcal{B}/{\sim}$.

**Proposition 2.30.** The energy quasi-metric $d$ descends to a quasi-metric on $\mathcal{B}/{\sim}$ satisfying the identity of indiscernibles.

*Proof.* If $b_i \sim b_i'$ and $b_j \sim b_j'$, then

$$d(b_i, b_j) \le d(b_i, b_i') + d(b_i', b_j') + d(b_j', b_j) = d(b_i', b_j'),$$

and symmetrically $d(b_i', b_j') \le d(b_i, b_j)$. Hence $d$ is well-defined on equivalence classes. The identity of indiscernibles holds by construction. $\square$

**Convention 2.31.** For the remainder of the book, we assume that the quotient has been taken: $\mathcal{B}$ satisfies the identity of indiscernibles. If it does not, replace $\mathcal{B}$ by $\mathcal{B}/{\sim}$.

---

## 2.6 The energy quasi-metric as a directed graph

The energy quasi-metric has a natural interpretation as a weighted directed graph.

**Construction 2.32.** Let $\mathcal{B}$ be a belief space with energy quasi-metric $d$. Define a directed graph $G_d$ with:

- Vertex set $\mathcal{B}$;
- Edge set $\{(b_i, b_j) : d(b_i, b_j) < +\infty\}$;
- Edge weight $d(b_i, b_j)$.

Then $d$ is exactly the shortest-path metric of $G_d$. Conversely, any weighted directed graph with non-negative weights induces an energy quasi-metric on its vertex set.

**Proposition 2.33.** The energy quasi-metric $d$ is the shortest-path metric of the graph $G_d$. That is, $d(b_i, b_j)$ equals the minimum over all paths in $G_d$ from $b_i$ to $b_j$ of the sum of edge weights.

*Proof.* By construction. $\square$

**Remark 2.34.** The graph $G_d$ is the "universal" representation of the energy quasi-metric. It shows that the theory of quasi-metrics is equivalent to the theory of weighted directed graphs with non-negative weights. This equivalence will be used repeatedly.

**Example 2.35 (Complete graph).** If $d(b_i, b_j) < +\infty$ for all $b_i, b_j$, then $G_d$ is the complete directed graph on $\mathcal{B}$. In this case, the shortest-path metric is the same as the edge weights: $d(b_i, b_j)$ is the weight of the edge from $b_i$ to $b_j$.

**Example 2.36 (Sparse graph).** If $d(b_i, b_j) = +\infty$ for many pairs, then $G_d$ is sparse. The shortest-path metric is nontrivial: it requires path composition.

---

## 2.7 What we assume and what we do not

Let us summarize the assumptions and non-assumptions of the theory.

**We assume:**

- **(A1) Belief space.** There is a set $\mathcal{B}$ of beliefs, equipped with a distinguished initial state $s_0$.
- **(A2) Energy quasi-metric.** There is a function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0} \cup \{+\infty\}$ satisfying identity, non-negativity, and the triangle inequality.
- **(A3) Identity of indiscernibles.** Distinct beliefs have positive distance: $d(b_i, b_j) > 0$ for $b_i \neq b_j$.
- **(A4) Finiteness.** $d(b_i, b_j) < +\infty$ for all $b_i, b_j \in \mathcal{B}$. (This is automatic if $\mathcal{B}$ is defined by bounded reachability from $s_0$.)

**We do not assume:**

- **Symmetry.** $d(b_i, b_j) \neq d(b_j, b_i)$ in general.
- **Metric structure.** $d$ need not satisfy any additional properties beyond (A2)–(A4).
- **Path-independence of $\mathcal{C}$.** The underlying cost function may be path-dependent; only the minimization $d$ is path-independent.
- **A topology.** $\mathcal{B}$ is a bare set. Topologies are induced by $d$ (and by its asymmetry), not assumed.

**Remark 2.37.** The assumptions (A1)–(A4) are minimal. They are satisfied by every information processing system with bounded reachability. The theory developed in this book applies to all such systems.

---

## 2.8 The complex quasi-metric: preview

We close this chapter with a preview of what is to come.

The energy quasi-metric $d$ captures the *cost* of transitions. But cost alone does not capture the full structure of belief space. There is a second quantity, the **debt**, which measures the *asymmetry* of the cost in a precise sense. The debt will be defined in Chapter 3 and developed in Chapters 4–5.

The cost and debt together form a complex object:

$$Q(b_i, b_j) = d(b_i, b_j) + i \cdot D(b_i, b_j),$$

where $D$ is the debt. The modulus $|Q|$ is a metric; the argument $\arg Q$ is a phase. The complex structure is a $\mathbb{Z}/2$-grading, and the gauge group is the group of real-valued functions on $\mathcal{B}$.

This is the central object of the book. Everything else is a consequence.

---

## 2.9 Exercises

**Exercise 2.1.** Let $\mathcal{B}$ be a finite set and let $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$ be a quasi-metric. Show that $d$ induces a weighted directed graph $G_d$ on $\mathcal{B}$ with edge weights $d(b_i, b_j)$. Compute $G_d$ for $\mathcal{B} = \{1, 2, 3\}$ with

$$d = \begin{pmatrix} 0 & 1 & 3 \\ 2 & 0 & 1 \\ 1 & 2 & 0 \end{pmatrix}.$$

**Exercise 2.2.** Show that if $d$ is symmetric, then $G_d$ is an undirected graph (or rather, a directed graph with symmetric edge weights). Give an example of a symmetric quasi-metric that is not a metric.

**Exercise 2.3.** Prove that if $d(b_i, b_j) = 0$ and $d(b_j, b_i) = 0$, then $b_i \sim b_j$ is an equivalence relation. Show that the quotient $\mathcal{B}/{\sim}$ is a metric space.

**Exercise 2.4.** Give an example of an information processing system where the energy quasi-metric is asymmetric but the underlying cost function is symmetric. (Hint: consider path composition.)

**Exercise 2.5.** Let $\mathcal{B}$ be the set of probability distributions on a finite set $\Omega$, and let $d(\mu, \nu) = D_{\mathrm{KL}}(\nu \| \mu)$. Verify that $d$ satisfies (A2)–(A4) but not symmetry.

**Exercise 2.6.** Let $\mathcal{B}$ be a finite set with the energy quasi-metric

$$d = \begin{pmatrix} 0 & 2 & 5 \\ 1 & 0 & 3 \\ 4 & 1 & 0 \end{pmatrix}.$$

Compute the shortest-path metric $d^*$ of the graph $G_d$. Is $d^* = d$? If not, explain why.

**Exercise 2.7.** Show that the energy quasi-metric $d$ is the *largest* quasi-metric on $\mathcal{B}$ satisfying $d(b_i, b_j) \le \mathcal{C}(b_i, b_j)$ for all $(b_i, b_j) \in \mathcal{T}$. (Hint: use the triangle inequality.)

**Exercise 2.8.** Give an example of a belief space $\mathcal{B}$ that is infinite but has finite diameter: $\sup_{b_i, b_j} d(b_i, b_j) < +\infty$.

**Exercise 2.9.** Let $\mathcal{B}$ be a belief space. Show that the relation $b_i \preceq b_j \iff d(b_i, b_j) < +\infty$ is a preorder on $\mathcal{B}$. When is it a partial order?

**Exercise 2.10.** Reflect on the following question: is the energy quasi-metric $d$ a *fundamental* quantity, or is it derived from a deeper structure? Write a short essay (one page) arguing for your position.


---

**End of Chapter 2.**
