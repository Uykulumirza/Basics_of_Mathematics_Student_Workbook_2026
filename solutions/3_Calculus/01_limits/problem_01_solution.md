# Exercise 1: Dominant Terms in a Sequence

## 1. Problem Statement

Compute
$$\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7}.$$
Explain why the highest-degree terms determine the result.

> **Why this exercise:** introduces the idea of a dominant term and teaches how to simplify the behavior of expressions for large arguments.

---

## 2. Theoretical Background and Concepts

When evaluating the limit of a rational sequence $a_n = \frac{P(n)}{Q(n)}$ as $n \to \infty$, direct substitution of "$n = \infty$" leads to the **indeterminate form** $\left[\frac{\infty}{\infty}\right]$, because both the numerator $4n^2 - 3n + 1$ and the denominator $2n^2 + 5n - 7$ grow without bound as $n \to \infty$.

To resolve this indeterminate form rigorously, we rely on the following fundamental properties of sequence limits:

1. **Basic Reciprocal Limits:** For any positive exponent $k > 0$,
   $$\lim_{n\to\infty} \frac{1}{n^k} = 0.$$
   In particular, $\lim_{n\to\infty} \frac{1}{n} = 0$ and $\lim_{n\to\infty} \frac{1}{n^2} = 0$.
2. **Algebraic Limit Laws for Convergent Sequences:** If $\lim_{n\to\infty} x_n = X$ and $\lim_{n\to\infty} y_n = Y$ (where $X, Y \in \mathbb{R}$), then:
   - **Linearity:** $\lim_{n\to\infty} (c x_n \pm d y_n) = cX \pm dY$ for any constants $c, d \in \mathbb{R}$.
   - **Quotient Rule:** $\lim_{n\to\infty} \frac{x_n}{y_n} = \frac{X}{Y}$, provided that $Y \neq 0$ and $y_n \neq 0$ for all sufficiently large $n$.
3. **Principle of Dominant Terms:** In any polynomial $P(n) = c_k n^k + c_{k-1} n^{k-1} + \dots + c_0$ with leading coefficient $c_k \neq 0$, factoring out the highest power $n^k$ gives:
   $$P(n) = n^k \left(c_k + \frac{c_{k-1}}{n} + \dots + \frac{c_0}{n^k}\right).$$
   As $n \to \infty$, all fractions $\frac{c_j}{n^{k-j}}$ vanish, meaning the parenthetical factor converges to the non-zero constant $c_k$. Thus, the asymptotic behavior of the entire polynomial for large $n$ is governed by its **leading (highest-degree) term** $c_k n^k$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form and Highest Power
Let the sequence be denoted by
$$a_n = \frac{4n^2-3n+1}{2n^2+5n-7}, \quad n \in \mathbb{N}^+.$$
Note that for all $n \ge 1$, the quadratic $2n^2 + 5n - 7 = (2n+7)(n-1)$ is zero only at $n=1$; for all $n \ge 2$, the denominator is strictly positive ($2n^2 + 5n - 7 \ge 8 + 10 - 7 = 11 > 0$), so $a_n$ is well-defined for all $n \ge 2$. Since we only care about the behavior as $n \to \infty$, we restrict attention to $n \ge 2$.

Both the numerator and the denominator are polynomials of degree $2$:
- Numerator: $P(n) = 4n^2 - 3n + 1$, with highest-degree term $4n^2$.
- Denominator: $Q(n) = 2n^2 + 5n - 7$, with highest-degree term $2n^2$.

As $n \to \infty$, both $P(n) \to +\infty$ and $Q(n) \to +\infty$, yielding the indeterminate form $\left[\frac{\infty}{\infty}\right]$.

### Step 2: Factor Out the Highest Power $n^2$
We factor $n^2$ out of every term in both the numerator and the denominator. Because $n \ge 2 > 0$, we have $n^2 \neq 0$, allowing us to cancel the common factor $n^2$:

$$\begin{aligned}
a_n &= \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} \\[6pt]
&= \frac{n^2 \left(4 - \frac{3n}{n^2} + \frac{1}{n^2}\right)}{n^2 \left(2 + \frac{5n}{n^2} - \frac{7}{n^2}\right)} \\[6pt]
&= \frac{4 - \frac{3}{n} + \frac{1}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}}.
\end{aligned}$$

### Step 3: Evaluate the Limits of the Individual Terms
We know the elementary reciprocal limits:
$$\lim_{n\to\infty} \frac{1}{n} = 0 \quad \text{and} \quad \lim_{n\to\infty} \frac{1}{n^2} = 0.$$

Using the constant multiple and sum/difference limit laws, we compute the limit of the transformed numerator:
$$\lim_{n\to\infty} \left(4 - \frac{3}{n} + \frac{1}{n^2}\right) = 4 - 3\left(\lim_{n\to\infty} \frac{1}{n}\right) + \lim_{n\to\infty} \frac{1}{n^2} = 4 - 3(0) + 0 = 4.$$

Similarly, we compute the limit of the transformed denominator:
$$\lim_{n\to\infty} \left(2 + \frac{5}{n} - \frac{7}{n^2}\right) = 2 + 5\left(\lim_{n\to\infty} \frac{1}{n}\right) - 7\left(\lim_{n\to\infty} \frac{1}{n^2}\right) = 2 + 5(0) - 7(0) = 2.$$

### Step 4: Apply the Quotient Rule for Limits
Since both the new numerator and denominator converge to finite real numbers, and the limit of the denominator is $2 \neq 0$, the Quotient Rule for limits applies directly:
$$\lim_{n\to\infty} \frac{4n^2-3n+1}{2n^2+5n-7} = \frac{\lim_{n\to\infty}\left(4 - \frac{3}{n} + \frac{1}{n^2}\right)}{\lim_{n\to\infty}\left(2 + \frac{5}{n} - \frac{7}{n^2}\right)} = \frac{4}{2} = 2.$$

### Step 5: Explanation of Why the Highest-Degree Terms Dominate
Why do the lower-degree terms ($-3n + 1$ in the numerator and $+5n - 7$ in the denominator) have no effect on the final limit?

1. **Relative Magnitude (Asymptotic Ratio):** As $n$ grows large, $n^2$ grows much faster than $n$ or a constant $1$. Specifically, comparing the linear term $-3n$ to the quadratic term $4n^2$ via their ratio gives:
   $$\frac{|-3n|}{4n^2} = \frac{3}{4n} \xrightarrow{n\to\infty} 0, \qquad \frac{1}{4n^2} \xrightarrow{n\to\infty} 0.$$
   For instance, when $n = 1000$, the leading term in the numerator is $4n^2 = 4{,}000{,}000$, whereas the linear and constant terms combined are $-3(1000) + 1 = -2{,}999$, which accounts for less than $0.075\%$ of the value of the numerator.
2. **Survival After Normalization:** When we divide numerator and denominator by the common growth scale $n^2$, the highest-degree terms $4n^2$ and $2n^2$ become the non-zero constants $4$ and $2$, whereas every lower-degree term $c \cdot n^k$ ($k < 2$) gets divided by a higher power of $n$, turning into $\frac{c}{n^{2-k}} \to 0$. Thus, in the limit $n \to \infty$, only the ratio of the leading terms survives:
   $$\lim_{n\to\infty} \frac{4n^2 - 3n + 1}{2n^2 + 5n - 7} = \lim_{n\to\infty} \frac{4n^2}{2n^2} = \frac{4}{2} = 2.$$

---

## 4. Verification and Consistency Checks

### Numerical Check for Large $n$
Let us evaluate $a_n = \frac{4n^2-3n+1}{2n^2+5n-7}$ for increasing values of $n$ to confirm the convergence toward $2$:

| $n$ | Numerator $4n^2 - 3n + 1$ | Denominator $2n^2 + 5n - 7$ | $a_n$ (Exact Fraction) | $a_n$ (Decimal Approx.) | Error $|a_n - 2|$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $10$ | $371$ | $243$ | $\frac{371}{243}$ | $1.526749$ | $0.473251$ |
| $100$ | $39{,}701$ | $20{,}493$ | $\frac{39{,}701}{20{,}493}$ | $1.937296$ | $0.062704$ |
| $1{,}000$ | $3{,}997{,}001$ | $2{,}004{,}993$ | $\frac{3{,}997{,}001}{2{,}004{,}993}$ | $1.993524$ | $0.006476$ |
| $10{,}000$ | $399{,}970{,}001$ | $200{,}049{,}993$ | $\frac{399{,}970{,}001}{200{,}049{,}993}$ | $1.999350$ | $0.000650$ |

Each tenfold increase in $n$ reduces the distance $|a_n - 2|$ by a factor of approximately $10$, confirming convergence to $2$.

### Independent Algebraic Check (Polynomial Division / Decomposition)
We can also rewrite $a_n$ by splitting off the leading multiple of the denominator:
$$4n^2 - 3n + 1 = 2(2n^2 + 5n - 7) - 13n + 15.$$
Dividing both sides by $2n^2 + 5n - 7$ (for $n \ge 2$) yields:
$$a_n = 2 - \frac{13n - 15}{2n^2 + 5n - 7}.$$
In the remainder fraction, dividing numerator and denominator by $n^2$ gives:
$$\frac{13n - 15}{2n^2 + 5n - 7} = \frac{\frac{13}{n} - \frac{15}{n^2}}{2 + \frac{5}{n} - \frac{7}{n^2}} \xrightarrow{n\to\infty} \frac{0 - 0}{2 + 0 - 0} = 0.$$
This not only confirms $\lim_{n\to\infty} a_n = 2 - 0 = 2$, but also explains why $a_n$ approaches $2$ from below ($a_n \approx 2 - \frac{13}{2n} = 2 - \frac{6.5}{n}$ for large $n$, matching our table where $a_{1000} \approx 2 - 0.0065 = 1.9935$).

### Final Conclusion
$$\boxed{\lim_{n\to\infty}\frac{4n^2-3n+1}{2n^2+5n-7} = 2}$$
