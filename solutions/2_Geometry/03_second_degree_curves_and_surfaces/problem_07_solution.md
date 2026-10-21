# Solution to Exercise 7: Classifying a Second-Degree Equation

## 1. Problem Statement

Determine the type of geometric object in the real plane $\mathbb{R}^2$ described by each of the following second-degree equations:
1. $4x^2 + 9y^2 = 36$,
2. $x^2 - y^2 = 1$,
3. $x^2 - 4y = 0$,
4. $x^2 + y^2 + 1 = 0$.

In the last case, explain clearly why there are no real points satisfying the equation.

---

## 2. Theoretical Background and Concepts

### Algebraic Signatures of Planar Conic Sections
A second-degree equation in two variables without a mixed $xy$ term has the form:
$$Ax^2 + By^2 + Dx + Ey + F = 0$$
The relative signs and presence of the quadratic coefficients $A$ and $B$, together with the sign of the constant term after completing the square, determine the curve's classification:

| Algebraic Pattern | Canonical Form | Geometric Object |
| :--- | :--- | :--- |
| $A > 0, B > 0$ ($A \neq B$), positive RHS | $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ | **Ellipse** |
| $A = B > 0$, positive RHS | $x^2 + y^2 = R^2$ | **Circle** |
| $A$ and $B$ have opposite signs, non-zero RHS | $\frac{x^2}{a^2} - \frac{y^2}{b^2} = \pm 1$ | **Hyperbola** |
| Exactly one quadratic term ($A = 0$ or $B = 0$) and the other variable appears linearly | $x^2 = 4py$ or $y^2 = 4px$ | **Parabola** |
| $A > 0, B > 0$, negative RHS | $\frac{x^2}{a^2} + \frac{y^2}{b^2} = -1$ | **Empty set** in $\mathbb{R}^2$ (imaginary ellipse/circle) |

### Non-Negativity of Squares in $\mathbb{R}$
A fundamental property of the real number system $\mathbb{R}$ is that the square of any real number $u \in \mathbb{R}$ is non-negative:
$$u^2 \ge 0 \quad \text{for all } u \in \mathbb{R}, \quad \text{with } u^2 = 0 \iff u = 0$$
Consequently, a sum of squares of real variables $x^2 + y^2$ can never be strictly negative.

---

## 3. Detailed Step-by-Step Solution

### Case 1: $4x^2 + 9y^2 = 36$ — Ellipse
1. **Normalize to canonical form:**
   Divide both sides of the equation by $36$ to obtain $1$ on the right-hand side:
   $$\frac{4x^2}{36} + \frac{9y^2}{36} = \frac{36}{36} \iff \frac{x^2}{9} + \frac{y^2}{4} = 1$$
2. **Classification and geometric features:**
   Both variables $x$ and $y$ are squared, both quadratic terms have the **same (positive) sign**, the right-hand side is positive ($+1$), and the denominators are unequal ($9 \neq 4$).
   - **Object:** An **ellipse** centered at the origin $(0, 0)$.
   - **Semiaxes:** Horizontal semi-major axis $a = \sqrt{9} = 3$ (vertices at $(\pm 3, 0)$) and vertical semi-minor axis $b = \sqrt{4} = 2$ (co-vertices at $(0, \pm 2)$).

---

### Case 2: $x^2 - y^2 = 1$ — Hyperbola
1. **Write in canonical form:**
   The equation is already normalized with $1$ on the right-hand side:
   $$\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1$$
2. **Classification and geometric features:**
   Both variables $x$ and $y$ appear squared, but their coefficients have **opposite signs** ($+1$ for $x^2$ and $-1$ for $y^2$).
   - **Object:** A **rectangular (equilateral) hyperbola** centered at the origin $(0, 0)$.
   - **Key features:** Because the positive term is $x^2$, the branches open horizontally to the left and right, with vertices at $(\pm 1, 0)$, equal semiaxes $a = b = 1$, and perpendicular asymptotes $y = \pm x$.

---

### Case 3: $x^2 - 4y = 0$ — Parabola
1. **Isolate the quadratic term:**
   Adding $4y$ to both sides gives the canonical equation:
   $$x^2 = 4y \quad \left(\text{or } y = \frac{1}{4}x^2\right)$$
2. **Classification and geometric features:**
   Only **one variable ($x$) is squared**, while the second variable ($y$) appears only to the **first (linear) power**.
   - **Object:** A **parabola**.
   - **Key features:** Its vertex is at the origin $(0, 0)$, its axis of symmetry is the vertical axis $Oy$ ($x = 0$), and because the coefficient of $y$ is positive ($4p = 4 \implies p = 1 > 0$), it opens **upward** toward positive $y$, with focus at $(0, 1)$ and directrix $y = -1$.

---

### Case 4: $x^2 + y^2 + 1 = 0$ — Empty Set (Imaginary Circle)
1. **Isolate the constant term:**
   Subtracting $1$ from both sides yields:
   $$x^2 + y^2 = -1$$
2. **Classification and explanation of why no real points exist:**
   - **Object:** The **empty set** $\varnothing$ in the real coordinate plane $\mathbb{R}^2$ (often referred to algebraically as an *imaginary circle*).
   - **Why there are no real points:**
     For every pair of real coordinates $(x, y) \in \mathbb{R}^2$, the squares $x^2$ and $y^2$ satisfy:
     $$x^2 \ge 0 \qquad \text{and} \qquad y^2 \ge 0$$
     Adding these two non-negative quantities gives:
     $$x^2 + y^2 \ge 0$$
     Therefore, adding $1$ to both sides of the inequality shows that for all $(x, y) \in \mathbb{R}^2$:
     $$x^2 + y^2 + 1 \ge 0 + 1 = 1 > 0$$
     Since the left-hand side $x^2 + y^2 + 1$ is always at least $1$, it can never equal $0$ (equivalently, a non-negative sum $x^2 + y^2 \ge 0$ can never equal the negative number $-1$). Hence, the solution set in $\mathbb{R}^2$ is empty:
     $$\left\{(x, y) \in \mathbb{R}^2 : x^2 + y^2 + 1 = 0\right\} = \varnothing$$

---

## 4. Verification and Consistency Checks

We can verify each real curve (Cases 1–3) by testing a characteristic point and verify Case 4 by checking its minimum value:

1. **Case 1 ($4x^2 + 9y^2 = 36$):**
   Testing the horizontal vertex $(3, 0)$ gives $4(3)^2 + 9(0)^2 = 36 + 0 = 36 \checkmark$, and testing the vertical co-vertex $(0, 2)$ gives $4(0)^2 + 9(2)^2 = 0 + 36 = 36 \checkmark$.
2. **Case 2 ($x^2 - y^2 = 1$):**
   Testing the vertex $(1, 0)$ gives $1^2 - 0^2 = 1 \checkmark$; testing $(0, y)$ gives $-y^2 = 1$, confirming no $y$-axis intercept exists.
3. **Case 3 ($x^2 - 4y = 0$):**
   Testing the vertex $(0, 0)$ gives $0 - 0 = 0 \checkmark$, and testing the focal-chord endpoints $(\pm 2, 1)$ gives $(\pm 2)^2 - 4(1) = 4 - 4 = 0 \checkmark$.
4. **Case 4 ($x^2 + y^2 + 1 = 0$):**
   The function $f(x, y) = x^2 + y^2 + 1$ attains its absolute minimum on $\mathbb{R}^2$ at the origin $(0, 0)$, where $f(0, 0) = 0^2 + 0^2 + 1 = 1 > 0$. Since $\min_{(x,y)\in\mathbb{R}^2} f(x, y) = 1 > 0$, no root exists in $\mathbb{R}^2$.
