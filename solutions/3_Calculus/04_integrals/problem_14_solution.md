# Solution to Problem 14: A Piecewise-Defined Function

## 1. Problem Statement

Let
$$f(x)=\begin{cases}x+1,&-1\le x<1,\\2,&1\le x\le3.\end{cases}$$
Sketch the graph, decide where to split the integral, compute
$$\int_{-1}^{3}f(x)\,dx$$
and verify the result geometrically.

> **Why this problem:** it requires understanding the definition of the function before carrying out the calculation.

---

## 2. Theoretical Background and Concepts

### Additivity of the Definite Integral Over Subintervals
Let $f: [a, b] \to \mathbb{R}$ be integrable on $[a, b]$. For any interior point $c \in (a, b)$, the definite integral satisfies the **Interval Additivity Property**:
$$\int_a^b f(x)\,dx = \int_a^c f(x)\,dx + \int_c^b f(x)\,dx.$$
When $f(x)$ is a **piecewise-defined function** that uses different algebraic formulas on $[a, c)$ and $[c, b]$, a single antiderivative formula cannot be applied across the entire interval $[a, b]$ at once. Instead, we must split the integral at the transition point(s) $x = c$ where the formula changes.

*(Note: Modifying the value of an integrand at a single endpoint—such as $x = 1$ in $[-1, 1)$ versus $[-1, 1]$—does not affect the value of the Riemann integral on $[-1, 1]$; moreover, here $f(x)$ is continuous at $x = 1$ since $\lim_{x\to 1^-} (x+1) = 1+1 = 2 = f(1)$.)*

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analysing and Sketching the Graph of $f(x)$ on $[-1, 3]$
Let us examine the two branches of $f(x)$:
1. **First branch on $[-1, 1)$:** $f(x) = x + 1$ is a straight line with slope $1$ and $y$-intercept $1$, rising from the point $(-1, 0)$ through $(0, 1)$ toward $(1, 2)$.
2. **Second branch on $[1, 3]$:** $f(x) = 2$ is a horizontal line at height $y = 2$ from $(1, 2)$ to $(3, 2)$.
3. **Continuity at the transition point $x = 1$:** As $x \to 1^-$, $x + 1 \to 2$, which equals $f(1) = 2$. Thus, the two segments meet continuously at the corner point $(1, 2)$.

```
        y
      3 +
        |
      2 +                 (1,2) *-----------+-----------+ (3,2)
        |                     / |           |           |
        |                   /   |           |           |
      1 +           (0,1) *     |  Triangle | Rectangle |
        |               /   (+) |   Area=2  |  Area=4   |
        |             /         |           |           |
    ----+-----+-----*-----------+-----------+-----------+---> x
       -2    -1    0            1           2           3
           (-1,0)
```

### Step 2: Deciding Where to Split the Integral
Because the algebraic formula defining $f(x)$ changes at **$x = 1$** (from the linear function $x + 1$ on $[-1, 1)$ to the constant function $2$ on $[1, 3]$), we must split the definite integral over $[-1, 3]$ at the transition point **$c = 1$**:
$$\int_{-1}^3 f(x)\,dx = \int_{-1}^1 f(x)\,dx + \int_1^3 f(x)\,dx = \int_{-1}^1 (x + 1)\,dx + \int_1^3 2\,dx.$$

### Step 3: Analytical Computation of the Split Integrals
We compute each sub-integral using the Fundamental Theorem of Calculus:

1. **First Integral on $[-1, 1]$:**
   An antiderivative of $f_1(x) = x + 1$ is $F_1(x) = \frac{x^2}{2} + x$ (verified by $F_1'(x) = \frac{d}{dx}\left(\frac{x^2}{2} + x\right) = x + 1$). Evaluating from $-1$ to $1$:
   $$\begin{aligned}
   \int_{-1}^1 (x + 1)\,dx &= \left[\frac{x^2}{2} + x\right]_{-1}^1 \\
   &= \left(\frac{1^2}{2} + 1\right) - \left(\frac{(-1)^2}{2} + (-1)\right) \\
   &= \left(\frac{1}{2} + 1\right) - \left(\frac{1}{2} - 1\right) \\
   &= \frac{3}{2} - \left(-\frac{1}{2}\right) = \frac{4}{2} = 2.
   \end{aligned}$$

2. **Second Integral on $[1, 3]$:**
   An antiderivative of $f_2(x) = 2$ is $F_2(x) = 2x$ (verified by $F_2'(x) = \frac{d}{dx}(2x) = 2$). Evaluating from $1$ to $3$:
   $$\begin{aligned}
   \int_1^3 2\,dx &= \big[2x\big]_1^3 \\
   &= 2(3) - 2(1) \\
   &= 6 - 2 = 4.
   \end{aligned}$$

3. **Total Value of the Definite Integral:**
   Summing the two parts:
   $$\int_{-1}^3 f(x)\,dx = 2 + 4 = 6.$$

### Step 4: Geometric Verification
Since $f(x) \ge 0$ everywhere on $[-1, 3]$, the definite integral $\int_{-1}^3 f(x)\,dx$ equals the exact geometric area of the region under the graph $y = f(x)$, which decomposes at $x = 1$ into two elementary polygons (or a single right trapezoid):
1. **On $[-1, 1]$ (Right Triangle):**
   The region under $y = x + 1$ from $x = -1$ to $x = 1$ is a right triangle with base $b = 1 - (-1) = 2$ and height $h = 2$:
   $$A_{\text{triangle}} = \frac{1}{2} \cdot b \cdot h = \frac{1}{2} \cdot 2 \cdot 2 = 2.$$
2. **On $[1, 3]$ (Rectangle):**
   The region under $y = 2$ from $x = 1$ to $x = 3$ is a rectangle (specifically, a square) of width $w = 3 - 1 = 2$ and height $h = 2$:
   $$A_{\text{rectangle}} = w \cdot h = 2 \cdot 2 = 4.$$
3. **Total Geometric Area:**
   $$A_{\text{total}} = A_{\text{triangle}} + A_{\text{rectangle}} = 2 + 4 = 6.$$
   *(Alternatively, viewing the entire region on $[-1, 3]$ as a single trapezoid of height $h = 2$ with parallel horizontal bases of length $b_1 = 3 - (-1) = 4$ along the $x$-axis and $b_2 = 3 - 1 = 2$ along $y = 2$, its area is $\frac{b_1 + b_2}{2}\cdot h = \frac{4 + 2}{2}\cdot 2 = 6$.)*

The geometric calculation confirms the analytical integral $\int_{-1}^3 f(x)\,dx = 6$.

---

## 4. Verification and Consistency Checks

1. **Continuous Piecewise Antiderivative Check:** Notice that if we define $F(x) = \begin{cases}\frac{1}{2}(x+1)^2, & -1 \le x < 1, \\ 2x, & 1 \le x \le 3,\end{cases}$ then $F(x)$ is continuous at $x = 1$ ($F(1^-) = \frac{1}{2}(2)^2 = 2 = F(1)$) and satisfies $F'(x) = f(x)$ on $[-1, 3]$, with $F(3) - F(-1) = 6 - 0 = 6$.
2. **Lower/Upper Bound Check:** Since $0 \le f(x) \le 2$ on $[-1, 3]$ of length $4$, we must have $0 \cdot 4 \le \int_{-1}^3 f(x)\,dx \le 2 \cdot 4$, i.e., $0 \le 6 \le 8$, which holds.
