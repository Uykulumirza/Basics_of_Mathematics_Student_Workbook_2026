# Solution to Problem 9: A Logarithm and the Chain Rule

## 1. Problem Statement

For
$$f(x)=\ln(x^2+1)$$
compute the derivative. Then determine the sign of $f'(x)$ for $x<0$, $x=0$, and $x>0$, and describe qualitatively how the function behaves around zero.

> **Why this problem:** it connects differentiation with sign analysis and the behavior of a function.

---

## 2. Theoretical Background and Concepts

1. **Domain of a Logarithmic Composition**: The natural logarithm $\ln u$ is defined for all strictly positive real numbers $u > 0$. Thus, $\ln(u(x))$ is defined wherever $u(x) > 0$.
2. **Derivative of the Natural Logarithm and the Chain Rule**:
   The derivative of $\ln u$ with respect to $u > 0$ is:
   $$\frac{d}{du}(\ln u) = \frac{1}{u}$$
   When $u = u(x) > 0$ is a differentiable function of $x$, the **chain rule** yields the logarithmic derivative formula:
   $$\frac{d}{dx}\left[\ln(u(x))\right] = \frac{1}{u(x)} \cdot u'(x) = \frac{u'(x)}{u(x)}$$
3. **First Derivative Test and Monotonicity**: Let $f$ be differentiable on an interval $I$:
   - If $f'(x) < 0$ for all $x \in I$, then $f$ is **strictly decreasing** on $I$.
   - If $f'(x) > 0$ for all $x \in I$, then $f$ is **strictly increasing** on $I$.
   - If $f'(x)$ changes sign from negative ($x < x_0$) to zero ($x = x_0$) to positive ($x > x_0$), then $f$ has a **local (and here global) minimum** at $x = x_0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Derivative of $f(x) = \ln(x^2 + 1)$

1. **Domain of $f$**:
   Since $x^2 \ge 0$ for every real number $x \in \mathbb{R}$, the inner argument satisfies:
   $$x^2 + 1 \ge 1 > 0 \quad \text{for all } x \in \mathbb{R}$$
   Therefore, the logarithm is always taking a strictly positive input, and the domain of $f$ is the entire real line:
   $$\operatorname{Dom}(f) = \mathbb{R} = (-\infty, \infty)$$

2. **Compute $f'(x)$ via the Chain Rule**:
   We decompose $f(x) = \ln(x^2 + 1)$ into its outer and inner layers:
   - **Outer function**: $g(u) = \ln u \implies g'(u) = \frac{1}{u}$
   - **Inner function**: $u(x) = x^2 + 1 \implies u'(x) = \frac{d}{dx}(x^2 + 1) = 2x$

   Applying the **chain rule** $f'(x) = g'(u(x)) \cdot u'(x)$:
   $$f'(x) = \frac{1}{x^2 + 1} \cdot (2x) = \frac{2x}{x^2 + 1}$$

---

### Step 2: Determine the sign of $f'(x)$ for $x < 0$, $x = 0$, and $x > 0$

To analyze the sign of
$$f'(x) = \frac{2x}{x^2 + 1},$$
observe first that the denominator satisfies $x^2 + 1 \ge 1 > 0$ for **all** $x \in \mathbb{R}$. Because dividing by a strictly positive quantity never changes the sign of an expression, the sign of $f'(x)$ is determined entirely by the numerator $2x$:

1. **For $x < 0$**:
   - Numerator: $2x < 0$
   - Denominator: $x^2 + 1 > 0$
   - Quotient:
     $$f'(x) = \frac{2x}{x^2 + 1} < 0 \quad (\text{strictly negative})$$

2. **For $x = 0$**:
   - Numerator: $2(0) = 0$
   - Denominator: $0^2 + 1 = 1 > 0$
   - Quotient:
     $$f'(0) = \frac{0}{1} = 0 \quad (\text{zero})$$

3. **For $x > 0$**:
   - Numerator: $2x > 0$
   - Denominator: $x^2 + 1 > 0$
   - Quotient:
     $$f'(x) = \frac{2x}{x^2 + 1} > 0 \quad (\text{strictly positive})$$

We can summarize the sign analysis in a variation table:

| Interval / Point | $(-\infty, 0)$ | $x = 0$ | $(0, +\infty)$ |
| :--- | :---: | :---: | :---: |
| Sign of $2x$ | $-$ | $0$ | $+$ |
| Sign of $x^2 + 1$ | $+$ | $+$ | $+$ |
| **Sign of $f'(x)$** | **$-$ (negative)** | **$0$** | **$+$ (positive)** |
| **Behavior of $f(x)$** | $\searrow$ strictly decreasing | horizontal tangent (min $0$) | $\nearrow$ strictly increasing |

---

### Step 3: Qualitative description of the behavior of $f(x)$ around zero

- **To the left of zero ($x < 0$)**: Because $f'(x) < 0$, as $x$ increases toward $0$ from the left, the function $f(x) = \ln(x^2 + 1)$ **strictly decreases** toward the origin.
- **At zero ($x = 0$)**: The function reaches the point $(0, f(0)) = (0, \ln 1) = (0, 0)$. Since $f'(0) = 0$, the graph has a **horizontal tangent line** ($y = 0$, the $x$-axis) at the origin. Because $f'(x)$ changes sign from negative to positive across $x = 0$, the function attains its **strict global minimum** of $f(0) = 0$ at $x = 0$.
- **To the right of zero ($x > 0$)**: Because $f'(x) > 0$, as $x$ increases away from $0$ to the right, the function **strictly increases**.
- **Symmetry and Shape Near $x = 0$**: Since $f(-x) = \ln((-x)^2 + 1) = \ln(x^2 + 1) = f(x)$, the graph is **even** (symmetric with respect to the $y$-axis). Very close to $x = 0$, since $\ln(1 + u) \approx u$ for small $u = x^2$, the graph behaves like the upward-opening parabola $y \approx x^2$, smoothly curving down to touch $(0, 0)$ and rising symmetrically on the right.

---

## 4. Verification and Consistency Checks

1. **Symmetry Check**:
   - $f(x) = \ln(x^2 + 1)$ is an even function ($f(-x) = f(x)$), and its derivative $f'(x) = \frac{2x}{x^2 + 1}$ is an odd function ($f'(-x) = -f'(x)$).
   - For instance, at $x = -1$ and $x = 1$, we have $f(-1) = f(1) = \ln 2 \approx 0.693$, while the slopes are opposite: $f'(-1) = -1$ and $f'(1) = +1$.
2. **Direct Algebraic Confirmation of the Global Minimum**:
   Since $x^2 \ge 0$ with equality if and only if $x = 0$, we have $x^2 + 1 \ge 1$, and because $\ln u$ is strictly increasing on $(0, \infty)$,
   $$f(x) = \ln(x^2 + 1) \ge \ln(1) = 0 \quad \text{for all } x \in \mathbb{R},$$
   with $f(x) = 0 \iff x = 0$. This independently confirms our derivative sign analysis.
