# Exercise 6: From a Sequence to a Function — Limit at Infinity

## 1. Problem Statement

Compute
$$\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2}.$$
Compare the method with Exercise 1. Explain what changes when moving from $n$ to a real variable $x$, and what stays the same.

> **Why this exercise:** deliberately transfers a technique from sequence limits to function limits.

---

## 2. Theoretical Background and Concepts

### Limit of a Function at Infinity
Let $f : D \to \mathbb{R}$ be a real-valued function defined on a domain $D \subseteq \mathbb{R}$ that contains an interval of the form $(M_0, \infty)$. We say that
$$\lim_{x\to\infty} f(x) = L$$
if for every $\varepsilon > 0$, there exists a real number $M > M_0$ such that for all real numbers $x \in D$ satisfying $x > M$, we have $|f(x) - L| < \varepsilon$.

### Sequential Criterion (Heine's Definition of Function Limits)
A bridge between function limits and sequence limits is given by **Heine's Theorem**: $\lim_{x\to\infty} f(x) = L$ if and only if for every sequence of real numbers $(x_n)$ in the domain $D$ such that $\lim_{n\to\infty} x_n = +\infty$, the sequence of function values $(f(x_n))$ converges to $L$. In particular, taking $x_n = n \in \mathbb{N}^+$ shows that a sequence is simply the restriction of a real function to positive integers!

### Fundamental Reciprocal Limits and Limit Laws for Functions
Just as for sequences, for any constant exponent $k > 0$:
$$\lim_{x\to\infty} \frac{1}{x^k} = 0 \quad \left(\text{in particular, } \lim_{x\to\infty} \frac{1}{x} = 0 \text{ and } \lim_{x\to\infty} \frac{1}{x^2} = 0\right).$$
Furthermore, if $\lim_{x\to\infty} g(x) = G$ and $\lim_{x\to\infty} h(x) = H$ with $H \neq 0$, the sum, difference, constant multiple, and quotient limit laws hold identically to the sequence case.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analyze the Domain and Indeterminate Form
Let the function be
$$f(x) = \frac{3x^2-x+1}{5x^2+4x-2}.$$
The domain of $f$ consists of all real numbers $x \in \mathbb{R}$ where the denominator $5x^2 + 4x - 2 \neq 0$. By the quadratic formula, the zeros of the denominator are:
$$x_{1,2} = \frac{-4 \pm \sqrt{16 - 4(5)(-2)}}{10} = \frac{-4 \pm \sqrt{56}}{10} = \frac{-2 \pm \sqrt{14}}{5} \approx -1.1483, \; 0.3483.$$
Since we are taking the limit as $x \to \infty$, we may restrict $x$ to the interval $(1, \infty)$, on which $5x^2 + 4x - 2 > 5(1)^2 + 4(1) - 2 = 7 > 0$. Thus $f(x)$ is well-defined and continuous on $(1, \infty)$, and $x \neq 0$.

As $x \to \infty$, both $3x^2 - x + 1 \to +\infty$ and $5x^2 + 4x - 2 \to +\infty$, giving the indeterminate form $\left[\frac{\infty}{\infty}\right]$.

### Step 2: Factor Out the Dominant Power $x^2$
Because both the numerator and denominator are quadratic polynomials (degree $2$), we factor out $x^2$ from each and cancel $x^2$ (valid since $x > 1 \implies x^2 \neq 0$):
$$\begin{aligned}
f(x) &= \frac{3x^2 - x + 1}{5x^2 + 4x - 2} \\[6pt]
&= \frac{x^2\left(3 - \frac{x}{x^2} + \frac{1}{x^2}\right)}{x^2\left(5 + \frac{4x}{x^2} - \frac{2}{x^2}\right)} \\[6pt]
&= \frac{3 - \frac{1}{x} + \frac{1}{x^2}}{5 + \frac{4}{x} - \frac{2}{x^2}}.
\end{aligned}$$

### Step 3: Evaluate the Limit Using Function Limit Laws
Using the elementary limits $\lim_{x\to\infty} \frac{1}{x} = 0$ and $\lim_{x\to\infty} \frac{1}{x^2} = 0$:
- Limit of the numerator:
  $$\lim_{x\to\infty} \left(3 - \frac{1}{x} + \frac{1}{x^2}\right) = 3 - 0 + 0 = 3.$$
- Limit of the denominator:
  $$\lim_{x\to\infty} \left(5 + \frac{4}{x} - \frac{2}{x^2}\right) = 5 + 4(0) - 2(0) = 5 \neq 0.$$

Applying the Quotient Rule for function limits:
$$\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2} = \frac{\lim_{x\to\infty}\left(3 - \frac{1}{x} + \frac{1}{x^2}\right)}{\lim_{x\to\infty}\left(5 + \frac{4}{x} - \frac{2}{x^2}\right)} = \frac{3}{5}.$$

---

### Step 4: Comparison with Exercise 1 — What Changes and What Stays the Same

#### What Stays the Same (Computational & Structural Similarity)
1. **Indeterminate Form and Principle of Dominant Terms:** Both limits have the indeterminate form $\left[\frac{\infty}{\infty}\right]$ with quadratic polynomials in the numerator and denominator. In both cases, the highest-degree terms ($4n^2$ and $2n^2$ in Exercise 1; $3x^2$ and $5x^2$ here) dominate for large arguments, and the limit equals the ratio of the leading coefficients ($4/2 = 2$ vs. $3/5$).
2. **Algebraic Technique:** The exact same algebraic manipulation—factoring out the highest power ($n^2$ or $x^2$) and canceling it—is used in both problems.
3. **Vanishing Reciprocal Terms and Limit Laws:** Both proofs rely on the vanishing of reciprocal powers ($\frac{1}{n}, \frac{1}{n^2} \to 0$ vs. $\frac{1}{x}, \frac{1}{x^2} \to 0$) and the algebraic limit laws for sums, constant multiples, and quotients.

#### What Changes (Conceptual & Domain Differences)
1. **Continuous Real Variable vs. Discrete Integer Index:**
   - In Exercise 1, the argument $n \in \mathbb{N}^+ = \{1, 2, 3, \dots\}$ takes only **discrete positive integer values**; the graph of the sequence is a set of isolated points $(n, a_n)$.
   - In Exercise 6, the argument $x \in \mathbb{R}$ varies **continuously** over all sufficiently large real numbers (including non-integers and irrationals like $x = 100.5$ or $x = 100\pi$); the graph of $f(x)$ is a continuous curve approaching the horizontal asymptote $y = \frac{3}{5}$.
2. **Domain Considerations (Zeros of the Denominator):**
   - For a sequence $a_n$, we only need the denominator to be non-zero for integers $n$ (or for all integers $n \ge N_0$).
   - For a function $f(x)$, the domain excludes all real roots of the denominator ($x = \frac{-2 \pm \sqrt{14}}{5}$). Because these roots are bounded above by $x_2 \approx 0.3483$, $f(x)$ is defined on the entire ray $(1, \infty)$, which allows the limit $x \to \infty$ to be taken over a continuous interval.
3. **Direction of Infinity:** For a sequence index $n \in \mathbb{N}^+$, only $n \to +\infty$ is meaningful. For a real function $f(x)$, one can study both $x \to +\infty$ and $x \to -\infty$ (here both equal $\frac{3}{5}$, giving the horizontal asymptote $y = \frac{3}{5}$ in both directions).

---

## 4. Verification and Consistency Checks

### Numerical Check for Large Real Values of $x$
Let us evaluate $f(x) = \frac{3x^2-x+1}{5x^2+4x-2}$ at several increasing real arguments (including non-integer values) and compare with $\frac{3}{5} = 0.6$:

| $x$ | Numerator $3x^2 - x + 1$ | Denominator $5x^2 + 4x - 2$ | $f(x)$ (Decimal Approx.) | Target Limit $\frac{3}{5}$ | Error $\left|f(x) - 0.6\right|$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $10.5$ | $321.25$ | $591.25$ | $0.543340$ | $0.600000$ | $0.056660$ |
| $100$ | $29{,}901$ | $50{,}398$ | $0.593297$ | $0.600000$ | $0.006703$ |
| $1{,}000.5$ | $3{,}002{,}000.25$ | $5{,}009{,}001.25$ | $0.599321$ | $0.600000$ | $0.000679$ |
| $10{,}000$ | $299{,}990{,}001$ | $500{,}039{,}998$ | $0.599932$ | $0.600000$ | $0.000068$ |

### Independent Algebraic Decomposition Check
We can rewrite $f(x)$ by extracting $\frac{3}{5}$ of the denominator from the numerator:
$$3x^2 - x + 1 = \frac{3}{5}(5x^2 + 4x - 2) - \frac{17}{5}x + \frac{11}{5}.$$
Dividing by $5x^2 + 4x - 2$ gives:
$$f(x) = \frac{3}{5} - \frac{17x - 11}{5(5x^2 + 4x - 2)}.$$
As $x \to \infty$, the remainder fraction has degree $1$ in the numerator and degree $2$ in the denominator, so by the Degree Trichotomy Rule from Exercise 2 it approaches $0$ (behaving like $\frac{17}{25x} = \frac{0.68}{x}$, which matches the error $0.00068$ at $x=1000$). Thus $\lim_{x\to\infty} f(x) = \frac{3}{5} - 0 = \frac{3}{5}$.

### Final Conclusion
$$\boxed{\lim_{x\to\infty}\frac{3x^2-x+1}{5x^2+4x-2} = \frac{3}{5}}$$
