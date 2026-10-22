# Exercise 3: A Square Root and Removing an Indeterminate Form

## 1. Problem Statement

Compute
$$\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right).$$
Use the conjugate expression and explain why this transformation removes the difficulty.

> **Why this exercise:** introduces conjugation as a deliberate technique for removing an indeterminate form.

---

## 2. Theoretical Background and Concepts

### The Indeterminate Form $[\infty - \infty]$
As $n \to \infty$, both $\sqrt{n^2+5n} \to +\infty$ and $n \to +\infty$. Consequently, the difference $\sqrt{n^2+5n} - n$ is of the **indeterminate form** $[\infty - \infty]$.

A common mistake is to argue that because $\sqrt{n^2+5n} \approx \sqrt{n^2} = n$ for large $n$, the difference $\sqrt{n^2+5n} - n$ must approach $n - n = 0$. This reasoning is flawed: when two quantities both grow like $n$, their leading terms $n$ and $-n$ cancel out, so the limit of their difference is governed by the **next-order (sub-leading) correction** inside the square root!

### Conjugation (Rationalizing the Difference of Radicals)
To expose the exact sub-leading term without guesswork, we use the algebraic identity for the **difference of squares**:
$$(A - B)(A + B) = A^2 - B^2.$$
For an expression of the form $A - B = \sqrt{U} - V$ (where $A + B = \sqrt{U} + V > 0$), its **conjugate** is $A + B = \sqrt{U} + V$. Multiplying and dividing by the conjugate gives:
$$\sqrt{U} - V = \left(\sqrt{U} - V\right) \cdot \frac{\sqrt{U} + V}{\sqrt{U} + V} = \frac{U - V^2}{\sqrt{U} + V}.$$

### Continuity of the Square Root Function
Because the function $g(x) = \sqrt{x}$ is continuous on $[0, \infty)$, if a positive sequence $x_n$ converges to $L \ge 0$, then:
$$\lim_{n\to\infty} \sqrt{x_n} = \sqrt{\lim_{n\to\infty} x_n} = \sqrt{L}.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Terms and Multiply by the Conjugate
Let $a_n = \sqrt{n^2+5n} - n$ for $n \in \mathbb{N}^+$. Here $A = \sqrt{n^2+5n}$ and $B = n$.
Since $n \ge 1$, both $\sqrt{n^2+5n} > 0$ and $n > 0$, so the conjugate expression $\sqrt{n^2+5n} + n$ is strictly positive and never zero.

Multiplying $a_n$ by $1 = \frac{\sqrt{n^2+5n}+n}{\sqrt{n^2+5n}+n}$ and applying $(A-B)(A+B) = A^2 - B^2$ in the numerator gives:
$$\begin{aligned}
a_n &= \left(\sqrt{n^2+5n} - n\right) \cdot \frac{\sqrt{n^2+5n} + n}{\sqrt{n^2+5n} + n} \\[6pt]
&= \frac{\left(\sqrt{n^2+5n}\right)^2 - n^2}{\sqrt{n^2+5n} + n} \\[6pt]
&= \frac{(n^2 + 5n) - n^2}{\sqrt{n^2+5n} + n} \\[6pt]
&= \frac{5n}{\sqrt{n^2+5n} + n}.
\end{aligned}$$

### Step 2: Factor Out $n$ from the Radical and Simplify
Notice that after canceling $n^2 - n^2$ in the numerator, the expression $\frac{5n}{\sqrt{n^2+5n}+n}$ is now of the standard indeterminate form $\left[\frac{\infty}{\infty}\right]$, where both numerator and denominator grow linearly with $n$.

For $n > 0$, we have $\sqrt{n^2} = |n| = n$. Factoring $n^2$ out of the expression inside the square root yields:
$$\sqrt{n^2+5n} = \sqrt{n^2\left(1 + \frac{5}{n}\right)} = \sqrt{n^2}\sqrt{1 + \frac{5}{n}} = n\sqrt{1 + \frac{5}{n}}.$$

Substituting this back into the denominator and factoring out $n$:
$$\begin{aligned}
a_n &= \frac{5n}{n\sqrt{1 + \frac{5}{n}} + n} \\[6pt]
&= \frac{5n}{n\left(\sqrt{1 + \frac{5}{n}} + 1\right)} \\[6pt]
&= \frac{5}{\sqrt{1 + \frac{5}{n}} + 1}.
\end{aligned}$$

### Step 3: Evaluate the Limit as $n \to \infty$
Now we take the limit as $n \to \infty$:
1. Since $\lim_{n\to\infty} \frac{5}{n} = 0$, we have:
   $$\lim_{n\to\infty} \left(1 + \frac{5}{n}\right) = 1 + 0 = 1.$$
2. By the continuity of the square root function at $x = 1$:
   $$\lim_{n\to\infty} \sqrt{1 + \frac{5}{n}} = \sqrt{\lim_{n\to\infty}\left(1 + \frac{5}{n}\right)} = \sqrt{1} = 1.$$
3. Therefore, the denominator approaches $1 + 1 = 2 \neq 0$, and by the Quotient Rule:
   $$\lim_{n\to\infty} \left(\sqrt{n^2+5n} - n\right) = \lim_{n\to\infty} \frac{5}{\sqrt{1 + \frac{5}{n}} + 1} = \frac{5}{\sqrt{1 + 0} + 1} = \frac{5}{1 + 1} = \frac{5}{2}.$$

### Step 4: Why Conjugation Removes the Difficulty
Why did multiplying by the conjugate resolve the problem?
1. **Elimination of the Square Root in the Numerator:** In the original expression $\sqrt{n^2+5n} - n$, the leading term $n^2$ was trapped inside the radical $\sqrt{n^2+5n}$, preventing us from directly subtracting $n$ algebraically. Squaring both terms via $(A-B)(A+B) = A^2 - B^2$ liberated $n^2 + 5n$ from the radical, allowing the exact algebraic cancellation $(n^2 + 5n) - n^2 = 5n$.
2. **Replacing Cancellation ($\infty - \infty$) with Reinforcement ($\infty + \infty$):** In the original difference $\sqrt{n^2+5n} - n$, two nearly equal large quantities were subtracted, creating destructive cancellation where the dominant $O(n)$ parts vanished. In the denominator of the conjugated expression, $\sqrt{n^2+5n} + n$, the two positive terms are **added** ($\infty + \infty$). Because both terms are positive and reinforce each other ($\approx n + n = 2n$), there is no cancellation in the denominator, and factoring out $n$ immediately yields a non-zero limit $1 + 1 = 2$ in the denominator.

---

## 4. Verification and Consistency Checks

### Numerical Check for Large $n$
Let us compute $a_n = \sqrt{n^2+5n} - n$ for $n = 10, 100, 1000, 10000$ and compare with $\frac{5}{2} = 2.5$:

| $n$ | $n^2 + 5n$ | $\sqrt{n^2+5n}$ | $a_n = \sqrt{n^2+5n} - n$ | Target Limit $\frac{5}{2}$ | Error $\left|\frac{5}{2} - a_n\right|$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $10$ | $150$ | $12.2474487$ | $2.2474487$ | $2.5000000$ | $0.2525513$ |
| $100$ | $10{,}500$ | $102.4695077$ | $2.4695077$ | $2.5000000$ | $0.0304923$ |
| $1{,}000$ | $1{,}005{,}000$ | $1002.4968828$ | $2.4968828$ | $2.5000000$ | $0.0031172$ |
| $10{,}000$ | $100{,}050{,}000$ | $10002.4996876$ | $2.4996876$ | $2.5000000$ | $0.0003124$ |

### Independent Check via Completing the Square and Squeeze Theorem
We can complete the square inside the radical $\sqrt{n^2+5n}$:
$$n^2 + 5n = \left(n + \frac{5}{2}\right)^2 - \frac{25}{4}.$$
On one hand, for all $n \ge 1$, $n^2 + 5n < \left(n + \frac{5}{2}\right)^2$, so taking square roots gives $\sqrt{n^2+5n} < n + \frac{5}{2}$, or $\sqrt{n^2+5n} - n < \frac{5}{2}$.
On the other hand, for any $\varepsilon > 0$, when $n$ is large enough, $n^2 + 5n > \left(n + \frac{5}{2} - \varepsilon\right)^2 = n^2 + (5 - 2\varepsilon)n + \left(\frac{5}{2}-\varepsilon\right)^2$. This confirms intuitively and rigorously why $\sqrt{n^2+5n}$ behaves like $n + \frac{5}{2}$ for large $n$, making $\sqrt{n^2+5n} - n \to \frac{5}{2}$ from below.

### Final Conclusion
$$\boxed{\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right) = \frac{5}{2}}$$
