# Exercise 4: Powers and Oscillation

## 1. Problem Statement

Analyze
$$\left(\frac23\right)^n,\qquad \left(\frac32\right)^n,\qquad (-1)^n,\qquad \frac{(-1)^n}{n}.$$
For each sequence, describe the type of behavior and justify your answer.

> **Why this exercise:** organizes the basic types of sequence behavior and shows that oscillation does not always rule out convergence.

---

## 2. Theoretical Background and Concepts

To classify the behavior of sequences as $n \to \infty$, we use the following core theorems of real analysis:

1. **Geometric Sequence Behavior ($r^n$):** For a fixed real ratio $r \in \mathbb{R}$, the behavior of the geometric sequence $a_n = r^n$ depends critically on $r$:
   - If $|r| < 1$, then $\lim_{n\to\infty} r^n = 0$. If $0 < r < 1$, the decay is strictly monotonic ($r^{n+1} < r^n$).
   - If $r = 1$, then $r^n = 1 \to 1$.
   - If $r > 1$, then $\lim_{n\to\infty} r^n = +\infty$ (strictly increasing unbounded exponential growth). By **Bernoulli's Inequality**, writing $r = 1 + h$ with $h = r - 1 > 0$ gives $(1+h)^n \ge 1 + nh \to +\infty$.
   - If $r \le -1$, the sequence diverges by oscillation (bounded oscillation if $r = -1$; unbounded oscillation if $r < -1$).

2. **Subsequence Criterion for Convergence:** A sequence $(a_n)$ converges to a limit $L$ if and only if **every** subsequence $(a_{n_k})$ converges to the same limit $L$. In particular, if the subsequence of even-indexed terms $(a_{2k})$ and the subsequence of odd-indexed terms $(a_{2k-1})$ converge to two different limits ($L_{\text{even}} \neq L_{\text{odd}}$), then $\lim_{n\to\infty} a_n$ **does not exist**.

3. **Squeeze Theorem (Sandwich Theorem) and Absolute Value Criterion:**
   - If $x_n \le y_n \le z_n$ for all sufficiently large $n$, and $\lim_{n\to\infty} x_n = \lim_{n\to\infty} z_n = L$, then $\lim_{n\to\infty} y_n = L$.
   - As a special case, $\lim_{n\to\infty} a_n = 0 \iff \lim_{n\to\infty} |a_n| = 0$, because $-|a_n| \le a_n \le |a_n|$.

---

## 3. Detailed Step-by-Step Solution

### Sequence 1: $a_n = \left(\frac{2}{3}\right)^n$

- **Type of Behavior:** **Convergent to $0$; strictly decreasing (monotonic geometric decay).**
- **Limit:** $\lim_{n\to\infty} \left(\frac{2}{3}\right)^n = 0$.
- **Justification:**
  1. **Positivity and Monotonicity:** Since $\frac{2}{3} > 0$, we have $a_n = \left(\frac{2}{3}\right)^n > 0$ for all $n \in \mathbb{N}^+$. Furthermore, the ratio of consecutive terms is:
     $$\frac{a_{n+1}}{a_n} = \frac{2}{3} < 1 \implies a_{n+1} < a_n \quad \text{for all } n \ge 1.$$
     Since $(a_n)$ is strictly decreasing and bounded below by $0$, the Monotone Convergence Theorem guarantees that $L = \lim_{n\to\infty} a_n$ exists and $L \ge 0$.
  2. **Rigorous Value of the Limit:** Passing to the limit in the recurrence relation $a_{n+1} = \frac{2}{3} a_n$ gives $L = \frac{2}{3} L \implies \frac{1}{3}L = 0 \implies L = 0$.
     Alternatively, since $r = \frac{2}{3}$ satisfies $|r| = \frac{2}{3} < 1$, the standard geometric sequence theorem yields $\lim_{n\to\infty} \left(\frac{2}{3}\right)^n = 0$.

---

### Sequence 2: $b_n = \left(\frac{3}{2}\right)^n$

- **Type of Behavior:** **Divergent to $+\infty$; strictly increasing (unbounded exponential growth).**
- **Limit:** $\lim_{n\to\infty} \left(\frac{3}{2}\right)^n = +\infty$.
- **Justification:**
  1. **Monotonic Growth:** Here the base is $r = \frac{3}{2} = 1.5 > 1$. For every $n \ge 1$,
     $$b_{n+1} = \frac{3}{2} b_n > b_n > 0,$$
     so the sequence is strictly increasing.
  2. **Unboundedness via Bernoulli's Inequality:** Write $\frac{3}{2} = 1 + \frac{1}{2}$. By Bernoulli's Inequality ($(1+h)^n \ge 1 + nh$ for $h > -1$ and $n \in \mathbb{N}^+$):
     $$\left(\frac{3}{2}\right)^n = \left(1 + \frac{1}{2}\right)^n \ge 1 + \frac{n}{2}.$$
     Since $\lim_{n\to\infty} \left(1 + \frac{n}{2}\right) = +\infty$, by comparison we conclude that $\lim_{n\to\infty} \left(\frac{3}{2}\right)^n = +\infty$.

---

### Sequence 3: $c_n = (-1)^n$

- **Type of Behavior:** **Divergent by bounded (undamped) oscillation.**
- **Limit:** $\lim_{n\to\infty} (-1)^n$ **does not exist**.
- **Justification:**
  The terms of the sequence alternate perpetually between $-1$ and $+1$:
  $$(c_n)_{n=1}^\infty = (-1, +1, -1, +1, -1, +1, \dots).$$
  To prove rigorously that the limit does not exist, examine the even and odd subsequences:
  - **Even subsequence ($n = 2k$, $k \in \mathbb{N}^+$):**
    $$c_{2k} = (-1)^{2k} = \left((-1)^2\right)^k = 1^k = 1 \implies \lim_{k\to\infty} c_{2k} = 1.$$
  - **Odd subsequence ($n = 2k-1$, $k \in \mathbb{N}^+$):**
    $$c_{2k-1} = (-1)^{2k-1} = -1 \implies \lim_{k\to\infty} c_{2k-1} = -1.$$
  Because the two subsequences converge to different limits ($1 \neq -1$), the sequence $c_n = (-1)^n$ cannot approach any single real number (nor $\pm\infty$), and therefore diverges.

---

### Sequence 4: $d_n = \frac{(-1)^n}{n}$

- **Type of Behavior:** **Convergent to $0$ via damped oscillation (alternating signs with decreasing amplitude).**
- **Limit:** $\lim_{n\to\infty} \frac{(-1)^n}{n} = 0$.
- **Justification:**
  The first few terms are $-1, +\frac{1}{2}, -\frac{1}{3}, +\frac{1}{4}, -\frac{1}{5}, \dots$. Although the sign alternates between positive and negative just like $(-1)^n$, the amplitude of the oscillation is divided by $n$ and shrinks toward $0$. We can prove convergence to $0$ in two equivalent ways:
  1. **Method 1: Squeeze Theorem:**
     For every $n \in \mathbb{N}^+$, we have $-1 \le (-1)^n \le 1$. Dividing this inequality by $n > 0$ preserves the inequality signs:
     $$-\frac{1}{n} \le \frac{(-1)^n}{n} \le \frac{1}{n}.$$
     Since $\lim_{n\to\infty} \left(-\frac{1}{n}\right) = 0$ and $\lim_{n\to\infty} \frac{1}{n} = 0$, the **Squeeze Theorem** implies that:
     $$\lim_{n\to\infty} \frac{(-1)^n}{n} = 0.$$
  2. **Method 2: Absolute Value Criterion:**
     Taking the absolute value of $d_n$ gives:
     $$|d_n| = \left|\frac{(-1)^n}{n}\right| = \frac{|(-1)^n|}{|n|} = \frac{1}{n}.$$
     Since $\lim_{n\to\infty} |d_n| = \lim_{n\to\infty} \frac{1}{n} = 0$, it follows immediately that $\lim_{n\to\infty} d_n = 0$.

---

## 4. Verification and Consistency Checks

### Numerical Comparison Table
The table below illustrates the four distinct qualitative behaviors across increasing values of $n$:

| $n$ | $a_n = \left(\frac{2}{3}\right)^n$ (Geometric Decay) | $b_n = \left(\frac{3}{2}\right)^n$ (Exponential Growth) | $c_n = (-1)^n$ (Undamped Oscillation) | $d_n = \frac{(-1)^n}{n}$ (Damped Oscillation) |
| :--- | :--- | :--- | :--- | :--- |
| $1$ | $0.666667$ | $1.500000$ | $-1$ | $-1.000000$ |
| $2$ | $0.444444$ | $2.250000$ | $+1$ | $+0.500000$ |
| $3$ | $0.296296$ | $3.375000$ | $-1$ | $-0.333333$ |
| $4$ | $0.197531$ | $5.062500$ | $+1$ | $+0.250000$ |
| $10$ | $0.017342$ | $57.665039$ | $+1$ | $+0.100000$ |
| $20$ | $0.000301$ | $3{,}325.256730$ | $+1$ | $+0.050000$ |
| $100$ | $2.46 \times 10^{-18}$ | $4.07 \times 10^{17}$ | $+1$ | $+0.010000$ |
| **As $n \to \infty$** | **$\to 0$** | **$\to +\infty$** | **Does not exist** | **$\to 0$** |

### Consistency Check Between Sequences 1 & 2 and Sequences 3 & 4
- Notice that $a_n \cdot b_n = \left(\frac{2}{3}\right)^n \left(\frac{3}{2}\right)^n = 1^n = 1$ for all $n$. Since $b_n = \frac{1}{a_n}$ and $a_n > 0$ with $a_n \to 0^+$, it is completely consistent that $b_n = \frac{1}{a_n} \to +\infty$.
- Comparing $c_n = (-1)^n$ and $d_n = \frac{(-1)^n}{n}$ highlights an essential pedagogical insight: **oscillation of sign does not prevent convergence**, provided the amplitude $|d_n|$ of the oscillation converges to $0$.

### Final Conclusion
$$\boxed{\lim_{n\to\infty}\left(\frac{2}{3}\right)^n = 0, \quad \lim_{n\to\infty}\left(\frac{3}{2}\right)^n = +\infty, \quad \lim_{n\to\infty}(-1)^n \text{ DNE}, \quad \lim_{n\to\infty}\frac{(-1)^n}{n} = 0}$$
