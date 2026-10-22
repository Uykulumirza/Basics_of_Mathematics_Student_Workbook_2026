# Exercise 8: A Square Root in a Function Limit

## 1. Problem Statement

Compute
$$\lim_{x\to4}\frac{\sqrt{x}-2}{x-4}$$
by rationalizing the numerator. Compare the idea with Exercise 3 involving a sequence.

> **Why this exercise:** reinforces transferring the same algebraic technique between two types of limits.

---

## 2. Theoretical Background and Concepts

### The Indeterminate Form $\left[\frac{0}{0}\right]$ Involving Radicals
When evaluating $\lim_{x\to x_0} \frac{f(x)}{g(x)}$ where both $f(x_0) = 0$ and $g(x_0) = 0$, the zero in the numerator and the zero in the denominator are caused by a hidden common factor that vanishes at $x = x_0$. When the numerator or denominator contains a square root $\sqrt{x} - \sqrt{x_0}$, we can expose the factor $x - x_0$ using **conjugation (rationalization)**.

### Rationalizing the Numerator via Difference of Squares
For any $x \ge 0$ and $a > 0$, multiplying $\sqrt{x} - a$ by its **conjugate** $\sqrt{x} + a$ and applying the difference-of-squares identity $(A - B)(A + B) = A^2 - B^2$ gives:
$$\left(\sqrt{x} - a\right)\left(\sqrt{x} + a\right) = \left(\sqrt{x}\right)^2 - a^2 = x - a^2.$$
Equivalently, one can view $x - a^2$ as a difference of squares of $\sqrt{x}$ and $a$:
$$x - a^2 = \left(\sqrt{x}\right)^2 - a^2 = \left(\sqrt{x} - a\right)\left(\sqrt{x} + a\right).$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Indeterminate Form Analysis
Consider the function
$$f(x) = \frac{\sqrt{x}-2}{x-4}, \quad D_f = [0, 4) \cup (4, \infty).$$
Since $x = 4$ is an interior point of $[0, \infty)$ (except for being punctured at $4$), $f(x)$ is defined on the punctured neighborhood $(0, 4) \cup (4, \infty)$ around $x = 4$.

Testing the limits of the numerator and denominator as $x \to 4$:
- Numerator: $\lim_{x\to 4} (\sqrt{x} - 2) = \sqrt{4} - 2 = 2 - 2 = 0$.
- Denominator: $\lim_{x\to 4} (x - 4) = 4 - 4 = 0$.

Thus, we have the indeterminate form $\left[\frac{0}{0}\right]$.

### Step 2: Rationalize the Numerator Using the Conjugate
The conjugate of $\sqrt{x} - 2$ is $\sqrt{x} + 2$. For all $x \ge 0$, we have $\sqrt{x} \ge 0$, so $\sqrt{x} + 2 \ge 2 > 0$. Therefore, multiplying the numerator and denominator by $\sqrt{x} + 2$ is valid for all $x \in D_f$:
$$\begin{aligned}
\frac{\sqrt{x}-2}{x-4} &= \frac{\sqrt{x}-2}{x-4} \cdot \frac{\sqrt{x}+2}{\sqrt{x}+2} \\[6pt]
&= \frac{\left(\sqrt{x}\right)^2 - 2^2}{(x-4)\left(\sqrt{x}+2\right)} \\[6pt]
&= \frac{x - 4}{(x-4)\left(\sqrt{x}+2\right)}.
\end{aligned}$$

### Step 3: Cancel the Zero-Producing Factor $(x - 4)$ and Compute the Limit
When taking the limit as $x \to 4$, we only consider values $x \neq 4$, so $x - 4 \neq 0$. Canceling the common factor $x - 4$ from the numerator and denominator yields:
$$\frac{x - 4}{(x-4)\left(\sqrt{x}+2\right)} = \frac{1}{\sqrt{x}+2} \quad \text{for all } x \ge 0, \; x \neq 4.$$

Now the expression $\frac{1}{\sqrt{x}+2}$ is continuous at $x = 4$ because $\sqrt{x}$ is continuous on $[0, \infty)$ and the denominator at $x = 4$ is $\sqrt{4} + 2 = 4 \neq 0$. Applying the Quotient Rule and continuity of $\sqrt{x}$:
$$\lim_{x\to 4}\frac{\sqrt{x}-2}{x-4} = \lim_{x\to 4}\frac{1}{\sqrt{x}+2} = \frac{1}{\sqrt{4}+2} = \frac{1}{2+2} = \frac{1}{4}.$$

---

### Step 4: Comparison with Exercise 3

| Feature | Exercise 3: $\lim_{n\to\infty}\left(\sqrt{n^2+5n}-n\right)$ | Exercise 8: $\lim_{x\to 4}\frac{\sqrt{x}-2}{x-4}$ |
| :--- | :--- | :--- |
| **Type of Object & Limit** | Sequence limit at infinity ($n \to \infty$, $n \in \mathbb{N}^+$) | Function limit at a finite point ($x \to 4$, $x \in \mathbb{R}$) |
| **Initial Indeterminate Form** | $[\infty - \infty]$ (difference of two large quantities) | $\left[\frac{0}{0}\right]$ (quotient of two vanishing quantities) |
| **Core Algebraic Tool** | Multiply by $\frac{\sqrt{n^2+5n}+n}{\sqrt{n^2+5n}+n}$ using $(A-B)(A+B)=A^2-B^2$ | Multiply by $\frac{\sqrt{x}+2}{\sqrt{x}+2}$ using $(A-B)(A+B)=A^2-B^2$ |
| **What Conjugation Achieves in the Numerator** | Frees $n^2+5n$ from the radical so the leading terms $n^2 - n^2$ cancel, leaving $5n$ | Frees $x$ from the radical to form $x - 4$, which cancels the factor $x - 4$ in the denominator |
| **Why the New Conjugate Factor is Harmless** | $\sqrt{n^2+5n} + n$ replaces $\infty - \infty$ with $\infty + \infty \approx 2n$ | $\sqrt{x} + 2$ replaces $2 - 2 = 0$ with $2 + 2 = 4 \neq 0$ |

**Summary of the Connection:**
In both exercises, a subtraction involving a square root ($A - B$) causes destructive cancellation: in Exercise 3, the leading infinite terms cancel ($\sqrt{n^2+5n} \approx n$ vs. $n$), whereas in Exercise 8, the finite values at $x=4$ cancel ($\sqrt{4} = 2$ vs. $2$, creating $0/0$). Multiplying by the conjugate $A + B$ squares away the square root in $A^2 - B^2$ so the cancellation can be simplified algebraically, while the conjugate sum $A + B$ has two positive terms of the same sign that **add** rather than cancel ($\infty + \infty$ in Exercise 3; $2 + 2 = 4$ in Exercise 8).

---

## 4. Verification and Consistency Checks

### Numerical Check Near $x = 4$
Let us evaluate $f(x) = \frac{\sqrt{x}-2}{x-4}$ for $x$ approaching $4$ from both sides and compare with $\frac{1}{4} = 0.25$:

| $x$ | $\sqrt{x}$ | Numerator $\sqrt{x}-2$ | Denominator $x-4$ | $f(x) = \frac{\sqrt{x}-2}{x-4}$ | Target $\frac{1}{4}$ | Error $|f(x) - 0.25|$ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $3.9$ | $1.97484177$ | $-0.02515823$ | $-0.1$ | $0.2515823$ | $0.2500000$ | $0.0015823$ |
| $3.99$ | $1.99749844$ | $-0.00250156$ | $-0.01$ | $0.2501563$ | $0.2500000$ | $0.0001563$ |
| $3.999$ | $1.99974998$ | $-0.00025002$ | $-0.001$ | $0.2500156$ | $0.2500000$ | $0.0000156$ |
| $4.001$ | $2.00024998$ | $+0.00024998$ | $+0.001$ | $0.2499844$ | $0.2500000$ | $0.0000156$ |
| $4.01$ | $2.00249844$ | $+0.00249844$ | $+0.01$ | $0.2498439$ | $0.2500000$ | $0.0001561$ |
| $4.1$ | $2.02484567$ | $+0.02484567$ | $+0.1$ | $0.2484567$ | $0.2500000$ | $0.0015433$ |

### Independent Check via Factoring the Denominator or Substitution
Let $u = \sqrt{x}$. As $x \to 4$, by continuity of the square root function, $u \to \sqrt{4} = 2$ (with $u \neq 2$ for $x \neq 4$). Since $x = u^2$, the limit transforms into a standard rational limit:
$$\lim_{x\to 4}\frac{\sqrt{x}-2}{x-4} = \lim_{u\to 2}\frac{u-2}{u^2-4} = \lim_{u\to 2}\frac{u-2}{(u-2)(u+2)} = \lim_{u\to 2}\frac{1}{u+2} = \frac{1}{2+2} = \frac{1}{4}.$$
(Also note that $\lim_{x\to 4}\frac{\sqrt{x}-\sqrt{4}}{x-4}$ is by definition the derivative of $g(x) = \sqrt{x}$ at $x = 4$, which is $g'(4) = \left.\frac{1}{2\sqrt{x}}\right|_{x=4} = \frac{1}{2(2)} = \frac{1}{4}$.)

### Final Conclusion
$$\boxed{\lim_{x\to4}\frac{\sqrt{x}-2}{x-4} = \frac{1}{4}}$$
