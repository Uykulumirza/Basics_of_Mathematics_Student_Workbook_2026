# Exercise 15: Observation Versus Proof

## 1. Problem Statement

Choose one sequence and one function from this set. For the sequence, compute several values for increasingly large $n$. For the function, prepare a table of values with arguments approaching the limit point from the left and right. Sketch the behavior of both objects.

Compare the observation with the analytical result and explain why a finite number of calculations or a sketch does not constitute a proof that the limit exists.

> **Why this exercise:** teaches how to distinguish intuition and observation from mathematical argument.

---

## 2. Theoretical Background and Concepts

### The Role of Empirical Observation vs. Deductive Proof in Analysis
In calculus and mathematical analysis, **numerical exploration** (tables of values) and **geometric visualization** (graphs/sketches) play a vital heuristic role: they build intuition, suggest candidate values for a limit $L$, and serve as sanity checks against algebraic errors.

However, the formal definition of a limit is a **universal statement over infinitely many inputs**:
- **For a sequence $(a_n)$:** $\lim_{n\to\infty} a_n = L$ means that for **every** tolerance $\varepsilon > 0$ (no matter how small, e.g., $\varepsilon = 10^{-1000}$), there exists an integer $N$ such that $|a_n - L| < \varepsilon$ for **all** $n > N$.
- **For a function $f(x)$:** $\lim_{x\to x_0} f(x) = L$ means that for **every** tolerance $\varepsilon > 0$, there exists a radius $\delta > 0$ such that $|f(x) - L| < \varepsilon$ for **all** $x$ in the punctured interval $0 < |x - x_0| < \delta$.

Because no finite table or finite-resolution drawing can check infinitely many values of $n$, infinitely many real numbers $x$ near $x_0$, or arbitrarily small $\varepsilon > 0$, empirical observation can never substitute for an **analytical proof**.

---

## 3. Detailed Step-by-Step Solution

### Part A: Chosen Sequence — $a_n = \frac{4n^2-3n+1}{2n^2+5n-7}$ as $n \to \infty$ (from Exercise 1)

#### 1. Analytical Result Recap
In Exercise 1, by factoring out the dominant power $n^2$ from numerator and denominator (for $n \ge 2$), we proved analytically that:
$$\lim_{n\to\infty} a_n = \lim_{n\to\infty} \frac{4n^2-3n+1}{2n^2+5n-7} = \lim_{n\to\infty} \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}} = \frac{4 - 0 + 0}{2 + 0 - 0} = 2.$$
Moreover, by polynomial division, $a_n = 2 - \frac{13n - 15}{2n^2 + 5n - 7} \approx 2 - \frac{6.5}{n}$ for large $n$.

#### 2. Numerical Table for Increasingly Large $n$
Let us evaluate $a_n$ for $n = 2, 5, 10, 20, 50, 100, 1000, 10000$:

| $n$ | Numerator $4n^2 - 3n + 1$ | Denominator $2n^2 + 5n - 7$ | Exact Value $a_n$ | Decimal Approximation | Distance $|a_n - 2|$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $2$ | $11$ | $11$ | $\frac{11}{11}$ | $1.000000$ | $1.000000$ |
| $5$ | $86$ | $68$ | $\frac{43}{34}$ | $1.264706$ | $0.735294$ |
| $10$ | $371$ | $243$ | $\frac{371}{243}$ | $1.526749$ | $0.473251$ |
| $20$ | $1{,}541$ | $893$ | $\frac{1541}{893}$ | $1.725644$ | $0.274356$ |
| $50$ | $9{,}851$ | $5{,}243$ | $\frac{9851}{5243}$ | $1.878886$ | $0.121114$ |
| $100$ | $39{,}701$ | $20{,}493$ | $\frac{39701}{20493}$ | $1.937296$ | $0.062704$ |
| $1{,}000$ | $3{,}997{,}001$ | $2{,}004{,}993$ | $\frac{3997001}{2004993}$ | $1.993524$ | $0.006476$ |
| $10{,}000$ | $399{,}970{,}001$ | $200{,}049{,}993$ | $\frac{399970001}{200049993}$ | $1.999350$ | $0.000650$ |

#### 3. Sketch of the Sequence $(a_n)$
The graph of the sequence consists of **isolated points** $(n, a_n)$ that climb monotonically toward the dashed horizontal line $y = 2$ (the limit):

```text
  a_n
   ^
 2.0 + - - - - - - - - - - - - - - - - - - - - - - - - - -  y = 2 (Limit)
     |                                           *     *
 1.8 +                                     *
     |                               *
 1.6 +
     |                         *
 1.4 +
     |                   *
 1.2 +             *
     |
 1.0 +       *
     |
 0.0 +-------+-----+-----+-----+-----+-----+-----+-----+---> n
     0       2     5    10    20    35    50   100   1000
```

---

### Part B: Chosen Function — $f(x) = \frac{x^2-4x+3}{x-3}$ as $x \to 3$ (from Exercise 7)

#### 1. Analytical Result Recap
In Exercise 7, we noted that the domain is $D_f = \mathbb{R} \setminus \{3\}$ (so $f(3)$ is undefined). For all $x \neq 3$, factoring the numerator gives:
$$f(x) = \frac{(x-3)(x-1)}{x-3} = x - 1 \quad (x \neq 3),$$
and therefore:
$$\lim_{x\to 3} f(x) = \lim_{x\to 3} (x - 1) = 3 - 1 = 2.$$

#### 2. Numerical Table Approaching $x = 3$ from Left and Right
Let us evaluate $f(x) = \frac{x^2-4x+3}{x-3}$ for arguments approaching $3$ from the left ($x \to 3^-$: $2.5, 2.9, 2.99, 2.999$) and from the right ($x \to 3^+$: $3.5, 3.1, 3.01, 3.001$):

| Left Approach ($x \to 3^-$) | $x^2 - 4x + 3$ | $x - 3$ | $f(x)$ | Right Approach ($x \to 3^+$) | $x^2 - 4x + 3$ | $x - 3$ | $f(x)$ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $2.5$ | $-0.75$ | $-0.5$ | $1.5$ | $3.5$ | $+1.25$ | $+0.5$ | $2.5$ |
| $2.9$ | $-0.19$ | $-0.1$ | $1.9$ | $3.1$ | $+0.21$ | $+0.1$ | $2.1$ |
| $2.99$ | $-0.0199$ | $-0.01$ | $1.99$ | $3.01$ | $+0.0201$ | $+0.01$ | $2.01$ |
| $2.999$ | $-0.001999$ | $-0.001$ | $1.999$ | $3.001$ | $+0.002001$ | $+0.001$ | $2.001$ |
| **As $x \to 3^-$** | **$\to 0^-$** | **$\to 0^-$** | **$\to 2^-$** | **As $x \to 3^+$** | **$\to 0^+$** | **$\to 0^+$** | **$\to 2^+$** |

#### 3. Sketch of the Function $f(x)$
The graph of $f(x) = \frac{x^2-4x+3}{x-3}$ is the straight line $y = x - 1$ with an **open circle (removable discontinuity / hole)** at $(3, 2)$ because $x = 3$ is not in the domain of $f$:

```text
            y
            ^
          4 +                                   *
            |                                *
          3 +                             *   y = f(x) = (x^2 - 4x + 3)/(x - 3)
            |                          *
          2 + - - - - - - - - - - - o         <-- Open circle (hole) at (3, 2);
            |                    *  :             limit is 2, f(3) is undefined
          1 +                 *     :
            |              *        :
   ---------+-----+-----*-----------+-----+-----> x
           -1     0  *  1     2     3     4
            |     *
         -1 +  *
            |
```

---

### Part C: Comparison and Why Finite Calculations or Sketches Are Not Proofs

#### Comparison of Observation with Analytical Result
In both examples, the numerical tables and sketches are **completely consistent** with our analytical proofs:
- For the sequence $(a_n)$, the computed values $1.527, 1.937, 1.9935, 1.99935$ strongly suggest that $a_n$ approaches $2$ from below at a rate proportional to $\frac{1}{n}$.
- For the function $f(x)$, the left-hand values $1.9, 1.99, 1.999$ and right-hand values $2.1, 2.01, 2.001$ pinch symmetrically toward the height $y = 2$.

#### Five Reasons Why a Finite Table or Sketch Cannot Prove a Limit Exists

1. **Unexamined Tail ($n > N_{\max}$) and Unexamined Micro-Scale ($0 < |x - x_0| < \delta_{\min}$):**
   - For the sequence, our table stops at $n = 10{,}000$. A sequence limit depends **only** on the infinite tail $n > 10{,}000$. For example, the modified sequence
     $$\tilde{a}_n = \frac{4n^2-3n+1}{2n^2+5n-7} + 10^{-30} n^3$$
     agrees with our table to more than $15$ decimal places for every $n \le 10{,}000$, yet $\lim_{n\to\infty} \tilde{a}_n = +\infty$.
   - Similarly, for the function, our table stops at $|x - 3| = 0.001$. A function such as
     $$\tilde{f}(x) = \frac{x^2-4x+3}{x-3} + \sin\left(\frac{\pi}{10^{-6}(x-3)}\right)$$
     or $\frac{x^2-4x+3}{x-3} + \frac{10^{-20}}{(x-3)^2}$ behaves almost identically to $f(x)$ at $x = 2.9, 2.99, 2.999$, yet fails to have a limit as $x \to 3$ because of wild oscillation or blow-up inside $|x - 3| < 10^{-6}$.

2. **Rapid Oscillation Between Sampled Grid Points (Aliasing):**
   Suppose we added $\sin\left(\frac{2\pi}{x-3}\right)$ or a factor that vanishes specifically at decimal powers $x - 3 = \pm 10^{-k}$ (such as $\sin\left(\pi \log_{10}|x-3|\right)$). Evaluating only at $x = 3 \pm 0.1, 3 \pm 0.01, 3 \pm 0.001$ would sample the oscillation only at its zeros, hiding the fact that the function oscillates between $+1$ and $-1$ at intermediate points!

3. **Finite Resolution of Any Sketch:**
   Every physical or pixel-based plot has finite line thickness and finite resolution. A plot cannot visually distinguish a continuous curve from one with a tiny jump of $10^{-9}$, nor can it show infinite oscillation like $\sin\left(\frac{1}{x-3}\right)$ compressed into a single pixel around $x = 3$. Worse still, plotting software simply connects finitely many sampled points with straight line segments, so the "hole" at $x = 3$ is invisible unless added manually from analytical knowledge!

4. **Floating-Point Cancellation Errors Near $0/0$:**
   If you evaluate $f(x) = \frac{x^2-4x+3}{x-3}$ on a standard computer for $x$ extremely close to $3$ (say $x = 3 + 10^{-16}$), floating-point rounding causes **catastrophic cancellation** in $x^2 - 4x + 3$, producing $0.0$ or garbage values instead of $2.0$! Thus, purely numerical evaluation can even falsely suggest that a convergent limit diverges or jumps to $0$.

5. **Inability to Establish Exact Values:**
   Even when a limit exists, finite decimal tables only yield approximations ($1.99935\dots$) and can never prove whether the exact limit is $2$, $1.999999999$, or $\frac{2000000}{1000001}$. Only an analytical proof (using algebraic identities, inequalities, and limit theorems) guarantees behavior for **all** $n > N$ and **all** $0 < |x - x_0| < \delta$.

---

## 4. Verification and Consistency Checks

### Exact Error Formula Verification
- **For the sequence $a_n$:** From Exercise 1,
  $$2 - a_n = \frac{13n - 15}{2n^2 + 5n - 7}.$$
  At $n = 100$, this formula gives $2 - a_{100} = \frac{1300 - 15}{20000 + 500 - 7} = \frac{1285}{20493} \approx 0.062704$, matching our numerical table to $6$ decimal places.
- **For the function $f(x)$:** For all $x \neq 3$, $f(x) = x - 1$, so the exact error from the limit $L = 2$ is:
  $$|f(x) - 2| = |(x - 1) - 2| = |x - 3|.$$
  This analytically proves the $\varepsilon$-$\delta$ condition with $\delta = \varepsilon$: for every $\varepsilon > 0$, $0 < |x - 3| < \varepsilon \implies |f(x) - 2| = |x - 3| < \varepsilon$, matching every row of our left/right table ($|f(2.999) - 2| = 0.001$, $|f(3.001) - 2| = 0.001$).

### Final Conclusion
$$\boxed{\text{Sequence: } \lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7} = 2; \quad \text{Function: } \lim_{x\to 3}\frac{x^2-4x+3}{x-3} = 2; \quad \text{Finite tables/sketches guide intuition but cannot replace analytical proof.}}$$
