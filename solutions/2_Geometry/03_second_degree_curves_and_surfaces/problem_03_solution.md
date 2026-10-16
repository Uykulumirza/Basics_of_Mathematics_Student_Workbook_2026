# Solution to Exercise 3: Ellipse

## 1. Problem Statement

Given the canonical equation of the ellipse:
$$\frac{x^2}{25} + \frac{y^2}{9} = 1$$

1. Find the lengths of the semi-axes.
2. Determine the coordinates of all intercepts with the coordinate axes.
3. Make a geometric sketch/plot of the curve.
4. Explain along which coordinate axis the ellipse is more stretched and how this property is immediately visible from the algebraic structure of the equation.

---

## 2. Theoretical Background and Concepts

### Canonical Form of an Origin-Centered Ellipse
The canonical equation of an ellipse centered at $(0, 0)$ whose principal axes coincide with the coordinate axes is:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$$
where:
- $a > 0$ represents the length of the horizontal semi-axis along the $x$-axis.
- $b > 0$ represents the length of the vertical semi-axis along the $y$-axis.

### Geometric Significance of the Denominators
- Setting $y = 0$ gives $\frac{x^2}{a^2} = 1 \implies x^2 = a^2 \implies x = \pm a$. Thus, the maximum horizontal reach from the center is $a$.
- Setting $x = 0$ gives $\frac{y^2}{b^2} = 1 \implies y^2 = b^2 \implies y = \pm b$. Thus, the maximum vertical reach from the center is $b$.
- The axis with the larger denominator corresponds to the **major axis** (the direction of greatest elongation).
- The focal distance $c$ satisfies the Pythagorean relation for the major axis:
  $$c = \sqrt{|a^2 - b^2|}$$
  Foci always lie along the major axis at distance $c$ from the center.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Semiaxis Lengths
Comparing $\frac{x^2}{25} + \frac{y^2}{9} = 1$ with the canonical form:
- $a^2 = 25 \implies a = \sqrt{25} = 5$ (horizontal semi-axis)
- $b^2 = 9 \implies b = \sqrt{9} = 3$ (vertical semi-axis)

Since $a = 5 > b = 3$:
- The **semi-major axis** has length $a = 5$.
- The **semi-minor axis** has length $b = 3$.

---

### Step 2: Determine Coordinate Intercepts
- **$x$-intercepts (setting $y = 0$):**
  $$\frac{x^2}{25} + 0 = 1 \implies x^2 = 25 \implies x = \pm 5$$
  The ellipse intersects the $x$-axis at the major vertices:
  $$V_1 = (-5, 0) \qquad \text{and} \qquad V_2 = (5, 0)$$

- **$y$-intercepts (setting $x = 0$):**
  $$0 + \frac{y^2}{9} = 1 \implies y^2 = 9 \implies y = \pm 3$$
  The ellipse intersects the $y$-axis at the co-vertices:
  $$B_1 = (0, -3) \qquad \text{and} \qquad B_2 = (0, 3)$$

---

### Step 3: Foci and Focal Distance
The linear eccentricity (focal distance) is:
$$c = \sqrt{a^2 - b^2} = \sqrt{25 - 9} = \sqrt{16} = 4$$

Since the major axis is horizontal, the foci lie on the $x$-axis:
$$F_1 = (-4, 0) \qquad \text{and} \qquad F_2 = (4, 0)$$

---

### Step 4: Explanation of Elongation and Equation Structure
- **Direction of Stretching:** The ellipse is more stretched along the **$x$-axis**. The full horizontal span is $2a = 10$, whereas the vertical span is only $2b = 6$.
- **Visibility in the Equation:** This elongation is directly visible from the denominators:
  $$25 > 9 \implies a^2 > b^2 \implies a > b$$
  In the equation $\frac{x^2}{25} + \frac{y^2}{9} = 1$, the larger number ($25$) is located directly beneath $x^2$. Because dividing $x^2$ by a larger denominator compresses the contribution of $x$ toward the total sum of $1$, $x$ can take on larger numerical values (up to $\pm 5$) before saturating the unit bound than $y$ can (which is capped at $\pm 3$).

---

### Step 5: Geometric Sketch

```
                        y
                        ^
                        |  (0, 3)
                 .  - - + - - .
             '          |          '
          *             |             *
       *    F1(-4,0)    |   F2(4,0)      *
<-----*-----------------+-----------------*-----> x
   (-5, 0)              |              (5, 0)
       *                |                *
          *             |             *
             '          |          '
                 .  - - + - - .
                        |  (0, -3)
```

---

## 4. Verification and Consistency Checks

1. **Sum of Focal Distances (Definition of Ellipse):**
   For any point $P$ on an ellipse, the sum of distances to both foci must equal $2a = 10$:
   $$d(P, F_1) + d(P, F_2) = 2a = 10$$
   Testing the co-vertex $B_2 = (0, 3)$ with foci $F_1 = (-4, 0)$ and $F_2 = (4, 0)$:
   $$d(B_2, F_1) = \sqrt{(-4 - 0)^2 + (0 - 3)^2} = \sqrt{16 + 9} = \sqrt{25} = 5$$
   $$d(B_2, F_2) = \sqrt{(4 - 0)^2 + (0 - 3)^2} = \sqrt{16 + 9} = \sqrt{25} = 5$$
   Sum:
   $$5 + 5 = 10 = 2a \quad \checkmark$$

2. **Area Consistency:**
   The area enclosed by an ellipse is given by:
   $$\text{Area} = \pi \cdot a \cdot b = \pi \cdot 5 \cdot 3 = 15\pi$$
   Bounded in the bounding box $[-5, 5] \times [-3, 3]$ of area $10 \times 6 = 60$. Notice $15\pi \approx 47.12 < 60$, fully consistent.

