# Exercise 2: Different Growth Rates

## 1. Problem Statement

Compute
$$\lim_{n\to\infty}\frac{3n+1}{n^2+4},\qquad \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}.$$
Compare the two cases and formulate a general observation about the degrees of the polynomials in the numerator and denominator.

> **Why this exercise:** teaches how to compare growth rates and recognize qualitatively different cases.

---

## 2. Theoretical Background and Concepts

When evaluating the limit as $n \to \infty$ of a rational expression
$$R(n) = \frac{P(n)}{Q(n)} = \frac{a_p n^p + a_{p-1} n^{p-1} + \dots + a_0}{b_q n^q + b_{q-1} n^{q-1} + \dots + b_0}, \quad a_p \neq 0, \; b_q \neq 0,$$
both $P(n)$ and $Q(n)$ grow without bound (assuming $p, q \ge 1$), creating an indeterminate form $\left[\frac{\infty}{\infty}\right]$. The outcome of the competition between the numerator and the denominator depends on their **relative growth rates**, which are determined by the degrees $p = \deg P$ and $q = \deg Q$:

1. **Factoring the Dominant Powers:** By factoring $n^p$ from the numerator and $n^q$ from the denominator, we obtain:
   $$\frac{P(n)}{Q(n)} = n^{p-q} \cdot \frac{a_p + \frac{a_{p-1}}{n} + \dots + \frac{a_0}{n^p}}{b_q + \frac{b_{q-1}}{n} + \dots + \frac{b_0}{n^q}}.$$
2. **Limit of the Normalized Ratio:** As $n \to \infty$, all reciprocal terms $\frac{1}{n^k}$ ($k \ge 1$) approach $0$, so the fraction on the right converges to the finite non-zero constant $\frac{a_p}{b_q}$.
3. **Behavior of the Power Factor $n^{p-q}$:**
   - If $p < q$, then $p - q < 0$, so $n^{p-q} = \frac{1}{n^{q-p}} \to 0$.
   - If $p = q$, then $p - q = 0$, so $n^{p-q} = 1$.
   - If $p > q$, then $p - q > 0$, so $n^{p-q} \to +\infty$.

---

## 3. Detailed Step-by-Step Solution

### Part A: First Limit $\lim_{n\to\infty}\frac{3n+1}{n^2+4}$

#### Step 1: Analyze the Degrees
Here the numerator is $P(n) = 3n + 1$, a polynomial of degree $\deg P = 1$, and the denominator is $Q(n) = n^2 + 4$, a polynomial of degree $\deg Q = 2$. Notice that $n^2 + 4 \ge 5 > 0$ for all $n \in \mathbb{N}^+$, so the expression is always well-defined.

#### Step 2: Factor Out the Highest Power of the Denominator ($n^2$)
Alternatively, we can factor $n$ from the numerator and $n^2$ from the denominator (or divide both numerator and denominator by $n^2$):
$$\begin{aligned}
\frac{3n+1}{n^2+4} &= \frac{n^2\left(\frac{3n}{n^2} + \frac{1}{n^2}\right)}{n^2\left(1 + \frac{4}{n^2}\right)} \\[6pt]
&= \frac{\frac{3}{n} + \frac{1}{n^2}}{1 + \frac{4}{n^2}}.
\end{aligned}$$
(Equivalently, factoring out the leading power from each separately gives $\frac{n(3 + 1/n)}{n^2(1 + 4/n^2)} = \frac{1}{n} \cdot \frac{3 + 1/n}{1 + 4/n^2}$.)

#### Step 3: Apply Limit Laws
Using $\lim_{n\to\infty} \frac{1}{n} = 0$ and $\lim_{n\to\infty} \frac{1}{n^2} = 0$:
- Numerator limit: $\lim_{n\to\infty} \left(\frac{3}{n} + \frac{1}{n^2}\right) = 3(0) + 0 = 0$.
- Denominator limit: $\lim_{n\to\infty} \left(1 + \frac{4}{n^2}\right) = 1 + 4(0) = 1 \neq 0$.

By the Quotient Rule for limits:
$$\lim_{n\to\infty}\frac{3n+1}{n^2+4} = \frac{0}{1} = 0.$$

---

### Part B: Second Limit $\lim_{n\to\infty}\frac{2n^3-n}{5n^2+1}$

#### Step 1: Analyze the Degrees
Here the numerator is $P(n) = 2n^3 - n$, a polynomial of degree $\deg P = 3$, and the denominator is $Q(n) = 5n^2 + 1$, a polynomial of degree $\deg Q = 2$. For all $n \in \mathbb{N}^+$, $5n^2 + 1 \ge 6 > 0$.

#### Step 2: Factor Out the Highest Powers from Numerator and Denominator
We factor $n^3$ from the numerator and $n^2$ from the denominator (or divide both numerator and denominator by $n^2$, the highest power of the denominator):
$$\begin{aligned}
\frac{2n^3-n}{5n^2+1} &= \frac{n^3\left(2 - \frac{1}{n^2}\right)}{n^2\left(5 + \frac{1}{n^2}\right)} \\[6pt]
&= n \cdot \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}}.
\end{aligned}$$

#### Step 3: Evaluate the Limit of Each Factor
As $n \to \infty$, $\frac{1}{n^2} \to 0$, so the rational factor converges to a strictly positive constant:
$$\lim_{n\to\infty} \frac{2 - \frac{1}{n^2}}{5 + \frac{1}{n^2}} = \frac{2 - 0}{5 + 0} = \frac{2}{5} > 0.$$
Meanwhile, the first factor satisfies:
$$\lim_{n\to\infty} n = +\infty.$$
Since the product consists of a sequence diverging to $+\infty$ and a sequence converging to a positive number $\frac{2}{5} > 0$, their product diverges to $+\infty$:
$$\lim_{n\to\infty}\frac{2n^3-n}{5n^2+1} = (+\infty) \cdot \frac{2}{5} = +\infty.$$

---

### Part C: Comparison and General Observation (The Degree Trichotomy Rule)

#### Comparison of the Two Cases
- In the **first limit**, the denominator has degree $2$ while the numerator has degree $1$. Quadratic growth $n^2$ outpaces linear growth $3n$ so overwhelmingly that the fraction shrinks like $\frac{3}{n} \to 0$.
- In the **second limit**, the numerator has degree $3$ while the denominator has degree $2$. Cubic growth $2n^3$ outpaces quadratic growth $5n^2$ by a factor of $\frac{2}{5}n$, causing the ratio to grow without bound toward $+\infty$.
- In **Exercise 1**, both numerator and denominator had degree $2$, so their growth rates were balanced ($n^2$ vs. $n^2$) and the limit was the finite non-zero ratio of leading coefficients $\frac{4}{2} = 2$.

#### General Trichotomy Rule for Rational Limits at Infinity
Let $P(n) = a_p n^p + \dots + a_0$ and $Q(n) = b_q n^q + \dots + b_0$ be polynomials with degrees $\deg P = p$ and $\deg Q = q$, where $a_p \neq 0$ and $b_q \neq 0$. Then:
$$\frac{P(n)}{Q(n)} = n^{p-q} \cdot \frac{a_p + \frac{a_{p-1}}{n} + \dots + \frac{a_0}{n^p}}{b_q + \frac{b_{q-1}}{n} + \dots + \frac{b_0}{n^q}}.$$
Comparing $\deg P = p$ and $\deg Q = q$ gives three exhaustive cases:

1. **Case 1: $\deg P < \deg Q$ ($p < q$).**
   The denominator grows faster than the numerator. The factor $n^{p-q} = \frac{1}{n^{q-p}} \to 0$, so:
   $$\lim_{n\to\infty} \frac{P(n)}{Q(n)} = 0.$$
2. **Case 2: $\deg P = \deg Q$ ($p = q$).**
   The numerator and denominator grow at the same rate. The powers $n^p$ and $n^q$ cancel completely ($n^{p-q} = 1$), and the limit equals the ratio of the leading coefficients:
   $$\lim_{n\to\infty} \frac{P(n)}{Q(n)} = \frac{a_p}{b_q}.$$
3. **Case 3: $\deg P > \deg Q$ ($p > q$).**
   The numerator grows faster than the denominator. The factor $n^{p-q} \to +\infty$, so the sequence diverges to $+\infty$ or $-\infty$ depending on the sign of the ratio of the leading coefficients $\frac{a_p}{b_q}$:
   $$\lim_{n\to\infty} \frac{P(n)}{Q(n)} = \begin{cases} +\infty & \text{if } \frac{a_p}{b_q} > 0, \\ -\infty & \text{if } \frac{a_p}{b_q} < 0. \end{cases}$$

---

## 4. Verification and Consistency Checks

### Numerical Check for Increasing $n$
Let $a_n = \frac{3n+1}{n^2+4}$ and $b_n = \frac{2n^3-n}{5n^2+1}$. Evaluating both sequences for $n = 10, 100, 1000$:

| $n$ | $a_n = \frac{3n+1}{n^2+4}$ | Asymptotic Approx. $\frac{3}{n}$ | $b_n = \frac{2n^3-n}{5n^2+1}$ | Asymptotic Approx. $\frac{2}{5}n = 0.4n$ |
| :--- | :--- | :--- | :--- | :--- |
| $10$ | $\frac{31}{104} \approx 0.298077$ | $0.300000$ | $\frac{1{,}990}{501} \approx 3.972056$ | $4.0$ |
| $100$ | $\frac{301}{10{,}004} \approx 0.030088$ | $0.030000$ | $\frac{1{,}999{,}900}{50{,}001} \approx 39.997200$ | $40.0$ |
| $1{,}000$ | $\frac{3{,}001}{1{,}000{,}004} \approx 0.003001$ | $0.003000$ | $\frac{1{,}999{,}999{,}000}{5{,}000{,}001} \approx 399.999720$ | $400.0$ |

### Independent Bounding Check
- For $a_n$: Since $n \ge 1$, $0 < \frac{3n+1}{n^2+4} \le \frac{3n+n}{n^2} = \frac{4}{n}$. By the Squeeze Theorem, since $\lim_{n\to\infty} 0 = 0$ and $\lim_{n\to\infty} \frac{4}{n} = 0$, we immediately confirm $\lim_{n\to\infty} a_n = 0$.
- For $b_n$: For $n \ge 1$, $2n^3 - n \ge n^3$ and $5n^2 + 1 \le 6n^2$, so $b_n \ge \frac{n^3}{6n^2} = \frac{n}{6} \to +\infty$, independently confirming divergence to $+\infty$.

### Final Conclusion
$$\boxed{\lim_{n\to\infty}\frac{3n+1}{n^2+4} = 0, \qquad \lim_{n\to\infty}\frac{2n^3-n}{5n^2+1} = +\infty}$$
