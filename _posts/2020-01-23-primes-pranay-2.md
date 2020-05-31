---
layout: post  
mathjax: true  
type: "proof"  
author: Pranay Yadav   
title: "Erdős' proof"
---

## Sixth Proof for the infinitude of primes by Erdős

### Proof by contradiction  

**Strategy:** Assume that the harmonic series of primes $\sum_{p\in \mathbb{P}}\frac{1}{p}$ converges. Use a bound on the sum to create 2 sets of numbers that can be obtained from the finitely many primes. Show that the cardinality of these 2 sets is less than the cardinality of the whole, indicating that a finite number of primes can not reach all possible numbers.

### Steps:

1. Setting the stage: Constrain the number of integers obtained from finite primes into 2 sets
2. Small primes: FTOA and the square-free numbers trick   
3. Large primes: Bounds for cardinality 
4. Conflict in cardinality  

---

### Setting the stage

If $\sum_{p\in \mathbb{P}}\frac{1}{p}$ converges, then the contribution of the tail of the sum tends to 0. Therefore, for some larger prime numbers, there exists a natural number $k$ such that:    


$$
\begin{equation} \tag{1}
\sum_{i > k}\frac{1}{p_i}<\frac{1}{2}
\end{equation}
$$
​    

Here, the index $k$ captures the distinction between large and small primes where:

- $p_1, p_2,\ldots,p_k$ are *small* primes
- $p_{k+1}, p_{k+2},\ldots$ are *large* primes

Multiplying the inequality above by an arbitrary natural number $N$:    


$$
\begin{equation} \tag{2}
\sum_{i > k}\frac{N}{p_i} < \frac{N}{2}
\end{equation}
$$
   

Using the notion of *small* and *large* primes, we can define the following sets:    

​    
$$
\text{Let } S = \{1,2,3,\ldots,N\} \\
X = \{\text{elements in S which have only small primes as factors}\} \\
Y = \{\text{elements in S which have at least one large prime as a factor}\} \\
$$
   

Since $X$ does not have any elements with a large prime as a factor, together $X$ and $Y$ span the entire set $S$, we have the following further properties:    

​    
$$
X\cup Y=S\ \text{ and }\ X\cap Y= \phi \\
\begin{equation} \\
|X| +|Y|  = |S| =N \\ \tag{3}
\end{equation}
$$

---

### Small primes

Consider an element $x \in X$. Using the fundamental theorem of arithmetic, $x$ can be factorized as:    

​    
$$
x = p_{1}^{a_1}p_{2}^{a_2}p_{3}^{a_3}\ldots p_{k}^{a_k}
$$
​    

Equivalently, $x$ can also be factorized into a square-free part and a square. For example, $24=2^3 3^1 =2^2 6$. Thus,    


$$
x=r^2 (p_{1}^{a'_1}p_{2}^{a'_2}p_{3}^{a'_3}\ldots p_{k}^{a'_k})
$$
​    

where the exponent $a'_i$ of each $p_i$ can be either $0$ or $1$. All higher terms get absorbed in $r$, since:

- if the exponent $a_i$ is even, then either $2$ completely divides it, or leaves a remainder of $1$ upon subsequent divisions
- if the exponent $a_i$ is odd, then division by $2$ leaves a remainder of $1$

The number $r^2$ can be at most as large as $x$ - if $x$ is a perfect square, while $x$ itself can be as large as $N$, giving the inequality:    

​    
$$
r^2 \le x \le N \\
r \le \sqrt{N} \\
\text{taking only the integer part:}\\
r \le \lfloor \sqrt{N}\rfloor
$$
​    

Since $a'_i$ can take two values, $0$ or $1$, for $k$ primes, there will be $k$ possible such exponents. Therefore the total number of combinations of such binary exponents are $2^k$. Thus, the total possible cardinality of $X$:    

​    
$$
\begin{equation} \tag{4} \\
|X| \le 2^k \lfloor\sqrt N \rfloor \\
\end{equation}
$$

---

### Large primes

For a prime number $p_i$, the integer part of $\frac{N}{p_i}$ reflects the number of integers that are multiples of it. The cardinality of $Y$ can be then expressed as the inequality:    

​    
$$
|Y| \le \lfloor \frac{N}{p_{k+1}}\rfloor + \lfloor \frac{N}{p_{k+2}}\rfloor + \ldots \\
|Y| \le \sum_{i>k}\ \lfloor \frac{N}{p_{i}}\rfloor
$$
​    

Since the floor function is always at least as small as the value passed into it:    

​    
$$
|Y| \le \sum_{i>k}\ \lfloor \frac{N}{p_{i}}\rfloor \le \sum_{i>k}\ \frac{N}{p_{i}}
$$
​    

Using the inequality from equation $2$, we have:    

​    
$$
\begin{equation} \tag{5} \\
|Y| < \frac{N}{2} \\
\end{equation}
$$

---

### Conflict

A value for $N$ can be chosen such that $2^k \sqrt N \le \frac{N}{2}$. Solving provides one such value for $N = 2^{2k+2}$. Substituting this in equations $4$ and $5$, and solving for $|X|+|Y|$ gives:    

​    
$$
|X|+|Y| < 2^k \lfloor \sqrt(2^{2k+2}) \rfloor + \frac{2^{2k+2}}{2} \\
= 2^k 2^{k+1} + 2^{2k+1} = 2^{2k+1} + 2^{2k+1} = 2^{2k+2} \\
|X|+|Y| < 2^{2k+2} \\
\text{But, }|S| = N = 2^{2k+2}, \text{ and thus we have here:} \\
|X|+|Y| < |S|
$$
​    

This is in conflict with the equality from $3$ and we have a contradiction. Having finitely many primes is not enough to generate all numbers.

Therefore, the harmonic series of primes diverges! 

---





