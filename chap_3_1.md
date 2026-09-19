# Chapter 3: The Debt Function

---

In Chapter 2, we established that the energy quasi-metric $d$ captures the cost of transitions between beliefs. But cost alone does not capture the full structure of belief space. There is a second quantity—the **debt**—which measures the asymmetry of cost in a precise and canonical way.

This chapter introduces the debt function, states its defining axioms, and derives its most immediate consequences. The central result—that debt is a potential difference—is deferred to Chapter 4. Here we establish what debt is and why it is the right object to study.

---

## 3.1 The asymmetry of cost

Let us begin with a simple observation.

**Observation 3.1.** The energy quasi-metric $d$ need not be symmetric. There may exist $b_i, b_j \in \mathcal{B}$ with $d(b_i, b_j) \neq d(b_j, b_i)$.

This is not a defect. It is a feature. The asymmetry of $d$ is a genuine quantity, and it deserves a name.

**Definition 3.2 (Asymmetry).** The *asymmetry* of the energy quasi-metric $d$ is the function $A : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ defined by

$$A(b_i, b_j) := d(b_i, b_j) - d(b_j, b_i).$$

**Proposition 3.3 (Properties of asymmetry).** The asymmetry $A$ satisfies:

- **(i) Antisymmetry.** $A(b_i, b_j) = -A(b_j, b_i)$ for all $b_i, b_j$.
- **(ii) Vanishing on the diagonal.** $A(b, b) = 0$ for all $b$.
- **(iii) Boundedness.** $|A(b_i, b_j)| \le d(b_i, b_j) + d(b_j, b_i)$.
- **(iv) Sign.** $A(b_i, b_j) > 0$ if and only if $d(b_i, b_j) > d(b_j, b_i)$.

*Proof.* (i) $A(b_i, b_j) = d(b_i, b_j) - d(b_j, b_i) = -(d(b_j, b_i) - d(b_i, b_j)) = -A(b_j, b_i)$.

(ii) $A(b, b) = d(b, b) - d(b, b) = 0$.

(iii) $|A(b_i, b_j)| = |d(b_i, b_j) - d(b_j, b_i)| \le d(b_i, b_j) + d(b_j, b_i)$ by the triangle inequality on $\mathbb{R}$.

(iv) Immediate. $\square$

The asymmetry $A$ measures the *extent* to which the cost is asymmetric. It is positive when going from $b_i$ to $b_j$ is more expensive than going the other way, negative when it is cheaper, and zero when the two costs are equal.

**Remark 3.4.** The asymmetry $A$ is a 2-form in the discrete sense: it is a function on ordered pairs that is antisymmetric and vanishes on the diagonal. This is the first hint of the differential structure that will be developed in Part V.

**Remark 3.5.** The asymmetry $A$ is not the same as the debt. It is the *magnitude* of the debt, in a sense to be made precise. The debt itself is a potential difference—a derivative, not a magnitude. The relationship between $A$ and $D$ will be clarified in Chapter 4.

---

## 3.2 Why asymmetry is not enough

The asymmetry $A$ captures the directional imbalance of cost, but it does not capture the *structure* of that imbalance.

Consider two belief spaces:

- **Space 1.** $d(b_1, b_2) = 2$, $d(b_2, b_1) = 1$, $d(b_2, b_3) = 2$, $d(b_3, b_2) = 1$, $d(b_1, b_3) = 4$, $d(b_3, b_1) = 2$.
- **Space 2.** $d(b_1, b_2) = 2$, $d(b_2, b_1) = 1$, $d(b_2, b_3) = 2$, $d(b_3, b_2) = 1$, $d(b_1, b_3) = 3$, $d(b_3, b_1) = 1$.

In both spaces, the asymmetry $A(b_1, b_2) = 1$ and $A(b_2, b_3) = 1$. But the asymmetry $A(b_1, b_3)$ differs: $2$ in Space 1, $2$ in Space 2. Wait—let me recompute.

Space 1: $A(b_1, b_3) = 4 - 2 = 2$.
Space 2: $A(b_1, b_3) = 3 - 1 = 2$.

Both give $A(b_1, b_3) = 2$. So this example does not distinguish them. Let me try again.

Consider:

- **Space 1.** $d(b_1, b_2) = 2$, $d(b_2, b_1) = 1$, $d(b_2, b_3) = 2$, $d(b_3, b_2) = 1$, $d(b_1, b_3) = 4$, $d(b_3, b_1) = 2$.
- **Space 2.** $d(b_1, b_2) = 2$, $d(b_2, b_1) = 1$, $d(b_2, b_3) = 3$, $d(b_3, b_2) = 1$, $d(b_1, b_3) = 4$, $d(b_3, b_1) = 2$.

In Space 1: $A(b_1, b_2) = 1$, $A(b_2, b_3) = 1$, $A(b_1, b_3) = 2$.
In Space 2: $A(b_1, b_2) = 1$, $A(b_2, b_3) = 2$, $A(b_1, b_3) = 2$.

Now $A(b_1, b_2) + A(b_2, b_3) = 2$ in Space 1, which equals $A(b_1, b_3)$. In Space 2, $A(b_1, b_2) + A(b_2, b_3) = 3$, which does *not* equal $A(b_1, b_3) = 2$.

So the asymmetry $A$ is **not additive** in general. It does not telescope. It is not a coboundary. And this is precisely why we need a different object—the debt—which *is* additive and *does* telescope.

**Remark 3.6.** The asymmetry $A$ is a 2-form; the debt $D$ will be a 1-form. The relationship between them is that $A$ is the *derivative* of $D$ in a suitable sense. This will be made precise in Chapter 11.

---

## 3.3 The debt function: definition

We now introduce the central object of the book.

**Definition 3.7 (Debt function).** Let $\mathcal{B}$ be a belief space. A *debt function* is a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ satisfying:

- **(D1) Additivity.** $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$ for all $b_i, b_j, b_k \in \mathcal{B}$.
- **(D2) Antisymmetry.** $D(b_i, b_j) = -D(b_j, b_i)$ for all $b_i, b_j \in \mathcal{B}$.

These are the only axioms. Everything else follows.

**Remark 3.8.** The axioms (D1) and (D2) are minimal. They are satisfied by any potential difference: if $\psi : \mathcal{B} \to \mathbb{R}$ is any function, then $D(b_i, b_j) := \psi(b_j) - \psi(b_i)$ satisfies (D1) and (D2). The central result of Chapter 4 is that *every* debt function arises this way.

**Remark 3.9.** The debt function is *not* the same as the asymmetry $A$. The asymmetry is a 2-form; the debt is a 1-form. The asymmetry measures the *magnitude* of directional imbalance; the debt measures the *potential* that generates it. The relationship between them will be made precise in Chapter 11.

---

## 3.4 Immediate consequences

The two axioms (D1) and (D2) have immediate consequences.

**Proposition 3.10 (Identity).** $D(b, b) = 0$ for all $b \in \mathcal{B}$.

*Proof.* By (D2), $D(b, b) = -D(b, b)$. Hence $2D(b, b) = 0$, so $D(b, b) = 0$. $\square$

**Proposition 3.11 (Cycle invariance).** For any closed path $b_1 \to b_2 \to \cdots \to b_n \to b_1$,

$$\sum_{k=1}^n D(b_k, b_{k+1}) = 0,$$

where $b_{n+1} := b_1$.

*Proof.* By (D1), the sum telescopes:

$$\sum_{k=1}^n D(b_k, b_{k+1}) = \sum_{k=1}^n \bigl[D(b_1, b_{k+1}) - D(b_1, b_k)\bigr] = D(b_1, b_1) - D(b_1, b_1) = 0.$$

Wait, this is not quite right. Let me redo.

By (D1), $D(b_k, b_{k+1}) = D(b_1, b_{k+1}) - D(b_1, b_k)$ for each $k$. Summing:

$$\sum_{k=1}^n D(b_k, b_{k+1}) = \sum_{k=1}^n \bigl[D(b_1, b_{k+1}) - D(b_1, b_k)\bigr] = D(b_1, b_{n+1}) - D(b_1, b_1) = D(b_1, b_1) - D(b_1, b_1) = 0.$$

Here $b_{n+1} = b_1$, so $D(b_1, b_{n+1}) = D(b_1, b_1) = 0$. Hence the sum is zero. $\square$

**Proposition 3.12 (Path independence).** If $\gamma_1$ and $\gamma_2$ are two paths from $b_i$ to $b_j$, then

$$\sum_{e \in \gamma_1} D(e) = \sum_{e \in \gamma_2} D(e).$$

*Proof.* The concatenation $\gamma_1 \cdot \gamma_2^{-1}$ is a closed path. By Proposition 3.11, its total debt is zero. Hence the debt of $\gamma_1$ equals the debt of $\gamma_2$. $\square$

**Remark 3.13.** Proposition 3.12 is the key property. It says that the debt of a path depends only on the endpoints, not on the path itself. This is the defining property of a *conservative* quantity. Debt is conservative.

**Proposition 3.14 (Gauge invariance).** Let $\psi : \mathcal{B} \to \mathbb{R}$ and let $D(b_i, b_j) := \psi(b_j) - \psi(b_i)$. Then $D$ satisfies (D1) and (D2). Moreover, if $\psi' := \psi + c$ for a constant $c \in \mathbb{R}$, then $D_{\psi'} = D_\psi$.

*Proof.* (D1): $\psi(b_k) - \psi(b_i) = [\psi(b_j) - \psi(b_i)] + [\psi(b_k) - \psi(b_j)]$. (D2): $\psi(b_j) - \psi(b_i) = -[\psi(b_i) - \psi(b_j)]$. Gauge invariance: constants cancel in differences. $\square$

**Remark 3.15.** Proposition 3.14 says that *every* potential difference is a debt function. The converse—that every debt function is a potential difference—is the content of the basepoint theorem (Chapter 4). Together, they establish that debt functions and potential differences are the same thing.

---

## 3.5 Debt as a 1-cochain

The axioms (D1) and (D2) have a natural interpretation in the language of cohomology.

**Definition 3.16 (Discrete de Rham complex).** Let $\mathcal{B}$ be a set, viewed as the vertex set of the complete directed graph on $\mathcal{B}$. For $k \ge 0$, let $C^k(\mathcal{B})$ be the $\mathbb{R}$-vector space of functions on $(k+1)$-tuples $(b_0, \dots, b_k)$ of $\mathcal{B}$.

- $C^0(\mathcal{B})$ is the space of functions $\psi : \mathcal{B} \to \mathbb{R}$.
- $C^1(\mathcal{B})$ is the space of functions $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$.
- $C^2(\mathcal{B})$ is the space of functions $A : \mathcal{B} \times \mathcal{B} \times \mathcal{B} \to \mathbb{R}$.

**Definition 3.17 (Coboundary).** The *coboundary* $\delta : C^0(\mathcal{B}) \to C^1(\mathcal{B})$ is

$$(\delta\psi)(b_i, b_j) := \psi(b_j) - \psi(b_i).$$

The *coboundary* $\delta : C^1(\mathcal{B}) \to C^2(\mathcal{B})$ is

$$(\delta D)(b_i, b_j, b_k) := D(b_j, b_k) - D(b_i, b_k) + D(b_i, b_j).$$

**Proposition 3.18.** $\delta^2 = 0$.

*Proof.* Direct computation:

$$(\delta^2\psi)(b_i, b_j, b_k) = (\delta\psi)(b_j, b_k) - (\delta\psi)(b_i, b_k) + (\delta\psi)(b_i, b_j)$$
$$= [\psi(b_k) - \psi(b_j)] - [\psi(b_k) - \psi(b_i)] + [\psi(b_j) - \psi(b_i)] = 0. \quad \square$$

**Proposition 3.19.** A function $D \in C^1(\mathcal{B})$ satisfies (D1) if and only if $\delta D = 0$. That is, $D$ is a *cocycle*.

*Proof.* $\delta D = 0$ means

$$D(b_j, b_k) - D(b_i, b_k) + D(b_i, b_j) = 0$$

for all $b_i, b_j, b_k$. Rearranging:

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k).$$

This is exactly (D1). $\square$

**Proposition 3.20.** A function $D \in C^1(\mathcal{B})$ satisfies (D2) if and only if $D$ is *alternating*: $D(b_i, b_j) = -D(b_j, b_i)$.

*Proof.* Immediate. $\square$

**Corollary 3.21.** Debt functions are exactly the alternating 1-cocycles of the discrete de Rham complex on $\mathcal{B}$.

**Remark 3.22.** This is the cohomological characterization of debt. The two axioms (D1) and (D2) are the two conditions for $D$ to be an alternating 1-cocycle. The basepoint theorem (Chapter 4) will show that every such cocycle is a coboundary, i.e., $D = \delta\psi$ for some $\psi \in C^0(\mathcal{B})$. This is the statement that the first cohomology of the complete directed graph on $\mathcal{B}$ is trivial.

---

## 3.6 The debt of a transition

Let us interpret the debt function in the context of belief space.

**Definition 3.23 (Debt of a transition).** For a transition $b_i \to b_j$, the *debt* is $D(b_i, b_j)$.

**Interpretation 3.24.** The debt $D(b_i, b_j)$ measures the change in a *potential* $\psi$ associated with the belief space. If $\psi(b)$ represents the "computational obligation" or "entropy" or "free energy" of belief $b$, then $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ is the change in that quantity when transitioning from $b_i$ to $b_j$.

- **Positive debt:** $D(b_i, b_j) > 0$. The transition increases the potential. The system takes on new obligations.
- **Negative debt:** $D(b_i, b_j) < 0$. The transition decreases the potential. The system pays down existing obligations.
- **Zero debt:** $D(b_i, b_j) = 0$. The transition preserves the potential. The system remains in equilibrium.

**Remark 3.25.** The interpretation of $\psi$ is deliberately left open. In different applications, $\psi$ may represent different quantities: entropy, free energy, computational obligation, information content, or something else. The theory does not depend on the interpretation. What matters is that $\psi$ exists and that $D$ is its coboundary.

**Proposition 3.26 (Debt of a path).** For a path $\gamma = (b_0, b_1, \dots, b_n)$, the total debt is

$$\sum_{k=0}^{n-1} D(b_k, b_{k+1}) = \psi(b_n) - \psi(b_0).$$

*Proof.* Telescoping. $\square$

**Corollary 3.27.** The total debt of a path depends only on the endpoints, not on the path itself.

*Proof.* Immediate from Proposition 3.26. $\square$

**Remark 3.28.** This is the fundamental property of debt. It is a *conservative* quantity: it depends only on the endpoints, not on the path. This is in contrast to the cost $d$, which is minimized over paths but is not itself path-independent (the cost of a specific path depends on the path; the minimum cost does not).

---

## 3.7 The debt-to-cost ratio

The debt $D$ and the cost $d$ together determine a natural ratio.

**Definition 3.29 (Debt-to-cost ratio).** For a transition $b_i \to b_j$ with $d(b_i, b_j) > 0$, the *debt-to-cost ratio* is

$$r(b_i, b_j) := \frac{D(b_i, b_j)}{d(b_i, b_j)}.$$

When $d(b_i, b_j) = 0$, the ratio is undefined (or infinite, if $D \neq 0$).

**Proposition 3.30.** The debt-to-cost ratio satisfies:

- **(i)** $r(b, b) = 0$;
- **(ii)** $r(b_i, b_j) = -r(b_j, b_i) \cdot \frac{d(b_j, b_i)}{d(b_i, b_j)}$;
- **(iii)** $r(b_i, b_j)$ is invariant under gauge transformations of $\psi$.

*Proof.* (i) $D(b, b) = 0$ and $d(b, b) = 0$, so the ratio is $0/0$; define it as $0$.

(ii) $r(b_i, b_j) = D(b_i, b_j)/d(b_i, b_j) = -D(b_j, b_i)/d(b_i, b_j) = -r(b_j, b_i) \cdot d(b_j, b_i)/d(b_i, b_j)$.

(iii) $D$ is gauge-invariant (Proposition 3.14), and $d$ is independent of $\psi$. $\square$

**Remark 3.31.** The ratio $r$ is dimensionless. It measures the "debt intensity" of a transition. A transition with $r = 0$ is pure cost (no debt). A transition with $|r| = \infty$ is pure debt (no cost). The ratio is a natural coordinate on the space of transitions.

**Remark 3.32.** In Chapter 6, we will see that the ratio $r$ is the tangent of the phase of the complex quasi-metric $Q = d + iD$. Specifically, $\arg Q = \arctan(r)$. This will connect the debt-to-cost ratio to the geometric structure of $Q$.

---

## 3.8 Why debt is the right object

We close this chapter with a reflection on why debt, rather than asymmetry, is the right object to study.

**The asymmetry $A$ is not additive.** As we saw in §3.2, $A(b_i, b_k) \neq A(b_i, b_j) + A(b_j, b_k)$ in general. The asymmetry of a composed transition is not the sum of the asymmetries of its parts. This means that $A$ does not telescope, does not define a path-independent quantity, and does not admit a potential.

**The debt $D$ is additive.** By axiom (D1), $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$. The debt of a composed transition *is* the sum of the debts of its parts. This means that $D$ telescopes, defines a path-independent quantity, and admits a potential (Chapter 4).

**The asymmetry $A$ is a 2-form.** It is a function on triangles, antisymmetric under vertex reversal. It measures the *curvature* of the cost.

**The debt $D$ is a 1-form.** It is a function on edges, antisymmetric under edge reversal. It measures the *gradient* of the potential.

**The relationship.** The asymmetry $A$ is the *derivative* of the debt $D$ in a suitable sense. Specifically, $A(b_i, b_j) = D(b_i, b_j) - D(b_j, b_i) + \text{correction terms}$ involving the symmetric part of $d$. The precise relationship will be made clear in Chapter 11, where we develop the polar decomposition of quasi-metrics.

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

We have also introduced the debt-to-cost ratio $r(b_i, b_j) = D(b_i, b_j)/d(b_i, b_j)$, which measures the "debt intensity" of a transition and will play a central role in the geometric theory of Chapter 6.

The central remaining question is: does every debt function arise from a potential? That is, given $D$ satisfying (D1) and (D2), does there exist $\psi : \mathcal{B} \to \mathbb{R}$ with $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$? The answer is yes, and the proof is the subject of Chapter 4.

---

## 3.10 Exercises

**Exercise 3.1.** Verify that the function $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ satisfies (D1) and (D2) for any $\psi : \mathcal{B} \to \mathbb{R}$.

**Exercise 3.2.** Give an example of a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$ that satisfies (D1) but not (D2). Give an example that satisfies (D2) but not (D1).

**Exercise 3.3.** Prove that if $D$ satisfies (D1) and (D2), then $D(b_i, b_j) = 0$ for all $b_i, b_j$ if and only if $D$ is identically zero.

**Exercise 3.4.** Let $\mathcal{B} = \{1, 2, 3\}$ and let $D$ be defined by

$$D(1, 2) = 2, \quad D(2, 3) = 3, \quad D(1, 3) = 5,$$

with $D$ extended by antisymmetry and $D(i, i) = 0$. Verify that $D$ satisfies (D1) and (D2). Find a potential $\psi$ such that $D = \delta\psi$.

**Exercise 3.5.** Let $\mathcal{B}$ be a set and let $D$ satisfy (D1) and (D2). Prove that for any basepoint $s_0 \in \mathcal{B}$, the function $\psi_{s_0}(b) := D(s_0, b)$ satisfies $D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)$.

**Exercise 3.6.** Show that the debt-to-cost ratio $r$ is invariant under the addition of a constant to $\psi$, but is *not* invariant under a general gauge transformation $\psi \mapsto \psi + \chi$ where $\chi$ is not constant.

**Exercise 3.7.** Let $\mathcal{B}$ be a finite set with $n$ elements. Show that the space of debt functions on $\mathcal{B}$ is isomorphic to $\mathbb{R}^{n-1}$.

**Exercise 3.8.** Prove that the asymmetry $A(b_i, b_j) = d(b_i, b_j) - d(b_j, b_i)$ is *not* a debt function in general. (Hint: find a counterexample to additivity.)

**Exercise 3.9.** Let $D$ be a debt function and let $c \in \mathbb{R}$. Show that $cD$ is also a debt function. What is the corresponding potential?

**Exercise 3.10.** Reflect on the following question: why is additivity the right axiom for debt, rather than some weaker condition? Write a short essay (one page) arguing for your position.

---

*In the next chapter, we prove the basepoint theorem: every debt function is a potential difference. The proof is constructive, and it shows that the potential can be recovered from any basepoint by a single evaluation.*

---

**End of Chapter 3.**
