# Solution to Problem 12: Symmetry, Sign, and Absolute Value

## 1. Problem Statement

Compare
$$\int_{-2}^{2}x\,dx$$
and
$$\int_{-2}^{2}|x|\,dx.$$
Before calculating, predict the results from symmetry and a sketch, then carry out the calculation and explain the difference.

> **Why this problem:** it teaches how to use symmetry and geometry before applying a computational procedure.

---

## 2. Theoretical Background and Concepts

### Integrals of Odd and Even Functions on Symmetric Intervals $[-a, a]$
Let $f: [-a, a] \to \mathbb{R}$ be integrable on an interval $[-a, a]$ symmetric about the origin $x = 0$:
1. **Odd Function ($f(-x) = -f(x)$):** The graph is symmetric with respect to the origin $(0,0)$. The signed area on $[-a, 0]$ is the exact negative of the signed area on $[0, a]$, so they cancel completely:
   $$\int_{-a}^a f(x)\,dx = 0.$$
2. **Even Function ($f(-x) = f(x)$):** The graph is symmetric with respect to the $y$-axis. The signed area on $[-a, 0]$ equals the signed area on $[0, a]$, so they double:
   $$\int_{-a}^a f(x)\,dx = 2\int_0^a f(x)\,dx.$$

### Definition of the Absolute Value Function
The absolute value function $|x|$ is defined piecewise by:
$$|x| = \begin{cases} -x, & \text{if } x < 0, \\ x, & \text{if } x \ge 0. \end{cases}$$
To integrate an expression containing $|x|$ over an interval that straddles $x = 0$, we use the additivity of the definite integral to split the integral at the corner point $x = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Sketching the Graphs and Predicting the Results from Symmetry and Geometry

Let $I_1 = \int_{-2}^2 x\,dx$ and $I_2 = \int_{-2}^2 |x|\,dx$. Before computing any antiderivatives, we sketch both graphs on $[-2, 2]$:

```text
  Graph of f(x) = x on [-2, 2]                  Graph of g(x) = |x| on [-2, 2]
                   y                                               y
                   ^                                               ^
                 2 +           * (2,2)         (-2,2) *          2 +           * (2,2)
                   |         / :                      : \          |         / :
                 1 +       *   :                      :   *      1 +       *   :
                   |     / (+) :                      : (+) \      |     / (+) :
   ----+-----+-----*-----------+---> x         ----+--+-------+----*----+------+---> x
      -2    -1   0 |     1     2                  -2         -1  0(0,0) 1      2
       : (-)     / |
       :       *   + -1
       :     /     |
(-2,-2)* - - - - - + -2
```

1. **Prediction for $I_1 = \int_{-2}^2 x\,dx$:**
   - **By Symmetry:** The function $f(x) = x$ is an **odd function** since $f(-x) = -x = -f(x)$, and the interval $[-2, 2]$ is symmetric about $0$.
   - **By Geometry:** On $[-2, 0]$, the graph forms a right triangle **below** the $x$-axis with base $2$ and height $2$, giving a signed area of $-\frac{1}{2}(2)(2) = -2$. On $[0, 2]$, it forms a congruent right triangle **above** the $x$-axis with base $2$ and height $2$, giving a signed area of $+\frac{1}{2}(2)(2) = +2$.
   - **Predicted Value:** The negative and positive signed areas cancel out completely:
     $$I_1 = -2 + 2 = 0.$$

2. **Prediction for $I_2 = \int_{-2}^2 |x|\,dx$:**
   - **By Symmetry:** The function $g(x) = |x|$ is an **even, non-negative function** since $g(-x) = |-x| = |x| = g(x) \ge 0$ on the symmetric interval $[-2, 2]$.
   - **By Geometry:** Taking the absolute value reflects the left triangle across the $x$-axis into the upper half-plane. Thus, the region under $y = |x|$ on $[-2, 2]$ consists of **two congruent right triangles above the $x$-axis**, each of base $2$, height $2$, and positive area $\frac{1}{2}(2)(2) = 2$.
   - **Predicted Value:** The two positive areas add together:
     $$I_2 = 2 + 2 = 4.$$

---

### Step 2: Exact Analytical Calculations

1. **Analytical Calculation of $I_1 = \int_{-2}^2 x\,dx$:**
   Using the antiderivative $F(x) = \frac{x^2}{2}$ (where $F'(x) = x$) and the Fundamental Theorem of Calculus:
   $$\begin{aligned}
   I_1 = \int_{-2}^2 x\,dx &= \left[\frac{x^2}{2}\right]_{-2}^2 \\
   &= \frac{2^2}{2} - \frac{(-2)^2}{2} \\
   &= \frac{4}{2} - \frac{4}{2} = 2 - 2 = 0.
   \end{aligned}$$

2. **Analytical Calculation of $I_2 = \int_{-2}^2 |x|\,dx$:**
   Because $|x|$ changes its algebraic formula at $x = 0$ ($|x| = -x$ for $x \in [-2, 0]$ and $|x| = x$ for $x \in [0, 2]$), we split the integral at $x = 0$:
   $$\begin{aligned}
   I_2 = \int_{-2}^2 |x|\,dx &= \int_{-2}^0 |x|\,dx + \int_0^2 |x|\,dx \\
   &= \int_{-2}^0 (-x)\,dx + \int_0^2 x\,dx \\
   &= \left[-\frac{x^2}{2}\right]_{-2}^0 + \left[\frac{x^2}{2}\right]_0^2 \\
   &= \left(0 - \left(-\frac{(-2)^2}{2}\right)\right) + \left(\frac{2^2}{2} - 0\right) \\
   &= \left(0 + \frac{4}{2}\right) + \frac{4}{2} \\
   &= 2 + 2 = 4.
   \end{aligned}$$
   *(Equivalently, using even symmetry: $\int_{-2}^2 |x|\,dx = 2\int_0^2 x\,dx = 2\left[\frac{x^2}{2}\right]_0^2 = 2(2) = 4$.)*

---

### Step 3: Explaining the Difference Between the Two Integrals
The two integrals differ ($I_1 = 0$ vs. $I_2 = 4$) because:
- $\int_{-2}^2 x\,dx = 0$ computes the **net signed area** of $y = x$. Because $x$ is odd, every negative ordinate $-x_0$ on $[-2, 0)$ is paired with an equal positive ordinate $+x_0$ on $(0, 2]$, producing exact cancellation between the two halves of the interval.
- $\int_{-2}^2 |x|\,dx = 4$ computes the **total unsigned geometric area** between $y = x$ and the $x$-axis. The absolute value replaces negative values on $[-2, 0)$ with positive values $|-x| = -x > 0$, turning cancellation ($-2 + 2 = 0$) into reinforcement ($2 + 2 = 4$).

---

## 4. Verification and Consistency Checks

1. **Antiderivative Check for $|x|$:** Note that on $(-\infty, 0)$, $\frac{d}{dx}\left(-\frac{x^2}{2}\right) = -x = |x|$, and on $(0, \infty)$, $\frac{d}{dx}\left(\frac{x^2}{2}\right) = x = |x|$ (more compactly, $G(x) = \frac{1}{2}x|x|$ is a $C^1(\mathbb{R})$ antiderivative of $|x|$ everywhere, giving $[G(x)]_{-2}^2 = \frac{1}{2}(2)|2| - \frac{1}{2}(-2)|-2| = 2 - (-2) = 4$).
2. **Comparison with Predictions:** Both analytical results ($I_1 = 0$ and $I_2 = 4$) agree $100\%$ with the symmetry and geometric triangle predictions made in Step 1.
