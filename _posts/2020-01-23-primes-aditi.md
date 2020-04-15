---
layout: post
mathjax: true
author: Aditi Kathpalia
title: "Lecture 2 Extension: Proofs for the Infinitude of primes"
---


**Proof on the Infinitude of Primes - using Mersenne numbers**



Suppose $\mathbb{P}$, the set of primes is finite and $p$ is the largest prime. We have assumed a contradiction to the fact that the set $\mathbb{P}$ is infinite. Numbers of the form $2^s-1$ are called Mersenne numbers, where $s$ is a prime. Let us consider the Mersenne number $2^p-1$ . Then two cases arise:

**Case 1:**  $2^p-1$ is a prime.

We know that $2^p-1>p$  as $p>1$. If that is the case, there is a contradiction to the assumption that $p$ is the largest prime.  Hence the assumption is false and the set $\mathbb{P}$ is infinite.

**Case 2:** $2^p-1$ is not a prime.

For this case we show that a prime factor $q$ of $2^p-1$ is greater than $p$, which again is a contradiction to the fact that the set $\mathbb{P}$ is finite (with $p$ being the largest prime).

Since $q \vert 2^p-1$, $2^p-1 \equiv 0 \,(\mod q)$  or
$$
\begin{equation}
\tag{1}
2^p \equiv 1 \,(\mod q)
\label{eq_1}
\end{equation}
$$
To explain congruence and modular arithmetic (the notations of $\equiv$ and $\mod{}$) as well as some amount of group theory (which will be used in the proof), we take a detour and then come back to the proof.

**Detour**

**Congruence** is a statement about divisibility. It is defined as follows:

If an integer, $m$, not zero, divides the difference $a-b$, we say that $a$ is congruent to $b$ modulo $m$ and write it as $a \equiv b \,(\mod m)$.  If $a-b$ is not divisible by $m$, we say that $a$ is not congruent to $b$ modulo $m$ and write it as $a \not\equiv b \,(\mod m)$.

In other words, we can say that $a$ and $b$ leave the same remainder when divided by $m$.

For e.g. - $3 \equiv 5 \,(\mod 2)$, $10 \equiv 0 \,(\mod 5)$, $5 \not\equiv 13 \,(\mod 3)$.

$a-b \equiv 0 \,(\mod m)$, $a \equiv b \,(\mod m)$ and $b \equiv a \,(\mod m)$ are equivalent statements.

**Groups**

A group $G$ is a set of elements $a,b,c,\ldots$ together with a single valued binary operation $\oplus$ such that,

1. the set is closed under the operation, i.e. if $a,b \in G$ then $a \oplus b \in G$.

2. the associative law holds, namely,  $a \oplus (b \oplus c) = (a \oplus b) \oplus c \: \forall \: a,b,c \in G$.

3. the set has a unique identity element, $e$. That is,

   $\exists \: e \in G$ s.t. $\forall \: a \in G, \: a \oplus e=e \oplus a = a $.

4.   each element in $G$ has a unique inverse in $G$.

   $\forall \: a \in G, \: \exists \: a^{-1} \in G$, s.t.  $a \oplus a^{-1}= a^{-1} \oplus a$

There is an extra condition for an abelian/ commutative group, which is as follows:

$a \oplus b= b \oplus a \: \forall$ pair of elements $a,b \in G$ .

Examples - $(\mathbb{Z},+)$ is  a group, $(\mathbb{R}^*,\times)$ , where $\mathbb{R}^*= \{\mathbb{R}-0\}$ is a group

Other groups can be formed by taking congruences modulo $m$.

Additive group modulo 6 is as depicted below:

| $\oplus$ |  0   |  1   |  2   |  3   |  4   |  5   |
| :------: | :--: | :--: | :--: | :--: | :--: | :--: |
|  **0**   |  0   |  1   |  2   |  3   |  4   |  5   |
|  **1**   |  1   |  2   |  3   |  4   |  5   |  0   |
|  **2**   |  2   |  3   |  4   |  5   |  0   |  1   |
|  **3**   |  3   |  4   |  5   |  0   |  1   |  2   |
|  **4**   |  4   |  5   |  0   |  1   |  2   |  3   |
|  **5**   |  5   |  0   |  1   |  2   |  3   |  4   |



A multiplicative group modulo 3 is as given below:

| **$\times$** |  1   |  2   |
| :----------: | :--: | :--: |
|    **1**     |  1   |  2   |
|    **2**     |  2   |  1   |



Now we define the **order of an element** of a group as well as a **cyclic group**.

Let $G$ be any group, finite or infinite, and $a$ an element of $G$. If $a^s=e$ ($e$ is identity element of the group) for  some positive integer $s$, then $a$ is said to be of finite order. If $a$ is of finite order, the order of $a$ is the smallest positive integer $r$ such that $a^r=e$. If there is no positive integer $s$ such that $a^s=e$, then $a$ is said to be of infinite order.

A group $G$ is said to be cyclic if it contains an element $a$ such that the powers of $a$
$$
\ldots a^{-3}, a^{-2}, a^{-1}, a^0=e, a, a^2, a^3, \ldots
$$
comprise the whole group; such an element $a$ is said to generate the group and is called a generator.

The **order of a group** is equal to the number of elements in the group.

Now, let us get **back to the proof**.

We construct a multiplicative group $\mod q$, $(\mathbb{Z_q}^*,\cdot)$ where $q$ is the prime number considered before. The group $\mathbb{Z_q}^*$ consists of elements $\\{1,2,\ldots,q-1\\}$.  We prove that for any prime $q$, $\mathbb{Z_q}^*$ is a multiplicative group, by showing that it satisfies the axioms of a group:

1. Closure: If $a,b \in  \mathbb{Z_q}^*$, then $a \cdot b \in \mathbb{Z_q}^*$

   Since $q$ is a prime and contains only integers less than itself,  $gcd(a,q)=1$ and $gcd(b,q)=1$.

   Now, according to Bezout's identity, if $a'$ and $q'$ are integers with $gcd(a',q')=d$, then $\exists \: x',y' \in \mathbb{Z}$ such that $a'x'+q'y'=d$. More generally, any integers of the form $a'x'+q'y'$ are multiples of $d$.

   Thus, in our case, the below equations are satisfied

$$
\begin{equation}
\tag{GCD1}
ax_0+qy_0=1
\label{eq_gcd_1}
\end{equation}
$$

$$
\begin{equation}
\tag{GCD2}
bx_1+qy_1=1
\label{eq_gcd_2}
\end{equation}
$$

​		From Eqs. \eqref{eq_gcd_1} and $\eqref{eq_gcd_2}$, we get,  

​		
$$
\begin{equation}
\tag{GCD3}
(ax_0+qy_0)(bx_1+qy_1)=1 \\
ax_0bx_1+ax_0qy_1+qy_0bx_1+qy_0qy_1=1 \\
ab(x_0x_1)+q(ax_0y_1+y_0bx_1+qy_0y_1)=1
\label{eq_gcd_3}
\end{equation}
$$
​		Based on Eq. $\ref{eq_gcd_3}$, it can be said that $gcd(ab,q)=1$. Hence  $a \cdot b \in \mathbb{Z_q}^*$.

2. Identity:
   $$
   1 \cdot a= a \cdot 1=a \: \forall \: a \in \mathbb{Z_q}^*
   $$

3. Associativity: holds for multiplication and also for modular multiplication.

4. Inverse: From Eq. $\ref{eq_gcd_1}$, we have $ax_0+qy_0=1$. Taking modulo $q$ on both sides, we get $ax_0=1 \: (\mod q)$.  It can also be visualized as $x_0a+qy_0=1$. Thus, $gcd(x_0,q)=1$. From this, it can be said that $x_0=a^{-1} \in \mathbb{Z_q}^*$.

   To show the uniqueness of the $a^{-1}$, let us consider $x_{0}' \in \mathbb{Z_q}^*$ such that $x_{0}' \neq x_0$ and $ax_{0}'=1 \: (\mod q)$.  Thus, $ax_{0}'=ax_0 \: (\mod q)$. Multiplying with $a^{-1}$ on RHS, we get:
   $$
   x_{0}'=x_0 \: (\mod q)
   $$
   Since $x_{0}' \in \mathbb{Z_q}^*$, $1\leq x_{0}' < q$. So the above equation is impossible for $x_{0}' \neq x_0$. Hence, a unique inverse exists.



Thus, we have proved that $\mathbb{Z_q}^*$ is a **multiplicative group**. Moreover, it is a proved theorem that $\mathbb{Z_q}^*$ is a **cyclic group** for any prime $q$.  We omit the proof for this here.

From Eq. $\ref{eq_1}$, if we consider the group $\mathbb{Z_q}^*$, with 2 being an element of the group; we can observe that $p$ is the order of 2. Since $p$ is prime, there can be no positive integer $c<p$ for which $2^c \equiv 1 \: (\mod q)$ holds.

Now, according to a **special case of Lagrange's theorem**, if a group $G$ has a cyclic group as its subgroup, then,

**The order of an element of a finite group $G$ is a divisor of the order of the group.**

Proof: Let the element $a$ be a generator of the group and have order $r$. Then,
$$
e, a, a^2, a^3, \ldots, a^{r-1}
$$
are $r$ distinct elements of $G$ and belong to a set $A$. All other powers of $a$ merely repeat the above elements.

If these $r$ elements do not exhaust the group, there is some other element, say $b_2$. Then it can be proved that
$$
b_2, b_2a, b_2a^2, \ldots, b_2a^{r-1}
$$
are $r$ distinct elements all different from $r$ elements of $A$ and belong to a set $B$.

This is because if

1. $b_2a^s=b_2a^t$, then $a^s=a^t$ (by multiplying on the left by $b_2^{-1}$)

   But $a$ has order $r$ and the considered powers of $a$ are less than $r$, not allowing any of the powers to be equivalent.

2. $b_2a^s=a^t$ , then $b_2=a^{t-s}$ . This would mean that $b_2$ would be among the considered powers of $a$ and is not distinct.

If $G$ is not exhausted by the sets $A$ and $B$, then there exists another element $b_3$ that gives rise to $r$ new elements:
$$
b_3,b_3a,b_3a^2, \ldots, b_2a^{r-1}
$$
all different from the elements in $A$ and $B$, with the same argument as for the previous set.

This process of obtaining new elements $b_2,b_3,\ldots$ must terminate since $G$ is finite. So if the last batch of new elements is, say,
$$
b_k,b_ka,b_ka^2, \ldots, b_ka^{r-1}
$$
then the order of the group is $kr$ and $r|kr$. Hence, it is proved that the order of an element of a finite group is a divisor of the order of the group.

Now, if we consider for our group  $\mathbb{Z_q}^*$, since $p$ is the order of element 2 in the group and $q-1$ is the order of the group, it can be said that $p|(q-1)$. This means that $p \leq (q-1)$. Hence, $p < q$.

Thus, we have proved that $\exists$ a prime $q>p$. This is a contradiction to the fact that $\mathbb{P}$ is a finite set with $p$ being the largest prime. Hence, it is proved that the number of primes is infinite.    
