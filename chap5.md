# Chapter 5: Cohomology & Minimality

---

In Chapter 3, we introduced the debt function $D$ through two axioms:

- **(D1) Additivity**
$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

- **(D2) Antisymmetry**
$$D(b_i, b_j) = -D(b_j, b_i).$$

In Chapter 4, we showed that these axioms imply a stronger structural result: every debt function can be written as the difference of a potential,

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

The basepoint construction gives the potential explicitly.

This raises a new question:

> **Are both axioms actually necessary?**

There is also a second question.

The exactness result of Chapter 4 assumes that the debt function is defined on every ordered pair of states. What happens if some transitions are unavailable?

These questions lead naturally to two different mathematical ideas:

1. **minimality** — determining which axioms are logically independent;
2. **cohomology** — understanding what prevents a locally consistent debt function from being globally representable by a potential.

The distinction is important.

On a complete state space, the situation is exceptionally rigid. On a sparse graph, nontrivial cycles can appear, and the global structure becomes richer.

---

## 5.1 Logical minimality

We begin with the simplest question.

Suppose

$$D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$$

satisfies the additivity axiom

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$$

for every $b_i, b_j, b_k \in \mathcal{B}$.

Do we need to separately assume antisymmetry?

The answer is no. Antisymmetry follows from additivity.

This does **not** mean that (D2) should be removed from our conceptual framework. It means that (D2) is logically redundant once (D1) is assumed globally.

---

## 5.2 Additivity implies identity and antisymmetry

We first recover the identity property.

### Proposition 5.1 (Additivity implies zero self-debt)

Suppose $D$ satisfies (D1) for every triple of states. Then

$$D(b, b) = 0$$

for every $b \in \mathcal{B}$.

*Proof.* Set $b_i = b_j = b$ in (D1). Then

$$D(b, b_k) = D(b, b) + D(b, b_k).$$

Subtracting $D(b, b_k)$ from both sides gives

$$D(b, b) = 0. \quad \square$$

So the identity property does not need to be introduced independently either.

We can now derive (D2).

### Proposition 5.2 (Additivity implies antisymmetry)

Suppose $D$ satisfies (D1) for every triple of states. Then

$$D(b_i, b_j) = -D(b_j, b_i).$$

*Proof.* Set $b_k = b_i$ in (D1). Then

$$D(b_i, b_i) = D(b_i, b_j) + D(b_j, b_i).$$

By Proposition 5.1, $D(b_i, b_i) = 0$. Therefore,

$$0 = D(b_i, b_j) + D(b_j, b_i),$$

and hence

$$D(b_i, b_j) = -D(b_j, b_i). \quad \square$$

Thus (D1) already contains the information expressed separately by (D2).

---

## 5.3 The minimality theorem

The previous propositions give the following theorem.

### Theorem 5.3 (Additivity alone is sufficient)

Let $\mathcal{B}$ be a nonempty set and let $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$. If $D$ satisfies

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$$

for every $b_i, b_j, b_k \in \mathcal{B}$, then:

1. $D(b, b) = 0$ for every $b \in \mathcal{B}$;
2. $D(b_i, b_j) = -D(b_j, b_i)$;
3. every closed path has zero total debt;
4. $D$ is representable as

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)$$

for some potential $\psi : \mathcal{B} \to \mathbb{R}$.

*Proof.* Parts 1 and 2 follow from Propositions 5.1 and 5.2.

For part 3, let $b_0, b_1, \ldots, b_n$ be a closed path with $b_n = b_0$. Repeated application of (D1) gives

$$D(b_0, b_n) = \sum_{k=0}^{n-1} D(b_k, b_{k+1}).$$

Since $b_n = b_0$,

$$D(b_0, b_n) = D(b_0, b_0) = 0.$$

Therefore,

$$\sum_{k=0}^{n-1} D(b_k, b_{k+1}) = 0.$$

Finally, by Chapter 4, the basepoint construction gives a potential $\psi$ satisfying

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i). \quad \square$$

---

## 5.4 Why keep two axioms?

If (D1) logically implies (D2), why did we introduce both?

Because **logical minimality and conceptual decomposition are different things**.

The two axioms express different interpretations:

- (D1) describes how debt accumulates along successive transitions.
- (D2) describes reversal of a transition.
- (D1) says debt is compositional.
- (D2) says reversing direction changes the sign.

Keeping both axioms therefore makes the intended structure visible.

We can distinguish two statements:

> **Conceptual formulation:** debt satisfies additivity and antisymmetry.

and

> **Minimal logical formulation:** global additivity alone is sufficient.

There is no contradiction between these statements. The first describes the structure we want to study. The second describes the logical redundancy inside that structure.

We retain (D2) as a separate axiom because it makes the reversal structure explicit. The fact that it is logically derivable from (D1) is a theorem, not a reason to omit it.

---

## 5.5 Debt as a discrete differential

Chapter 4 showed that

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

This suggests a useful interpretation.

The potential $\psi$ assigns a scalar quantity to each state. The debt function records the difference between two states. We may therefore think of $D$ as a **discrete differential** of $\psi$. Symbolically,

$$D = \delta\psi,$$

where $\delta$ denotes the operation that converts a potential into pairwise differences:

$$(\delta\psi)(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

The notation is useful because it separates two objects:

- $\psi$ lives on states;
- $D$ lives on transitions between states.

The debt function therefore contains information about **changes**, while the potential contains information about **levels**.

**Remark 5.4.** The term "discrete differential" is an analogy, not a literal identification. The operator $\delta$ is a difference operator, not a derivative. There is no limiting process involved. The analogy is useful because it suggests the right algebraic structure—a cochain complex—but it should not be taken to imply that the discrete theory is a special case of the continuous one.

---

## 5.6 Gauge freedom and the kernel of $\delta$

Suppose $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Let $c \in \mathbb{R}$ and define $\widetilde{\psi}(b) = \psi(b) + c$. Then

$$\widetilde{\psi}(b_j) - \widetilde{\psi}(b_i) = (\psi(b_j) + c) - (\psi(b_i) + c) = \psi(b_j) - \psi(b_i).$$

Hence

$$\delta(\psi + c) = \delta\psi.$$

The constant is invisible to the debt function. This is the gauge freedom already encountered in Chapter 4.

More generally, consider the operator $\delta : \psi \mapsto D$ defined by $(\delta\psi)(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Suppose $\delta\psi = 0$. Then $\psi(b_j) - \psi(b_i) = 0$ for every pair of states, so $\psi(b_i) = \psi(b_j)$ for every $b_i, b_j \in \mathcal{B}$. If $\mathcal{B}$ is nonempty, $\psi$ must be constant. Thus

$$\boxed{\ker \delta = \lbrace \text{constant functions} \rbrace.}$$

This explains mathematically why potentials are unique only up to an additive constant.

**Remark 5.5 (Finite state spaces).** Suppose $\mathcal{B} = \{b_1, \ldots, b_n\}$. A potential is determined by the $n$ values $\psi(b_1), \ldots, \psi(b_n)$. But adding the same constant to all of them does not change the debt. Therefore, only $n - 1$ independent quantities remain. For example, we may impose the normalization $\psi(b_1) = 0$, in which case $\psi(b_i) = D(b_1, b_i)$ for every $i$. The potential is completely determined. This gives the dimension count $n - 1$ for the space of potentials modulo constants.

---

## 5.7 The complete state space

There is an important reason why the theory becomes so simple when $D$ is defined on every pair.

Consider the complete directed graph associated with $\mathcal{B}$. Every pair of states has a directed transition. Therefore, every triple $(b_i, b_j, b_k)$ can be tested against the additivity relation

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

This condition is extremely strong. It forces every two-step path from $b_i$ to $b_k$ to have exactly the same debt as the direct transition. In particular, the entire pairwise structure is determined by a single potential. This is the rigid case.

Now suppose not every transition exists. Let $G = (V, E)$ be a directed graph, and let the debt function be defined only on available edges: $D : E \to \mathbb{R}$. For an edge $e = (u, v)$, we write its debt as $D(u, v)$.

The expression $D(u, v) + D(v, w)$ only makes sense as a path debt when the corresponding edges exist. More importantly, there may be no direct edge from $u$ to $w$. Therefore, the global equation $D(u, w) = D(u, v) + D(v, w)$ cannot always be imposed. This changes the mathematical problem.

---

## 5.8 Path debt on a directed graph

Let $\gamma = (b_0, b_1, \ldots, b_n)$ be a directed path. Define its debt by

$$D(\gamma) = \sum_{k=0}^{n-1} D(b_k, b_{k+1}).$$

A potential representation would require $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ on every available edge. Then every path would satisfy

$$D(\gamma) = \psi(b_n) - \psi(b_0).$$

Therefore, if two paths connect the same states, they must have the same total debt. This gives a practical criterion for exactness.

Consider a closed directed path $\gamma = (b_0, b_1, \ldots, b_n)$ with $b_n = b_0$. If $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$, then

$$D(\gamma) = \psi(b_n) - \psi(b_0) = 0.$$

Therefore, every exact debt function must satisfy

$$\boxed{D(\gamma) = 0}$$

for every closed path. This condition is necessary. Under appropriate graph assumptions, it is also sufficient.

The important idea is:

> **Nonzero debt around a closed loop is an obstruction to global exactness.**

**Example 5.6 (A simple cycle).** Consider three states $b_1, b_2, b_3$ with directed edges

$$b_1 \to b_2, \qquad b_2 \to b_3, \qquad b_3 \to b_1.$$

Suppose

$$D(b_1, b_2) = 1, \qquad D(b_2, b_3) = 2, \qquad D(b_3, b_1) = 1.$$

The debt around the cycle is $1 + 2 + 1 = 4$. Therefore, $D(\gamma) = 4 \neq 0$. No potential $\psi$ can satisfy $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ on all three edges.

Indeed, the first two edges would require

$$\psi(b_2) - \psi(b_1) = 1, \qquad \psi(b_3) - \psi(b_2) = 2.$$

Adding gives $\psi(b_3) - \psi(b_1) = 3$. But the third edge requires $\psi(b_1) - \psi(b_3) = 1$, which implies $\psi(b_3) - \psi(b_1) = -1$. The two requirements contradict one another. The cycle carries a genuine obstruction.

---

## 5.9 Exact and non-exact debt

We can now distinguish two cases.

**Exact debt.** A debt function is exact if there exists a potential $\psi$ such that $D(u, v) = \psi(v) - \psi(u)$ for every relevant transition. Then every closed path has zero total debt.

**Non-exact debt.** A debt function is non-exact if no such global potential exists. A nonzero closed-loop debt provides a concrete obstruction: $D(\gamma) \neq 0$.

The distinction is important because local transition values need not always come from a global scalar potential.

---

## 5.10 The cohomological framework

The language of cohomology provides a systematic way to organize this distinction. We now give a precise definition for the case of a directed graph.

Let $G = (V, E)$ be a directed graph.

- A **0-cochain** is a function $\psi : V \to \mathbb{R}$.
- A **1-cochain** is a function $D : E \to \mathbb{R}$.
- The **coboundary operator** $\delta$ takes a 0-cochain $\psi$ to the 1-cochain $\delta\psi$ defined by
$$(\delta\psi)(u, v) := \psi(v) - \psi(u).$$
- A 1-cochain $D$ is a **1-cocycle** if
$$\sum_{e \in \gamma} D(e) = 0$$
for every closed directed path $\gamma$ in $G$.
- A 1-cochain $D$ is a **1-coboundary** if $D = \delta\psi$ for some 0-cochain $\psi$.

The **first cohomology group** of $G$ with coefficients in $\mathbb{R}$ is

$$H^1(G; \mathbb{R}) := \frac{\lbrace \text{1-cocycles} \rbrace}{\lbrace \text{1-coboundaries} \rbrace}.$$

The interpretation is:

> $H^1(G; \mathbb{R})$ measures the obstruction to representing a consistent transition quantity globally as a potential difference.

If $H^1(G; \mathbb{R}) = 0$, then every 1-cocycle is a 1-coboundary: every debt function with zero debt around every closed path is exact. If $H^1(G; \mathbb{R}) \neq 0$, then there exist closed 1-cochains that cannot be represented globally by a single potential.

This gives a mathematical language for the distinction between **local consistency** and **global exactness**.

**Example 5.7 ($H^1$ of the triangle).** Let $G$ be the directed triangle with vertices $b_1, b_2, b_3$ and edges

$$b_1 \to b_2, \qquad b_2 \to b_3, \qquad b_3 \to b_1.$$

A 1-cochain $D$ on $G$ is a triple $(D_{12}, D_{23}, D_{31}) \in \mathbb{R}^3$. The cocycle condition is

$$D_{12} + D_{23} + D_{31} = 0.$$

This is one linear equation in three variables, so the space of 1-cocycles is 2-dimensional. A 1-coboundary is a triple of the form

$$(\psi_2 - \psi_1, \psi_3 - \psi_2, \psi_1 - \psi_3)$$

for some $(\psi_1, \psi_2, \psi_3) \in \mathbb{R}^3$. The space of 1-coboundaries is the image of the map $\delta : \mathbb{R}^3 \to \mathbb{R}^3$, which has rank 2 (the kernel is the constant functions, dimension 1). Therefore, the space of 1-coboundaries is 2-dimensional, and

$$H^1(G; \mathbb{R}) = \frac{\text{2-dimensional}}{\text{2-dimensional}} = 0.$$

This is consistent with the fact that on the triangle, every 1-cocycle is exact. The obstruction in Example 5.6 was not a cohomological obstruction in the sense of $H^1$; it was a failure of the cocycle condition itself. The cycle had nonzero debt, so the 1-cochain was not a cocycle.

**Remark 5.8.** The example above shows that $H^1$ is not the only relevant invariant. The space of 1-cocycles may be nontrivial, but if every 1-cocycle is a 1-coboundary, then $H^1 = 0$ and exactness holds for all cocycles. The obstruction to exactness for a *specific* 1-cochain is whether that cochain is a cocycle. The cohomology group $H^1$ measures the obstruction that remains *after* imposing the cocycle condition.

**Example 5.9 ($H^1 \neq 0$).** Consider a directed graph with two vertices $u, v$ and two parallel edges $e_1, e_2$ from $u$ to $v$, but no edge from $v$ to $u$. A 1-cochain assigns a real number to each edge: $(D_1, D_2)$. A closed path must return to its starting point, but since there is no edge from $v$ to $u$, the only closed paths are trivial (length 0). Therefore, every 1-cochain is a 1-cocycle (vacuously). A 1-coboundary is a pair $(\psi(v) - \psi(u), \psi(v) - \psi(u))$ with both components equal. Therefore, the space of 1-coboundaries is 1-dimensional, while the space of 1-cocycles is 2-dimensional, and

$$H^1(G; \mathbb{R}) \cong \mathbb{R}.$$

This is the simplest example where $H^1 \neq 0$. The obstruction is the "parallel edge" structure: two edges between the same vertices can carry different debts, and no potential can account for both.

---

## 5.11 Exactness on sparse graphs

We now prove the graph analogue of the basepoint theorem.

**Theorem 5.10 (Exactness on strongly connected graphs).** Let $G = (V, E)$ be a strongly connected directed graph, and let $D : E \to \mathbb{R}$ be a 1-cochain. Suppose:

1. **Antisymmetry on edges:** if $(u, v) \in E$ and $(v, u) \in E$, then $D(v, u) = -D(u, v)$.
2. **Zero debt around every closed path:** for every closed directed path $\gamma$ in $G$,
$$\sum_{e \in \gamma} D(e) = 0.$$

Then there exists a potential $\psi : V \to \mathbb{R}$ such that

$$D(u, v) = \psi(v) - \psi(u)$$

for every edge $(u, v) \in E$.

*Proof.* Choose a basepoint $s_0 \in V$. Since $G$ is strongly connected, for every $v \in V$ there exists a directed path from $s_0$ to $v$. Define

$$\psi(v) := D(\gamma_{s_0 \to v}),$$

where $\gamma_{s_0 \to v}$ is any directed path from $s_0$ to $v$.

We first show that $\psi$ is well-defined, i.e., that the value does not depend on the choice of path. Let $\gamma_1$ and $\gamma_2$ be two paths from $s_0$ to $v$. We must show $D(\gamma_1) = D(\gamma_2)$.

Since $G$ is strongly connected, there exists a path $\gamma_2^{-1}$ from $v$ to $s_0$ (not necessarily the reverse of $\gamma_2$). Consider the closed path $\gamma_1 \cdot \gamma_2^{-1}$. By assumption 2,

$$D(\gamma_1 \cdot \gamma_2^{-1}) = 0.$$

By additivity along paths,

$$D(\gamma_1 \cdot \gamma_2^{-1}) = D(\gamma_1) + D(\gamma_2^{-1}).$$

Therefore, $D(\gamma_1) = -D(\gamma_2^{-1})$. Similarly, consider the closed path $\gamma_2 \cdot \gamma_2^{-1}$, which gives $D(\gamma_2) = -D(\gamma_2^{-1})$. Hence $D(\gamma_1) = D(\gamma_2)$. This shows that $\psi$ is well-defined.

Now let $(u, v) \in E$. We must show $D(u, v) = \psi(v) - \psi(u)$. Choose a path $\gamma_{s_0 \to u}$ from $s_0$ to $u$. Then $\gamma_{s_0 \to u} \cdot (u, v)$ is a path from $s_0$ to $v$. By definition of $\psi$,

$$\psi(v) = D(\gamma_{s_0 \to u} \cdot (u, v)) = D(\gamma_{s_0 \to u}) + D(u, v) = \psi(u) + D(u, v).$$

Therefore, $D(u, v) = \psi(v) - \psi(u)$. $\square$

**Remark 5.11.** The proof uses strong connectivity to ensure that every state is reachable from $s_0$ and that a path from $v$ back to $s_0$ always exists. Without strong connectivity, the construction may fail for states not reachable from $s_0$, and the well-definedness argument requires modification.

**Remark 5.12.** In the case where the graph is not strongly connected, we can still apply the theorem to each strongly connected component separately, obtaining a potential on each component. The potentials on different components are independent, so the uniqueness is up to a constant *on each component*, not a single global constant.

**Corollary 5.13.** On a strongly connected directed graph, every 1-cocycle is a 1-coboundary. That is,

$$H^1(G; \mathbb{R}) = 0.$$

*Proof.* A 1-cocycle is a 1-cochain satisfying the zero-debt-around-closed-paths condition. By Theorem 5.10, such a cochain is a 1-coboundary. $\square$

**Remark 5.14.** Corollary 5.13 is a discrete analogue of the Poincaré lemma: on a simply connected space, every closed 1-form is exact. The role of simple connectivity is played here by strong connectivity of the directed graph, combined with the cocycle condition.

---

## 5.12 The main structural picture

We can now summarize the mathematical hierarchy.

For a complete pairwise debt function:

$$\boxed{\text{Additivity} \Longrightarrow \text{Antisymmetry} \Longrightarrow \text{Exactness}}$$

More precisely, additivity alone implies antisymmetry, and together with the complete domain it yields the potential representation.

For a restricted graph, the picture becomes:

$$\boxed{\text{edge data} \longrightarrow \text{path sums} \longrightarrow \text{closed-loop constraints} \longrightarrow \text{exactness or obstruction}}$$

The obstruction is what cohomology is designed to organize.

**Remark 5.15 (Logical vs. structural minimality).** At this point we should distinguish two kinds of minimality.

**Logical minimality** asks: which axioms are sufficient to derive the desired properties? For the complete pairwise debt function, (D1) alone is sufficient; (D2) follows from (D1).

**Structural minimality** asks: what is the smallest set of conditions needed for exactness on a restricted graph? This is a different question. On a sparse graph, the answer depends on which edges exist, which paths exist, which cycles exist, whether the graph is strongly connected, and what cochain structure is being used. Therefore, the sparse-graph problem cannot simply be reduced to the complete-space result.

---

## 5.13 What we have learned

The debt function has two complementary descriptions.

**Algebraic description.** Debt satisfies the composition law

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

**Potential description.** Debt is generated by a scalar potential:

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

The first description emphasizes transitions. The second emphasizes states. The basepoint theorem establishes their equivalence in the complete pairwise setting.

---

## 5.14 Summary

The main results of this chapter are:

1. Additivity implies zero self-debt: $D(b, b) = 0$.
2. Additivity implies antisymmetry: $D(b_i, b_j) = -D(b_j, b_i)$.
3. Therefore, (D2) is logically redundant when (D1) holds globally.
4. We nevertheless retain (D1) and (D2) as conceptual axioms because they describe different structural meanings.
5. The potential-to-debt map is $(\delta\psi)(b_i, b_j) = \psi(b_j) - \psi(b_i)$.
6. Potentials are unique up to an additive constant.
7. Exact debt has zero total debt around every closed path.
8. Exact debt is path independent.
9. On a finite state space with $n$ states, exact debt is determined by $n - 1$ independent potential differences.
10. Sparse directed graphs require a separate treatment because not every pairwise relation exists.
11. Nonzero debt around a closed loop is an obstruction to a global potential.
12. On a strongly connected directed graph, every 1-cocycle is a 1-coboundary: $H^1(G; \mathbb{R}) = 0$.
13. Cohomology provides a natural language for studying the difference between closed and exact structures.

The central idea can be summarized as

$$\boxed{\text{Debt} = \text{Potential Difference}}$$

in the complete setting, while in more general transition structures the question becomes whether such a global potential exists at all.

---

## 5.15 Exercises

**Exercise 5.1 — Redundancy of antisymmetry.** Suppose $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$ for every triple of states. Prove directly that $D(b_i, b_j) = -D(b_j, b_i)$. Do not assume antisymmetry during the proof.

**Exercise 5.2 — Zero self-debt.** Using only (D1), prove that $D(b, b) = 0$. Explain why this means that zero self-debt does not need to be introduced as a separate axiom.

**Exercise 5.3 — Potential construction.** Let $\mathcal{B} = \{b_1, b_2, b_3, b_4\}$ and suppose $D(b_1, b_2) = 2$, $D(b_1, b_3) = 5$, $D(b_1, b_4) = 1$. Construct a potential $\psi$ using $b_1$ as the basepoint. Then compute $D(b_2, b_3)$, $D(b_2, b_4)$, and $D(b_3, b_4)$.

**Exercise 5.4 — Gauge freedom.** Suppose $\psi(b_1) = 0$, $\psi(b_2) = 3$, $\psi(b_3) = 7$. Define $\widetilde{\psi}(b) = \psi(b) + 10$. Verify that $\psi$ and $\widetilde{\psi}$ generate exactly the same debt function.

**Exercise 5.5 — Zero cycle debt.** Consider $b_1 \to b_2 \to b_3 \to b_1$ with $D(b_1, b_2) = 2$, $D(b_2, b_3) = -1$, and $D(b_3, b_1) = -1$. Compute the total debt around the cycle. Construct a potential $\psi$ that generates these edge values.

**Exercise 5.6 — Nonzero cycle debt.** Consider the same graph but let $D(b_1, b_2) = 2$, $D(b_2, b_3) = 1$, and $D(b_3, b_1) = 1$. Show that no potential $\psi$ can generate these three edge values.

**Exercise 5.7 — Path independence.** Let $G$ be a strongly connected directed graph, and suppose every closed path has zero total debt. Let $\gamma_1$ and $\gamma_2$ be two directed paths from $b_i$ to $b_j$. Show that $D(\gamma_1) = D(\gamma_2)$. Be explicit about how strong connectivity is used to construct a closed path from $\gamma_1$ and $\gamma_2$.

**Exercise 5.8 — Reconstructing a potential.** Let $G$ be a strongly connected directed graph with a debt value assigned to every edge. Choose a reference state $s_0$. Assume every closed path has zero total debt. Define $\psi(b) = D(\gamma_{s_0 \to b})$. Explain why this definition does not depend on the chosen path.

**Exercise 5.9 — Dimension count.** Let $\mathcal{B} = \{b_1, \ldots, b_n\}$. Explain why potentials form an $n$-dimensional vector space, while potentials modulo additive constants have dimension $n - 1$.

**Exercise 5.10 — Complete debt matrix.** Let $\psi = (0, 2, 5, 9)$. Construct the complete debt matrix $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Verify:

1. $D(b_i, b_i) = 0$;
2. $D(b_i, b_j) = -D(b_j, b_i)$;
3. (D1) holds.

**Exercise 5.11 — Sparse graph.** Consider a graph with states $\mathcal{B} = \{b_1, b_2, b_3\}$ and edges $b_1 \to b_2$, $b_2 \to b_3$. There is no edge from $b_1$ to $b_3$. Explain why the equation $D(b_1, b_3) = D(b_1, b_2) + D(b_2, b_3)$ cannot automatically be treated as an equality between three edge values. What additional structure would be needed to define the left-hand side?

**Exercise 5.12 — Cohomology of the triangle.** Let $G$ be the directed triangle with vertices $b_1, b_2, b_3$ and edges $b_1 \to b_2$, $b_2 \to b_3$, $b_3 \to b_1$. Compute $H^1(G; \mathbb{R})$ explicitly. Show that every 1-cocycle is a 1-coboundary.

**Exercise 5.13 — Cohomology with parallel edges.** Consider a directed graph with two vertices $u, v$ and two parallel edges $e_1, e_2$ from $u$ to $v$, but no edge from $v$ to $u$. Compute $H^1(G; \mathbb{R})$ explicitly. Give an example of a 1-cocycle that is not a 1-coboundary.

**Exercise 5.14 — Conceptual question.** We have shown that $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Does this mean that the potential $\psi$ is more fundamental than the debt $D$? Give arguments for both interpretations. The theorem establishes a mathematical representation, but it does not by itself determine which object should be regarded as conceptually primary.
