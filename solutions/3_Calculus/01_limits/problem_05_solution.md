# Exercise 5: The Classical Limit Leading to the Number $e$

## 1. Problem Statement

Compute
$$\lim_{n\to\infty}\left(1+\frac1n\right)^n.$$
Calculate several values for increasing $n$ and compare the observed behavior with the value of the limit. Explain why a few values do not constitute a proof.

> **Why this exercise:** connects a central limit with intuition based on concrete terms of a sequence.

---

## 2. Theoretical Background and Concepts

### The Indeterminate Form $[1^\infty]$
Consider the sequence
$$e_n = \left(1 + \frac{1}{n}\right)^n, \quad n \in \mathbb{N}^+.$$
As $n \to \infty$, the base $1 + \frac{1}{n}$ approaches $1$, while the exponent $n$ grows to $+\infty$. This produces the **indeterminate form** $[1^\infty]$, which reflects a competition between two opposing forces:
- **Force 1 (Shrinking Base):** The base $1 + \frac{1}{n}$ gets closer and closer to $1$, which pulls powers toward $1$ (since $1^n = 1$).
- **Force 2 (Growing Exponent):** Since $1 + \frac{1}{n} > 1$, raising a number greater than $1$ to an increasingly large exponent $n \to \infty$ pushes the result upward.

### Definition of Euler's Number $e$ and the Monotone Convergence Theorem
A fundamental theorem of real analysis states that every sequence $(e_n)$ that is **monotonically increasing** ($e_n < e_{n+1}$) and **bounded above** ($e_n < M$ for some constant $M \in \mathbb{R}$) converges to a finite real limit (its supremum). Applying this theorem to $e_n = \left(1 + \frac{1}{n}\right)^n$ defines **Euler's number** $e$:
$$\lim_{n\to\infty} \left(1 + \frac{1}{n}\right)^n = e \approx 2.718281828459045\dots$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: State the Value of the Limit and Outline its Theoretical Proof
The limit of the sequence is Euler's constant $e$:
$$\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^n = e \approx 2.718281828\dots$$

To prove rigorously that this limit exists and is finite (between $2$ and $3$), one uses the **Binomial Theorem**:
$$\begin{aligned}
e_n = \left(1 + \frac{1}{n}\right)^n &= \sum_{k=0}^n \binom{n}{k} \frac{1}{n^k} \\[6pt]
&= 1 + n\left(\frac{1}{n}\right) + \frac{n(n-1)}{2!}\frac{1}{n^2} + \frac{n(n-1)(n-2)}{3!}\frac{1}{n^3} + \dots + \frac{n(n-1)\cdots 1}{n!}\frac{1}{n^n} \\[6pt]
&= 1 + 1 + \frac{1}{2!}\left(1 - \frac{1}{n}\right) + \frac{1}{3!}\left(1 - \frac{1}{n}\right)\left(1 - \frac{2}{n}\right) + \dots + \frac{1}{n!}\left(1 - \frac{1}{n}\right)\cdots\left(1 - \frac{n-1}{n}\right).
\end{aligned}$$

From this expansion, two crucial properties follow immediately:
1. **Strict Monotonicity ($e_n < e_{n+1}$):** When $n$ increases to $n+1$, each factor $\left(1 - \frac{j}{n}\right)$ increases to $\left(1 - \frac{j}{n+1}\right)$, and one additional positive term is added at the end ($k = n+1$). Therefore, $e_1 < e_2 < e_3 < \dots < e_n < e_{n+1}$.
2. **Boundedness Above ($e_n < 3$):** Since each factor $\left(1 - \frac{j}{n}\right) < 1$ and $k! = 1 \cdot 2 \cdot 3 \cdots k \ge 2^{k-1}$ for all $k \ge 2$, we have:
   $$2 \le e_n < 1 + 1 + \frac{1}{2!} + \frac{1}{3!} + \dots + \frac{1}{n!} < 1 + 1 + \frac{1}{2} + \frac{1}{2^2} + \dots + \frac{1}{2^{n-1}} = 1 + \left(2 - \frac{1}{2^{n-1}}\right) < 3.$$
By the **Monotone Convergence Theorem**, since $(e_n)$ is strictly increasing and bounded above by $3$, it must converge to a finite limit $e \in (2, 3)$.

---

### Step 2: Table of Numerical Values for Increasing $n$
Let us compute $e_n = \left(1 + \frac{1}{n}\right)^n$ for $n = 1, 2, 5, 10, 100, 1000, 10000$ and compare each value with $e \approx 2.718281828$:

| $n$ | Base $1 + \frac{1}{n}$ | Expression $\left(1 + \frac{1}{n}\right)^n$ | Decimal Value of $e_n$ | Difference $e - e_n$ |
| :--- | :--- | :--- | :--- | :--- |
| $1$ | $2.0000$ | $(2)^1$ | $2.000000000$ | $0.718281828$ |
| $2$ | $1.5000$ | $(1.5)^2 = \frac{9}{4}$ | $2.250000000$ | $0.468281828$ |
| $5$ | $1.2000$ | $(1.2)^5 = \frac{248832}{100000}$ | $2.488320000$ | $0.229961828$ |
| $10$ | $1.1000$ | $(1.1)^{10}$ | $2.593742460$ | $0.124539368$ |
| $100$ | $1.0100$ | $(1.01)^{100}$ | $2.704813829$ | $0.013467999$ |
| $1{,}000$ | $1.0010$ | $(1.001)^{1000}$ | $2.716923932$ | $0.001357896$ |
| $10{,}000$ | $1.0001$ | $(1.0001)^{10000}$ | $2.718145927$ | $0.000135902$ |
| $\infty$ | $\to 1^+$ | $\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^n$ | $e \approx 2.718281828$ | $0$ |

#### Comparison of Observed Behavior with the Limit
- **Monotonic Increase:** The table confirms that as $n$ increases from $1$ to $10{,}000$, the terms $e_n$ increase steadily ($2.000 \to 2.250 \to 2.488 \to 2.594 \to 2.705 \to 2.717 \to 2.7181$).
- **Decelerating Growth:** Although $e_n$ keeps increasing, the increments between successive powers of $10$ shrink rapidly:
  - From $n=10$ to $n=100$: increase of $+0.11107$.
  - From $n=100$ to $n=1{,}000$: increase of $+0.01211$.
  - From $n=1{,}000$ to $n=10{,}000$: increase of $+0.00122$.
- **Approach from Below:** Every term $e_n$ is strictly less than $e \approx 2.718281828$, and the error $e - e_n \approx \frac{e}{2n}$ decreases by a factor of $10$ whenever $n$ is multiplied by $10$.

---

### Step 3: Why a Finite Number of Values Does Not Constitute a Proof
Computing $e_n$ for finitely many values of $n$ (even millions of values on a computer) provides valuable numerical intuition, but **cannot constitute a mathematical proof** of convergence for several fundamental reasons:

1. **The Limit is an Asymptotic Property of Infinitely Many Terms:**
   The definition of $\lim_{n\to\infty} a_n = L$ requires that for every $\varepsilon > 0$, there exists an index $N$ such that $|a_n - L| < \varepsilon$ for **all** $n > N$. Any finite table only inspects $n \in \{n_1, n_2, \dots, n_k\}$ up to some maximum $N_{\max}$ (here $10{,}000$), leaving the infinitely many terms $n > N_{\max}$ completely unexamined.
2. **Slow Divergence Can Masquerade as Convergence:**
   A sequence can grow so slowly that a table of values looks almost flat, yet the sequence actually diverges to $+\infty$. For example, the harmonic partial sums $H_n = \sum_{k=1}^n \frac{1}{k}$ or the iterated logarithm $\ln(\ln(n+10))$ increase by tiny amounts between $n = 1{,}000$ and $n = 10{,}000$, looking as if they are stabilizing, even though $\lim_{n\to\infty} H_n = +\infty$. Without the theoretical upper bound $e_n < 3$, the table alone cannot rule out the possibility that $e_n$ grows very slowly to $+\infty$.
3. **Delayed Change of Behavior:**
   A sequence can behave nicely for the first $10{,}000$ terms and then diverge dramatically for $n > 10^6$ (for instance, $\left(1 + \frac{1}{n}\right)^n + 10^{-100} n^2$ would match our table to $9$ decimal places up to $n = 10{,}000$, yet diverge to $+\infty$).
4. **Inability to Identify the Exact Limit Value:**
   Even if we suspected convergence from the table, finite decimal approximations (plus floating-point rounding errors for very large $n$) cannot prove whether the exact limit is $2.71828\dots$, a rational fraction, or the transcendental number $e = \sum_{k=0}^\infty \frac{1}{k!}$.

---

## 4. Verification and Consistency Checks

### Series Comparison Check
Using the series representation $e = \sum_{k=0}^\infty \frac{1}{k!}$, the partial sum up to $k=7$ is:
$$1 + 1 + \frac{1}{2} + \frac{1}{6} + \frac{1}{24} + \frac{1}{120} + \frac{1}{720} + \frac{1}{5040} = 2 + 0.5 + 0.166667 + 0.041667 + 0.008333 + 0.001389 + 0.000198 \approx 2.718254,$$
which closely matches $e_{10000} \approx 2.718146$.

### Asymptotic Error Check via Logarithms
Taking the natural logarithm of $e_n = \left(1 + \frac{1}{n}\right)^n$ using the Taylor expansion $\ln(1+x) = x - \frac{x^2}{2} + O(x^3)$ for small $x = \frac{1}{n}$ gives:
$$\ln e_n = n \ln\left(1 + \frac{1}{n}\right) = n\left(\frac{1}{n} - \frac{1}{2n^2} + O\left(\frac{1}{n^3}\right)\right) = 1 - \frac{1}{2n} + O\left(\frac{1}{n^2}\right).$$
Exponentiating both sides yields:
$$e_n = e^{1 - \frac{1}{2n} + O(1/n^2)} = e \cdot \left(1 - \frac{1}{2n} + O\left(\frac{1}{n^2}\right)\right) \implies e - e_n \approx \frac{e}{2n} \approx \frac{1.35914}{n}.$$
For $n = 1{,}000$, this formula predicts $e - e_{1000} \approx 0.001359$, and for $n = 10{,}000$, it predicts $e - e_{10000} \approx 0.0001359$, in agreement with our table.

### Final Conclusion
$$\boxed{\lim_{n\to\infty}\left(1+\frac{1}{n}\right)^n = e \approx 2.718281828\dots}$$
