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

**Definition 2.8 (Reachability).** A state $s_j$ is *reachable* from a state $s_i$ if there exists at least a path from $s_i$ to $s_j$. The *reachability relation* is the transitive closure of $\mathcal{T}$.

**Definition 2.9 (Bounded reachability).** A state $s_j$ is *reachable from* $s_i$ with budget $B$ if there exists a path from $s_i$ to $s_j$ with cost at most $B$.

**Definition 2.10 (Belief space).** Let $(\mathcal{S}, \mathcal{T}, \mathcal{C})$ be an information processing system and let $s_0 \in \mathcal{S}$ be a distinguished *initial state*. The *belief space* is

$$\mathcal{B} := \lbrace s \in \mathcal{S} : s \text{ is reachable from } s_0 \text{ with finite budget}\rbrace.$$

The elements of $\mathcal{B}$ are called *beliefs*.

**Remark 2.11.** The term "belief" is deliberately broad. A belief may be a probability distribution, a computational configuration, a memory state, or anything else. The theory does not depend on the interpretation. What matters is that $\mathcal{B}$ is a set equipped with a cost function, and that every element is reachable from a common origin.

**Remark 2.12.** The choice of initial state $s_0$ is a gauge choice. Different initial states give different belief spaces, related by translation. The theory is invariant under this choice. This will be made precise in Chapter 4.

**Convention 2.13.** For the remainder of the book, we fix an information processing system, an initial state $s_0$, and the associated belief space $\mathcal{B}$. All constructions are relative to this data. We write $b, b_i, b_j, \dots$ for elements of $\mathcal{B}$.

---

## 2.3 The energy pseudo-quasi-metric

The cost of moving between beliefs extends from paths to pairs by minimization.

**Definition 2.14 (Energy pseudo-quasi-metric).**
The *energy pseudo-quasi-metric* is the function

$$
d:\mathcal{B}\times\mathcal{B}\to\mathbb{R}_{\geq0}\cup\{+\infty\}
$$

defined by

$$
d(b_i,b_j):=\inf_{\gamma:b_i\to b_j}\mathcal{C}(\gamma),
$$

where the infimum is taken over all paths from $b_i$ to $b_j$. If no path exists, we define

$$
d(b_i,b_j):=+\infty.
$$

We assume that path costs are non-negative and subadditive under concatenation:

$$
\mathcal{C}(\gamma_1\cdot\gamma_2)
\leq
\mathcal{C}(\gamma_1)+\mathcal{C}(\gamma_2).
$$

This allows the cost of a composed path to be strictly smaller than the sum of the costs of its constituent paths, for example when the composition produces an efficiency or shared computational cost.

**Proposition 2.15.**
The energy pseudo-quasi-metric satisfies:

* **(i) Identity:** $d(b,b)=0$ for all $b\in\mathcal{B}$.
* **(ii) Non-negativity:** $d(b_i,b_j)\geq0$ for all $b_i,b_j\in\mathcal{B}$.
* **(iii) Triangle inequality:**

$$
d(b_i,b_k)
\leq
d(b_i,b_j)+d(b_j,b_k)
$$

for all $b_i,b_j,b_k\in\mathcal{B}$.

*Proof.*

**(i)** The empty path from $b$ to itself has cost zero. Since all path costs are non-negative,

$$
d(b,b)=0.
$$

**(ii)** Since $\mathcal{C}(\gamma)\geq0$ for every path $\gamma$, its infimum is also non-negative. If no path exists, $d(b_i,b_j)=+\infty$, which also belongs to the extended non-negative real numbers.

**(iii)** Let $\gamma_1:b_i\to b_j$ and $\gamma_2:b_j\to b_k$ be paths. Their concatenation

$$
\gamma_1\cdot\gamma_2:b_i\to b_k
$$

is a path from $b_i$ to $b_k$. By subadditivity of the path cost,

$$
\mathcal{C}(\gamma_1\cdot\gamma_2)
\leq
\mathcal{C}(\gamma_1)+\mathcal{C}(\gamma_2).
$$

Since $d(b_i,b_k)$ is the infimum over all paths from $b_i$ to $b_k$,

$$
d(b_i,b_k)
\leq
\mathcal{C}(\gamma_1\cdot\gamma_2)
\leq
\mathcal{C}(\gamma_1)+\mathcal{C}(\gamma_2).
$$

This holds for every pair of paths $\gamma_1$ and $\gamma_2$. Taking the infimum independently over all paths from $b_i$ to $b_j$ and from $b_j$ to $b_k$ gives

$$
d(b_i,b_k)
\leq
d(b_i,b_j)+d(b_j,b_k).
$$

Therefore, $d$ satisfies the triangle inequality. $\square$


**Remark 2.16.** The triangle inequality for $d$ follows from the definition of $d$ as an infimum over paths together with the subadditivity of $\mathcal{C}$ under concatenation:

$$
\mathcal{C}(\gamma_1\cdot\gamma_2)
\leq
\mathcal{C}(\gamma_1)+\mathcal{C}(\gamma_2).
$$

Thus, the induced energy pseudo-quasi-metric satisfies the triangle inequality by construction. What is not implied by this construction is symmetry. In general,

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

**Remark 2.17.** The terminology "pseudo-quasi-metric" reflects two possible failures of the usual metric structure. The function $d$ need not be symmetric, and distinct states may have zero distance. If $d$ is symmetric, it becomes a pseudometric; if, in addition,

$$
d(b_i,b_j)=0\Longrightarrow b_i=b_j,
$$

then $d$ is a metric.

**Proposition 2.18 (Endpoint dependence of $d$).**
The quantity $d(b_i,b_j)$ depends only on the endpoints $b_i$ and $b_j$, because it is defined as the infimum of the costs of all paths connecting them. In particular, for every path $\gamma:b_i\to b_j$,

$$
d(b_i,b_j)\leq\mathcal{C}(\gamma).
$$

Moreover,

$$
d(b_i,b_j)=\mathcal{C}(\gamma)
$$

if and only if $\gamma$ attains the infimum and is therefore an optimal path.

*Proof.* Immediate from the definition of $d$ as the infimum of the costs of all paths from $b_i$ to $b_j$. $\square$

**Remark 2.19.** The energy pseudo-quasi-metric $d$ is an *emergent* quantity. It is not given independently; it is derived from the underlying path-cost function $\mathcal{C}$ by minimization. The construction converts a path-dependent cost into an endpoint-dependent quantity by retaining only the least-cost path between each pair of states.


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

## 2.5 The Failure of Identity

The energy quasi-metric need not satisfy the identity of indiscernibles.

Recall that the identity of indiscernibles requires

$$
d(b_i,b_j)=0 \quad \Longrightarrow \quad b_i=b_j.
$$

For an energy pseudo-quasi-metric, distinct states may instead be connected by transitions of zero cost.

**Proposition 2.25.** There may exist distinct $b_i,b_j\in\mathcal{B}$ such that

$$
b_i\neq b_j
\qquad\text{and}\qquad
d(b_i,b_j)=0.
$$

*Proof.* Suppose that $(b_i,b_j)\in\mathcal{T}$ is a permitted transition with

$$
\mathcal{C}(b_i,b_j)=0.
$$

Since the direct transition is a path from $b_i$ to $b_j$,

$$
d(b_i,b_j) = \inf_{\gamma:b_i\to b_j}\mathcal{C}(\gamma) \leq \mathcal{C}(b_i,b_j) = 0.
$$

Because $d$ is non-negative,

$$
d(b_i,b_j)=0.
$$

If $b_i\neq b_j$, the identity of indiscernibles fails. $\square$

The important point is that zero cost does not necessarily mean that two states are literally the same state. It means only that, under the chosen cost model, moving between them may require no computational or energetic expenditure.

### Example 2.26 — Computational Equivalence

Let $\mathcal{B}$ be a set of computational configurations.

Suppose that the cost model assigns zero cost to transformations that change the representation of a computation without changing the computation itself. For example, assume that two configurations representing the same computational operation can be transformed into one another at zero cost.

Then distinct configurations $b_i\neq b_j$ may satisfy

$$
d(b_i,b_j)=d(b_j,b_i)=0.
$$

Thus the cost structure cannot distinguish these configurations through energy expenditure alone.

This is not a theorem about computation in general. It is a consequence of the particular cost model being used.

### Example 2.27 — Gauge Equivalence

Let $\mathcal{B}$ be a set of states in a model with a gauge symmetry.

Suppose that gauge-related states are assigned zero transition cost in both directions. If

$$
b_i\neq b_j
$$

but $b_i$ and $b_j$ are related by a gauge transformation, then

$$
d(b_i,b_j)=d(b_j,b_i)=0.
$$

Again, the conclusion depends on the chosen cost model: gauge equivalence does not by itself imply zero computational or energetic cost.

### Remark 2.28

When distinct states can have zero cost in both directions, the original state space contains distinctions that are invisible to the cost structure.

This motivates the relation

$$
b_i\sim b_j
\quad\Longleftrightarrow\quad
d(b_i,b_j)=d(b_j,b_i)=0.
$$

The relation identifies states that are mutually indistinguishable with respect to zero cost.

Under the assumptions that $d(b,b)=0$ and that $d$ satisfies the triangle inequality, $\sim$ is an equivalence relation:

* **Reflexivity:** $d(b,b)=0$.
* **Symmetry:** built into the definition of $\sim$.
* **Transitivity:** if $b_i\sim b_j$ and $b_j\sim b_k$, then

$$
d(b_i,b_k)
\leq
d(b_i,b_j)+d(b_j,b_k)
=0,
$$

and non-negativity gives $d(b_i,b_k)=0$. The reverse direction follows in the same way.

The resulting equivalence classes should not be interpreted automatically as metaphysically "true" states. They are simply the states that the chosen cost structure identifies at zero cost.

### Definition 2.29 — Quotient Belief Space

Let $\sim$ be the equivalence relation defined by

$$
b_i\sim b_j
\quad\Longleftrightarrow\quad
d(b_i,b_j)=d(b_j,b_i)=0.
$$

The **quotient belief space** is

$$
\mathcal{B}/\sim.
$$

An element of $\mathcal{B}/\sim$ is therefore an equivalence class of states that are mutually zero-cost.

### Proposition 2.30 — Induced Quasi-Metric on the Quotient

Let $d$ be an energy pseudo-quasi-metric on $\mathcal{B}$. Then $d$ induces a well-defined quasi-metric $\bar d$ on $\mathcal{B}/\sim$ by

$$
\bar d([b_i],[b_j])=d(b_i,b_j).
$$

Moreover,

$$
\bar d([b_i],[b_j])=0
\quad\Longleftrightarrow\quad
[b_i]=[b_j].
$$

*Proof.*

First we show that the definition is independent of the representatives.

Suppose

$$
b_i\sim b_i'
\qquad\text{and}\qquad
b_j\sim b_j'.
$$

By the triangle inequality,

$$
d(b_i,b_j)
\leq
d(b_i,b_i')
+
d(b_i',b_j')
+
d(b_j',b_j).
$$

Since $b_i\sim b_i'$ and $b_j\sim b_j'$,

$$
d(b_i,b_i')=0
\qquad\text{and}\qquad
d(b_j',b_j)=0.
$$

Therefore,

$$
d(b_i,b_j)\leq d(b_i',b_j').
$$

Interchanging the primed and unprimed representatives gives

$$
d(b_i',b_j')\leq d(b_i,b_j).
$$

Hence

$$
d(b_i,b_j)=d(b_i',b_j').
$$

Thus $\bar d$ is well-defined.

The non-negativity and triangle inequality of $\bar d$ are inherited directly from $d$.

Finally, suppose

$$
\bar d([b_i],[b_j])=0.
$$

Then

$$
d(b_i,b_j)=0.
$$

Because $\bar d$ is a quasi-metric on equivalence classes, the corresponding reverse distance is also zero exactly when the two classes are equivalent. By the definition of $\sim$,

$$
d(b_i,b_j)=d(b_j,b_i)=0
\quad\Longleftrightarrow\quad
[b_i]=[b_j].
$$

Therefore the identity of indiscernibles holds on the quotient. $\square$

### Convention 2.31

For the remainder of the book, we work on the quotient whenever zero-cost equivalence is present.

Thus, when necessary, $\mathcal{B}$ is understood to mean

$$
\mathcal{B}/\sim.
$$

This removes distinctions that are invisible to the bidirectional zero-cost structure and allows the resulting quasi-metric to satisfy the identity of indiscernibles.


---

## 2.6 The Energy Quasi-Metric as a Directed Graph

The energy quasi-metric has a natural representation as a weighted directed graph.

The connection is important because the graph makes the directional and compositional structure of energy cost explicit. A transition from $b_i$ to $b_j$ need not have the same cost as the reverse transition, and some states may not be reachable from one another at all.

**Construction 2.32.** Let $\mathcal{B}$ be a belief space equipped with an energy quasi-metric

$$
d:\mathcal{B}\times\mathcal{B}\rightarrow\mathbb{R}_{\geq 0}\cup\{+\infty\}.
$$

Define a weighted directed graph $G_d$ by:

* Vertex set $\mathcal{B}$;
* Directed edge $(b_i,b_j)$ whenever $d(b_i,b_j)<+\infty$;
* Edge weight $d(b_i,b_j)$.

Thus, every finite value of the quasi-metric is represented by a directed edge.

### Proposition 2.33 — Graph Representation

The energy quasi-metric $d$ is equal to the shortest-path distance induced by the weighted directed graph $G_d$.

More precisely,

$$ 
d(b_i,b_j) = \inf_{\gamma:b_i\to b_j} \mathcal{C}_{G_d}(\gamma),
$$

where $\mathcal{C}_{G_d}(\gamma)$ is the sum of the edge weights along the path $\gamma$.

*Proof.*

Consider first a pair $(b_i,b_j)$ for which

$$
d(b_i,b_j)<+\infty.
$$

By construction, $G_d$ contains the direct edge

$$
b_i\rightarrow b_j
$$

with weight $d(b_i,b_j)$. Therefore the shortest-path distance satisfies

$$
d_{G_d}(b_i,b_j)\leq d(b_i,b_j).
$$

Now consider any path

$$
b_i=b_0\rightarrow b_1\rightarrow\cdots\rightarrow b_n=b_j.
$$

Its total cost is

$$
\sum_{k=0}^{n-1}d(b_k,b_{k+1}).
$$

Repeated application of the triangle inequality gives

$$
d(b_i,b_j)
\leq
\sum_{k=0}^{n-1}d(b_k,b_{k+1}).
$$

Since this holds for every path from $b_i$ to $b_j$,

$$
d(b_i,b_j)\leq d_{G_d}(b_i,b_j).
$$

Combining the two inequalities,

$$
d_{G_d}(b_i,b_j)=d(b_i,b_j).
$$

If no path exists, both quantities are $+\infty$.

Therefore $d$ is exactly the shortest-path distance induced by $G_d$. $\square$

### Remark 2.34

The graph $G_d$ provides a canonical **representation** of the energy quasi-metric.

It is not, however, a unique representation: different weighted directed graphs can have the same shortest-path distance.

The important correspondence is therefore not a one-to-one equivalence between graphs and quasi-metrics. Rather, a weighted directed graph generates an energy quasi-metric through shortest-path minimization, while an energy quasi-metric can itself be represented by a weighted directed graph.

This gives two complementary viewpoints:

$$
\text{local transitions}
\longrightarrow
\text{weighted directed graph}
\longrightarrow
\text{shortest-path cost}.
$$

and

$$
\text{energy quasi-metric}
\longrightarrow
\text{canonical graph representation}.
$$

### Proposition 2.35 — Graphs Induce Energy Pseudo-Quasi-Metrics

Let $G=(V,E,w)$ be a directed graph with non-negative edge weights.

Define

$$
d_G(b_i,b_j) = \inf_{\gamma:b_i\to b_j} \mathcal{C}(\gamma),
$$

where $\mathcal{C}(\gamma)$ is the sum of the edge weights along $\gamma$, and set

$$
d_G(b_i,b_j)=+\infty
$$

when no path from $b_i$ to $b_j$ exists.

Then $d_G$ is an energy pseudo-quasi-metric on $V$.

*Proof.*

Non-negativity follows from the non-negative edge weights.

The empty path gives

$$
d_G(b_i,b_i)=0.
$$

For any paths $\gamma_1:b_i\to b_j$ and $\gamma_2:b_j\to b_k$, their concatenation is a path from $b_i$ to $b_k$ with cost

$$
\mathcal{C}(\gamma_1\cdot\gamma_2) = \mathcal{C}(\gamma_1)+\mathcal{C}(\gamma_2).
$$

Therefore,

$$
d_G(b_i,b_k)
\leq
d_G(b_i,b_j)+d_G(b_j,b_k).
$$

Thus the triangle inequality holds.

Symmetry is not required, since the graph is directed. Identity of indiscernibles may also fail when distinct vertices can be connected by paths of zero total cost.

Hence $d_G$ is an energy pseudo-quasi-metric. $\square$

### Example 2.36 — Complete Directed Graph

Suppose

$$
d(b_i,b_j)<+\infty
$$

for every pair $b_i,b_j\in\mathcal{B}$.

Then $G_d$ is a complete directed graph.

Every pair of vertices has a direct edge whose weight is

$$
d(b_i,b_j).
$$

The triangle inequality guarantees that no indirect path can have lower cost:

$$
d(b_i,b_j)
\leq
d(b_i,b_k)+d(b_k,b_j).
$$

Therefore the shortest-path distance is exactly the original edge weight:

$$
d_{G_d}(b_i,b_j)=d(b_i,b_j).
$$

### Example 2.37 — Sparse Directed Graph

Suppose that

$$
d(b_i,b_j)=+\infty
$$

for many pairs of states.

Then many directed edges are absent from $G_d$.

A state $b_j$ may nevertheless be reachable from $b_i$ through intermediate states:

$$
b_i\rightarrow b_k\rightarrow b_j.
$$

In this case,

$$
d(b_i,b_j)
\leq
d(b_i,b_k)+d(b_k,b_j).
$$

The cost between the two states therefore depends on path composition.

If no path exists at all, then

$$
d(b_i,b_j)=+\infty.
$$

The sparse case makes the reachability structure of the belief space explicit: finite energy cost corresponds to reachability, while infinite cost corresponds to the absence of a path.

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



