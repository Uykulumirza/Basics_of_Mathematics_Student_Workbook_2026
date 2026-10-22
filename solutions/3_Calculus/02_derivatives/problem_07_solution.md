# Solution to Problem 7: A Trigonometric Composition

## 1. Problem Statement

For
$$f(x)=\sin(x^2+1)$$
compute the derivative. Explicitly identify the outer function, the inner function, and the derivative of the inner function. Finally, determine the sign of $f'(0)$.

> **Why this problem:** it reinforces the chain rule in a different type of composition.

---

## 2. Theoretical Background and Concepts

1. **Recognizing Trigonometric Compositions**:
   Notice the crucial structural difference between $\sin(x^2 + 1)$ and $(\sin x)(x^2 + 1)$:
   - Here, $\sin$ is **not** multiplied by $(x^2 + 1)$; rather, $x^2 + 1$ is the **input argument** (angle in radians) fed into the sine function.
   - Therefore, $f(x) = \sin(x^2 + 1)$ is a composite function $f(x) = g(u(x))$, requiring the **chain rule**, not the product rule.
2. **The Chain Rule for $\sin(u(x))$**:
   Since $\frac{d}{du}(\sin u) = \cos u$, if $u(x)$ is a differentiable function of $x$, the chain rule gives:
   $$\frac{d}{dx}\left[\sin(u(x))\right] = \cos(u(x)) \cdot u'(x)$$
3. **Trichotomy of Real Numbers (Sign of a Number)**: Every real number is either strictly positive ($>0$), strictly negative ($<0$), or zero ($=0$). Zero is **neither positive nor negative**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Explicitly identify the outer function, inner function, and their derivatives

To evaluate $f(x) = \sin(x^2 + 1)$ at a given $x$, we first calculate the polynomial $x^2 + 1$ and then take the sine of that number:
1. **Inner function**:
   $$u = u(x) = x^2 + 1$$
2. **Derivative of the inner function**:
   Applying the power rule and constant rule to $u(x) = x^2 + 1$:
   $$u'(x) = \frac{du}{dx} = \frac{d}{dx}\left(x^2 + 1\right) = 2x + 0 = 2x$$
3. **Outer function**:
   $$y = g(u) = \sin u$$
4. **Derivative of the outer function**:
   Differentiating $g(u) = \sin u$ with respect to its argument $u$:
   $$g'(u) = \frac{dy}{du} = \frac{d}{du}(\sin u) = \cos u$$
   Evaluating $g'(u)$ at the inner function $u = x^2 + 1$ gives:
   $$g'(u(x)) = \cos(x^2 + 1)$$

---

### Step 2: Combine using the chain rule to find $f'(x)$

Applying the **chain rule** $f'(x) = g'(u(x)) \cdot u'(x)$:
$$f'(x) = \cos(x^2 + 1) \cdot (2x)$$

Writing the algebraic factor $2x$ in front of the cosine function (to avoid any ambiguity about whether $2x$ is inside the cosine argument) yields:
$$f'(x) = 2x\cos(x^2 + 1)$$

---

### Step 3: Evaluate $f'(0)$ and determine its sign

Substituting $x = 0$ into $f'(x) = 2x\cos(x^2 + 1)$:
$$f'(0) = 2(0)\cos(0^2 + 1) = 0 \cdot \cos(1) = 0$$

**Sign of $f'(0)$ and Conceptual Explanation**:
- The value of $f'(0)$ is **zero** ($f'(0) = 0$), so its sign is **neither positive nor negative** ($\operatorname{sgn}(f'(0)) = 0$).
- **Why does $f'(0) = 0$ even though $\cos(1) \neq 0$?**
  At $x = 0$, the outer derivative factor is $\cos(0^2 + 1) = \cos(1\text{ rad}) \approx 0.5403 > 0$ (since $0 < 1 < \frac{\pi}{2} \approx 1.5708$). If a student forgot the chain rule and wrote $\cos(x^2 + 1)$ without the inner derivative $2x$, they would falsely conclude that the derivative at $x = 0$ is $\cos(1) > 0$.
  However, because the inner function $u(x) = x^2 + 1$ has a horizontal tangent at $x = 0$ ($u'(0) = 0$), small changes in $x$ near $0$ produce no first-order change in $u = x^2 + 1$, which in turn produces no first-order change in $\sin(x^2 + 1)$. Consequently, $f'(0) = 0$, and the graph of $f(x) = \sin(x^2 + 1)$ has a **horizontal tangent line** at $(0, \sin 1)$.

---

## 4. Verification and Consistency Checks

1. **Symmetry (Even/Odd) Check**:
   - The function $f(x) = \sin(x^2 + 1)$ depends on $x$ only through $x^2$. Therefore, $f(-x) = \sin((-x)^2 + 1) = \sin(x^2 + 1) = f(x)$, meaning $f$ is an **even function** on $\mathbb{R}$.
   - The derivative of any differentiable even function is an **odd function** and must equal $0$ at $x = 0$.
   - Checking our formula: $f'(-x) = 2(-x)\cos((-x)^2 + 1) = -2x\cos(x^2 + 1) = -f'(x)$, which is indeed odd and vanishes at $x = 0$.
2. **Local Behavior Around $x = 0$**:
   - Since $\cos(x^2 + 1) > 0$ for $x$ near $0$ (specifically for $x^2 + 1 < \frac{\pi}{2}$, i.e., $|x| < \sqrt{\frac{\pi}{2} - 1} \approx 0.755$), the sign of $f'(x) = 2x\cos(x^2 + 1)$ near $x = 0$ is determined by $2x$:
     - For $-\sqrt{\frac{\pi}{2}-1} < x < 0$, $f'(x) < 0$ ($f$ is decreasing).
     - At $x = 0$, $f'(0) = 0$.
     - For $0 < x < \sqrt{\frac{\pi}{2}-1}$, $f'(x) > 0$ ($f$ is increasing).
   - This confirms that $x = 0$ is a local minimum of $f(x)$, with value $f(0) = \sin(1) \approx 0.8415$.
