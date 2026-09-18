# Chapter 1: Cost Is Not a Metric

---

Cost is not a metric. This is not a scandal, and it is not noise. It is structure.

The standard assumption in information processing is that the cost of moving between two states is a metric: symmetric, non-negative, and satisfying the triangle inequality. The assumption is almost always false. Costs are asymmetric—uploading and downloading are not the same. Costs violate the triangle inequality—bulk discounts, fixed fees, and amortization make the direct path more expensive than a detour. Costs are path-dependent—the same transition costs different amounts depending on history.

And yet the failures are not random. They have a shape. This book is about that shape.

---

## 1.1 The metric assumption

Let us begin with what everyone assumes.

When we model an information processing system—a computer, a brain, a market, a belief—we typically assign to each pair of states a number representing the cost of moving between them. Call the set of states $\mathcal{B}$, and call the cost function $d : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$.

The standard assumptions are:

- **Non-negativity.** $d(b_i, b_j) \ge 0$ for all $b_i, b_j$.
- **Identity.** $d(b, b) = 0$ for all $b$.
- **Symmetry.** $d(b_i, b_j) = d(b_j, b_i)$ for all $b_i, b_j$.
- **Triangle inequality.** $d(b_i, b_k) \le d(b_i, b_j) + d(b_j, b_k)$ for all $b_i, b_j, b_k$.

When all four hold, $d$ is a **metric**, and the pair $(\mathcal{B}, d)$ is a **metric space**. Metric spaces are the foundation of geometry, topology, analysis, and virtually every algorithm that involves distance.

The metric assumption is so pervasive that it is rarely stated. It is absorbed into the language. We say "the cost of moving from $A$ to $B$" as though there were a single well-defined number, the same in both directions, satisfying the usual inequalities. We say "near" and "far" as though these were symmetric relations.

But they are not. And the failures are not small.

---

## 1.2 What survives

Not all of the metric axioms fail equally. Three of them survive almost everywhere; one does not.

**Non-negativity survives.** Cost is never negative. You cannot pay a negative amount to move from one state to another. This is not a deep fact—it is a convention about what we mean by "cost"—but it is a robust one.

**Identity survives.** Not updating—staying in the same state—costs nothing. The transition from $b$ to $b$ is free. This, too, is a convention, but a natural one: if there is no change, there is nothing to pay for.

**Symmetry fails.** The cost of going from $b_i$ to $b_j$ need not equal the cost of going from $b_j$ to $b_i$. Uploading and downloading are not the same. Encrypting and decrypting are not the same. Buying and selling are not the same. The bid-ask spread is precisely the statement that $d(A, B) \neq d(B, A)$.

**The triangle inequality fails.** The cost of going directly from $b_i$ to $b_k$ need not be bounded by the cost of going through an intermediate state $b_j$. Sometimes the direct path is *more* expensive than a detour—fixed fees, setup costs, minimum charges. Sometimes it is *cheaper*—bulk discounts, economies of scale, amortization.

So the situation is this: cost satisfies non-negativity and identity, but not symmetry and not the triangle inequality.

A function satisfying non-negativity, identity, and the triangle inequality—but not symmetry—is called a **quasi-metric**. A function satisfying non-negativity, identity, and symmetry—but allowing distinct points at zero distance—is called a **pseudometric**. A function satisfying all three of non-negativity, identity, and the triangle inequality, but with the triangle inequality holding only *up to a correction*, is a **pseudo-quasi-metric with defect**.

That defect is what this book is about.

---

## 1.3 The probabilistic question

Here is the question that motivates everything that follows.

*Under what condition is cost a pseudo-quasi-metric?*

The answer is not "always" and not "never." It is probabilistic.

**Cost is a pseudo-quasi-metric with probability $\alpha$, and fails to be one with probability $1 - \alpha$.**

When the triangle inequality holds—when cost *is* a pseudo-quasi-metric—nothing extra is needed. The cost function is what it appears to be: a number, positive, zero on the diagonal, satisfying the triangle inequality, asymmetric but otherwise well-behaved.

When the triangle inequality fails—when cost is *not* a pseudo-quasi-metric—something else appears. A correction emerges. The cost function is no longer a single number; it is a number *plus a residual*. The residual measures the extent of the failure.

We call that residual **debt**.

$$\text{cost} \longrightarrow \text{cost} + i \cdot \text{debt}.$$

The real part is the usual cost. The imaginary part is the correction that emerges when the triangle inequality fails. The complex number is not a decoration. It is the natural packaging of "cost, together with the amount by which cost fails to be a quasi-metric."

---

## 1.4 Why debt is imaginary

A natural question: why $i$? Why not simply treat cost and debt as two real numbers, a pair $(c, D) \in \mathbb{R}^2$?

There are three answers, and they are the same three that will recur throughout the book.

**First: the failure has a sign.** Debt is not just a magnitude. When the triangle inequality fails, it fails in one of two directions. It can fail *subadditively*—the direct path is more expensive than the detour, $d(b_i, b_k) > d(b_i, b_j) + d(b_j, b_k)$—or *superadditively*—the direct path is cheaper than the detour, $d(b_i, b_k) < d(b_i, b_j) + d(b_j, b_k)$. These are not the same failure. They have opposite signs. Debt must be a signed quantity, and the sign must be meaningful.

**Second: the correction is antisymmetric.** Debt is not a symmetric relation. If going from $b_i$ to $b_j$ incurs debt $D(b_i, b_j)$, then going from $b_j$ to $b_i$ incurs debt $-D(b_i, b_j)$. Debt reverses sign under reversal of the transition. This is exactly the defining property of the imaginary unit: $i$ changes sign under complex conjugation, and the imaginary part of $Q$ is antisymmetric whenever the real part is symmetric.

**Third: the modulus is a metric.** The quantity $|Q| = \sqrt{c^2 + D^2}$ satisfies the triangle inequality whenever $c$ and $D$ do. This is not true for an arbitrary pair of numbers; it is true because $\mathbb{R}^2$ with the Euclidean norm is a normed space. The complex structure provides the Euclidean norm naturally, and the Euclidean norm is what makes the triangle inequality work. If cost alone fails the triangle inequality, the modulus of the complex cost may still satisfy it—and when it does, that is a genuine theorem, not a convention.

Together, these three facts mean that the complex structure is not a choice. It is what the structure of cost and debt *wants* to be.

---

## 1.5 Why this is not noise

It would be easy to treat the failures of the metric assumption as defects—as noise to be averaged away, or as pathologies to be assumed absent.

But the failures are not random. They have a shape. And the shape is the same in every case.

**Asymmetry** is a statement about the *direction* of a transition. It says that the cost of going one way is not the cost of going the other. This is a statement about a **1-form**: a function that assigns a number to each directed edge, with the property that reversing the edge changes the sign.

**Non-triangularity** is a statement about the *composition* of transitions. It says that the cost of going directly is not the sum of the costs of going indirectly. The discrepancy—the amount by which the triangle inequality fails—is a **2-form**: a function that assigns a number to each triangle, antisymmetric under the reversal of its vertices.

**Path-dependence** is a statement about the *integrability* of the cost. It says that the cost of a path is not determined by its endpoints. The obstruction to integrability is a **curvature**: a function that assigns a number to each loop, invariant under deformations that do not cross singularities.

**Non-identity** is a statement about the *kernel* of the cost. It says that there are states at zero distance that are not the same state. The equivalence classes are the level sets of a **potential**: a function that assigns a number to each state, with the property that zero-cost transitions are exactly those that preserve the number.

In each case, the failure is not noise. It is structure. And the structure is the structure of **differential forms**.

---

## 1.6 The thesis of this book

The thesis of this book is that cost is not a scalar. It is the real part of a complex object:

$$Q(b_i, b_j) = \text{cost}(b_i, b_j) + i \cdot \text{debt}(b_i, b_j).$$

The real part is the usual cost. The imaginary part is debt—the correction that emerges when cost fails to be a pseudo-quasi-metric.

Debt is not a defect. It is a **potential difference**. It is exact, antisymmetric, additive, gauge-invariant, and cycle-cancelling. It is, in the technical sense, a **coboundary**: the image of a potential function under the discrete exterior derivative.

And once you see this, the whole structure falls into place. The asymmetry of cost becomes a polar decomposition. The triangle inequality becomes a Minkowski inequality in $\mathbb{R}^2$. The topology of the space becomes a lattice of four topologies. The gauge freedom becomes an $\mathbb{R}$-action. The complex structure becomes a $\mathbb{Z}/2$-grading.

None of this is imposed. It is discovered. The structure was always there. It was just hidden in the assumption that cost is a scalar.

---

## 1.7 What this book is not

This book is not about applications. It is not about neural networks, or quantum computing, or thermodynamics of computation, or any of the other fields where cost is a central concept. Those connections exist, and they are interesting, but they are not the point.

This book is about the mathematics. It is about the structure of cost when cost is not a metric. It is about the complex quasi-metric, the debt function, the $\gamma$-family, the topology lattice, the equilibrium hierarchy, the $\mathbb{Z}/2$-grading, and the categorical picture.

It is a book of theorems and proofs. Every statement is either a definition, a proposition, a theorem, or a corollary. Every proof is complete. Every construction is canonical.

The goal is not to be useful. The goal is to be **true and beautiful**, and to let the structure speak for itself.

---


## 1.9 Exercises

**Exercise 1.1.** Give an example of a cost function on a finite set that is asymmetric. Compute $d(b_i, b_j)$ and $d(b_j, b_i)$ for all pairs, and verify that $d$ is a quasi-metric but not a metric.

**Exercise 1.2.** Give an example of a cost function that violates the triangle inequality in the subadditive direction. Verify that $d(b_i, b_k) > d(b_i, b_j) + d(b_j, b_k)$ for some triple.

**Exercise 1.3.** Give an example of a cost function that violates the triangle inequality in the superadditive direction. Verify that $d(b_i, b_k) < d(b_i, b_j) + d(b_j, b_k)$ for some triple.

**Exercise 1.4.** Give an example of a pseudometric that is not a metric.

**Exercise 1.5.** For each of the four failures described in §1.5, give a real-world example of an information processing system exhibiting that failure.

**Exercise 1.6.** Prove that if $d$ is a quasi-metric on $\mathcal{B}$, then the symmetrization $d_{\text{avg}}(b_i, b_j) := \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i))$ is a pseudometric.

**Exercise 1.7.** Prove that if $d$ is a quasi-metric, then the asymmetry $\alpha(b_i, b_j) := \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i))$ is antisymmetric and vanishes on the diagonal. (Note the factor of $\tfrac{1}{2}$: this is the canonical normalization for a 1-form.)

**Exercise 1.8.** Show that the decomposition $d = S + \alpha$, where $S$ is the symmetrization and $\alpha$ is the asymmetry defined in Exercise 1.7, is unique.

**Exercise 1.9.** Give an example of a cost function that is path-dependent. Show that in this case, the cost of a transition is not a function of the endpoints alone.

**Exercise 1.10.** Suppose cost is a pseudo-quasi-metric with probability $\alpha$. Define the debt $D(b_i, b_j)$ as the expected violation of the triangle inequality along the transition from $b_i$ to $b_j$. Show that $D$ is antisymmetric and vanishes on the diagonal.

**Exercise 1.11.** Reflect on the following question: is the metric assumption a *modeling choice* or a *fact about the world*? Write a short essay (one page) arguing for your position.
