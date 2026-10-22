# Solution to Problem 1: Derivative of a Polynomial and the Slope of a Tangent Line

## 1. Problem Statement

For
$$f(x)=3x^5-2x^3+7x-4$$
find $f'(x)$. Then compute $f'(0)$ and $f'(1)$, determine the signs of the obtained values, and explain what they say about the slope of the tangent line to the graph at these two points.

> **Why this problem:** it reinforces the power rule and connects the value of the derivative at a point with the geometric meaning of the tangent slope.

---

## 2. Theoretical Background and Concepts

1. **The Power Rule**: For any real exponent $n$ (and in particular for any positive integer $n \in \mathbb{N}$), the derivative of $x^n$ with respect to $x$ is:
   $$\frac{d}{dx}\left(x^n\right) = n x^{n-1}$$
2. **Derivative of a Constant**: For any real constant $c \in \mathbb{R}$,
   $$\frac{d}{dx}(c) = 0$$
   because a constant function does not change as $x$ changes.
3. **Linearity of Differentiation (Sum, Difference, and Constant Multiple Rules)**: If $u(x)$ and $v(x)$ are differentiable functions and $a, b \in \mathbb{R}$ are constants, then:
   $$\frac{d}{dx}\left[a\,u(x) + b\,v(x)\right] = a\,u'(x) + b\,v'(x)$$
   This allows us to differentiate any polynomial term by term.
4. **Geometric Interpretation of the Derivative**: If $f$ is differentiable at $x = x_0$, then the number $f'(x_0)$ is the **slope** of the line tangent to the graph $y = f(x)$ at the point $(x_0, f(x_0))$:
   - If $f'(x_0) > 0$, the tangent line slopes **upward** from left to right (the function is locally increasing at $x_0$).
   - If $f'(x_0) < 0$, the tangent line slopes **downward** from left to right (the function is locally decreasing at $x_0$).
   - If $f'(x_0) = 0$, the tangent line is **horizontal**.
   - A larger magnitude $|f'(x_0)|$ corresponds to a **steeper** tangent line.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the derivative $f'(x)$

The given function is a fifth-degree polynomial defined for all $x \in \mathbb{R}$:
$$f(x) = 3x^5 - 2x^3 + 7x - 4$$

Because $f(x)$ is a linear combination of powers of $x$ and a constant term, we apply the **linearity of the derivative** (the sum/difference rule and the constant multiple rule) to differentiate each term separately:
$$f'(x) = \frac{d}{dx}\left(3x^5 - 2x^3 + 7x - 4\right) = 3\frac{d}{dx}\left(x^5\right) - 2\frac{d}{dx}\left(x^3\right) + 7\frac{d}{dx}(x) - \frac{d}{dx}(4)$$

Now we apply the **power rule** $\frac{d}{dx}(x^n) = nx^{n-1}$ to the first three terms and the **constant rule** to the last term:
- For $x^5$ ($n=5$): $\frac{d}{dx}(x^5) = 5x^{5-1} = 5x^4$, so $3\frac{d}{dx}(x^5) = 3(5x^4) = 15x^4$.
- For $x^3$ ($n=3$): $\frac{d}{dx}(x^3) = 3x^{3-1} = 3x^2$, so $-2\frac{d}{dx}(x^3) = -2(3x^2) = -6x^2$.
- For $x = x^1$ ($n=1$): $\frac{d}{dx}(x^1) = 1\cdot x^{1-1} = 1\cdot x^0 = 1$, so $7\frac{d}{dx}(x) = 7(1) = 7$.
- For the constant $4$: $\frac{d}{dx}(4) = 0$.

Combining these results gives the derivative formula:
$$f'(x) = 15x^4 - 6x^2 + 7$$

---

### Step 2: Evaluate $f'(0)$ and $f'(1)$ and determine their signs

1. **At $x = 0$**:
   Substitute $x = 0$ into $f'(x)$:
   $$f'(0) = 15(0)^4 - 6(0)^2 + 7 = 0 - 0 + 7 = 7$$
   Since $7 > 0$, the value $f'(0)$ is **strictly positive** ($f'(0) > 0$). Note that the corresponding point on the graph is $(0, f(0)) = (0, -4)$.

2. **At $x = 1$**:
   Substitute $x = 1$ into $f'(x)$:
   $$f'(1) = 15(1)^4 - 6(1)^2 + 7 = 15 - 6 + 7 = 16$$
   Since $16 > 0$, the value $f'(1)$ is also **strictly positive** ($f'(1) > 0$). Note that the corresponding point on the graph is $(1, f(1)) = (1, 3 - 2 + 7 - 4) = (1, 4)$.

---

### Step 3: Geometric interpretation of the tangent line slopes

- **At $(0, -4)$**: Because $f'(0) = 7 > 0$, the tangent line to the graph of $f$ at $x = 0$ has a positive slope of $m = 7$. Geometrically, this means the tangent line **rises (slopes upward) from left to right**: for each $1$-unit increase in $x$ along the tangent line, $y$ increases by $7$ units. Near $x = 0$, the function $f(x)$ is strictly increasing.
- **At $(1, 4)$**: Because $f'(1) = 16 > 0$, the tangent line to the graph of $f$ at $x = 1$ has a positive slope of $m = 16$. This tangent line also **rises (slopes upward) from left to right**, and the function is strictly increasing at $x = 1$.
- **Comparison of steepness**: Since $f'(1) = 16 > 7 = f'(0)$, the tangent line at $(1, 4)$ is more than twice as **steep** as the tangent line at $(0, -4)$, indicating that $f(x)$ is increasing more rapidly at $x = 1$ than at $x = 0$.

---

## 4. Verification and Consistency Checks

1. **Degree and Parity Check**:
   - The non-constant part of $f(x)$, namely $3x^5 - 2x^3 + 7x$, is an **odd function** of degree $5$.
   - Differentiating an odd polynomial of degree $5$ must yield an **even polynomial** of degree $4$. Indeed, $f'(x) = 15x^4 - 6x^2 + 7$ contains only even powers of $x$ ($x^4$, $x^2$, and $x^0$) and has degree $4$.
2. **Global Sign Check via Completing the Square**:
   We can rewrite $f'(x)$ by completing the square in $u = x^2$:
   $$f'(x) = 15\left(x^4 - \frac{2}{5}x^2\right) + 7 = 15\left(x^2 - \frac{1}{5}\right)^2 - \frac{15}{25} + 7 = 15\left(x^2 - \frac{1}{5}\right)^2 + \frac{32}{5}$$
   Since $15\left(x^2 - \frac{1}{5}\right)^2 \ge 0$ for all $x \in \mathbb{R}$, we see that $f'(x) \ge \frac{32}{5} = 6.4 > 0$ for every real $x$. This confirms that $f'(0) = 7$ and $f'(1) = 16$ must both be positive and at least $6.4$.
3. **Difference Quotient Approximation at $x = 0$ and $x = 1$**:
   - Near $x = 0$ with $h = 0.01$:
     $$\frac{f(0.01) - f(0)}{0.01} = \frac{3(0.01)^5 - 2(0.01)^3 + 7(0.01) - 4 - (-4)}{0.01} = 3(0.01)^4 - 2(0.01)^2 + 7 \approx 6.9998 \approx 7 = f'(0)$$
   - Near $x = 1$ with $h = 0.001$:
     $$f(1.001) = 3(1.001)^5 - 2(1.001)^3 + 7(1.001) - 4 \approx 4.016024$$
     $$\frac{f(1.001) - f(1)}{0.001} \approx \frac{4.016024 - 4}{0.001} = 16.024 \approx 16 = f'(1)$$
   Both numerical checks confirm our exact analytical values.
