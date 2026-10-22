# Solution to Problem 2: A Parabola from the Perspective of the Derivative

## 1. Problem Statement
For $f(x)=x^2-4x+1$, find the minimum using the derivative. Compare the result with the vertex form and explain why both approaches lead to the same point.

> **Why this problem:** it connects a new tool with the familiar geometry of a parabola.

---

## 2. Theoretical Background and Concepts
A quadratic function $f(x) = ax^2 + bx + c$ ($a > 0$) can be analyzed from two complementary viewpoints:
1. **Analytical (Calculus) Approach:** Using the derivative $f'(x) = 2ax + b$, we locate the stationary point where $f'(x) = 0$. Since $f'(x) < 0$ for $x < -\frac{b}{2a}$ and $f'(x) > 0$ for $x > -\frac{b}{2a}$ (and $f''(x) = 2a > 0$), this point is the unique global minimum.
2. **Algebraic / Geometric Approach (Completing the Square):** Rewriting $f(x)$ in vertex form $f(x) = a(x - p)^2 + q$ isolates the variable $x$ inside a non-negative square $(x - p)^2 \ge 0$, immediately revealing the minimum value $q$ achieved at $x = p$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Finding the Minimum Using the Derivative
Given the function $f(x) = x^2 - 4x + 1$ with domain $D_f = \mathbb{R}$, we compute its first derivative:
$$f'(x) = \frac{d}{dx}(x^2 - 4x + 1) = 2x - 4 = 2(x - 2).$$
To find the critical point, we set $f'(x) = 0$:
$$2(x - 2) = 0 \iff x = 2.$$

Next, we examine the sign of $f'(x)$ around $x = 2$:

| Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: |
| **Sign of $f'(x) = 2(x-2)$** | $-$ | $0$ | $+$ |
| **Behavior of $f(x)$** | $\searrow$ ( strictly decreasing ) | **Global Minimum** ($-3$) | $\nearrow$ ( strictly increasing ) |

Because $f$ is strictly decreasing on $(-\infty, 2]$ and strictly increasing on $[2, \infty)$ (which is also confirmed by the second derivative $f''(x) = 2 > 0$), $f$ attains its **strict global minimum** at $x = 2$. Evaluating $f(2)$:
$$f_{\min} = f(2) = 2^2 - 4(2) + 1 = 4 - 8 + 1 = -3.$$
Thus, the minimum point is **$(2, -3)$**.

### Step 2: Comparison with the Vertex Form (Completing the Square)
We transform $f(x) = x^2 - 4x + 1$ into vertex form by completing the square on $x^2 - 4x$:
$$f(x) = (x^2 - 4x + 4) - 4 + 1 = (x - 2)^2 - 3.$$
Since the square of any real number is non-negative, we have:
$$(x - 2)^2 \ge 0 \quad \text{for all } x \in \mathbb{R},$$
with equality $(x - 2)^2 = 0$ holding **if and only if** $x = 2$. Adding $-3$ to both sides yields:
$$f(x) = (x - 2)^2 - 3 \ge -3 \quad \text{for all } x \in \mathbb{R}.$$
Therefore, the minimum value is $q = -3$, attained uniquely at $x = p = 2$, giving the exact same vertex **$(2, -3)$**.

### Step 3: Why Both Approaches Lead to the Exact Same Point
Both methods identify the point $(2, -3)$ because they describe the same geometric and analytical property in different languages:
1. **Symmetry and Zero Rate of Change:** From the vertex form $f(x) = (x - 2)^2 - 3$, the graph is symmetric about the vertical line $x = 2$, since $f(2 + h) = h^2 - 3 = f(2 - h)$. For any smooth symmetric curve, the secant slope between symmetric points $(2 - h, f(2 - h))$ and $(2 + h, f(2 + h))$ is zero, which forces the tangent line at the vertex $x = 2$ to be horizontal ($f'(2) = 0$).
2. **Derivative of the Squared Term:** Differentiating the vertex form directly via the chain rule gives:
   $$f'(x) = \frac{d}{dx}\bigl[(x - 2)^2 - 3\bigr] = 2(x - 2).$$
   The factor $(x - 2)$ that vanishes at the minimum of the square $(x - 2)^2 \ge 0$ is the exact same linear factor that vanishes when setting the instantaneous rate of change $f'(x) = 0$. At the bottom of the parabola, the function stops decreasing ($f'(x) < 0$ for $x < 2$) and begins increasing ($f'(x) > 0$ for $x > 2$), so its instantaneous rate of change must pass through zero at $x = 2$.

---

## 4. Verification and Consistency Checks
1. **Canonical Vertex Formulas:** For $f(x) = ax^2 + bx + c$ with $a = 1, b = -4, c = 1$:
   $$p = -\frac{b}{2a} = -\frac{-4}{2(1)} = 2, \qquad q = -\frac{\Delta}{4a} = -\frac{(-4)^2 - 4(1)(1)}{4(1)} = -\frac{12}{4} = -3.$$
   This matches $(2, -3)$ from both methods.
2. **Symmetric Test Values:** Evaluating $f(x)$ at $x = 1$ and $x = 3$ gives $f(1) = 1 - 4 + 1 = -2 > -3$ and $f(3) = 9 - 12 + 1 = -2 > -3$, confirming symmetry about $x = 2$ and that $f(2) = -3$ is lower than neighboring values.
