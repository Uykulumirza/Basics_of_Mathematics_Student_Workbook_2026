# Solution to Problem 10: The Tangent Line as an Application of the Derivative

## 1. Problem Statement

For
$$f(x)=x^2-3x+1$$
find the equation of the tangent line at the point with $x=2$. Give the point of tangency, the value $f'(2)$, the equation of the line, and verify that the point lies on the obtained tangent line.

> **Why this problem:** it combines the derivative and the equation of a line into a complete geometric problem.

---

## 2. Theoretical Background and Concepts

1. **Equation of the Tangent Line**:
   Let $f$ be a function that is differentiable at $x = x_0$. The **tangent line** to the graph $y = f(x)$ at the point of tangency $P_0 = (x_0, y_0) = (x_0, f(x_0))$ is the unique straight line that passes through $P_0$ with slope equal to the derivative $m = f'(x_0)$.
2. **Point-Slope and Slope-Intercept Forms**:
   - **Point-slope form**:
     $$y - f(x_0) = f'(x_0)(x - x_0)$$
   - **Slope-intercept form**: Solving for $y$ yields
     $$y = f'(x_0)x + \left[f(x_0) - f'(x_0)x_0\right] = mx + b$$
3. **Geometric Meaning**: The tangent line is the best linear approximation $L(x) = f(x_0) + f'(x_0)(x - x_0)$ to the curve $y = f(x)$ near $x = x_0$. At $x = x_0$, both the function and the tangent line share the same value ($L(x_0) = f(x_0)$) and the same instantaneous rate of change ($L'(x_0) = f'(x_0)$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the point of tangency $(2, f(2))$

To find the $y$-coordinate of the point on the graph $y = f(x)$ corresponding to $x_0 = 2$, we substitute $x = 2$ into the original function $f(x) = x^2 - 3x + 1$:
$$y_0 = f(2) = (2)^2 - 3(2) + 1 = 4 - 6 + 1 = -1$$

Thus, the **point of tangency** is:
$$P_0 = (2, -1)$$

---

### Step 2: Compute the derivative $f'(x)$ and the slope $f'(2)$

We differentiate $f(x) = x^2 - 3x + 1$ term by term using the **power rule**, **constant multiple rule**, and **constant rule**:
$$f'(x) = \frac{d}{dx}\left(x^2\right) - 3\frac{d}{dx}(x) + \frac{d}{dx}(1) = 2x - 3(1) + 0 = 2x - 3$$

Now we evaluate $f'(x)$ at $x_0 = 2$ to obtain the slope $m$ of the tangent line at $P_0(2, -1)$:
$$m = f'(2) = 2(2) - 3 = 4 - 3 = 1$$

*(Important note: $f'(x) = 2x - 3$ is the derivative formula for arbitrary $x$, whereas the slope of the tangent line at $x = 2$ is the **constant number** $m = f'(2) = 1$. Never substitute the variable expression $2x - 3$ as the slope $m$ in the line equation!)*

---

### Step 3: Write the equation of the tangent line

Using the **point-slope formula** $y - y_0 = m(x - x_0)$ with $(x_0, y_0) = (2, -1)$ and slope $m = f'(2) = 1$:
$$y - (-1) = 1 \cdot (x - 2)$$
$$y + 1 = x - 2$$

Subtracting $1$ from both sides gives the **equation of the tangent line** in slope-intercept form:
$$y = x - 3$$

---

### Step 4: Verify that the point of tangency lies on the obtained tangent line

To verify that the point of tangency $P_0 = (2, -1)$ lies on the line $y = x - 3$, we substitute $x = 2$ into the right-hand side of the line equation:
$$y_{\text{line}}(2) = 2 - 3 = -1$$

Since $y_{\text{line}}(2) = -1 = f(2)$, the coordinates $(2, -1)$ satisfy the equation $y = x - 3$, confirming that the tangent line passes through the point of tangency on the parabola.

---

## 4. Verification and Consistency Checks

1. **Algebraic Tangency (Double Root / Discriminant) Check**:
   For a parabola $y = f(x)$, a non-vertical line $y = mx + b$ is tangent to the parabola at $x = x_0$ if and only if the difference $f(x) - y_{\text{line}}(x)$ has a **double root** at $x = x_0$. Let us compute the difference between the parabola $f(x) = x^2 - 3x + 1$ and our tangent line $y = x - 3$:
   $$f(x) - (x - 3) = (x^2 - 3x + 1) - (x - 3) = x^2 - 4x + 4 = (x - 2)^2$$
   Because $(x - 2)^2$ has a double root at $x = 2$ and satisfies $(x - 2)^2 \ge 0$ for all $x \in \mathbb{R}$, the parabola $y = x^2 - 3x + 1$ lies entirely on or above the line $y = x - 3$ and touches it at the single point $x = 2$. This provides a complete, derivative-free algebraic proof that $y = x - 3$ is the exact tangent line at $(2, -1)$.
2. **Summary of Required Results**:
   - **Point of tangency**: $(2, -1)$
   - **Derivative value (slope)**: $f'(2) = 1$
   - **Tangent line equation**: $y = x - 3$
   - **Verification at $x = 2$**: $y = 2 - 3 = -1 = f(2)$
