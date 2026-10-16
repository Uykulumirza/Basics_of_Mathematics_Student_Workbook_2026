# Solution to Exercise 4: Parabola

## 1. Problem Statement

Given the canonical equation of the parabola:
$$y^2 = 12x$$

1. Identify the vertex, axis of symmetry, and opening direction.
2. Find the focus and directrix line.
3. Compute the coordinates of the points on the parabola corresponding to $x = 3$.
4. Make a geometric sketch/plot based on these key geometric points.

---

## 2. Theoretical Background and Concepts

### Canonical Form of a Parabola Opening Along the $x$-Axis
A parabola with vertex at the origin and axis of symmetry along the $x$-axis has canonical equation:
$$y^2 = 2px$$
where:
- $p > 0$ is the **focal parameter** (the distance between the focus and the directrix).
- **Vertex:** $V = (0, 0)$.
- **Axis of Symmetry:** The line $y = 0$ (the $x$-axis). Because replacing $y$ with $-y$ preserves the equation ($(-y)^2 = y^2$), the curve is symmetric across the $x$-axis.
- **Focus:** $F = \left(\frac{p}{2}, 0\right)$.
- **Directrix:** The vertical line $x = -\frac{p}{2}$.
- **Geometric Definition:** Every point $P(x, y)$ on the parabola is equidistant from the focus $F$ and the directrix line $d$:
  $$d(P, F) = d(P, d)$$
- **Latus Rectum (Focal Width):** The chord passing through the focus perpendicular to the axis of symmetry has length equal to $2p$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Key Characteristics from the Canonical Form
Comparing $y^2 = 12x$ with $y^2 = 2px$:
$$2p = 12 \implies p = 6$$

1. **Vertex:**
   $$V = (0, 0)$$
2. **Axis of Symmetry:**
   $$y = 0 \quad (\text{the } x\text{-axis})$$
3. **Opening Direction:**
   Since $x = \frac{y^2}{12}$ and $y^2 \ge 0$ for all real $y$, we must have $x \ge 0$. The parabola opens to the **right** (in the positive $x$-direction).

---

### Step 2: Compute Focus and Directrix
With $p = 6$:
- **Focal distance from vertex:** $\frac{p}{2} = \frac{6}{2} = 3$.
- **Focus:**
  $$F = (3, 0)$$
- **Directrix line:**
  $$x = -3$$

---

### Step 3: Compute Points on the Parabola for $x = 3$
Substitute $x = 3$ into the equation:
$$y^2 = 12(3) = 36$$
Taking the square root gives:
$$y = \pm \sqrt{36} = \pm 6$$

Thus, the two points on the parabola at $x = 3$ are:
$$P_1 = (3, 6) \qquad \text{and} \qquad P_2 = (3, -6)$$

**Geometric Observation:** 
Notice that $x = 3$ is precisely the $x$-coordinate of the focus $F(3, 0)$. The line segment connecting $P_1(3, 6)$ and $P_2(3, -6)$ is the **latus rectum** of the parabola, and its length is:
$$\|P_1 - P_2\| = 6 - (-6) = 12 = 2p$$

---

### Step 4: Geometric Sketch

```
   Directrix: x = -3
           |             y
           |             ^
           |             |            * P1(3, 6)
           |             |          * |
           |             |        *   |
           |             |      *     |
   --------+-------------*----+-------+---------> x
    x = -3 |           V(0,0) |     F(3,0)
           |             |      *     |
           |             |        *   |
           |             |          * |
           |             |            * P2(3, -6)
           |             |
```

---

## 4. Verification and Consistency Checks

1. **Equidistance Verification (Parabola Definition):**
   Test point $P_1(3, 6)$:
   - Distance from $P_1(3, 6)$ to focus $F(3, 0)$:
     $$d(P_1, F) = \sqrt{(3 - 3)^2 + (6 - 0)^2} = \sqrt{0 + 36} = 6$$
   - Distance from $P_1(3, 6)$ to directrix line $x = -3$:
     $$d(P_1, d) = |3 - (-3)| = |3 + 3| = 6$$
   Since $d(P_1, F) = d(P_1, d) = 6$, the defining geometric property of the parabola is verified.

2. **Additional Curve Points Check:**
   - At $x = 0 \implies y = 0$ (the vertex $(0, 0)$).
   - At $x = 12 \implies y^2 = 144 \implies y = \pm 12$, points $(12, 12)$ and $(12, -12)$.
     Distance to focus: $\sqrt{(12 - 3)^2 + 12^2} = \sqrt{81 + 144} = \sqrt{225} = 15$.
     Distance to directrix: $|12 - (-3)| = 15 \checkmark$.

