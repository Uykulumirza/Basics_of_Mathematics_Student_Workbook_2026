# Solution to Problem 15: The Difference Quotient as a Check of the Derivative

## 1. Problem Statement

Choose one function from the problem set and a point $x_0$ at which the derivative exists. Compute $f'(x_0)$ exactly, and then calculate
$$\frac{f(x_0+h)-f(x_0)}h$$
for $h=1$, $0.1$, and $0.01$. Compare the values with $f'(x_0)$ and explain why the difference quotient approaching a single number is consistent with the definition of the derivative, while a few computations do not replace a limit argument.

> **Why this problem:** it connects the definition of the derivative with concrete calculations and teaches the distinction between observation and proof.

---

## 2. Theoretical Background and Concepts

1. **The Difference Quotient vs. the Derivative**:
   - For a fixed point $x_0$ and a non-zero increment $h \neq 0$, the **difference quotient**
     $$Q(h) = \frac{f(x_0 + h) - f(x_0)}{h}$$
     is the **average rate of change** of $f$ over the interval between $x_0$ and $x_0 + h$ (geometrically, the slope of the secant line through $(x_0, f(x_0))$ and $(x_0 + h, f(x_0 + h))$).
   - The **derivative** $f'(x_0)$ is the **instantaneous rate of change** at $x_0$ (geometrically, the slope of the tangent line at $(x_0, f(x_0))$), defined as the limit:
     $$f'(x_0) = \lim_{h \to 0} \frac{f(x_0 + h) - f(x_0)}{h}$$
2. **Numerical Approximation vs. Deductive Limit Proof**:
   - Evaluating $Q(h)$ for small values such as $h = 1, 0.1, 0.01$ provides a practical numerical check and builds intuition by showing how secant slopes approach the tangent slope.
   - However, a limit statement $\lim_{h \to 0} Q(h) = L$ is a statement about **infinitely many** arbitrarily small values of $h$ on **both** sides of $0$ ($h \to 0^+$ and $h \to 0^-$). Testing finitely many values of $h$ can never prove what happens as $h$ gets arbitrarily close to $0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Choose a function and point $x_0$, and compute $f'(x_0)$ exactly

We choose the quadratic function from **Problem 10**:
$$f(x) = x^2 - 3x + 1 \quad \text{at the point } x_0 = 2$$
(We also note the general formula in $h$ so every arithmetic step is exact and transparent.)

1. **Exact value of the function at $x_0 = 2$**:
   $$f(2) = 2^2 - 3(2) + 1 = 4 - 6 + 1 = -1$$

2. **Exact value of the derivative $f'(2)$**:
   Differentiating $f(x) = x^2 - 3x + 1$ using the power and sum rules gives:
   $$f'(x) = 2x - 3$$
   Evaluating at $x_0 = 2$:
   $$f'(2) = 2(2) - 3 = 1$$

---

### Step 2: Compute the difference quotient $\frac{f(2 + h) - f(2)}{h}$ for $h = 1, 0.1, 0.01$

First, let us simplify $f(2 + h)$ algebraically so we can verify each numerical calculation:
$$f(2 + h) = (2 + h)^2 - 3(2 + h) + 1 = (4 + 4h + h^2) - (6 + 3h) + 1 = -1 + h + h^2$$
Therefore, for any $h \neq 0$, the difference quotient at $x_0 = 2$ is:
$$Q(h) = \frac{f(2 + h) - f(2)}{h} = \frac{(-1 + h + h^2) - (-1)}{h} = \frac{h + h^2}{h} = 1 + h$$

Now let us calculate the exact numerical values directly from $\frac{f(2 + h) - f(2)}{h}$ for $h = 1$, $0.1$, and $0.01$:

1. **For $h = 1$ ($x_0 + h = 3$)**:
   - $f(3) = 3^2 - 3(3) + 1 = 9 - 9 + 1 = 1$
   - Difference quotient:
     $$\frac{f(2 + 1) - f(2)}{1} = \frac{f(3) - f(2)}{1} = \frac{1 - (-1)}{1} = \frac{2}{1} = 2$$

2. **For $h = 0.1$ ($x_0 + h = 2.1$)**:
   - $f(2.1) = (2.1)^2 - 3(2.1) + 1 = 4.41 - 6.3 + 1 = -0.89$
   - Difference quotient:
     $$\frac{f(2 + 0.1) - f(2)}{0.1} = \frac{-0.89 - (-1)}{0.1} = \frac{0.11}{0.1} = 1.1$$

3. **For $h = 0.01$ ($x_0 + h = 2.01$)**:
   - $f(2.01) = (2.01)^2 - 3(2.01) + 1 = 4.0401 - 6.03 + 1 = -0.9899$
   - Difference quotient:
     $$\frac{f(2 + 0.01) - f(2)}{0.01} = \frac{-0.9899 - (-1)}{0.01} = \frac{0.0101}{0.01} = 1.01$$

*(For completeness, if we also check negative increments approaching $0$ from the left: for $h = -1$, $Q(-1) = 0$; for $h = -0.1$, $Q(-0.1) = 0.9$; and for $h = -0.01$, $Q(-0.01) = 0.99$.)*

---

### Step 3: Compare the values with $f'(2) = 1$

Let us organize the results in a comparison table:

| Increment $h$ | Point $x_0 + h$ | Function Value $f(2 + h)$ | Difference Quotient $Q(h) = \frac{f(2+h)-f(2)}{h}$ | Exact Derivative $f'(2)$ | Error $|Q(h) - f'(2)|$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| $1$ | $3$ | $1$ | $2$ | $1$ | $1$ |
| $0.1$ | $2.1$ | $-0.89$ | $1.1$ | $1$ | $0.1$ |
| $0.01$ | $2.01$ | $-0.9899$ | $1.01$ | $1$ | $0.01$ |
| $-0.01$ | $1.99$ | $-1.0099$ | $0.99$ | $1$ | $0.01$ |

**Comparison**:
As $h$ shrinks by a factor of $10$ (from $1$ to $0.1$ to $0.01$), the difference quotient $Q(h)$ gets steadily closer to the exact derivative $f'(2) = 1$ ($2 \to 1.1 \to 1.01$), and the approximation error $|Q(h) - f'(2)| = |h|$ shrinks by the exact same factor of $10$ ($1 \to 0.1 \to 0.01$).

---

### Step 4: Explain consistency with the limit definition vs. why finite sampling is not a proof

1. **Why this convergence is consistent with the definition of the derivative**:
   By definition, $f'(2) = \lim_{h \to 0} \frac{f(2+h)-f(2)}{h} = 1$ means that we can make the difference quotient $Q(h)$ as close as we wish to $1$ by taking $h \neq 0$ sufficiently close to $0$. Our algebraic identity $Q(h) = 1 + h$ shows that the discrepancy between the secant slope $Q(h)$ and the tangent slope $f'(2) = 1$ is literally $h$, which approaches $0$ as $h \to 0$.

2. **Why a few numerical calculations cannot replace a rigorous limit argument**:
   - **Finitely many samples cannot see arbitrarily small scales**: Checking $h = 1, 0.1, 0.01$ only tests three points! A function could behave like $x^2 - 3x + 1$ for $|h| \ge 0.001$ and then have a sharp corner, jump, or wild oscillation (such as $\sin(1/h)$) for $|h| < 0.0001$.
   - **One-sided sampling misses corners**: Checking only positive values $h = 1, 0.1, 0.01$ only explores the **right-hand** derivative $f'_+(x_0)$. For example, in Problem 14 with $a = 5$ at $x_0 = 0$, testing $h = 1, 0.1, 0.01$ gives $Q(h) = 1, 0.1, 0.01 \to 0$, completely hiding the fact that for $h < 0$, $Q(h) = 5 \neq 0$ and the derivative does not exist!
   - **Floating-point rounding vs. exactness**: Even when a limit exists, numerical calculations only yield approximations (and for tiny $h$ like $10^{-16}$ on a computer, catastrophic cancellation in $f(x_0 + h) - f(x_0)$ destroys accuracy), whereas an algebraic limit proof establishes the exact value for all $h \to 0$.

---

## 4. Verification and Consistency Checks

1. **Alternative Check with $g(x) = x^2$ at $x_0 = 2$ (from Problem 11)**:
   If one instead chooses $g(x) = x^2$ at $x_0 = 2$, then $g'(2) = 2(2) = 4$, and the difference quotient is $\frac{(2+h)^2 - 4}{h} = 4 + h$, yielding $5$, $4.1$, and $4.01$ for $h = 1, 0.1, 0.01$, which approaches $g'(2) = 4$ by the exact same mechanism.
2. **Secant-to-Tangent Midpoint Property for Parabolas**:
   Notice that for our parabola $f(x) = x^2 - 3x + 1$, the average of the forward difference quotient $Q(h) = 1 + h$ and backward difference quotient $Q(-h) = 1 - h$ (the centered difference quotient $\frac{f(2+h) - f(2-h)}{2h}$) equals $\frac{(1+h)+(1-h)}{2} = 1 = f'(2)$ **exactly** for any $h \neq 0$.
