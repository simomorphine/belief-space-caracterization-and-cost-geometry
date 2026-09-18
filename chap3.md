# Chapter 3: The Debt Function

---

## 3.1 The asymmetry of cost

Chapter 2 established the energy quasi-metric $d$ as the cost of moving between states of the belief space. Because $d$ is a quasi-metric, it need not be symmetric. In general,

$$
d(b_i,b_j) \neq d(b_j,b_i).
$$

This asymmetry is not an error in the construction. It records the fact that moving from $b_i$ to $b_j$ may have a different cost from moving in the opposite direction.

**Observation 3.1.** There may exist $b_i,b_j\in\mathcal B$ such that

$$
d(b_i,b_j)\neq d(b_j,b_i).
$$

The first task of this chapter is therefore to isolate the asymmetric part of the energy quasi-metric.

**Definition 3.2 (Symmetric and antisymmetric parts).** Assume that $d(b_i,b_j)<+\infty$ for all $b_i,b_j\in\mathcal B$. Define

$$
S(b_i,b_j)
:=
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right)
$$

and

$$
A(b_i,b_j)
:=
\frac12\left(d(b_i,b_j)-d(b_j,b_i)\right).
$$

We call $S$ the **symmetric part** of the cost and $A$ the **antisymmetric part** of the cost.

The function $A$ measures the directional imbalance of the cost. It is positive when the transition from $b_i$ to $b_j$ is more expensive than the reverse transition, negative when it is cheaper, and zero when the two directions have equal cost.

**Proposition 3.3.** The antisymmetric part $A$ satisfies:

1. $A(b_i,b_j)=-A(b_j,b_i)$;
2. $A(b,b)=0$;
3. $A(b_i,b_j)>0$ if and only if $d(b_i,b_j)>d(b_j,b_i)$;
4.

$$
|A(b_i,b_j)|
\leq
\frac12\left(d(b_i,b_j)+d(b_j,b_i)\right).
$$

*Proof.*

For antisymmetry,

$$ 
A(b_j,b_i) = \frac12\left(d(b_j,b_i)-d(b_i,b_j)\right) = -A(b_i,b_j).
$$

On the diagonal,

$$
A(b,b) = \frac12\left(d(b,b)-d(b,b)\right) = 0.
$$

The sign property follows directly from the definition. Finally,

$$
|A(b_i,b_j)| = \frac12 \left| d(b_i,b_j)-d(b_j,b_i) \right|
$$

and therefore

$$
|A(b_i,b_j)|
\leq
\frac12
\left(
d(b_i,b_j)+d(b_j,b_i)
\right).
$$



The symmetric and antisymmetric parts reconstruct the original cost.

**Proposition 3.4 (Canonical decomposition).** The energy quasi-metric admits the decomposition

$$
d=S+A,
$$

where $S$ is symmetric and $A$ is antisymmetric. This decomposition is unique.

*Proof.*

By definition,

$$
S(b_i,b_j)+A(b_i,b_j) = \frac12(d(b_i,b_j)+d(b_j,b_i)) + \frac12(d(b_i,b_j)-d(b_j,b_i)),
$$

so

$$
S(b_i,b_j)+A(b_i,b_j)=d(b_i,b_j).
$$

The function $S$ is symmetric and $A$ is antisymmetric by construction.

For uniqueness, suppose

$$
d=S'+A',
$$

where $S'$ is symmetric and $A'$ is antisymmetric. Evaluating the same equation with $b_i$ and $b_j$ exchanged and adding and subtracting the two equations gives

$$
S'=S,\qquad A'=A.
$$

Thus the decomposition is unique. 

**Remark 3.5.** The antisymmetric component $A$ should not be identified with the debt function introduced in this chapter. $A$ is determined directly by the asymmetry of the energy quasi-metric. Debt is a separate object whose mathematical structure will be introduced independently.

The distinction is important. Asymmetry tells us that the cost of a transition depends on its direction. It does not, by itself, tell us why this asymmetry exists, whether it can be represented by a potential, or whether it satisfies additional structural properties.

The purpose of the following sections is to investigate this additional structure.

In particular, Chapter 4 will ask whether the debt function can be represented as a difference of potentials,

$$
D(b_i,b_j)=\psi(b_j)-\psi(b_i),
$$

and what assumptions are required for such a representation to exist.

---

## 3.3 The debt function: definition

We now introduce the central object of the book.

**Definition 3.6 (Debt function).** Let $\mathcal{B}$ be a belief space. A *debt function* is a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ satisfying:

- **(D1) Additivity.** $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$ for all $b_i, b_j, b_k \in \mathcal{B}$.
- **(D2) Antisymmetry.** $D(b_i, b_j) = -D(b_j, b_i)$ for all $b_i, b_j \in \mathcal{B}$.

These are the only axioms. Everything else follows.

**Remark 3.7.** The axioms (D1) and (D2) are minimal. They are satisfied by any potential difference: if $\psi : \mathcal{B} \to \mathbb{R}$ is any function, then $D(b_i, b_j) := \psi(b_j) - \psi(b_i)$ satisfies (D1) and (D2). The central result of Chapter 4 is that *every* debt function arises this way.

**Remark 3.8.** The debt function is *not* the same as the asymmetry $A$. The asymmetry measures the *magnitude* of directional imbalance; the debt measures the *potential* that generates it. The two are related by the polar decomposition of Chapter 11. For now, the essential difference is that $A$ is not additive while $D$ is additive by axiom (D1).

---

## 3.4 Immediate consequences

The two axioms (D1) and (D2) have immediate consequences.

**Proposition 3.9. (Identity).** $D(b, b) = 0$ for all $b \in \mathcal{B}$.

*Proof.* By (D2), $D(b, b) = -D(b, b)$. Hence $2D(b, b) = 0$, so $D(b, b) = 0$. $\square$

**Proposition 3.10. (Cycle invariance).** For any closed path $b_1 \to b_2 \to \cdots \to b_n \to b_1$,

$$\sum_{k=1}^n D(b_k, b_{k+1}) = 0,$$

where $b_{n+1} := b_1$.

*Proof.* By (D1), for each $k$,

$$D(b_k, b_{k+1}) = D(b_1, b_{k+1}) - D(b_1, b_k).$$

Summing over $k = 1, \dots, n$ and telescoping,

$$\sum_{k=1}^n D(b_k, b_{k+1}) = D(b_1, b_{n+1}) - D(b_1, b_1) = D(b_1, b_1) - D(b_1, b_1) = 0,$$

where we used $b_{n+1} = b_1$ and Proposition 3.14. $\square$

**Proposition 3.11. (Path independence).** If $\gamma_1$ and $\gamma_2$ are two paths from $b_i$ to $b_j$, then

$$\sum_{e \in \gamma_1} D(e) = \sum_{e \in \gamma_2} D(e).$$

*Proof.* The concatenation $\gamma_1 \cdot \gamma_2^{-1}$ is a closed path. By Proposition 3.10, its total debt is zero. Hence the debt of $\gamma_1$ equals the debt of $\gamma_2$. $\square$

**Remark 3.12.** Proposition 3.11 is the key property. It says that the debt of a path depends only on the endpoints, not on the path itself. This is the defining property of a *conservative* quantity. Debt is conservative.

**Proposition 3.13. (Gauge invariance).** Let $\psi : \mathcal{B} \to \mathbb{R}$ and let $D(b_i, b_j) := \psi(b_j) - \psi(b_i)$. Then $D$ satisfies (D1) and (D2). Moreover, if $\psi' := \psi + c$ for a constant $c \in \mathbb{R}$, then $D_{\psi'} = D_\psi$.

*Proof.* (D1): $\psi(b_k) - \psi(b_i) = [\psi(b_j) - \psi(b_i)] + [\psi(b_k) - \psi(b_j)]$. (D2): $\psi(b_j) - \psi(b_i) = -[\psi(b_i) - \psi(b_j)]$. Gauge invariance: constants cancel in differences. $\square$

**Remark 3.14.** Proposition 3.13 says that *every* potential difference is a debt function. The converse—that every debt function is a potential difference—is the content of the basepoint theorem (Chapter 4). Together, they establish that debt functions and potential differences are the same thing.

---

## 3.5 Debt as an alternating 1-cocycle

The axioms (D1) and (D2) have a natural interpretation in the language of cohomology.

**Definition 3.15 (Discrete de Rham complex).** Let $\mathcal{B}$ be a set, viewed as the vertex set of the complete directed graph on $\mathcal{B}$. For $k \ge 0$, let $C^k(\mathcal{B})$ be the $\mathbb{R}$-vector space of functions on $(k+1)$-tuples $(b_0, \dots, b_k)$ of $\mathcal{B}$.

- $C^0(\mathcal{B})$ is the space of functions $\psi : \mathcal{B} \to \mathbb{R}$.
- $C^1(\mathcal{B})$ is the space of functions $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$.
- $C^2(\mathcal{B})$ is the space of functions $A : \mathcal{B} \times \mathcal{B} \times \mathcal{B} \to \mathbb{R}$.

**Definition 3.16 (Coboundary).** The *coboundary* $\delta : C^0(\mathcal{B}) \to C^1(\mathcal{B})$ is

$$(\delta\psi)(b_i, b_j) := \psi(b_j) - \psi(b_i).$$

The *coboundary* $\delta : C^1(\mathcal{B}) \to C^2(\mathcal{B})$ is

$$(\delta D)(b_i, b_j, b_k) := D(b_j, b_k) - D(b_i, b_k) + D(b_i, b_j).$$

**Proposition 3.17.** $\delta^2 = 0$.

*Proof.* Direct computation:

$$(\delta^2\psi)(b_i, b_j, b_k) = (\delta\psi)(b_j, b_k) - (\delta\psi)(b_i, b_k) + (\delta\psi)(b_i, b_j)$$
$$= [\psi(b_k) - \psi(b_j)] - [\psi(b_k) - \psi(b_i)] + [\psi(b_j) - \psi(b_i)] = 0. \quad \square$$

**Proposition 3.18.** A function $D \in C^1(\mathcal{B})$ satisfies (D1) if and only if $\delta D = 0$. That is, $D$ is a *cocycle*.

*Proof.* $\delta D = 0$ means

$$D(b_j, b_k) - D(b_i, b_k) + D(b_i, b_j) = 0$$

for all $b_i, b_j, b_k$. Rearranging:

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

This is exactly (D1). $\square$

**Proposition 3.19.** A function $D \in C^1(\mathcal{B})$ satisfies (D2) if and only if $D$ is *alternating*: $D(b_i, b_j) = -D(b_j, b_i)$.

*Proof.* Immediate. $\square$

**Corollary 3.20.** Debt functions are exactly the alternating 1-cocycles of the discrete de Rham complex on $\mathcal{B}$.

**Remark 3.21.** This is the cohomological characterization of debt. The two axioms (D1) and (D2) are exactly the two conditions for $D$ to be an alternating 1-cocycle. The basepoint theorem (Chapter 4) will show that every such cocycle is a coboundary, i.e., $D = \delta\psi$ for some $\psi \in C^0(\mathcal{B})$. This is the statement that the first cohomology of the complete directed graph on $\mathcal{B}$ is trivial.

**Remark 3.22.** The asymmetry $A$ of Definition 3.2 is also an alternating 1-cochain, but it is *not* a cocycle: as Example 3.8 shows, $\delta A \neq 0$ in general. So $A$ and $D$ live in the same space $C^1(\mathcal{B})$ but in different subspaces: $A$ is an arbitrary alternating 1-cochain, while $D$ is an alternating 1-cocycle. The space of alternating 1-cocycles is strictly smaller.

---

## 3.6 The debt of a transition

Let us interpret the debt function in the context of belief space.

**Definition 3.28 (Debt of a transition).** For a transition $b_i \to b_j$, the *debt* is $D(b_i, b_j)$.

**Interpretation 3.29.** The debt $D(b_i, b_j)$ measures the change in a *potential* $\psi$ associated with the belief space. If $\psi(b)$ represents the "computational obligation" or "entropy" or "free energy" of belief $b$, then $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ is the change in that quantity when transitioning from $b_i$ to $b_j$.

- **Positive debt:** $D(b_i, b_j) > 0$. The transition increases the potential. The system takes on new obligations.
- **Negative debt:** $D(b_i, b_j) < 0$. The transition decreases the potential. The system pays down existing obligations.
- **Zero debt:** $D(b_i, b_j) = 0$. The transition preserves the potential. The system remains in equilibrium.

**Remark 3.30.** The interpretation of $\psi$ is deliberately left open. In different applications, $\psi$ may represent different quantities: entropy, free energy, computational obligation, information content, or something else. The theory does not depend on the interpretation. What matters is that $\psi$ exists and that $D$ is its coboundary.

**Proposition 3.31 (Debt of a path).** For a path $\gamma = (b_0, b_1, \dots, b_n)$, the total debt is

$$\sum_{k=0}^{n-1} D(b_k, b_{k+1}) = \psi(b_n) - \psi(b_0).$$

*Proof.* Telescoping. $\square$

**Corollary 3.32.** The total debt of a path depends only on the endpoints, not on the path itself.

*Proof.* Immediate from Proposition 3.31. $\square$

**Remark 3.33.** This is the fundamental property of debt. It is a *conservative* quantity: it depends only on the endpoints, not on the path. Note that the cost $d$ is path-independent in a different sense: $d(b_i,b_j)$ is the *minimum* cost over paths, so it depends only on the endpoints by definition. The debt is path-independent in the stronger sense that *every* path between $b_i$ and $b_j$ has the same debt.

---

## 3.7 The debt-to-cost ratio

The debt $D$ and the cost $d$ together determine a natural ratio.

**Definition 3.34 (Debt-to-cost ratio).** For a transition $b_i \to b_j$ with $d(b_i, b_j) > 0$, the *debt-to-cost ratio* is

$$r(b_i, b_j) := \frac{D(b_i, b_j)}{d(b_i, b_j)}.$$

When $d(b_i, b_j) = 0$, we adopt the convention $r(b_i, b_j) = 0$.

**Remark 3.35.** The convention $r(b,b) = 0$ at the diagonal reflects the fact that the diagonal transition carries no debt and no cost. It is the unique value consistent with the limit $d \to 0$ when $D$ also vanishes, which holds whenever the transition is not purely a debt phenomenon. In the pure-debt case ($d = 0$, $D \neq 0$), the ratio is genuinely undefined; such transitions are treated separately in Chapter 6.

**Proposition 3.36.** The debt-to-cost ratio satisfies:

- **(i)** $r(b, b) = 0$;
- **(ii)** $r(b_i, b_j) = -r(b_j, b_i) \cdot \dfrac{d(b_j, b_i)}{d(b_i, b_j)}$;
- **(iii)** $r(b_i, b_j)$ is invariant under gauge transformations of $\psi$.

*Proof.* (i) Convention.

(ii) $r(b_i, b_j) = D(b_i, b_j)/d(b_i, b_j) = -D(b_j, b_i)/d(b_i, b_j) = -r(b_j, b_i) \cdot d(b_j, b_i)/d(b_i, b_j)$.

(iii) $D$ is gauge-invariant (Proposition 3.18), and $d$ is independent of $\psi$. $\square$

**Remark 3.37.** The ratio $r$ is dimensionless. It measures the "debt intensity" of a transition. A transition with $r = 0$ is pure cost (no debt). A transition with $|r| \to \infty$ is pure debt (no cost). The ratio is a natural coordinate on the space of transitions.

**Remark 3.38.** Property (ii) is not the clean antisymmetry one might expect ($r(b_i,b_j) = -r(b_j,b_i)$). The correction factor $d(b_j,b_i)/d(b_i,b_j)$ appears because $D$ is antisymmetric but $d$ is not. If $d$ were symmetric, the ratio would be cleanly antisymmetric. The asymmetry of $d$ leaks into the ratio.

**Remark 3.39.** In Chapter 6, we will see that the ratio $r$ is the tangent of the phase of the complex quasi-metric $Q = d + iD$. Specifically, $\arg Q = \arctan(r)$. This will connect the debt-to-cost ratio to the geometric structure of $Q$.

---

## 3.8 Why debt is the right object

We close this chapter with a reflection on why debt, rather than asymmetry, is the right object to study.

**The asymmetry $A$ is not additive.** As Example 3.8 shows, $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$ in general. The asymmetry of a composed transition is not the sum of the asymmetries of its parts. This means that $A$ does not telescope, does not define a path-independent quantity, and does not admit a potential.

**The debt $D$ is additive.** By axiom (D1), $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$. The debt of a composed transition *is* the sum of the debts of its parts. This means that $D$ telescopes, defines a path-independent quantity, and admits a potential (Chapter 4).

**The asymmetry $A$ is an arbitrary alternating 1-cochain.** It lives in $C^1(\mathcal{B})$ and satisfies (D2) but not (D1).

**The debt $D$ is an alternating 1-cocycle.** It lives in the subspace of $C^1(\mathcal{B})$ consisting of functions satisfying both (D1) and (D2).

**The relationship.** The asymmetry $A$ and the debt $D$ are both alternating 1-cochains, but they live in different subspaces: $A$ is an arbitrary alternating 1-cochain, while $D$ is an alternating 1-cocycle. The precise relationship between them—how $A$ decomposes into a cocycle part and a non-cocycle part—is developed in Chapter 11 via the polar decomposition of quasi-metrics. For now, the essential point is that additivity is what allows telescoping, path-independence, and the existence of a potential, and $A$ does not have it while $D$ does by axiom.

**The moral.** Debt is the right object because it is additive. Additivity is what allows telescoping, path-independence, and the existence of a potential. The asymmetry, while natural, is not additive, and therefore does not admit the same rich structure.

---

## 3.9 Summary

We have introduced the debt function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$, defined by two axioms:

- **(D1) Additivity.** $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$.
- **(D2) Antisymmetry.** $D(b_i, b_j) = -D(b_j, b_i)$.

We have shown that these axioms imply:

- **Identity.** $D(b, b) = 0$.
- **Cycle invariance.** The total debt of any closed path is zero.
- **Path independence.** The total debt of a path depends only on the endpoints.
- **Gauge invariance.** Debt is invariant under addition of a constant to the potential.
- **Cohomological characterization.** Debt functions are exactly the alternating 1-cocycles of the discrete de Rham complex.

We have also introduced the asymmetry $A$ with the canonical $\tfrac{1}{2}$ normalization, shown that $d = S + A$ decomposes uniquely into symmetric and antisymmetric parts, and shown by example that $A$ is *not* additive—which is precisely why debt, and not asymmetry, is the right object to study.

Finally, we have introduced the debt-to-cost ratio $r(b_i, b_j) = D(b_i, b_j)/d(b_i, b_j)$, which measures the "debt intensity" of a transition and will play a central role in the geometric theory of Chapter 6.

The central remaining question is: does every debt function arise from a potential? That is, given $D$ satisfying (D1) and (D2), does there exist $\psi : \mathcal{B} \to \mathbb{R}$ with $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$? The answer is yes, and the proof is the subject of Chapter 4.

---

## 3.10 Exercises

**Exercise 3.1.** Verify that the function $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ satisfies (D1) and (D2) for any $\psi : \mathcal{B} \to \mathbb{R}$.

**Exercise 3.2.** Give an example of a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ that satisfies (D1) but not (D2). Give an example that satisfies (D2) but not (D1).

**Exercise 3.3.** Let $\mathcal{B} = \{1, 2, 3\}$ and let $D$ be defined by

$$D(1, 2) = 2, \quad D(2, 3) = 3, \quad D(1, 3) = 5,$$

with $D$ extended by antisymmetry and $D(i, i) = 0$. Verify that $D$ satisfies (D1) and (D2). Find a potential $\psi$ such that $D = \delta\psi$.

**Exercise 3.4.** Let $\mathcal{B}$ be a set and let $D$ satisfy (D1) and (D2). Prove that for any basepoint $s_0 \in \mathcal{B}$, the function $\psi_{s_0}(b) := D(s_0, b)$ satisfies $D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)$.

**Exercise 3.5.** Prove that the decomposition $d = S + A$ of Proposition 3.7 is unique. (Hint: consider $d - d^T$ where $d^T(b_i,b_j) := d(b_j,b_i)$.)

**Exercise 3.6.** Show that the asymmetry $A$ is *not* additive: exhibit a belief space and a triple $(b_i, b_j, b_k)$ with $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$.

**Exercise 3.7.** Show that the debt-to-cost ratio $r$ is invariant under the addition of a constant to $\psi$, but is *not* invariant under a general gauge transformation $\psi \mapsto \psi + \chi$ where $\chi$ is not constant. (Hint: consider whether the ratio depends on $\psi$ at all.)

**Exercise 3.8.** Let $\mathcal{B}$ be a finite set with $n$ elements. Show that the space of debt functions on $\mathcal{B}$ is isomorphic to $\mathbb{R}^{n-1}$. (Hint: use Exercise 3.4 to construct a map from debt functions to potentials, and identify its kernel.)

**Exercise 3.9.** Prove that the asymmetry $A(b_i, b_j) = \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i))$ is *not* a debt function in general. (Hint: use Exercise 3.6.)

**Exercise 3.10.** Let $D$ be a debt function and let $c \in \mathbb{R}$. Show that $cD$ is also a debt function. What is the corresponding potential?

**Exercise 3.11.** Reflect on the following question: why is additivity the right axiom for debt, rather than some weaker condition? Write a short essay (one page) arguing for your position.


