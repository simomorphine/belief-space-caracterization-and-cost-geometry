# Chapter 1: Cost Is Not a Metric

---

Textbooks say [cost](https://en.wikipedia.org/wiki/Cost) is *like* a metric. They do not say cost *is* a metric.

The distinction matters. "Like a metric" means: we will use the metric apparatus as a model, knowing it is an approximation, and we will not be held responsible for the cases where it breaks. "Is a metric" means: the four axioms hold, and any failure is an error in your analysis.

The hedge is honest. It is also unnamed. Textbooks say "like a metric" because they do not have a language for what cost actually is. They know the metric axioms fail. They know the failure is not noise. But they have no framework for the failure, so they retreat to approximation.

This book supplies the framework. The hedge was pointing at something real. That something is **debt**, and the object that carries it is a **complex quasi-metric**.

Cost is not a metric. This is not a scandal, and it is not noise. It is structure. This book is about that structure.

---

## 1.1 The metric assumption

Let us begin with what the textbook says.

When we model an information processing system—a computer, a brain, a market, a belief—we typically assign to each pair of states a number representing the cost of moving between them. Call the set of states $\mathcal{B}$, and call the cost function $C : \mathcal{B} \times \mathcal{B} \to \mathbb{R}_{\ge 0}$.

The textbook then says: treat $C$ *like* a metric. That is, **assume**, for the purposes of the model:

- **Non-negativity.** $d(b_i, b_j) \ge 0$ for all $b_i, b_j$.
- **Identity.** $d(b, b) = 0$ for all $b$.
- **Symmetry.** $d(b_i, b_j) = d(b_j, b_i)$ for all $b_i, b_j$.
- **Triangle inequality.** $d(b_i, b_k) \le d(b_i, b_j) + d(b_j, b_k)$ for all $b_i, b_j, b_k$.

When all four hold, $d$ is a **metric**, and the pair $(\mathcal{B}, d)$ is a **metric space**. Metric spaces are the foundation of geometry, topology, analysis, and virtually every algorithm that involves distance.

The textbook knows these four assumptions do not all hold. It says "like a metric" precisely because it knows. But it does not say *which* assumptions fail, or *how*, or *what takes their place*. It leaves the "like" unanalyzed.

This book analyzes the "like."

---

## 1.2 What survives

Not all of the metric axioms fail equally. Three of them survive almost everywhere; one does not.

**Non-negativity survives.** Cost is never negative. You cannot pay a negative amount to move from one state to another. This is not a deep fact—it is a convention about what we mean by "cost"—but it is a robust one.

**Identity survives.** Not updating—staying in the same state—costs nothing. The transition from $b$ to $b$ is free. If there is no change, there is nothing to pay for.

**Symmetry fails.** The cost of going from $b_i$ to $b_j$ need not equal the cost of going from $b_j$ to $b_i$. Uploading and downloading are not the same. Encrypting and decrypting are not the same. Buying and selling are not the same. The bid-ask spread—where the ask price $A$ exceeds the bid price $B$—is precisely the statement that $d(A, B) \neq d(B, A)$.

**The triangle inequality fails.** The cost of going directly from $b_i$ to $b_k$ need not be bounded by the cost of going through an intermediate state $b_j$. Sometimes the direct path is *more* expensive than a detour—fixed fees, setup costs, minimum charges. Sometimes it is *cheaper*—bulk discounts, economies of scale, amortization.

So the situation is this: cost satisfies non-negativity and identity, but not symmetry and not the triangle inequality.

The objects that result when these axioms fail have standard names:

- A function satisfying non-negativity, identity, and the triangle inequality—but not symmetry—is called a **quasi-metric**.
- A function satisfying non-negativity, identity, and symmetry—but allowing distinct points at zero distance—is called a **pseudometric**.
- A function satisfying non-negativity, identity, and the triangle inequality—but allowing distinct points at zero distance—is called a **pseudo-quasi-metric**.
- A function satisfying non-negativity and identity, but neither symmetry nor the triangle inequality, is a **pseudo-quasi-metric with defect**.

The last object is the one that describes cost. Its defect is what this book is about.

**Remark 1.1.** The terminology is not perfectly standardized across the literature. Some authors use "quasi-metric" to mean what we call a "pseudo-quasi-metric," and some use "pseudometric" for what we call a "pseudometric" only when symmetry holds. Throughout this book we will use the definitions above, and we will flag any place where a result depends on the distinction.

---

## 1.3 The probabilistic question

Here is the question that motivates everything that follows.

*Under what condition is cost a pseudo-quasi-metric?*

The textbook's answer is: approximately always, in the regimes we care about. The hedge is that the approximation is good enough.

Our answer is different. The condition is not "approximately always." It is probabilistic.

**Cost is a pseudo-quasi-metric with probability $\alpha$, and fails to be one with probability $1 - \alpha$.**

Here $\alpha$ is a parameter of the model, not a claim about a random process. It measures the fraction of transitions for which the triangle inequality holds—or, more precisely, the measure of the set of triples $(b_i, b_j, b_k)$ for which the triangle inequality is satisfied, under whatever measure the analyst chooses to place on the belief space. The choice of measure is part of the modeling, and different choices give different values of $\alpha$. The framework developed in this book is compatible with any such choice; what matters is that $\alpha < 1$ in general, and that the $1 - \alpha$ part has structure.

When the triangle inequality holds—when cost *is* a pseudo-quasi-metric—nothing extra is needed. The cost function is what it appears to be: a number, positive, zero on the diagonal, satisfying the triangle inequality, asymmetric but otherwise well-behaved.

When the triangle inequality fails—when cost is *not* a pseudo-quasi-metric—something else appears. A correction emerges. The cost function is no longer a single number; it is a number *plus a residual*. The residual measures the extent of the failure.

We call that residual **debt**.

$$\text{cost} \longrightarrow \text{cost} + i \cdot \text{debt}.$$

The real part is the usual cost. The imaginary part is the correction that emerges when the triangle inequality fails. The complex number is not a decoration. It is the natural packaging of "cost, together with the amount by which cost fails to be a quasi-metric."

The textbook's "like a metric" is the statement that $\alpha$ is close to $1$. Our framework is the statement that the residual—the $1 - \alpha$ part—has a name, a sign, and a structure.

---

## 1.4 Why debt is imaginary

A natural question: why $i$? Why not simply treat cost and debt as two real numbers, a pair $(c, D) \in \mathbb{R}^2$?

There are three answers, and they are the same three that will recur throughout the book.

**First: the failure has a sign.** Debt is not just a magnitude. When the triangle inequality fails, it fails in one of two directions. It can fail *subadditively*—the direct path is more expensive than the detour, $d(b_i, b_k) > d(b_i, b_j) + d(b_j, b_k)$—or *superadditively*—the direct path is cheaper than the detour, $d(b_i, b_k) ≪ d(b_i, b_j) + d(b_j, b_k)$. These are not the same failure. They have opposite signs. Debt must be a signed quantity, and the sign must be meaningful.

**Second: the correction is antisymmetric.** Debt is not a symmetric relation. If going from $b_i$ to $b_j$ incurs debt $D(b_i, b_j)$, then going from $b_j$ to $b_i$ incurs debt $-D(b_i, b_j)$. This antisymmetry is not an arbitrary convention; it is forced by the requirement that debt be *additive around cycles*, which will be stated as an axiom in Chapter 3. The intuition is that if you traverse a cycle and return to your starting point, the debts incurred along the way must cancel. This is exactly the defining property of the imaginary unit: $i$ changes sign under complex conjugation, and the imaginary part of $Q$ is antisymmetric whenever the real part is symmetric.

**Third: the modulus is a metric.** The quantity $|Q| = \sqrt{c^2 + D^2}$ satisfies the triangle inequality whenever $c$ and $D$ do. This is not true for an arbitrary pair of numbers; it is true because $\mathbb{R}^2$ with the Euclidean norm is a normed space. The complex structure provides the Euclidean norm naturally, and the Euclidean norm is what makes the triangle inequality work. If cost alone fails the triangle inequality, the modulus of the complex cost may still satisfy it—and when it does, that is a genuine theorem, not a convention.

Together, these three facts mean that the complex structure is not a choice. It is what the structure of cost and debt *wants* to be.

---

## 1.5 Why the failures are structured

It would be easy to treat the failures of the metric assumption as defects—as noise to be averaged away, or as pathologies to be assumed absent. The textbook's hedge is a version of this: assume them absent, and trust that the assumption is good enough.

But the failures are not random. They have a shape. And the shape is the same in every case.

**Asymmetry** is a statement about the *direction* of a transition. It says that the cost of going one way is not the cost of going the other. This is a statement about a **1-form**: a function that assigns a number to each directed edge, with the property that reversing the edge changes the sign.

**Non-triangularity** is a statement about the *composition* of transitions. It says that the cost of going directly is not the sum of the costs of going indirectly. The discrepancy—the amount by which the triangle inequality fails—is a **2-form**: a function that assigns a number to each triangle, antisymmetric under the reversal of its vertices.

**Path-dependence** is a statement about the *integrability* of the cost. It says that the cost of a path is not determined by its endpoints. The obstruction to integrability is a **curvature**: a function that assigns a number to each loop, invariant under deformations that do not cross singularities.

**Non-identity** is a statement about the *kernel* of the cost. It says that there are states at zero distance that are not the same state. The equivalence classes are the level sets of a **potential**: a function that assigns a number to each state, with the property that zero-cost transitions are exactly those that preserve the number.

In each case, the failure is not noise. It is structure. And the structure is the structure of **differential forms**.

**Remark 1.2.** The correspondence between metric failures and differential forms is, at this stage, a heuristic. It will be made precise in Chapters 3–5, where the debt function is constructed from two axioms (additivity and antisymmetry) and shown to be a coboundary—the image of a potential function under the discrete exterior derivative. The reader who wants the formal development should proceed to Chapter 3; the reader who wants only the intuition can take the analogy at face value for now.

The textbook's "like a metric" acknowledges that the structure is there. It simply does not say what it is. This book does.

---

## 1.6 The thesis of this book

The thesis of this book is that cost is not a scalar. It is the real part of a complex object:

$$Q(b_i, b_j) = \text{cost}(b_i, b_j) + i \cdot \text{debt}(b_i, b_j).$$

The real part is the usual cost. The imaginary part is debt—the correction that emerges when cost fails to be a pseudo-quasi-metric.

Debt is not a defect. It is a **potential difference**. It is exact, antisymmetric, additive, gauge-invariant, and cycle-cancelling. It is, in the technical sense, a **coboundary**: the image of a potential function under the discrete exterior derivative.

The cochain complex in which debt lives is the simplicial cochain complex of the belief space, regarded as a directed graph. Debt is a 1-cochain; the potential is a 0-cochain; the exterior derivative is the coboundary operator. This will be made precise in Chapter 4.

And once you see this, the whole structure falls into place. The asymmetry of cost becomes a polar decomposition. The topology of the space becomes a lattice of four topologies. The gauge freedom becomes an $\mathbb{R}$-action. The complex structure becomes a $\mathbb{Z}/2$-grading.

None of this is imposed. It is discovered. The structure was always there. It was hidden in the hedge.

---

## 1.7 What this book is not

This book is not about applications. It is not about neural networks, or quantum computing, or thermodynamics of computation, or any of the other fields where cost is a central concept. Those connections exist, and they are interesting, but they are not the point.

This book is about the mathematics. It is about the structure of cost when cost is not a metric. It is about the complex quasi-metric, the debt function, the $\gamma$-family, the topology lattice, the equilibrium hierarchy, the $\mathbb{Z}/2$-grading, and the categorical picture.

It is a book of theorems and proofs. Every statement is either a definition, a proposition, a theorem, or a corollary. Every proof is complete. Every construction is canonical.

The goal is not to be useful. The goal is to be **true and beautiful**, and to let the structure speak for itself.

---

## 1.8 How to read this book

The book is organized into seven parts.

**Part I (Chapters 1–2)** introduces the problem and the setting: cost is not a metric, and belief space is the natural setting for the theory.

**Part II (Chapters 3–5)** develops the debt function from two axioms: additivity and antisymmetry. The central result is the basepoint theorem: any debt function is a potential difference.

**Part III (Chapters 6–8)** introduces the complex quasi-metric $Q = d + iD$, proves that its modulus is a metric, and develops the gauge structure.

**Part IV (Chapters 9–10)** develops the $\gamma$-family $d_\gamma = \sqrt{d^2 + \gamma^2 D^2}$, which interpolates between pure cost and full complex modulus.

**Part V (Chapters 11–13)** develops the polar decomposition of quasi-metrics and the bitopological structure, culminating in the equilibrium hierarchy.

**Part VI (Chapters 14–16)** develops the deeper structure: the $\mathbb{Z}/2$-grading, the categorical picture, and the open questions.

**Part VII (Chapters 17–18)** reflects on the nature of cost and closes the argument.

Each chapter is self-contained. Each begins with a definition and ends with exercises. The reader who wants only the main results can read the theorems and skip the proofs. The reader who wants the full structure should read everything.


---

## 1.9 Exercises

**Exercise 1.1.** Give an example of a cost function on a finite set that is asymmetric. Compute $d(b_i, b_j)$ and $d(b_j, b_i)$ for all pairs. Does the triangular inequality hold?

**Exercise 1.2.** Give an example of a cost function that violates the triangle inequality in the subadditive direction. Verify that $d(b_i, b_k) > d(b_i, b_j) + d(b_j, b_k)$ for some triple.

**Exercise 1.3.** Give an example of a cost function that violates the triangle inequality in the superadditive direction. Verify that $d(b_i, b_k) ≪ d(b_i, b_j) + d(b_j, b_k)$ for some triple.

**Exercise 1.4.** Give an example of a pseudometric that is not a metric.

**Exercise 1.5.** For each of the four failures described in §1.5, give a real-world example of an information processing system exhibiting that failure.

**Exercise 1.6.** Prove that if $d$ is a quasi-metric on $\mathcal{B}$, then the symmetrization $d_{\text{avg}}(b_i, b_j) := \tfrac{1}{2}(d(b_i, b_j) + d(b_j, b_i))$ is a pseudometric.

**Exercise 1.7.** Prove that if $d$ is a quasi-metric, then the asymmetry $A(b_i, b_j) := \tfrac{1}{2}(d(b_i, b_j) - d(b_j, b_i))$ is antisymmetric and vanishes on the diagonal. (Note the factor of $\tfrac{1}{2}$: this is the canonical normalization for a 1-form.)

**Exercise 1.8.** Show that the decomposition $d = S + A$, where $S$ is the symmetrization and $A$ is the asymmetry defined in Exercise 1.7, is unique.

**Exercise 1.9.** Give an example of a cost function that is path-dependent. Show that in this case, the cost of a transition is not a function of the endpoints alone.

**Exercise 1.10.** Suppose $d$ is a pseudo-quasi-metric and let $\alpha$ be a probability distribution over intermediate states. Define the signed debt $D(b_i,b_j)$ as the expected difference between the forward and reverse triangle-inequality defects. Show that $D$ is antisymmetric and vanishes on the diagonal.

**Exercise 1.11.** The textbook says cost is *like* a metric. Write a short essay (one page) explaining what you think the word "like" is doing in that sentence. Is it a hedge, a placeholder, or a precise claim?

**Exercise 1.12.** Reflect on the following question: is the metric assumption a *modeling choice* or a *fact about the world*? Write a short essay (one page) arguing for your position.

**Exercise 1.13. Disequilibrium Between Direct and Indirect Cost**

Let $d$ be a quasi-metric on a set of states $B$. Consider three states $b_i, b_j, b_k$ such that

$$d(b_i, b_k) ≪ d(b_i, b_j) + d(b_j, b_k).$$

1. Notice that the triangle inequality is satisfied (strictly).
2. Define the path-cost gap

$$\Delta(b_i, b_j, b_k) = d(b_i, b_j) + d(b_j, b_k) - d(b_i, b_k).$$

3. Show that $\Delta \geq 0$ whenever the triangle inequality holds.
4. Construct an example where $\Delta$ is large.
5. Discuss whether $\Delta$ can be interpreted as a measure of disequilibrium between the direct transition and the corresponding indirect path.

The purpose of this exercise is not to exhibit a violation of the triangle inequality. Instead, it asks whether satisfying the triangle inequality can still leave a meaningful amount of structure in the difference between direct and indirect costs.

**Exercise 1.14.** Suppose $d$ is a pseudo-quasi-metric. For a triple $(b_i, b_j, b_k)$, define the *forward defect* by
$$\Delta^+(b_i, b_j, b_k) := d(b_i, b_j) + d(b_j, b_k) - d(b_i, b_k),$$
and the *reverse defect* by
$$\Delta^-(b_i, b_j, b_k) := d(b_k, b_j) + d(b_j, b_i) - d(b_k, b_i).$$
Let $\alpha$ be a probability distribution over intermediate states $b_j$, and define the *signed debt*
$$D(b_i, b_k) := \mathbb{E}_{b_j \sim \alpha}\left[\Delta^+(b_i, b_j, b_k) - \Delta^-(b_i, b_j, b_k)\right].$$
Show that $D$ is antisymmetric and vanishes on the diagonal.


The book's posture is now: *not correcting the textbook, but exploring what its assumptions make possible.*
