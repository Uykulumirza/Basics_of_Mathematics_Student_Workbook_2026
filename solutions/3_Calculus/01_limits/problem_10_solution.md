# Exercise 10: Continuity of a Piecewise Function

## 1. Problem Statement

Find $a$ so that
$$f(x)=\begin{cases}ax+1,&x<2,\\x^2-1,&x\ge2\end{cases}$$
is continuous at $x=2$. Explicitly compare the left-hand limit, right-hand limit, and function value.

> **Why this exercise:** organizes the definition of continuity as agreement among three quantities.

---

## 2. Theoretical Background and Concepts

### Definition of Continuity at a Point
A function $f : D \to \mathbb{R}$ is **continuous at an interior point $x_0 \in D$** if and only if the limit of $f(x)$ as $x \to x_0$ exists and is equal to the value of the function at $x_0$:
$$\lim_{x\to x_0} f(x) = f(x_0).$$

### The Three-Part Criterion for Continuity of Piecewise Functions
Because the two-sided limit $\lim_{x\to x_0} f(x)$ exists if and only if the left-hand limit and the right-hand limit both exist and are equal, continuity of $f$ at a boundary point $x_0$ where the formula of a piecewise function changes is equivalent to the **simultaneous agreement of three quantities**:

1. **The Function Value $f(x_0)$ exists** ($x_0$ is in the domain of $f$).
2. **Both One-Sided Limits exist and are equal:**
   $$\lim_{x\to x_0^-} f(x) = \lim_{x\to x_0^+} f(x)$$
   (which ensures that the two-sided limit $\lim_{x\to x_0} f(x)$ exists).
3. **The Common Limit Equals the Function Value:**
   $$\lim_{x\to x_0^-} f(x) = \lim_{x\to x_0^+} f(x) = f(x_0).$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Left-Hand Limit at $x = 2$
When $x$ approaches $2$ from the left ($x \to 2^-$), we consider only values satisfying $x < 2$. On the interval $(-\infty, 2)$, the function is defined by the linear formula $f(x) = ax + 1$. Since any polynomial $ax + 1$ is continuous on $\mathbb{R}$, we evaluate the left-hand limit by direct substitution of $x = 2$:
$$\lim_{x\to 2^-} f(x) = \lim_{x\to 2^-} (ax + 1) = a(2) + 1 = 2a + 1.$$

### Step 2: Compute the Right-Hand Limit at $x = 2$
When $x$ approaches $2$ from the right ($x \to 2^+$), we consider only values satisfying $x > 2$. On the interval $[2, \infty)$, the function is defined by the quadratic formula $f(x) = x^2 - 1$. Since $x^2 - 1$ is a polynomial, we evaluate the right-hand limit by direct substitution of $x = 2$:
$$\lim_{x\to 2^+} f(x) = \lim_{x\to 2^+} (x^2 - 1) = 2^2 - 1 = 4 - 1 = 3.$$

### Step 3: Compute the Function Value at $x = 2$
To find $f(2)$, we look at which branch of the piecewise definition includes the equality $x = 2$. The second branch applies for $x \ge 2$, so we substitute $x = 2$ into $x^2 - 1$:
$$f(2) = 2^2 - 1 = 4 - 1 = 3.$$

### Step 4: Explicitly Compare the Three Quantities and Solve for $a$
Let us summarize and compare the three quantities required for continuity at $x = 2$:
- **Left-hand limit:** $\lim_{x\to 2^-} f(x) = 2a + 1$
- **Right-hand limit:** $\lim_{x\to 2^+} f(x) = 3$
- **Function value:** $f(2) = 3$

Notice that the right-hand limit and the function value already agree ($\lim_{x\to 2^+} f(x) = f(2) = 3$) because the right-hand branch $x^2 - 1$ is defined on the closed ray $x \ge 2$.

For $f$ to be continuous at $x = 2$, all three quantities must be equal:
$$\lim_{x\to 2^-} f(x) = \lim_{x\to 2^+} f(x) = f(2)$$
$$\implies 2a + 1 = 3.$$

Solving this linear equation for $a$:
$$\begin{aligned}
2a + 1 &= 3 \\
2a &= 3 - 1 = 2 \\
a &= \frac{2}{2} = 1.
\end{aligned}$$

---

## 4. Verification and Consistency Checks

### Substitution and Continuity Check for $a = 1$
When $a = 1$, the piecewise function becomes:
$$f(x) = \begin{cases} x + 1, & x < 2, \\ x^2 - 1, & x \ge 2. \end{cases}$$
Let us re-verify all three quantities at $x = 2$:
1. $\lim_{x\to 2^-} f(x) = \lim_{x\to 2^-} (x + 1) = 2 + 1 = 3$.
2. $\lim_{x\to 2^+} f(x) = \lim_{x\to 2^+} (x^2 - 1) = 2^2 - 1 = 3$.
3. $f(2) = 2^2 - 1 = 3$.

Since $\lim_{x\to 2^-} f(x) = \lim_{x\to 2^+} f(x) = 3$, the two-sided limit exists and equals $\lim_{x\to 2} f(x) = 3 = f(2)$, confirming that $f$ is continuous at $x = 2$ (and in fact continuous on all of $\mathbb{R}$, since $x+1$ is continuous on $(-\infty, 2)$ and $x^2-1$ is continuous on $(2, \infty)$).

### Numerical Check Near $x = 2$ (with $a = 1$)
| $x$ | Branch Used | $f(x)$ | Distance $|f(x) - f(2)|$ |
| :--- | :--- | :--- | :--- |
| $1.9$ | $x + 1$ ($x < 2$) | $2.9000$ | $0.1000$ |
| $1.99$ | $x + 1$ ($x < 2$) | $2.9900$ | $0.0100$ |
| $1.999$ | $x + 1$ ($x < 2$) | $2.9990$ | $0.0010$ |
| $2.000$ | $x^2 - 1$ ($x \ge 2$) | $3.0000$ | $0.0000$ |
| $2.001$ | $x^2 - 1$ ($x \ge 2$) | $3.004001$ | $0.004001$ |
| $2.01$ | $x^2 - 1$ ($x \ge 2$) | $3.0401$ | $0.0401$ |
| $2.1$ | $x^2 - 1$ ($x \ge 2$) | $3.4100$ | $0.4100$ |

Geometrically, setting $a = 1$ joins the left ray $y = x + 1$ ($x < 2$) directly to the starting point $(2, 3)$ of the right parabolic branch $y = x^2 - 1$ ($x \ge 2$), eliminating any jump discontinuity at $x = 2$.

### Final Conclusion
$$\boxed{a = 1 \quad \left(\text{giving } \lim_{x\to 2^-} f(x) = \lim_{x\to 2^+} f(x) = f(2) = 3\right)}$$
