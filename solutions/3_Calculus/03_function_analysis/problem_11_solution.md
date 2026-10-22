# Solution to Problem 11: A Parameter and the Number of Extrema

## 1. Problem Statement
For
$$f_a(x)=x^3-3ax$$
depending on $a$, determine the number of critical points and their character. Separate the parameter cases and justify why the structure of the graph changes.

> **Why this problem:** it teaches how to analyze an entire family of functions instead of a single example.

---

## 2. Theoretical Background and Concepts
1. **Parametric Family of Functions:** Given a real parameter $a \in \mathbb{R}$, the derivative $f_a'(x)$ is a quadratic polynomial in $x$ whose discriminant $\Delta_a$ depends on $a$. The sign of $a$ determines the number of real roots of $f_a'(x) = 0$.
2. **Sufficient Condition for Extrema:** A critical point $x_0$ ($f_a'(x_0) = 0$) is a local extremum if and only if $f_a'(x)$ **changes sign** across $x_0$. If $x_0$ is a root of even multiplicity (such as a double root of $f_a'(x) = 0$), then $f_a'(x) \ge 0$ (or $\le 0$) on both sides of $x_0$, so $x_0$ is a **stationary horizontal inflection point**, not an extremum.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Computing the Derivatives for General $a \in \mathbb{R}$
For every $a \in \mathbb{R}$, $f_a(x) = x^3 - 3ax$ is an odd cubic polynomial ($f_a(-x) = -f_a(x)$) defined on $D_{f_a} = \mathbb{R}$, with:
$$f_a'(x) = 3x^2 - 3a = 3(x^2 - a), \qquad f_a''(x) = 6x.$$
Notice that for **every** $a \in \mathbb{R}$, $f_a''(x) = 6x$ changes sign at $x = 0$, so $(0, 0)$ is always the unique inflection point and center of symmetry of the graph.

To find the critical points, we solve $f_a'(x) = 0$:
$$3(x^2 - a) = 0 \iff x^2 = a.$$
Because $x^2 \ge 0$ for all $x \in \mathbb{R}$, the number and nature of solutions to $x^2 = a$ depend on the sign of the parameter $a$. We must separate three cases: $a < 0$, $a = 0$, and $a > 0$.

---

### Step 2: Case-by-Case Analysis of the Parameter $a$

#### Case 1: $a < 0$
- **Number of Critical Points:** Since $x^2 \ge 0 > a$, the equation $x^2 = a$ has **no real solutions** (**$0$ critical points**).
- **Sign of $f_a'(x)$ and Monotonicity:** Since $a < 0$, we have $-a > 0$, so:
  $$f_a'(x) = 3(x^2 - a) \ge -3a > 0 \quad \text{for all } x \in \mathbb{R}.$$
  Even at the origin $x = 0$, the slope of the tangent line is strictly positive: $f_a'(0) = -3a > 0$.
- **Character / Extrema:** $f_a$ is **strictly increasing on all of $\mathbb{R}$** and has **no local extrema**.

#### Case 2: $a = 0$
- **Number of Critical Points:** The function simplifies to $f_0(x) = x^3$, and $f_0'(x) = 3x^2 = 0 \iff x = 0$ (a double root). Thus, there is **exactly $1$ critical point**, at $x = 0$.
- **Sign of $f_0'(x)$ and Character of $x = 0$:**
  $$f_0'(x) = 3x^2 > 0 \quad \text{for all } x \in \mathbb{R} \setminus \{0\}, \qquad f_0'(0) = 0.$$
  Because $f_0'(x)$ is positive on **both** $(-\infty, 0)$ and $(0, \infty)$, it does **not** change sign at $x = 0$.
- **Character / Extrema:** $f_0(x) = x^3$ is **strictly increasing on all of $\mathbb{R}$** and has **no local extrema**. The critical point $(0, 0)$ is a **stationary horizontal inflection point** (where $f_0'(0) = 0$ and $f_0''(0) = 0$ with $f_0''(x) = 6x$ changing sign).

#### Case 3: $a > 0$
- **Number of Critical Points:** When $a > 0$, the equation $x^2 = a$ has **$2$ distinct real critical points**:
  $$x_1 = -\sqrt{a} \quad \text{and} \quad x_2 = +\sqrt{a},$$
  so $f_a'(x) = 3(x + \sqrt{a})(x - \sqrt{a})$.
- **Sign Chart of $f_a'(x)$ and Character of the Critical Points:**

| Interval / Point | $(-\infty, -\sqrt{a})$ | $x = -\sqrt{a}$ | $(-\sqrt{a}, \sqrt{a})$ | $x = \sqrt{a}$ | $(\sqrt{a}, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f_a'(x)$** | $+$ | $0$ | $-$ | $0$ | $+$ |
| **Behavior of $f_a(x)$** | $\nearrow$ (increasing) | **Local Maximum** | $\searrow$ (decreasing) | **Local Minimum** | $\nearrow$ (increasing) |

- **Monotonicity and Extrema for $a > 0$:**
  - $f_a$ is **strictly increasing** on $(-\infty, -\sqrt{a}]$ and on $[\sqrt{a}, \infty)$, and **strictly decreasing** on $[-\sqrt{a}, \sqrt{a}]$.
  - At $x_1 = -\sqrt{a}$: $f_a'(x)$ changes from $+$ to $-$ (and $f_a''(-\sqrt{a}) = -6\sqrt{a} < 0$), so $f_a$ has a **strict local maximum**:
    $$f_a(-\sqrt{a}) = (-\sqrt{a})^3 - 3a(-\sqrt{a}) = -a\sqrt{a} + 3a\sqrt{a} = 2a\sqrt{a} = 2a^{3/2}.$$
  - At $x_2 = +\sqrt{a}$: $f_a'(x)$ changes from $-$ to $+$ (and $f_a''(\sqrt{a}) = +6\sqrt{a} > 0$), so $f_a$ has a **strict local minimum**:
    $$f_a(\sqrt{a}) = (\sqrt{a})^3 - 3a(\sqrt{a}) = a\sqrt{a} - 3a\sqrt{a} = -2a\sqrt{a} = -2a^{3/2}.$$

---

### Step 3: Why the Structure of the Graph Changes (Geometric & Bifurcation Interpretation)
1. **Vertical Shift of the Derivative Parabola:** The derivative $y = f_a'(x) = 3x^2 - 3a$ is a parabola with vertex at $(0, -3a)$ opening upward:
   - When $a < 0$, the vertex $(0, -3a)$ lies **strictly above** the $x$-axis, so $f_a'(x) > 0$ everywhere and $f_a$ rises monotonically without ever leveling off.
   - As $a \to 0^-$, the vertex lowers until at $a = 0$ it **just touches** the $x$-axis tangentially at $x = 0$. The cubic momentarily flattens at $(0,0)$ before continuing upward.
   - When $a > 0$, the vertex $(0, -3a)$ drops **strictly below** the $x$-axis, creating an open interval $(-\sqrt{a}, \sqrt{a})$ where $f_a'(x) < 0$. This negative-slope middle interval forces the cubic to turn downward between its local maximum at $(-\sqrt{a}, 2a^{3/2})$ and its local minimum at $(\sqrt{a}, -2a^{3/2})$.
2. **Fold Bifurcation at $a = 0$:** As $a \to 0^+$, the distance between the two extrema $2\sqrt{a}$ and their vertical separation $4a^{3/2}$ both shrink to $0$; at $a = 0$ the local maximum and local minimum **collide and annihilate each other** at the inflection point $(0, 0)$.

---

## 4. Verification and Consistency Checks
| Parameter Case | Critical Points | Local Maxima | Local Minima | Monotonicity on $\mathbb{R}$ |
| :---: | :---: | :---: | :---: | :---: |
| **$a < 0$** | $0$ (none) | None | None | Strictly increasing on $\mathbb{R}$ |
| **$a = 0$** | $1$ ($x = 0$, inflection pt) | None | None | Strictly increasing on $\mathbb{R}$ |
| **$a > 0$** | $2$ ($x = \pm\sqrt{a}$) | $\left(-\sqrt{a}, 2a^{3/2}\right)$ | $\left(\sqrt{a}, -2a^{3/2}\right)$ | $\nearrow$ on $(-\infty, -\sqrt{a}]$, $\searrow$ on $[-\sqrt{a}, \sqrt{a}]$, $\nearrow$ on $[\sqrt{a}, \infty)$ |

Checking $a = 1$ gives $f_1(x) = x^3 - 3x$, which has local maximum $(-1, 2)$ and local minimum $(1, -2)$, matching the formulas $\left(\mp\sqrt{1}, \pm 2(1)^{3/2}\right)$.
