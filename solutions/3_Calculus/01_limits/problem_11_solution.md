# Exercise 11: An $n$-th Root

## 1. Problem Statement

Compute
$$\lim_{n\to\infty}\sqrt[n]{5^n+2^n}.$$
Explain which term dominates and why the transformation looks different from the case of a quotient of polynomials.

> **Why this exercise:** extends the idea of dominance to exponential expressions.

---

## 2. Theoretical Background and Concepts

### Exponential Dominance and the $n$-th Root Scale
In the sequence $a_n = \sqrt[n]{5^n + 2^n} = (5^n + 2^n)^{1/n}$, the expression inside the $n$-th root is a sum of two exponential terms, $5^n$ and $2^n$, with bases $5 > 2 > 0$. As $n \to \infty$:
- Inside the radical, $5^n + 2^n \to +\infty$.
- Outside the radical, the exponent $\frac{1}{n} \to 0$.
This creates the indeterminate form $[\infty^0]$.

To resolve it, we rely on three tools:
1. **Factoring Out the Dominant Exponential ($5^n$):** Since $5 > 2$, their ratio $\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n$ is a geometric sequence with base $r = \frac{2}{5} \in (0, 1)$, so $\lim_{n\to\infty} \left(\frac{2}{5}\right)^n = 0$.
2. **Properties of Radicals:** For any positive numbers $A, B > 0$, $\sqrt[n]{A \cdot B} = \sqrt[n]{A}\sqrt[n]{B}$, and $\sqrt[n]{5^n} = 5$.
3. **The Squeeze Theorem and the Fundamental $n$-th Root Limit:**
   For any constant $c > 0$,
   $$\lim_{n\to\infty} \sqrt[n]{c} = \lim_{n\to\infty} c^{1/n} = c^0 = 1.$$
   In particular, $\lim_{n\to\infty} \sqrt[n]{2} = 1$.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Via the Squeeze Theorem (Sandwich Theorem)

#### Step 1: Construct Lower and Upper Bounds Using the Dominant Term $5^n$
For every positive integer $n \in \mathbb{N}^+$, since $2^n > 0$ and $2^n < 5^n$ (because $0 < 2 < 5$), we can trap the sum $5^n + 2^n$ between $5^n$ and $2 \cdot 5^n$:
$$5^n < 5^n + 2^n < 5^n + 5^n = 2 \cdot 5^n.$$

#### Step 2: Take the $n$-th Root Across the Inequality
Because the $n$-th root function $x \mapsto \sqrt[n]{x} = x^{1/n}$ is strictly increasing on $(0, \infty)$, taking the $n$-th root preserves the inequalities:
$$\sqrt[n]{5^n} < \sqrt[n]{5^n + 2^n} < \sqrt[n]{2 \cdot 5^n}.$$
Simplifying the left and right sides using $\sqrt[n]{5^n} = 5$ and $\sqrt[n]{2 \cdot 5^n} = 5\sqrt[n]{2}$ gives:
$$5 < \sqrt[n]{5^n + 2^n} < 5 \cdot 2^{1/n} \quad \text{for all } n \in \mathbb{N}^+.$$

#### Step 3: Evaluate the Limits of the Bounding Sequences
- The lower bound is the constant sequence $L_n = 5$, so $\lim_{n\to\infty} 5 = 5$.
- For the upper bound $U_n = 5 \cdot 2^{1/n}$, since $\lim_{n\to\infty} \frac{1}{n} = 0$ and the exponential function $t \mapsto 2^t$ is continuous at $t = 0$ (or using the standard theorem $\lim_{n\to\infty} \sqrt[n]{2} = 1$), we have:
  $$\lim_{n\to\infty} \left(5 \cdot 2^{1/n}\right) = 5 \cdot \lim_{n\to\infty} 2^{1/n} = 5 \cdot 2^0 = 5 \cdot 1 = 5.$$

By the **Squeeze Theorem**, since $a_n = \sqrt[n]{5^n + 2^n}$ is trapped between two sequences that both converge to $5$, we conclude:
$$\lim_{n\to\infty} \sqrt[n]{5^n + 2^n} = 5.$$

---

### Method 2: Factoring Out $5^n$ Directly Inside the Radical
We can also write the transformation algebraically by factoring the dominant exponential $5^n$ out of the sum inside the $n$-th root:
$$\begin{aligned}
\sqrt[n]{5^n + 2^n} &= \sqrt[n]{5^n \left(1 + \frac{2^n}{5^n}\right)} \\[6pt]
&= \sqrt[n]{5^n} \cdot \sqrt[n]{1 + \left(\frac{2}{5}\right)^n} \\[6pt]
&= 5 \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n}.
\end{aligned}$$
Since $0 < \left(\frac{2}{5}\right)^n < 1$ for all $n \ge 1$, we have $1 < 1 + \left(\frac{2}{5}\right)^n < 2$, and therefore:
$$1 = 1^{1/n} < \left(1 + \left(\frac{2}{5}\right)^n\right)^{1/n} < 2^{1/n} \xrightarrow{n\to\infty} 1.$$
Multiplying by $5$ again yields $\lim_{n\to\infty} \sqrt[n]{5^n + 2^n} = 5 \cdot 1 = 5$.

---

### Step 4: Explanation of Dominance and Comparison with Quotients of Polynomials

1. **Which Term Dominates and Why:**
   The term **$5^n$ dominates $2^n$ exponentially**. Because the base $5$ is larger than the base $2$, the ratio of the sub-leading term to the leading term decays geometrically to zero:
   $$\frac{2^n}{5^n} = \left(\frac{2}{5}\right)^n = (0.4)^n \xrightarrow{n\to\infty} 0.$$
   For example, already at $n = 20$, $(0.4)^{20} \approx 1.1 \times 10^{-8}$, so $2^{20}$ is less than one hundred-millionth of $5^{20}$.

2. **Why the Transformation Looks Different from a Quotient of Polynomials:**
   - **Different Operation Neutralizing Growth ($\sqrt[n]{\cdot}$ vs. Division):**
     In a quotient of polynomials (such as $\frac{4n^2 - 3n + 1}{2n^2 + 5n - 7}$ in Exercise 1), the growth in the numerator is balanced by **division** by the denominator, so factoring out $n^2$ from top and bottom causes $n^2 / n^2 = 1$ to **cancel completely**, leaving the ratio of leading coefficients $\frac{4}{2} = 2$.
     In $\sqrt[n]{5^n + 2^n}$, there is no denominator! Instead, the exponential growth of $5^n$ is neutralized by the **$n$-th root operation** $(\cdot)^{1/n}$. When we factor $5^n$ out of the radical, it does not cancel against a denominator—instead, the $n$-th root reduces $5^n$ to its **base**:
     $$\sqrt[n]{5^n} = (5^n)^{1/n} = 5.$$
   - **Exponential vs. Power-Law Factoring:**
     In a polynomial, we factor out the highest power of the variable ($n^k$), turning lower terms into $\frac{c}{n^j} \to 0$. In a sum of exponentials $a^n + b^n$ with $a > b > 0$, we factor out the exponential with the **largest base** ($a^n$), turning the smaller exponential into a geometric sequence $\left(\frac{b}{a}\right)^n \to 0$.

---

## 4. Verification and Consistency Checks

### Numerical Check for Increasing $n$
Let us compute $a_n = \sqrt[n]{5^n + 2^n} = 5\left(1 + (0.4)^n\right)^{1/n}$ for increasing values of $n$:

| $n$ | $5^n$ | $2^n$ | Ratio $(2/5)^n$ | $a_n = \sqrt[n]{5^n + 2^n}$ | Error $a_n - 5$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $1$ | $5$ | $2$ | $0.40000000$ | $7.00000000$ | $2.00000000$ |
| $2$ | $25$ | $4$ | $0.16000000$ | $\sqrt{29} \approx 5.38516481$ | $0.38516481$ |
| $5$ | $3{,}125$ | $32$ | $0.01024000$ | $\sqrt[5]{3157} \approx 5.01019843$ | $0.01019843$ |
| $10$ | $9{,}765{,}625$ | $1{,}024$ | $0.00010486$ | $\sqrt[10]{9766649} \approx 5.00005243$ | $0.00005243$ |
| $20$ | $9.537 \times 10^{13}$ | $1{,}048{,}576$ | $1.0995 \times 10^{-8}$ | $5.0000000027$ | $2.75 \times 10^{-9}$ |

Notice how extraordinarily fast $a_n$ converges to $5$: at $n = 20$, $a_n$ is already within $3 \times 10^{-9}$ of $5$ because $(1 + x)^{1/n} \approx 1 + \frac{x}{n}$, so $a_n - 5 \approx \frac{5}{n}\left(\frac{2}{5}\right)^n$, which decays both algebraically and exponentially!

### Generalization Check ($\max$ Norm Property)
For any positive numbers $c_1, c_2, \dots, c_k > 0$, the same Squeeze Theorem argument shows:
$$\lim_{n\to\infty} \sqrt[n]{c_1^n + c_2^n + \dots + c_k^n} = \max(c_1, c_2, \dots, c_k).$$
Here $\max(5, 2) = 5$, which is consistent with our result.

### Final Conclusion
$$\boxed{\lim_{n\to\infty}\sqrt[n]{5^n+2^n} = 5}$$
