# Solution to Problem 6: Product Rule and Trigonometry

## 1. Problem Statement

For
$$f(x)=x\sin x+\cos x$$
compute the derivative and simplify the result. Then compute $f'(0)$ and interpret the direction of the tangent line at that point.

> **Why this problem:** it combines the product rule with trigonometric derivatives and geometric interpretation.

---

## 2. Theoretical Background and Concepts

1. **Derivatives of Basic Trigonometric Functions**: For $x$ measured in radians,
   $$\frac{d}{dx}(\sin x) = \cos x, \qquad \frac{d}{dx}(\cos x) = -\sin x$$
2. **Sum Rule and Product Rule**:
   - **Sum Rule**: $\frac{d}{dx}[A(x) + B(x)] = A'(x) + B'(x)$.
   - **Product Rule**: When differentiating a term of the form $u(x)v(x)$, such as $x\sin x$, both factors depend on $x$, so we must apply:
     $$\frac{d}{dx}\left[u(x)v(x)\right] = u'(x)v(x) + u(x)v'(x)$$
3. **Horizontal Tangent Lines**: If $f'(x_0) = 0$, the tangent line to the graph $y = f(x)$ at the point $(x_0, f(x_0))$ has slope $0$, meaning it is **horizontal** (parallel to the $x$-axis) with equation $y = f(x_0)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the derivative $f'(x)$ and simplify

The given function is a sum of two terms, defined for all $x \in \mathbb{R}$:
$$f(x) = \underbrace{x\sin x}_{\text{product}} + \cos x$$

By the **sum rule**, we differentiate the two terms separately:
$$f'(x) = \frac{d}{dx}(x\sin x) + \frac{d}{dx}(\cos x)$$

1. **Differentiating the first term $x\sin x$**:
   Because $x\sin x$ is the product of $u(x) = x$ and $v(x) = \sin x$, we apply the **product rule**:
   - $u(x) = x \implies u'(x) = 1$
   - $v(x) = \sin x \implies v'(x) = \cos x$
   Therefore:
   $$\frac{d}{dx}(x\sin x) = u'(x)v(x) + u(x)v'(x) = (1)(\sin x) + x(\cos x) = \sin x + x\cos x$$

2. **Differentiating the second term $\cos x$**:
   Using the standard trigonometric derivative formula:
   $$\frac{d}{dx}(\cos x) = -\sin x$$

3. **Combining and simplifying**:
   Substituting both derivatives back into the sum gives:
   $$f'(x) = (\sin x + x\cos x) + (-\sin x) = \sin x + x\cos x - \sin x$$
   Notice that the terms $+\sin x$ and $-\sin x$ cancel each other out identically! Thus, the simplified derivative is:
   $$f'(x) = x\cos x$$

---

### Step 2: Evaluate $f'(0)$ and interpret the tangent line geometrically

1. **Compute $f'(0)$**:
   Substituting $x = 0$ into our simplified formula $f'(x) = x\cos x$:
   $$f'(0) = 0 \cdot \cos(0) = 0 \cdot 1 = 0$$
   Also, the value of the function at $x = 0$ is:
   $$f(0) = 0\cdot\sin(0) + \cos(0) = 0 + 1 = 1$$
   So the point of tangency on the graph is $(0, f(0)) = (0, 1)$.

2. **Geometric Interpretation**:
   Because $f'(0) = 0$, the slope of the tangent line to the graph of $f$ at the point $(0, 1)$ is zero. Geometrically, this means the tangent line at $(0, 1)$ is **horizontal** (parallel to the $x$-axis), and its equation is:
   $$y = 1$$
   Near $x = 0$, the graph is momentarily flat and reaches a local minimum at $(0, 1)$.

---

## 4. Verification and Consistency Checks

1. **Parity (Symmetry) Check**:
   - Observe that $f(-x) = (-x)\sin(-x) + \cos(-x) = (-x)(-\sin x) + \cos x = x\sin x + \cos x = f(x)$. Thus, $f(x)$ is an **even function** (symmetric about the $y$-axis).
   - Every differentiable even function must have an **odd derivative**, and any odd function defined at $x = 0$ must satisfy $f'(0) = 0$.
   - Indeed, $f'(x) = x\cos x$ satisfies $f'(-x) = (-x)\cos(-x) = -x\cos x = -f'(x)$ (odd), and $f'(0) = 0$.
2. **Taylor Series Expansion Check Near $x = 0$**:
   Using the Maclaurin expansions $\sin x = x - \frac{x^3}{6} + O(x^5)$ and $\cos x = 1 - \frac{x^2}{2} + \frac{x^4}{24} + O(x^6)$:
   $$f(x) = x\left(x - \frac{x^3}{6} + \dots\right) + \left(1 - \frac{x^2}{2} + \dots\right) = 1 + \left(1 - \frac{1}{2}\right)x^2 - \frac{1}{8}x^4 + \dots = 1 + \frac{1}{2}x^2 - \frac{1}{8}x^4 + O(x^6)$$
   Differentiating this series term by term gives:
   $$f'(x) = x - \frac{1}{2}x^3 + O(x^5) = x\left(1 - \frac{x^2}{2} + O(x^4)\right) = x\cos x$$
   This confirms both the exact cancellation of the linear term ($f'(0) = 0$) and the local upward-opening parabolic shape $f(x) \approx 1 + \frac{1}{2}x^2$ near $(0, 1)$.
