---
layout: post
mathjax: true
author: Abhishek Nandekar
title: "Lecture 2 Extension: Proofs for the Infinitude of primes - Using Topology"
---

## The Topological Approach:

The infinitude of the set of Prime numbers can be proved using basic topological constructs. In this section, we look at the motivations behind the notions of *open* and *closed* sets, then, we'll discuss the basics of topology and finally we'll prove the infinitude of Primes.

### The Open Set:

Consider the set $\mathbb R$. Consider a real number $y \in \mathbb R$. This element $y$ will still be closer to zero than any other element $y_1 \notin \mathbb R$. In this manner, one may speak of whether two subsets of a topological space are "near" without defining the metric.

In general, a family of sets containing zero, used to approximate zero is referred to as the **neighbourhood basis** of  zero. Any member of this neighbourhood basis is the **open set**.

Consider an arbitrary set $X$. Given $x \in X$ we can define a collection of sets "around" $x$, including $x$ itself, used to approximate $x$. This collection of sets contains all open sets.

#### Definitions:

$U \subseteq \mathbb R^n$ is open if,  

$$\forall x \in U, \exists \text{ } \epsilon > 0$$
such that,  

$$\{|y-x| < \epsilon \implies y \in U | y \in \mathbb R^n\}$$

For any collection of open sets,

- Union any arbitrary number of open sets is open,
- Any finite intersection of open sets is open.


### Axioms of Topology

$X$ is a set, $\tau$ is a collection of subsets of $X$. If,

1. $\phi, X \in \tau$
2. $\tau_i' \subseteq \tau$, and $\cup_{i=1}^N \tau_i' \in \tau$, $N$ can be infinite.
3. $U_1 \in \tau$, and $U_2 \in \tau$, then $U_1 \cap U_2 \in \tau$

Then, $\tau$ is a topology on $X$ and the elements of $\tau$ are open sets.

The ordered pair $(X, \tau)$ is called a **topological space**.

#### Examples:

Let $X = \{1, 2, 3\}$.

- If $\tau = \{\phi, X\}$. In this case, all three axioms are satisfied. Hence $\tau$ is a genuine topology on $X$.
- If $\tau = \{\phi, \{1\}, X\}$, axiom 3 is not satisfied. Hence, $\tau$ is **not** a topology $X$.
- If $\tau = \{\phi, \{1\}, \{2\}, \{1, 2\}, X\}$, union of any subsets of $\tau$ is an element of $\tau$, and intersection of any elements of $\tau$ is an element of $\tau$. Hence all three axioms of topology are satisfied and $\tau$ is a genuine topology on $X$.

#### Closed Sets

Closed sets are the compliments of open sets.

##### Theorem 1
Any finite union of closed sets is closed.

##### Proof:
Consider the above given topological space $T = (X, \tau)$. Let $\bigcup_{i=1}^n V_i$ be a finite union of closed sets of $T$.

Then from [De Morgan's laws](https://proofwiki.org/wiki/De_Morgan%27s_Laws_(Set_Theory)):  

$$X \setminus \bigcup_{i=1}^n V_i = \bigcap_{i=1}^n (X \setminus V_i)$$

By definition, $X \setminus V_i$ is an open set in $T$.

Using Axiom 3,  we can say,

$$\bigcap_{i=1}^n(S \setminus V_i) = S \setminus \bigcup_{i=1}^n V_i$$

LHS is a finite intersection of open sets, and hence is open.

$\implies$RHS is also an open set. Hence $S \setminus \bigcup_{i=1}^n V_i$ is open, implying that $\bigcup_{i=1}^n V_i$ is closed.             $\square$

### Proof for the infinitude of Primes

Let $O \subseteq \mathbb Z$. $O$ is an open set if it is either empty or, $\forall a \in O$, $\exists b>0$ such that

$$N_{a, b} = \{a + nb\big|n\in \mathbb Z\}$$
and $N_{a,b} \subseteq O$.

Clearly, the union of open sets is open again.
Let $N_{a, b_1} \subseteq O_1$ and $N_{a, b_2} \subseteq O_2$, and $a \in O_1 \cap O_2$. Then, $N_{a, b_1b_2} \subseteq O_1 \cap O_2$, which is also an open set. So, this family of sets is a bona fide topology in $\mathbb Z$

By this definition, we can observe two facts:

- Any nonempty open set is infinite.
- Any $N_{a, b}$ is closed as well.

To prove the second fact, we can say that

$$N_{a, b} = \mathbb Z \setminus \bigcup_{i=1}^{b-1} N_{a+i, b}$$

Observe the fact that $\forall n \in \mathbb Z \setminus \{-1, 1\}$, there exists a prime divisor $p \in \mathbb P$. Hence we can say,

$$ \bigcup_{p \in \mathbb P} N_{0, p} = \mathbb Z \setminus \{-1, 1\} $$

Now, if $\mathbb P$ is a finite set, then LHS is a finite union of closed sets and hence, is closed ( proved in Theorem 1 ).

$\implies$ $\{-1, 1\}$ should be an open set. But, as stated earlier, any nonempty open set is infinite. Hence, this is a contradiction. $\mathbb P$ should be an infinite set. $\square$
