# Chapter 3: The Debt Function

---

## 3.1 The asymmetry of cost

Chapter 2 established the energy quasi-metric $d$ as the cost of moving between states of the belief space. Because $d$ is a quasi-metric, it need not be symmetric. In general,

$$d(b_i, b_j) \neq d(b_j, b_i).$$

This asymmetry is not an error in the construction. It records the fact that moving from $b_i$ to $b_j$ may have a different cost from moving in the opposite direction.

**Observation 3.1.** There may exist $b_i, b_j \in \mathcal{B}$ such that

$$d(b_i, b_j) \neq d(b_j, b_i).$$

The first task of this chapter is therefore to isolate the asymmetric part of the energy quasi-metric.

**Definition 3.2 (Symmetric and antisymmetric parts).** Assume that $d(b_i, b_j) < +\infty$ for all $b_i, b_j \in \mathcal{B}$. Define

$$S(b_i, b_j) := \tfrac{1}{2}\left(d(b_i, b_j) + d(b_j, b_i)\right)$$

and

$$A(b_i, b_j) := \tfrac{1}{2}\left(d(b_i, b_j) - d(b_j, b_i)\right).$$

We call $S$ the **symmetric part** of the cost and $A$ the **antisymmetric part** of the cost.

The function $A$ measures the directional imbalance of the cost. It is positive when the transition from $b_i$ to $b_j$ is more expensive than the reverse transition, negative when it is cheaper, and zero when the two directions have equal cost.

**Proposition 3.3.** The antisymmetric part $A$ satisfies:

1. $A(b_i, b_j) = -A(b_j, b_i)$;
2. $A(b, b) = 0$;
3. $A(b_i, b_j) > 0$ if and only if $d(b_i, b_j) > d(b_j, b_i)$;
4. $|A(b_i, b_j)| \le \tfrac{1}{2}\left(d(b_i, b_j) + d(b_j, b_i)\right)$.

*Proof.*

For antisymmetry,

$$A(b_j, b_i) = \tfrac{1}{2}\left(d(b_j, b_i) - d(b_i, b_j)\right) = -A(b_i, b_j).$$

On the diagonal,

$$A(b, b) = \tfrac{1}{2}\left(d(b, b) - d(b, b)\right) = 0.$$

The sign property follows directly from the definition. Finally,

$$|A(b_i, b_j)| = \tfrac{1}{2}\left|d(b_i, b_j) - d(b_j, b_i)\right| \le \tfrac{1}{2}\left(d(b_i, b_j) + d(b_j, b_i)\right). \quad \square$$

The symmetric and antisymmetric parts reconstruct the original cost.

**Proposition 3.4 (Canonical decomposition).** The energy quasi-metric admits the decomposition

$$d = S + A,$$

where $S$ is symmetric and $A$ is antisymmetric. This decomposition is unique.

*Proof.*

By definition,

$$S(b_i, b_j) + A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i)) + \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i)) = d(b_i, b_j).$$

The function $S$ is symmetric and $A$ is antisymmetric by construction.

For uniqueness, suppose $d = S' + A'$, where $S'$ is symmetric and $A'$ is antisymmetric. Evaluating the same equation with $b_i$ and $b_j$ exchanged gives $d(b_j, b_i) = S'(b_i, b_j) - A'(b_i, b_j)$. Adding and subtracting the two equations yields $S' = S$ and $A' = A$. $\square$

**Remark 3.5.** The antisymmetric component $A$ should not be identified with the debt function introduced in this chapter. $A$ is determined directly by the asymmetry of the energy quasi-metric. Debt is a separate object whose mathematical structure will be introduced independently.

The distinction is important. Asymmetry tells us that the cost of a transition depends on its direction. It does not, by itself, tell us whether the directional quantity satisfies additional structural properties such as additivity or path independence.

The purpose of the following sections is to investigate this additional structure.

---

## 3.2 The debt function: definition

We now introduce the central object of the chapter.

**Definition 3.6 (Debt function).** Let $\mathcal{B}$ be a belief space. A **debt function** is a function

$$D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$$

satisfying:

- **(D1) Additivity.**
$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$$
for all $b_i, b_j, b_k \in \mathcal{B}$.

- **(D2) Antisymmetry.**
$$D(b_i, b_j) = -D(b_j, b_i)$$
for all $b_i, b_j \in \mathcal{B}$.

These are the only axioms. Everything else in this chapter will be derived from them.

**Remark 3.7.** The axioms (D1) and (D2) are satisfied by every potential difference. If $\psi : \mathcal{B} \to \mathbb{R}$ is any function and

$$D(b_i, b_j) := \psi(b_j) - \psi(b_i),$$

then $D$ satisfies both axioms.

The converse—that every debt function arises from such a potential—is the subject of Chapter 4.

**Remark 3.8.** The debt function is not the same as the asymmetry $A$.

The asymmetry $A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i))$ measures directional imbalance in the cost.

Debt is a separate function satisfying the stronger structural condition of additivity. In particular, $A$ need not be additive, whereas $D$ is additive by axiom (D1).

---

## 3.3 Immediate consequences

The two axioms (D1) and (D2) have immediate consequences.

**Proposition 3.9 (Identity).** For every $b \in \mathcal{B}$,

$$D(b, b) = 0.$$

*Proof.* By (D2), $D(b, b) = -D(b, b)$. Hence $2D(b, b) = 0$, so $D(b, b) = 0$. $\square$

**Proposition 3.10 (Cycle invariance).** For any closed path

$$b_1 \to b_2 \to \cdots \to b_n \to b_1,$$

the total debt is zero:

$$\sum_{k=1}^{n} D(b_k, b_{k+1}) = 0,$$

where $b_{n+1} := b_1$.

*Proof.* By (D1),

$$D(b_k, b_{k+1}) = D(b_1, b_{k+1}) - D(b_1, b_k).$$

Summing over $k = 1, \ldots, n$ gives a telescoping sum:

$$\sum_{k=1}^{n} D(b_k, b_{k+1}) = D(b_1, b_{n+1}) - D(b_1, b_1).$$

Since $b_{n+1} = b_1$ and Proposition 3.9 gives $D(b_1, b_1) = 0$,

$$\sum_{k=1}^{n} D(b_k, b_{k+1}) = 0. \quad \square$$

**Proposition 3.11 (Path independence).** If $\gamma_1$ and $\gamma_2$ are two paths from $b_i$ to $b_j$, then

$$\sum_{e \in \gamma_1} D(e) = \sum_{e \in \gamma_2} D(e).$$

*Proof.* This is an immediate corollary of additivity. Let $\gamma = (b_0, b_1, \ldots, b_n)$ be any path from $b_i$ to $b_j$. Repeated application of (D1) gives

$$\sum_{k=0}^{n-1} D(b_k, b_{k+1}) = D(b_0, b_n) = D(b_i, b_j).$$

Thus the total debt of any path from $b_i$ to $b_j$ depends only on its endpoints and is independent of the path taken. $\square$

**Remark 3.12.** Proposition 3.11 is a restatement of additivity, not a separate theorem. Additivity is *equivalent* to the conjunction of two properties:

1. **Endpoint determination:** the total debt of a path depends only on its endpoints.
2. **Path independence:** any two paths between the same endpoints have the same total debt.

This equivalence is what makes additivity the right axiom for debt: it says precisely that debt is a function of state, not of trajectory.

**Proposition 3.13 (Gauge invariance of potential representations).** Let $\psi : \mathcal{B} \to \mathbb{R}$ and define

$$D(b_i, b_j) := \psi(b_j) - \psi(b_i).$$

Then $D$ satisfies (D1) and (D2). Moreover, if $\psi' = \psi + c$ for a constant $c \in \mathbb{R}$, then

$$D_{\psi'} = D_\psi.$$

Conversely, if $D_\psi = D_{\psi'}$, then $\psi' - \psi$ is constant on each connected component of the graph $G_d$.

*Proof.*

For (D1),

$$\psi(b_k) - \psi(b_i) = [\psi(b_j) - \psi(b_i)] + [\psi(b_k) - \psi(b_j)].$$

For (D2),

$$\psi(b_j) - \psi(b_i) = -[\psi(b_i) - \psi(b_j)].$$

Finally,

$$(\psi(b_j) + c) - (\psi(b_i) + c) = \psi(b_j) - \psi(b_i).$$

Thus adding a constant to the potential does not change the debt.

For the converse, suppose $D_\psi = D_{\psi'}$. Then for all $b_i, b_j$,

$$(\psi(b_j) - \psi(b_i)) - (\psi'(b_j) - \psi'(b_i)) = 0,$$

so $(\psi - \psi')(b_j) = (\psi - \psi')(b_i)$ for all $b_i, b_j$ connected by an edge in $G_d$. Hence $\psi - \psi'$ is constant on each connected component. $\square$

**Remark 3.14.** Proposition 3.13 establishes the forward direction: every potential difference is a debt function. The converse is not assumed here. It is the central question of Chapter 4.

---

## 3.4 Why debt?

The energy quasi-metric $d$ describes the cost associated with moving between states of the belief space. Its asymmetry records the fact that the cost of moving from $b_i$ to $b_j$ may differ from the cost of moving from $b_j$ to $b_i$.

But cost asymmetry alone does not provide a complete description of what happens during an information-processing transition.

An information-processing system does not merely move between states. As it moves, it accumulates information, changes its internal state, makes decisions, and carries the consequences of previous transitions into future states. This motivates introducing a second quantity that is distinct from energetic cost.

We call this quantity **debt**.

The purpose of the debt function is not to measure how expensive a transition is. Instead, it records a directed quantity that accumulates along transitions and cancels when a closed cycle is completed.

This distinction is fundamental.

The cost function answers a question such as:

> **How much does it cost to move from one state to another?**

The debt function answers a different question:

> **What directed quantity is carried from one state to another?**

These quantities need not coincide.

**Example 3.15 (Thermodynamic debt).** Let $\mathcal{B}$ be the set of thermodynamic states of a system. Let $\psi(b)$ be the free energy of state $b$. Then

$$D(b_i, b_j) := \psi(b_j) - \psi(b_i)$$

is the change in free energy. It is additive (free energy changes add along a path) and antisymmetric (reversing a transition reverses the sign of the change). The cost $d(b_i, b_j)$ might be the heat dissipated during the transition, which need not be additive—dissipation depends on the path. Debt and cost are therefore distinct: debt is a state function, cost is not.

**Example 3.16 (Computational debt).** Let $\mathcal{B}$ be the set of configurations of a reversible computer. Let $\psi(b)$ be the number of bits set to $1$ in configuration $b$. Then

$$D(b_i, b_j) := \psi(b_j) - \psi(b_i)$$

is the net change in the number of $1$ bits. It is additive and antisymmetric. The cost $d(b_i, b_j)$ might be the number of gate operations required to go from $b_i$ to $b_j$, which is path-dependent. Again, debt and cost are distinct.

**Example 3.17 (Economic debt).** Let $\mathcal{B}$ be the set of portfolios held by a trader. Let $\psi(b)$ be the total value of portfolio $b$. Then

$$D(b_i, b_j) := \psi(b_j) - \psi(b_i)$$

is the change in portfolio value. It is additive and antisymmetric. The cost $d(b_i, b_j)$ might be the transaction cost of moving from portfolio $b_i$ to portfolio $b_j$, which depends on the specific trades required and need not be additive.

In each case, debt is a potential difference: it records the change in a state function. Cost is not. The two quantities are structurally different.

**Remark 3.18.** In particular, the antisymmetric part of the energy quasi-metric,

$$A(b_i, b_j) = \tfrac{1}{2}\left(d(b_i, b_j) - d(b_j, b_i)\right),$$

measures the directional imbalance of cost. There is no reason, in general, for this quantity to satisfy the additivity required of a debt function.

Debt is therefore introduced as an independent mathematical object rather than being defined as a transformation of the energy quasi-metric.

The two axioms imposed on debt express the structure we require.

**Additivity** means that debt accumulated over successive transitions is the sum of the debts of the individual transitions. Thus, for $b_i \to b_j \to b_k$, the total debt is

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

**Antisymmetry** means that reversing a transition reverses the sign of its debt:

$$D(b_i, b_j) = -D(b_j, b_i).$$

Together, these properties imply that debt is path-independent and that the total debt around every closed path is zero.

This gives debt a structure fundamentally different from the energy cost.

A path may have different energetic costs depending on how it is traversed, and the energy quasi-metric may therefore require a minimization over possible paths. Debt behaves differently: once the two endpoints are fixed, the total debt is already determined.

This observation leads to the central mathematical question of the next chapter.

If the debt between two states depends only on its endpoints, can the debt always be represented by assigning a scalar potential to each state?

That is, does there necessarily exist a function

$$\psi : \mathcal{B} \to \mathbb{R}$$

such that

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)?$$

Chapter 4 investigates this question.

---

## 3.5 The debt of a path

The path-independence result allows us to define the total debt accumulated along a path without introducing any additional structure.

**Definition 3.19 (Debt of a path).** Let $\gamma = (b_0, b_1, \ldots, b_n)$ be a path in $\mathcal{B}$. The **total debt** along $\gamma$ is defined by

$$D(\gamma) := \sum_{k=0}^{n-1} D(b_k, b_{k+1}).$$

The quantity $D(\gamma)$ is the accumulated debt along the sequence of transitions making up the path.

**Proposition 3.20 (Endpoint determination).** For any path $\gamma = (b_0, b_1, \ldots, b_n)$, the total debt satisfies

$$D(\gamma) = D(b_0, b_n).$$

*Proof.* Repeated application of (D1) gives

$$D(b_0, b_n) = D(b_0, b_1) + D(b_1, b_2) + \cdots + D(b_{n-1}, b_n).$$

Therefore, $D(\gamma) = D(b_0, b_n)$. $\square$

**Remark 3.21.** Proposition 3.20 gives another formulation of path independence. The total debt accumulated along a path is completely determined by its initial and final states.

No minimization over paths is required.

This property is one of the main structural differences between debt and the energy quasi-metric.

---

## 3.6 A finite example

Consider the belief space $\mathcal{B} = \{b_1, b_2, b_3\}$. Suppose

$$D(b_1, b_2) = 2, \qquad D(b_2, b_3) = 3.$$

By additivity,

$$D(b_1, b_3) = D(b_1, b_2) + D(b_2, b_3) = 2 + 3 = 5.$$

By antisymmetry,

$$D(b_2, b_1) = -2, \qquad D(b_3, b_2) = -3, \qquad D(b_3, b_1) = -5.$$

Consider the closed path $b_1 \to b_2 \to b_3 \to b_1$. Its total debt is

$$2 + 3 - 5 = 0.$$

Thus the cycle has zero total debt, as predicted by Proposition 3.10.

Now compare the two paths from $b_1$ to $b_3$:

$$b_1 \to b_3 \qquad \text{and} \qquad b_1 \to b_2 \to b_3.$$

The first has total debt $D(b_1, b_3) = 5$, while the second has total debt $D(b_1, b_2) + D(b_2, b_3) = 2 + 3 = 5$. The two paths have the same total debt.

Now suppose the energy quasi-metric on this space is

$$d(b_1, b_3) = 4, \qquad d(b_1, b_2) = 2, \qquad d(b_2, b_3) = 3.$$

Then the direct path from $b_1$ to $b_3$ has cost $4$, while the indirect path $b_1 \to b_2 \to b_3$ has cost $2 + 3 = 5$. The energy quasi-metric is path-dependent: different paths between the same endpoints have different costs. Debt, by contrast, is path-independent: both paths have debt $5$.

This is the distinction between path-dependent cost and path-independent debt. Cost is minimized over paths; debt is determined by endpoints alone.

---

## 3.7 Summary

This chapter introduced the debt function

$$D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$$

through two axioms:

- **(D1) Additivity:** $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$;
- **(D2) Antisymmetry:** $D(b_i, b_j) = -D(b_j, b_i)$.

From these axioms we derived:

- **Identity:** $D(b, b) = 0$;
- **Cycle invariance:** the total debt around every closed path is zero;
- **Path independence:** every path between the same endpoints has the same total debt;
- **Endpoint determination:** the total debt of a path equals the debt between its endpoints.

We also distinguished the debt function from the antisymmetric part of the energy quasi-metric.

The central remaining question is whether every debt function arises from a scalar potential. That is, given $D$ satisfying (D1) and (D2), does there exist

$$\psi : \mathcal{B} \to \mathbb{R}$$

such that

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)?$$

This is the central question of Chapter 4.

---

## 3.8 Exercises

**Exercise 3.1 — Antisymmetric cost.** Let $d(b_1, b_2) = 7$ and $d(b_2, b_1) = 3$. Compute the symmetric part $S(b_1, b_2)$ and the antisymmetric part $A(b_1, b_2)$. Verify that $d(b_1, b_2) = S(b_1, b_2) + A(b_1, b_2)$.

**Exercise 3.2 — Reconstructing the cost.** Suppose $S(b_i, b_j) = 4$ and $A(b_i, b_j) = -1$. Compute $d(b_i, b_j)$ and $d(b_j, b_i)$.

**Exercise 3.3 — Basic debt values.** Suppose $D(b_1, b_2) = 4$ and $D(b_2, b_3) = -7$. Use (D1) to determine $D(b_1, b_3)$. Then use (D2) to determine $D(b_2, b_1)$, $D(b_3, b_2)$, and $D(b_3, b_1)$.

**Exercise 3.4 — Zero debt on a cycle.** Let $D(b_1, b_2) = 2$, $D(b_2, b_3) = 5$, and $D(b_3, b_1) = -7$. Verify directly that the total debt around the cycle $b_1 \to b_2 \to b_3 \to b_1$ is zero.

**Exercise 3.5 — Path independence and consistency.** Suppose there are two paths from $b_1$ to $b_4$:

$$\gamma_1 : b_1 \to b_2 \to b_4, \qquad \gamma_2 : b_1 \to b_3 \to b_4.$$

The debt values on the edges are

$$D(b_1, b_2) = 2, \quad D(b_2, b_4) = 5, \quad D(b_1, b_3) = 4, \quad D(b_3, b_4) = 3.$$

Do these values determine a unique value of $D(b_1, b_4)$? If so, what is it? If not, why not?

**Exercise 3.6 — Detecting inconsistency.** Consider the directed transitions

$$D(b_1, b_2) = 2, \quad D(b_2, b_3) = 4, \quad D(b_1, b_3) = 7.$$

Can these three values belong to a debt function satisfying (D1)? Explain why or why not.

**Exercise 3.7 — Cycle test.** Suppose a directed graph contains the cycle $b_1 \to b_2 \to b_3 \to b_4 \to b_1$. The debt values on the first three edges are $2, -1, 5$. What must the debt on the final edge be if the function satisfies cycle invariance? What is $D(b_1, b_4)$? Does your answer depend on the path taken?

**Exercise 3.8 — Path reversal.** Let $\gamma : b_1 \to b_2 \to b_3 \to b_4$ with edge debts $3, -2, 6$. Compute the total debt of the reversed path $\gamma^{-1} : b_4 \to b_3 \to b_2 \to b_1$.

**Exercise 3.9 — Path debt.** Let $\gamma = (b_0, b_1, b_2, b_3, b_4)$ and suppose $D(b_0, b_1) = 1$, $D(b_1, b_2) = 4$, $D(b_2, b_3) = -2$, and $D(b_3, b_4) = 6$. Compute $D(\gamma)$. What does Proposition 3.20 imply about $D(b_0, b_4)$?

**Exercise 3.10 — Potential differences.** Let $\psi(b_1) = 2$, $\psi(b_2) = 5$, $\psi(b_3) = 1$. Define $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Compute $D(b_1, b_2)$, $D(b_2, b_3)$, and $D(b_1, b_3)$. Verify (D1) for the three states.

**Exercise 3.11 — Gauge transformation.** Let $\psi(b_1) = 2$ and $\psi(b_2) = 7$. Define $D(b_1, b_2) = \psi(b_2) - \psi(b_1)$. Now define $\psi'(b) = \psi(b) + 10$. Show that the debt remains unchanged.

**Exercise 3.12 — Conceptual distinction.** Explain in your own words why the antisymmetric part $A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i))$ cannot automatically be identified with the debt function $D$. Your answer should address the role of additivity.

**Exercise 3.13 — Debt in a physical system.** Consider a thermodynamic system with states $b_1, b_2, b_3$ and free energies $\psi(b_1) = 5$, $\psi(b_2) = 8$, $\psi(b_3) = 3$ (in some units). Compute the debt function $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ for all ordered pairs. Verify that the total debt around the cycle $b_1 \to b_2 \to b_3 \to b_1$ is zero. Explain in one sentence why this is a statement of energy conservation.
