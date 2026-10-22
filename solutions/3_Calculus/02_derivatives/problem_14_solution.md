# Solution to Problem 14: Continuity and Differentiability of a Piecewise Function

## 1. Problem Statement

Investigate the behavior at $x=0$ of
$$f(x)=\begin{cases}x^2,&x\ge0,\\ax,&x<0.\end{cases}$$
For which values of $a$ is the function continuous? For which values do the one-sided derivatives exist and agree? For which value of $a$ is the function differentiable? Explain why continuity alone is not sufficient.

> **Why this problem:** it requires an organized argument and a clear distinction between two concepts.

---

## 2. Theoretical Background and Concepts

1. **Continuity at a Point**:
   A function $f$ is **continuous at $x = x_0$** if and only if the left-hand limit, the right-hand limit, and the function value at $x_0$ all exist and are equal:
   $$\lim_{x \to x_0^-} f(x) = \lim_{x \to x_0^+} f(x) = f(x_0)$$
2. **One-Sided Derivatives and Differentiability at a Point**:
   - The **right-hand derivative** at $x_0$ is:
     $$f'_+(x_0) = \lim_{h \to 0^+} \frac{f(x_0 + h) - f(x_0)}{h}$$
   - The **left-hand derivative** at $x_0$ is:
     $$f'_-(x_0) = \lim_{h \to 0^-} \frac{f(x_0 + h) - f(x_0)}{h}$$
   - A function $f$ is **differentiable at $x = x_0$** if and only if both one-sided derivatives $f'_-(x_0)$ and $f'_+(x_0)$ exist as finite real numbers **and are equal**:
     $$f'_-(x_0) = f'_+(x_0) = f'(x_0)$$
3. **Relationship Between Differentiability and Continuity**:
   - **Differentiability $\implies$ Continuity**: Every function that is differentiable at $x_0$ is necessarily continuous at $x_0$.
   - **Continuity $\not\implies$ Differentiability**: A function can be continuous at $x_0$ yet fail to be differentiable at $x_0$ (for example, if the graph has a sharp **corner/kink**, a cusp, or a vertical tangent at $x_0$).

---

## 3. Detailed Step-by-Step Solution

### Part 1: For which values of $a$ is $f$ continuous at $x = 0$?

We check the three quantities required for continuity at $x_0 = 0$:
1. **Value of the function at $x = 0$**:
   Since $x = 0$ belongs to the branch $x \ge 0$, we use the formula $f(x) = x^2$:
   $$f(0) = 0^2 = 0$$

2. **Right-hand limit as $x \to 0^+$**:
   For $x > 0$, $f(x) = x^2$, so:
   $$\lim_{x \to 0^+} f(x) = \lim_{x \to 0^+} x^2 = 0^2 = 0$$

3. **Left-hand limit as $x \to 0^-$**:
   For $x < 0$, $f(x) = ax$, where $a \in \mathbb{R}$ is a constant, so:
   $$\lim_{x \to 0^-} f(x) = \lim_{x \to 0^-} (ax) = a \cdot 0 = 0$$

Comparing the three results:
$$\lim_{x \to 0^-} f(x) = 0 = \lim_{x \to 0^+} f(x) = f(0) \quad \text{for every } a \in \mathbb{R}$$

**Conclusion on Continuity**:
The function $f$ is **continuous at $x = 0$ for all real values of $a$ ($a \in \mathbb{R}$)**, because both branches meet at the origin $(0, 0)$ regardless of the slope $a$ of the left-hand ray.

---

### Part 2: For which values of $a$ do the one-sided derivatives at $x = 0$ exist and agree?

Using the limit definition of one-sided derivatives at $x_0 = 0$ with $f(0) = 0$:

1. **Right-hand derivative $f'_+(0)$**:
   For $h > 0$, we have $0 + h = h > 0$, so $f(h) = h^2$. Therefore:
   $$f'_+(0) = \lim_{h \to 0^+} \frac{f(0 + h) - f(0)}{h} = \lim_{h \to 0^+} \frac{h^2 - 0}{h} = \lim_{h \to 0^+} h = 0$$
   Thus, the right-hand derivative exists for all $a \in \mathbb{R}$ and equals $f'_+(0) = 0$.

2. **Left-hand derivative $f'_-(0)$**:
   For $h < 0$, we have $0 + h = h < 0$, so $f(h) = ah$. Therefore:
   $$f'_-(0) = \lim_{h \to 0^-} \frac{f(0 + h) - f(0)}{h} = \lim_{h \to 0^-} \frac{ah - 0}{h} = \lim_{h \to 0^-} a = a$$
   Thus, the left-hand derivative exists for all $a \in \mathbb{R}$ and equals $f'_-(0) = a$.

3. **When do the one-sided derivatives agree?**
   Setting the left-hand and right-hand derivatives equal:
   $$f'_-(0) = f'_+(0) \iff a = 0$$

**Conclusion on One-Sided Derivatives**:
Both one-sided derivatives $f'_-(0) = a$ and $f'_+(0) = 0$ **exist for all $a \in \mathbb{R}$**, and they **agree if and only if $a = 0$**.

---

### Part 3: For which value of $a$ is $f$ differentiable at $x = 0$?

A function is differentiable at $x = 0$ if and only if the two-sided limit $\lim_{h \to 0} \frac{f(h) - f(0)}{h}$ exists, which occurs if and only if both one-sided derivatives exist and are equal ($f'_-(0) = f'_+(0)$).

From Part 2, this happens **if and only if**:
$$a = 0$$
When $a = 0$, the function is differentiable at $x = 0$, and its derivative at $x = 0$ is $f'(0) = 0$.

---

### Part 4: Explain why continuity alone is not sufficient for differentiability

- **Continuity** at $x = 0$ only requires that the graph has **no break or jump** at $(0, 0)$—that is, as $x \to 0$ from either side, the *heights* $f(x)$ approach the same point $f(0) = 0$. Since $ax \to 0$ and $x^2 \to 0$ as $x \to 0$, the two pieces always connect at $(0, 0)$ for every $a \in \mathbb{R}$.
- **Differentiability** at $x = 0$ is a stricter condition: it requires that the graph be **locally smooth (linear)** at $(0, 0)$, meaning the *slopes* of the secant lines from the left and from the right must approach the **same single tangent slope** as we zoom in on $(0, 0)$.
- When $a \neq 0$, the left branch $y = ax$ arrives at the origin with constant slope $a \neq 0$, whereas the right branch $y = x^2$ leaves the origin with initial slope $0$ (horizontally). This creates a **sharp corner (kink)** at $(0, 0)$: there is no unique tangent line at the origin, because the slope jumps abruptly from $a$ on the left to $0$ on the right. Hence, continuity guarantees a connected curve, but cannot prevent a sharp corner.

---

## 4. Verification and Consistency Checks

1. **Special Case $a = 0$**:
   When $a = 0$, $f(x) = 0$ for $x < 0$ and $f(x) = x^2$ for $x \ge 0$. As $x \to 0^+$, the parabola $y = x^2$ flattens out horizontally so that its slope $2x \to 0$, smoothly matching the horizontal line $y = 0$ (slope $0$) on the left without any corner.
2. **Special Case $a = -1$ (Comparison with $|x|$)**:
   When $a = -1$, $f(x)$ behaves near $0$ like a lopsided V-shape: it descends along the line $y = -x$ (slope $-1$) for $x < 0$ and rises along the parabola $y = x^2$ (initial slope $0$) for $x \ge 0$, exhibiting an unmistakable corner of angle $\frac{3\pi}{4}$ at the origin despite being continuous everywhere.
