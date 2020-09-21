---
layout: post  
mathjax: true  
type: "proof"  
author: Dr. Nithin Nagaraj   
title: "The Counting Argument"
---

>**Theorem:** There exists an infinite number of primes

**Proof by Contradiction:** Let us assume that there are only $m$ primes and then we prove a contradiction by means of a counting argument.   


WLOG, let these primes be represented as $p_1, p_2, \ldots, p_m$ in an increasing order $(p_1 < p_2 < \ldots < p_m)$. As per the fundamental theorem of Arithmetic, every natural $1, 2, 3, \ldots$ can be represented uniquely as the product of prime factors. Let $n$ be a positive natural number greater than the largest prime number $p_m$($n > p_m$). Consider the set of consecutive natural numbers $S = \\{n+1, n+2, \ldots, n+n!\\}$ with a cardinality of $n!$. All these numbers are greater than the largest prime and hence are all composite. Let us *count* the number of composites (call it $C$) in an indirect manner as follows.

To calculate the exact value of $C$, we shall explicitly apply the **Sieve of Eratosthenes** to start counting the numbers which are definitely not primes (composite) between $n+1$ and $n + n!$(inclusive).

Let us first count the number of multiples of the first prime number($p_1 = 2$) in the set $S$. This is precisely the positive integer $C = n!/2$. Let us call whatever remains after we remove these $n!/2$ composite number as the residue $R = n! - C$. At this stepm $R = n!/2$. In this residue, let us *count* and remove thee multiples of the next prime number $p_2 = 3$. This would be $R/3 = n!/6$. So the count (of composite numbers) becomes $C = (n!/2) + (n!/6)$ and the new residue is $R = n! - C$. But, by our assumption, this process cannot go on indefinitely. We will at some point hit upon the last prime number $p_m$. By the **Fundamental Theorem of Arithmetic(FToA)**, we know that every number is uniquely represented as a product of primes, and hence, we only have to count the multiples of primes. Once we are done with counting th multiples of the largest prime $p_m$, we `STOP`.  

$$\begin{align*}
C = \frac{n!}{2} + \frac{1}{3}(n! - \frac{n!}{2}) + \frac{1}{5}(n! - \frac{n!}{2} - \frac{1}{3}(n! - \frac{n!}{2})) + \ldots + \frac{1}{p_m}(n! - \frac{n!}{2} - \frac{1}{3}(n! - \frac{n!}{2}) - \ldots)
\end{align*}$$

Let us see how the first terms look:

$$\begin{align*}
C &= (n!)\{\frac{1}{2} + \frac{1}{3}(\frac{1}{2}) + \frac{1}{5}(1 - \frac{2}{3}) + \frac{1}{7}(\frac{1}{3} - \frac{1}{5\cdot 3}) + \ldots +\} \\
C &= (n!)\{\frac{1}{2} + \frac{1}{6} + \frac{1}{15} + \frac{4}{3\cdot 5 \cdot 7} + \frac{4 \cdot 6}{3\cdot 5 \cdot 7 \cdot 11}+ \frac{4 \cdot 6 \cdot 10}{3\cdot 5 \cdot 7 \cdot 11 \cdot 13}+ \ldots +\} \\
C &= (n!)\{\frac{11}{15} + \frac{4}{15} [\frac{1}{7} + \frac{6}{7 \cdot 11} + \frac{6 \cdot 10}{7\cdot 11 \cdot 13} \ldots ]\} \\
C &= (n!)\{\frac{11}{15} + \frac{4}{15}X\}
\end{align*}$$
where,
$$ X  = \frac{1}{7} + \frac{6}{7 \cdot 11} + \frac{6 \cdot 10}{7\cdot 11 \cdot 13} \ldots $$    


We claim that $X<1$ and hence:

$$\begin{align*}
C &= (n!)\{\frac{11}{15} + \frac{4}{15}X\} \\
C &< (n!)\{\frac{11}{15} + \frac{4}{15}\} \\
C &< (n!)\frac{15}{15} \\
C &< n!
\end{align*}$$

But we had assumed that all the numbers in the set $S$ were composite which implies that $C = n!$. We have arrived a contradiction. Hence, the number of primes is **infinite**.


An important observation is that $n!/q$ is always a *whole* number ($>0$) for all $0 < q < n + 1$. This is vital for the argument to hold and that is  the reason we took a chunk of $n!$ consecutive natural numbers to do our counting.  

-----

**Proof for $X < 1$:**

$$
X = \frac{1}{7} + \frac{6}{7 \cdot 11} + \frac{6 \cdot 10}{7\cdot 11 \cdot 13} \ldots + \frac{6 \cdot 10 \cdot 12 \cdot 16 \cdots p_{m-1}-1}{7\cdot 11 \cdot 13 \cdots p_{m-1}\cdot p_m}
$$

To prove $X<1$, start backwards by constructing $X$ as follows:
$$\begin{align*}
\frac{1}{p_m} &< 1 \\
(p_{m-1} - 1)\frac{1}{p_m} &< (p_{m-1} - 1) \\
1 + (p_{m-1} - 1)\frac{1}{p_m} &< p_{m-1} \\
\frac{1}{p_{m-1}}(1 + \frac{(p_{m-1} - 1)}{p_m}) &< 1 \\
(p_{m-2} - 1)\frac{1}{p_{m-1}}(1 + \frac{(p_{m-1} - 1)}{p_m}) &< (p_{m-2} - 1)\\
1 + \frac{(p_{m-2} - 1)}{p_{m-1}}(1 + \frac{(p_{m-1} - 1)}{p_m}) &< p_{m - 2}\\
\frac{1}{p_{m - 2}}(1 + \frac{(p_{m-2} - 1)}{p_{m-1}}(1 + \frac{(p_{m-1} - 1)}{p_m})) &< 1\\
\frac{1}{p_{m - 2}}(1 + \frac{p_{m-2} - 1}{p_{m-1}} + \frac{(p_{m-2} - 1)(p_{m-1} - 1)}{p_{m - 1}\cdot p_m})) &< 1\\
&\vdots \\
X &< 1
\end{align*}$$


>**Corollary:** For all natural numbers $n>0$, there exists at least one prime number between $n+1$ and $n + n!$  

**Proof:** Simply observe that in the above proof, $p_m$ could be the largest prime less than $n$ and the proof still holds. This means that there must be at least **one** prime number between $n + 1$ and $n+n!$ for every $n >0$. To find the actual percentage or fraction of numbers that are prime, we need to evaluate $X$ accurately.    


**Tightening the bound:** Observe that the only requirement we had for the counting bound to work was the fact that $n!/q$ was always an integer for all prime numbers $q < n$. We can relax this and consider only the numbers $S = \\{n+1, n+2, \ldots, n+p_m!\\}$. Hence, the modified conclusion would be that there exists at least one prime number between $n+1$ and $n + p_m!$ for every $n>0$ with $p_m$ being the largest prime number less than $n$
