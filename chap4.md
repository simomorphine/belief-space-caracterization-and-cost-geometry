# Chapter 4: Exactness and the Basepoint Theorem

---

In Chapter 3, we introduced the debt function $D$ through two axioms:

- **(D1) Additivity**
- **(D2) Antisymmetry**

From these axioms, we derived several consequences, including identity, cycle invariance, and path independence.

We also observed that any function of the form

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)$$

automatically satisfies the two debt axioms.

The central question of this chapter is the converse:

> **Does every debt function arise as the difference of a potential?**

The main result is the **basepoint theorem**. It gives an explicit construction of the potential from the debt function and shows that the potential is unique up to an additive constant.

This establishes that, on the state space considered in this book, every debt function is **exact**.

**Remark 4.0 (Scope of this chapter).** The basepoint theorem is purely algebraic. It requires only a set $\mathcal{B}$ and a function $D$ satisfying (D1) and (D2). No graph structure, topology, or metric is used. The path-based interpretation of debt from Chapter 3 is a special case; the theorem is stated and proved in the more general algebraic setting. The graph structure will return in Chapter 5, where the cohomological interpretation requires it.

**Remark 4.0.1 (Additivity is algebraic, not path-based).** The additivity axiom (D1) is stated for *all* triples $b_i, b_j, b_k \in \mathcal{B}$, not only for triples that lie on some path. This is a strong condition. It says that debt composes algebraically, regardless of whether the intermediate state is reachable or on a path. This is the right axiom for the algebraic theory developed here. A weaker, path-based version of additivity is possible—requiring the composition law only along paths—but the basepoint theorem as stated requires the full algebraic version. We flag this distinction because it matters for interpreting the theory: debt is not merely a path-dependent quantity; it is an algebraic 1-cochain.

---

## 4.1 The exactness question

Let $\mathcal{B}$ be a state space and let

$$D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$$

be a debt function satisfying (D1) and (D2).

We know from Chapter 3 that debt is path-independent. If

$$\gamma = (b_0, b_1, \ldots, b_n)$$

is a path from $b_0$ to $b_n$, then its total debt is

$$D(\gamma) = \sum_{k=0}^{n-1} D(b_k, b_{k+1}).$$

The path independence result tells us that

$$D(\gamma) = D(b_0, b_n).$$

This suggests that debt may not fundamentally depend on the transition itself. Instead, it may arise from a quantity attached to the states.

Suppose there exists a function

$$\psi : \mathcal{B} \to \mathbb{R}$$

such that

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

Then the debt between two states is simply the change in the value of $\psi$.

The function $\psi$ will be called a **potential**.

The question is therefore:

> Given a debt function $D$, can we construct such a potential $\psi$?

The answer is provided by the following theorem.

---

## 4.2 The basepoint theorem

### Theorem 4.1 (Basepoint theorem)

Let $\mathcal{B}$ be a nonempty set and let

$$D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$$

satisfy:

**(D1) Additivity:**
$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$$
for all $b_i, b_j, b_k \in \mathcal{B}$.

**(D2) Antisymmetry:**
$$D(b_i, b_j) = -D(b_j, b_i)$$
for all $b_i, b_j \in \mathcal{B}$.

Then for **any** choice of basepoint $s_0 \in \mathcal{B}$, the function

$$\psi_{s_0}(b) := D(s_0, b)$$

satisfies

$$\boxed{D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)}$$

for all $b_i, b_j \in \mathcal{B}$.

Furthermore, if another function $\phi : \mathcal{B} \to \mathbb{R}$ satisfies

$$D(b_i, b_j) = \phi(b_j) - \phi(b_i),$$

then there exists a constant $c \in \mathbb{R}$ such that

$$\phi = \psi_{s_0} + c.$$

Thus the potential exists and is unique up to an additive constant.

---

## 4.3 Proof of the basepoint theorem

The proof is constructive.

### Step 1: Choose a basepoint

Fix $s_0 \in \mathcal{B}$. Define

$$\psi_{s_0}(b) := D(s_0, b).$$

This assigns a real number to every state relative to the chosen basepoint.

In particular,

$$\psi_{s_0}(s_0) = D(s_0, s_0).$$

By Proposition 3.9 (identity), $D(s_0, s_0) = 0$. Therefore,

$$\psi_{s_0}(s_0) = 0.$$

The chosen basepoint fixes the additive normalization of the potential. This is a consequence of the construction, not a separate assumption.

---

### Step 2: Compute the difference between two potential values

For arbitrary $b_i, b_j \in \mathcal{B}$,

$$\psi_{s_0}(b_j) - \psi_{s_0}(b_i) = D(s_0, b_j) - D(s_0, b_i).$$

By antisymmetry,

$$D(s_0, b_i) = -D(b_i, s_0).$$

Therefore,

$$D(s_0, b_j) - D(s_0, b_i) = D(s_0, b_j) + D(b_i, s_0).$$

Now apply additivity to the triple $(b_i, s_0, b_j)$:

$$D(b_i, b_j) = D(b_i, s_0) + D(s_0, b_j).$$

Combining the two equations,

$$\psi_{s_0}(b_j) - \psi_{s_0}(b_i) = D(b_i, b_j).$$

Therefore,

$$\boxed{D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)}.$$

This proves the existence of a potential representation.

---

### Step 3: Uniqueness up to a constant

Suppose $\psi$ and $\phi$ are two potentials representing the same debt function:

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)$$

and

$$D(b_i, b_j) = \phi(b_j) - \phi(b_i).$$

Therefore,

$$\psi(b_j) - \psi(b_i) = \phi(b_j) - \phi(b_i).$$

Rearranging,

$$\psi(b_j) - \phi(b_j) = \psi(b_i) - \phi(b_i).$$

Since $b_i$ and $b_j$ are arbitrary,

$$\psi(b) - \phi(b)$$

has the same value at every point of $\mathcal{B}$. Therefore there exists a constant $c \in \mathbb{R}$ such that

$$\psi(b) - \phi(b) = c.$$

Hence,

$$\boxed{\psi = \phi + c}.$$

The potential is therefore unique up to an additive constant. $\square$

**Remark 4.2 (Zero debt).** If $D \equiv 0$, then any constant potential represents $D$. The basepoint construction gives $\psi_{s_0} \equiv 0$, which is the representative that vanishes at $s_0$.

**Remark 4.3 (Uniqueness in the algebraic setting).** In the algebraic setting of this chapter, the potential is unique up to a *single* constant, not a constant on each connected component. This is because additivity is required for all triples, which forces the potential differences to be consistent across the entire set $\mathcal{B}$. When we restrict to a graph structure in Chapter 5, the uniqueness will be up to a constant on each connected component of the graph.

---

## 4.4 Consequences for paths

The potential representation makes the path structure transparent.

Let

$$\gamma = (b_0, b_1, \ldots, b_n)$$

be a path. Its total debt is

$$D(\gamma) = \sum_{k=0}^{n-1} D(b_k, b_{k+1}).$$

Using the potential representation,

$$D(b_k, b_{k+1}) = \psi(b_{k+1}) - \psi(b_k).$$

Therefore,

$$D(\gamma) = \sum_{k=0}^{n-1} \left[\psi(b_{k+1}) - \psi(b_k)\right].$$

The sum telescopes:

$$\boxed{D(\gamma) = \psi(b_n) - \psi(b_0)}.$$

The total debt of a path depends only on its endpoints.

### Corollary 4.4 (Path independence)

If $\gamma_1$ and $\gamma_2$ are two paths with the same initial state and final state, then

$$D(\gamma_1) = D(\gamma_2).$$

*Proof.* Suppose both paths start at $b_0$ and end at $b_n$. Then

$$D(\gamma_1) = \psi(b_n) - \psi(b_0) = D(\gamma_2). \quad \square$$

### Corollary 4.5 (Zero debt around closed paths)

For every closed path $\gamma$,

$$\boxed{D(\gamma) = 0}.$$

*Proof.* If $\gamma = (b_0, b_1, \ldots, b_n)$ with $b_n = b_0$, then

$$D(\gamma) = \psi(b_n) - \psi(b_0) = \psi(b_0) - \psi(b_0) = 0. \quad \square$$

This is the discrete analogue of the fact that an exact differential has zero integral around a closed path.

---

## 4.5 Change of basepoint

The potential constructed from one basepoint can be compared directly with the potential constructed from another.

### Proposition 4.6 (Change of basepoint)

Let $s_0, s_1 \in \mathcal{B}$ be two basepoints. Define

$$\psi_{s_0}(b) = D(s_0, b), \qquad \psi_{s_1}(b) = D(s_1, b).$$

Then

$$\boxed{\psi_{s_1}(b) = \psi_{s_0}(b) + D(s_1, s_0)}$$

for every $b \in \mathcal{B}$.

*Proof.* By additivity,

$$D(s_1, b) = D(s_1, s_0) + D(s_0, b).$$

Therefore,

$$\psi_{s_1}(b) = D(s_1, s_0) + \psi_{s_0}(b).$$

Since $D(s_1, s_0)$ does not depend on $b$, the two potentials differ only by a constant. $\square$

**Remark 4.7 (Basepoint as gauge choice).** The basepoint is therefore a **gauge choice**. Different basepoints produce different numerical representations of the potential, but they all represent exactly the same debt function. This is the first appearance of the gauge structure that will be developed systematically in Part III.

---

## 4.6 Exactness and the cohomological interpretation

We can now introduce the term **exact**.

A debt function is called **exact** if there exists a potential

$$\psi : \mathcal{B} \to \mathbb{R}$$

such that

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i).$$

The basepoint theorem gives the following result.

### Corollary 4.8 (Exactness of debt)

Every debt function on $\mathcal{B}$ is exact.

*Proof.* The basepoint theorem constructs a potential

$$\psi_{s_0}(b) = D(s_0, b)$$

satisfying $D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)$. Therefore $D$ is exact. $\square$

**Remark 4.9 (Cohomological language).** The result of Corollary 4.8 can be restated in the language of cohomology. We introduce this language informally here; it will be developed systematically in Chapter 5.

- A **0-cochain** is a function $\psi : \mathcal{B} \to \mathbb{R}$.
- A **1-cochain** is a function $D : \mathcal{B} \times \mathcal{B} \to \mathbb{R}$.
- The **coboundary operator** $\delta$ takes a 0-cochain $\psi$ to the 1-cochain $\delta\psi$ defined by
$$(\delta\psi)(b_i, b_j) := \psi(b_j) - \psi(b_i).$$
- A 1-cochain $D$ is a **cocycle** if $\delta D = 0$, where $\delta D$ is the 2-cochain defined by
$$(\delta D)(b_i, b_j, b_k) := D(b_j, b_k) - D(b_i, b_k) + D(b_i, b_j).$$
- A 1-cochain $D$ is a **coboundary** if $D = \delta\psi$ for some 0-cochain $\psi$.

In this language:

- **Additivity (D1) is the cocycle condition $\delta D = 0$.** Indeed, $\delta D = 0$ means
$$D(b_j, b_k) - D(b_i, b_k) + D(b_i, b_j) = 0,$$
which rearranges to $D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k)$.
- **The basepoint theorem says that every 1-cocycle is a 1-coboundary.** That is, $H^1(\mathcal{B}; \mathbb{R}) = 0$ for the trivial cochain complex on $\mathcal{B}$.
- **The uniqueness up to a constant says that the kernel of $\delta$ on 0-cochains is the constant functions.** That is, $H^0(\mathcal{B}; \mathbb{R}) = \mathbb{R}$.

This cohomological framing will be the starting point of Chapter 5.

**Remark 4.10 (Poincaré lemma, not the fundamental theorem of calculus).** The basepoint theorem is sometimes compared to the fundamental theorem of calculus. The analogy is suggestive but not quite right. The fundamental theorem of calculus relates differentiation and integration—two operations that are inverses of each other. The basepoint theorem relates a function on pairs (debt) to a function on points (potential) via a difference operator. There is no integration involved.

A better analogy is the **Poincaré lemma** for 1-forms on a simply connected space: every closed 1-form is exact. In the discrete setting, additivity is the "closed" condition ($\delta D = 0$), and the basepoint theorem says that on a connected graph, every closed 1-cochain is exact ($D = \delta\psi$). The state space $\mathcal{B}$ plays the role of a simply connected space; the additivity axiom guarantees that there are no "holes" in the cochain complex.

---

## 4.7 Examples

### Example 4.11 (Finite example)

Consider the state space $\mathcal{B} = \{b_1, b_2, b_3\}$. Suppose

$$D(b_1, b_2) = 2, \qquad D(b_2, b_3) = 3.$$

By additivity,

$$D(b_1, b_3) = D(b_1, b_2) + D(b_2, b_3) = 5.$$

By antisymmetry,

$$D(b_2, b_1) = -2, \qquad D(b_3, b_2) = -3, \qquad D(b_3, b_1) = -5.$$

Choose $s_0 = b_1$. The basepoint potential is

$$\psi(b_1) = D(b_1, b_1) = 0, \qquad \psi(b_2) = D(b_1, b_2) = 2, \qquad \psi(b_3) = D(b_1, b_3) = 5.$$

The entire debt function is reconstructed from the potential

$$\psi : b_1 \mapsto 0, \quad b_2 \mapsto 2, \quad b_3 \mapsto 5.$$

### Example 4.12 (General finite construction)

Suppose $\mathcal{B} = \{b_1, \ldots, b_n\}$. Choose $s_0 = b_1$. Then the potential is simply

$$\psi(b_i) = D(b_1, b_i).$$

Thus the values $D(b_1, b_1), D(b_1, b_2), \ldots, D(b_1, b_n)$ determine the entire debt function:

$$D(b_i, b_j) = D(b_1, b_j) - D(b_1, b_i).$$

Therefore, once the debt relative to one reference state is known, all pairwise debt values are determined.

If $|\mathcal{B}| = n$, the potential has $n$ values, but one additive constant is irrelevant. Thus only $n - 1$ independent real parameters are required to specify a debt function. This is an important reduction in the number of independent quantities.

### Example 4.13 (Thermodynamic debt)

Let $\mathcal{B}$ be the set of thermodynamic states of a system, and let $\psi(b)$ be the free energy of state $b$. Then

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)$$

is the change in free energy. It is additive and antisymmetric. The basepoint theorem says that any debt function on $\mathcal{B}$ has this form—there is always a state function whose differences are the debts. In the thermodynamic case, this state function is the free energy itself.

### Example 4.14 (Computational debt)

Let $\mathcal{B}$ be the set of configurations of a reversible computer, and let $\psi(b)$ be the number of bits set to $1$ in configuration $b$. Then

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)$$

is the net change in the number of $1$ bits. Again, debt is a potential difference.

---

## 4.8 What assumptions were actually used?

It is useful to be precise about the scope of the theorem.

The proof did **not** require:

- a metric on $\mathcal{B}$;
- a topology on $\mathcal{B}$;
- a graph structure on $\mathcal{B}$;
- a vector-space structure on $\mathcal{B}$;
- differentiability;
- continuity;
- probability;
- finite cardinality.

The proof used only:

1. a nonempty state space;
2. a real-valued debt function;
3. the debt axioms (D1) and (D2).

The state space may therefore be finite or infinite. It may be discrete or continuous. The theorem concerns the algebraic structure of the debt function, not the geometric structure of the underlying state space.

This distinction will become important later when we combine debt with the energy quasi-metric.

---

## 4.9 Potential representation is not an additional axiom

It is important not to add the potential representation as a third axiom.

We began with

$$\text{(D1) Additivity} \qquad \text{and} \qquad \text{(D2) Antisymmetry}.$$

The basepoint theorem proves that

$$D(b_i, b_j) = \psi(b_j) - \psi(b_i)$$

follows from those assumptions.

Therefore the potential representation is a **theorem**, not an independent assumption. This distinction matters for the logical structure of the theory. We can summarize it as

$$\boxed{\text{D1 + D2} \Longrightarrow \text{potential representation}}$$

rather than

$$\text{D1 + D2 + potential representation}.$$

The latter would introduce unnecessary redundancy.

---

## 4.10 Summary

Chapter 3 introduced the debt function through two axioms:

$$D(b_i, b_k) = D(b_i, b_j) + D(b_j, b_k) \qquad \text{(Additivity)}$$

and

$$D(b_i, b_j) = -D(b_j, b_i) \qquad \text{(Antisymmetry)}.$$

Chapter 4 established the converse relationship between debt and potential.

For any basepoint $s_0 \in \mathcal{B}$, define

$$\psi_{s_0}(b) = D(s_0, b).$$

Then

$$\boxed{D(b_i, b_j) = \psi_{s_0}(b_j) - \psi_{s_0}(b_i)}.$$

Therefore every debt function is exact.

The potential is unique up to an additive constant:

$$\psi'(b) = \psi(b) + c.$$

Changing the basepoint produces precisely such a constant shift.

The potential representation also makes path independence transparent:

$$D(\gamma) = \psi(b_{\text{final}}) - \psi(b_{\text{initial}}).$$

Consequently, every closed path has zero total debt.

The main structural result of the chapter can therefore be summarized as

$$\boxed{\text{Debt} = \text{difference of a potential}}.$$

In the next chapter, we will investigate this structure more deeply. In particular, we will develop the cohomological interpretation sketched in Remark 4.9 and ask an important logical question:

> **Are both debt axioms actually necessary, or is one sufficient to generate the entire structure?**

---

## 4.11 Exercises

**Exercise 4.1 — Constructing the potential.** Let $\mathcal{B} = \{b_1, b_2, b_3, b_4\}$ and suppose $D$ is a debt function. Choose $b_1$ as the basepoint and define $\psi(b) = D(b_1, b)$. Show directly that $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ for every pair of states.

**Exercise 4.2 — Explicit potential.** Let $D(i, j) = i^2 - j^2$ on $\mathcal{B} = \{1, 2, 3, 4\}$.

1. Verify that $D$ satisfies (D1).
2. Verify that $D$ satisfies (D2).
3. Choose $s_0 = 1$.
4. Compute $\psi_{s_0}(i)$.
5. Verify that $D(i, j) = \psi_{s_0}(j) - \psi_{s_0}(i)$.

**Exercise 4.3 — Change of basepoint.** Let $D$ be a debt function and let $s_0, s_1 \in \mathcal{B}$. Define $\psi_{s_0}(b) = D(s_0, b)$ and $\psi_{s_1}(b) = D(s_1, b)$. Prove that $\psi_{s_1}(b) = \psi_{s_0}(b) + D(s_1, s_0)$. Explain why the difference between the two potentials does not depend on $b$.

**Exercise 4.4 — Uniqueness.** Suppose $\psi$ and $\phi$ satisfy $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$ and $D(b_i, b_j) = \phi(b_j) - \phi(b_i)$. Prove that there exists $c \in \mathbb{R}$ such that $\phi = \psi + c$.

**Exercise 4.5 — Closed paths.** Let $\gamma = (b_0, b_1, \ldots, b_n)$ be a closed path, so that $b_n = b_0$. Using the potential representation, prove that $D(\gamma) = 0$.

**Exercise 4.6 — Path independence.** Let $\gamma_1$ and $\gamma_2$ be two paths with the same initial state and final state. Use the potential representation to prove that $D(\gamma_1) = D(\gamma_2)$. Explain why no minimization over paths is necessary.

**Exercise 4.7 — Recovering the debt function.** Suppose $\mathcal{B} = \{b_1, b_2, b_3\}$ and $\psi(b_1) = 1$, $\psi(b_2) = 4$, $\psi(b_3) = -2$. Compute $D(b_1, b_2)$, $D(b_2, b_3)$, and $D(b_3, b_1)$. Verify that the resulting function satisfies both debt axioms.

**Exercise 4.8 — Gauge transformation.** Let $D(b_i, b_j) = \psi(b_j) - \psi(b_i)$. Define $\psi'(b) = \psi(b) + c$ for some constant $c$. Prove that $\psi'$ generates exactly the same debt function. Then consider $\psi'(b) = \psi(b) + \chi(b)$ where $\chi$ is not constant. Under what condition on $\chi$ does $\psi'$ generate the same debt function? (Hint: the condition is that $\chi(b_j) - \chi(b_i) = 0$ for all $b_i, b_j$. What does this imply about $\chi$?)

**Exercise 4.9 — Number of independent values.** Let $\mathcal{B}$ contain $n$ states. Using the basepoint construction, explain why a debt function is completely determined by its values relative to one chosen basepoint. How many independent real parameters are required? Prove that no fewer than $n - 1$ parameters suffice. (Hint: consider the kernel of the map $\psi \mapsto \delta\psi$.)

**Exercise 4.10 — Infinite state spaces.** Prove that the basepoint theorem does not require $\mathcal{B}$ to be finite. Identify every step of the proof and explain why the argument remains valid when $\mathcal{B}$ is infinite.

**Exercise 4.11 — Cohomological language.** Using the definitions in Remark 4.9, verify the following:

1. The coboundary of a 0-cochain $\psi$ is the 1-cochain $(\delta\psi)(b_i, b_j) = \psi(b_j) - \psi(b_i)$.
2. The cocycle condition $\delta D = 0$ for a 1-cochain $D$ is equivalent to additivity (D1).
3. The basepoint theorem says that every 1-cocycle is a 1-coboundary.
4. The kernel of $\delta$ on 0-cochains is the constant functions.

**Exercise 4.12 — Zero debt function.** Let $D \equiv 0$ on $\mathcal{B}$. Verify that $D$ satisfies (D1) and (D2). What is the basepoint potential $\psi_{s_0}$? Show that every constant potential represents $D$, and that the basepoint construction gives the representative that vanishes at $s_0$.

**Exercise 4.13 — Poincaré lemma.** Compare the basepoint theorem to the Poincaré lemma for 1-forms on a simply connected space. In what sense is the basepoint theorem a discrete analogue of the Poincaré lemma? What role does the state space $\mathcal{B}$ play? What role does additivity play?

**Exercise 4.14 — Conceptual question.** The debt function was introduced independently of any potential. After proving the basepoint theorem, should we regard the potential or the debt function as the more fundamental object? Give arguments for both viewpoints. Do not assume that the theorem itself decides this philosophical question.
