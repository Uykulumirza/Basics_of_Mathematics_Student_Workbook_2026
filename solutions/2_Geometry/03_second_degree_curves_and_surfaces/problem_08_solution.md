# Solution to Exercise 8: Sphere

## 1. Problem Statement

Reduce the general second-degree equation in three variables
$$x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$$
to canonical form. Find the center and radius of the sphere. Give two explicit points on the sphere and check them in the equation.

---

## 2. Theoretical Background and Concepts

### Canonical and General Equations of a Sphere in $\mathbb{R}^3$
A **sphere** in three-dimensional Euclidean space $\mathbb{R}^3$ is the set of all points $P = (x, y, z)$ whose distance from a fixed center $C = (x_0, y_0, z_0)$ equals a constant radius $R > 0$. By the 3D Euclidean distance formula:
$$\sqrt{(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2} = R$$
Squaring both sides yields the **canonical equation of a sphere**:
$$(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$$

Expanding the three binomial squares transforms the canonical equation into the **general form**:
$$x^2 + y^2 + z^2 + Dx + Ey + Fz + G = 0$$
Note the direct analogy with the circle in $\mathbb{R}^2$: all three quadratic terms $x^2, y^2, z^2$ have equal positive coefficients, and there are no mixed product terms ($xy, yz, xz$). Completing the square independently in $x$, $y$, and $z$ recovers the center $(x_0, y_0, z_0)$ and $R^2$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Group Variables by Coordinate
Start with the given equation:
$$x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$$

Group the $x$-terms, $y$-terms, and $z$-terms into three separate pairs, and move the constant term $-2$ to the right-hand side:
$$(x^2 - 4x) + (y^2 + 2y) + (z^2 - 6z) = 2$$

---

### Step 2: Complete the Square in $x$, $y$, and $z$
1. **For the $x$-group ($x^2 - 4x$):**
   Half of $-4$ is $-2$, and $(-2)^2 = 4$:
   $$x^2 - 4x = (x^2 - 4x + 4) - 4 = (x - 2)^2 - 4$$

2. **For the $y$-group ($y^2 + 2y$):**
   Half of $+2$ is $+1$, and $1^2 = 1$:
   $$y^2 + 2y = (y^2 + 2y + 1) - 1 = (y + 1)^2 - 1$$

3. **For the $z$-group ($z^2 - 6z$):**
   Half of $-6$ is $-3$, and $(-3)^2 = 9$:
   $$z^2 - 6z = (z^2 - 6z + 9) - 9 = (z - 3)^2 - 9$$

---

### Step 3: Write the Canonical Equation
Add the completing-the-square constants ($4$, $1$, and $9$) to both sides of the grouped equation:
$$(x^2 - 4x + 4) + (y^2 + 2y + 1) + (z^2 - 6z + 9) = 2 + 4 + 1 + 9$$
$$(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$$

This is the **canonical form** of the sphere.

---

### Step 4: Identify the Center and Radius
Comparing $(x - 2)^2 + (y - (-1))^2 + (z - 3)^2 = 4^2$ with $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$:
- **Center of the sphere:**
  $$C = (x_0, y_0, z_0) = (2, -1, 3)$$
- **Radius of the sphere:**
  $$R^2 = 16 \implies R = \sqrt{16} = 4$$

---

### Step 5: Find Two Explicit Points on the Sphere
To obtain simple points on the sphere without radicals, we start at the center $C = (2, -1, 3)$ and move a distance $R = 4$ parallel to one of the coordinate axes (leaving the other two coordinates unchanged):

1. **Point $P_1$ (displaced by $+4$ along the $Ox$ direction):**
   $$P_1 = (2 + 4, -1, 3) = (6, -1, 3)$$
2. **Point $P_2$ (displaced by $+4$ along the $Oy$ direction):**
   $$P_2 = (2, -1 + 4, 3) = (2, 3, 3)$$

*(Other axis-aligned points on the sphere include $(-2, -1, 3)$, $(2, -5, 3)$, $(2, -1, 7)$, and $(2, -1, -1)$.)*

---

## 4. Verification and Consistency Checks

### 1. Checking Point $P_1 = (6, -1, 3)$ in Both Forms
- **In the Canonical Equation $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:**
  $$\text{LHS} = (6 - 2)^2 + (-1 + 1)^2 + (3 - 3)^2 = 4^2 + 0^2 + 0^2 = 16 = \text{RHS} \quad \checkmark$$
- **In the Original General Equation $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$:**
  $$\begin{aligned}
  \text{LHS} &= (6)^2 + (-1)^2 + (3)^2 - 4(6) + 2(-1) - 6(3) - 2 \\
  &= 36 + 1 + 9 - 24 - 2 - 18 - 2 \\
  &= 46 - 46 = 0 = \text{RHS} \quad \checkmark
  \end{aligned}$$

### 2. Checking Point $P_2 = (2, 3, 3)$ in Both Forms
- **In the Canonical Equation $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:**
  $$\text{LHS} = (2 - 2)^2 + (3 + 1)^2 + (3 - 3)^2 = 0^2 + 4^2 + 0^2 = 16 = \text{RHS} \quad \checkmark$$
- **In the Original General Equation $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$:**
  $$\begin{aligned}
  \text{LHS} &= (2)^2 + (3)^2 + (3)^2 - 4(2) + 2(3) - 6(3) - 2 \\
  &= 4 + 9 + 9 - 8 + 6 - 18 - 2 \\
  &= 28 - 28 = 0 = \text{RHS} \quad \checkmark
  \end{aligned}$$
