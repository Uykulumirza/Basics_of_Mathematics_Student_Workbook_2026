# Solution to Exercise 2: Circle by Completing the Square

## 1. Problem Statement

Reduce the general second-degree equation
$$x^2 + y^2 - 6x + 4y - 3 = 0$$
to canonical form. Find the center and radius of the circle, then substitute two simple points from the circle into both forms of the equation (the general form and the canonical form) to verify their equivalence.

---

## 2. Theoretical Background and Concepts

### General and Canonical Forms of a Circle
In the Cartesian plane $\mathbb{R}^2$, a circle is the locus of all points $(x, y)$ situated at a constant distance $R > 0$ (the **radius**) from a fixed point $C = (x_0, y_0)$ (the **center**). By the Euclidean distance formula, this geometric condition translates directly into the **canonical equation of a circle**:
$$(x - x_0)^2 + (y - y_0)^2 = R^2$$

Expanding the squares in the canonical form leads to the **general algebraic equation**:
$$x^2 + y^2 + Dx + Ey + F = 0$$
where $D = -2x_0$, $E = -2y_0$, and $F = x_0^2 + y_0^2 - R^2$.

### Method of Completing the Square
To reverse this expansion and recover the geometric parameters $(x_0, y_0)$ and $R$ from the general equation, we group terms by variable and apply the algebraic identity:
$$u^2 + bu = \left(u + \frac{b}{2}\right)^2 - \left(\frac{b}{2}\right)^2$$
This transformation absorbs the linear terms $Dx$ and $Ey$ into shifted squares $(x - x_0)^2$ and $(y - y_0)^2$, revealing the coordinate shift from the origin to the center $(x_0, y_0)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Group Variables and Isolate the Constant Term
Starting with the given general equation:
$$x^2 + y^2 - 6x + 4y - 3 = 0$$
We collect the $x$-terms together, collect the $y$-terms together, and move the constant term $-3$ to the right-hand side:
$$(x^2 - 6x) + (y^2 + 4y) = 3$$

---

### Step 2: Complete the Square for Each Coordinate
1. **For the $x$-terms ($x^2 - 6x$):**
   The coefficient of the linear term is $-6$. Taking half of this coefficient gives $\frac{-6}{2} = -3$, and squaring it yields $(-3)^2 = 9$. Thus:
   $$x^2 - 6x = (x^2 - 6x + 9) - 9 = (x - 3)^2 - 9$$

2. **For the $y$-terms ($y^2 + 4y$):**
   The coefficient of the linear term is $+4$. Taking half of this coefficient gives $\frac{4}{2} = 2$, and squaring it yields $2^2 = 4$. Thus:
   $$y^2 + 4y = (y^2 + 4y + 4) - 4 = (y + 2)^2 - 4$$

---

### Step 3: Write the Canonical Equation
Substitute the completed squares back into the grouped equation (or equivalently, add $9$ and $4$ to both sides of $(x^2 - 6x) + (y^2 + 4y) = 3$):
$$(x^2 - 6x + 9) + (y^2 + 4y + 4) = 3 + 9 + 4$$
$$(x - 3)^2 + (y + 2)^2 = 16$$

This is the **canonical form** of the circle's equation.

---

### Step 4: Determine the Center and Radius
Comparing $(x - 3)^2 + (y + 2)^2 = 16$ with the standard template $(x - x_0)^2 + (y - y_0)^2 = R^2$:
- Rewrite $(y + 2)^2$ as $(y - (-2))^2$, which identifies the center coordinates:
  $$C = (x_0, y_0) = (3, -2)$$
- Since $R^2 = 16$ and the radius $R$ must be positive:
  $$R = \sqrt{16} = 4$$

---

### Step 5: Select Two Simple Points on the Circle
The simplest points on a circle are its **cardinal points**, found by moving a distance $R = 4$ purely horizontally or purely vertically from the center $C = (3, -2)$:
- **Point $P_1$ (moving $R = 4$ units right along the horizontal line $y = -2$):**
  $$P_1 = (3 + 4, -2) = (7, -2)$$
- **Point $P_2$ (moving $R = 4$ units up along the vertical line $x = 3$):**
  $$P_2 = (3, -2 + 4) = (3, 2)$$

*(Other equally simple cardinal points are $(3 - 4, -2) = (-1, -2)$ and $(3, -2 - 4) = (3, -6)$.)*

---

## 4. Verification and Consistency Checks

### 1. Substitution of Point $P_1 = (7, -2)$ into Both Forms
- **In the Canonical Form $(x - 3)^2 + (y + 2)^2 = 16$:**
  $$\text{LHS} = (7 - 3)^2 + (-2 + 2)^2 = 4^2 + 0^2 = 16 + 0 = 16 = \text{RHS} \quad \checkmark$$
- **In the General Form $x^2 + y^2 - 6x + 4y - 3 = 0$:**
  $$\text{LHS} = (7)^2 + (-2)^2 - 6(7) + 4(-2) - 3 = 49 + 4 - 42 - 8 - 3 = 53 - 53 = 0 = \text{RHS} \quad \checkmark$$

### 2. Substitution of Point $P_2 = (3, 2)$ into Both Forms
- **In the Canonical Form $(x - 3)^2 + (y + 2)^2 = 16$:**
  $$\text{LHS} = (3 - 3)^2 + (2 + 2)^2 = 0^2 + 4^2 = 0 + 16 = 16 = \text{RHS} \quad \checkmark$$
- **In the General Form $x^2 + y^2 - 6x + 4y - 3 = 0$:**
  $$\text{LHS} = (3)^2 + (2)^2 - 6(3) + 4(2) - 3 = 9 + 4 - 18 + 8 - 3 = 21 - 21 = 0 = \text{RHS} \quad \checkmark$$

### 3. Algebraic Expansion Check
Expanding the canonical form directly confirms that no arithmetic error occurred:
$$(x - 3)^2 + (y + 2)^2 - 16 = (x^2 - 6x + 9) + (y^2 + 4y + 4) - 16 = x^2 + y^2 - 6x + 4y - 3 = 0 \quad \checkmark$$
