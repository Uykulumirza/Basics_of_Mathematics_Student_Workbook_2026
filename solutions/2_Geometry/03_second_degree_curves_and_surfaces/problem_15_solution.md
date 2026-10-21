# Solution to Exercise 15: Recognition and Sketch Without a Given Name

## 1. Problem Statement

Consider the two equations:
1. $4x^2 + 9y^2 - 8x + 36y + 4 = 0$ (in the plane $\mathbb{R}^2$),
2. $4x^2 + y^2 = z^2$ (in three-dimensional space $\mathbb{R}^3$).

- **For the first equation:** Reduce it to canonical form, recognize the curve, give its most important features, and make a sketch.
- **For the second equation:** Do not begin by using a ready-made name for the surface. First describe the horizontal cross-sections $z = c$ and the vertical cross-sections by the coordinate planes $x = 0$ and $y = 0$, paying careful attention to the different scales along the axes. Only then identify the surface and make a sketch.

---

## 2. Theoretical Background and Concepts

### Mechanism 1: Completing the Square for Planar Conics
A general second-degree equation $Ax^2 + By^2 + Dx + Ey + F = 0$ with $A > 0$ and $B > 0$ is reduced to canonical form by factoring out $A$ from the $x$-terms and $B$ from the $y$-terms, completing the square in each variable, and dividing by the resulting positive right-hand side constant $K$:
$$\frac{(x - x_0)^2}{a^2} + \frac{(y - y_0)^2}{b^2} = 1$$
From this canonical equation, we read off the center $(x_0, y_0)$, the horizontal semiaxis $a$, the vertical semiaxis $b$, the vertices, and the foci.

### Mechanism 2: Building a 3D Surface from Scaled Cross-Sections
When a 3D surface equation contains different positive weights before $x^2$ and $y^2$ (such as $4x^2 + y^2 = z^2$), slicing by horizontal planes $z = c$ and vertical planes $x = 0, y = 0$ reveals not only the topological family of curves (points, ellipses, intersecting lines) but also the **anisotropic scaling** along each coordinate axis. Dividing by $c^2$ (for $c \neq 0$) exposes the exact semiaxis lengths in the $x$- and $y$-directions as linear functions of $|c|$.

---

## 3. Detailed Step-by-Step Solution

### Part 1: Planar Curve $4x^2 + 9y^2 - 8x + 36y + 4 = 0$

#### Step 1.1: Complete the Square and Reduce to Canonical Form
Group the $x$-terms and $y$-terms and move the constant $+4$ to the right-hand side:
$$(4x^2 - 8x) + (9y^2 + 36y) = -4$$

Factor out the leading coefficients $4$ and $9$:
$$4(x^2 - 2x) + 9(y^2 + 4y) = -4$$

Complete the square inside each parenthesis:
- $x^2 - 2x = (x - 1)^2 - 1 \implies 4(x^2 - 2x) = 4(x - 1)^2 - 4$
- $y^2 + 4y = (y + 2)^2 - 4 \implies 9(y^2 + 4y) = 9(y + 2)^2 - 36$

Substitute back into the equation:
$$4(x - 1)^2 - 4 + 9(y + 2)^2 - 36 = -4$$
Add $4 + 36 = 40$ to both sides:
$$4(x - 1)^2 + 9(y + 2)^2 = 36$$
Divide both sides by $36$ to obtain the **canonical form**:
$$\frac{(x - 1)^2}{9} + \frac{(y + 2)^2}{4} = 1$$

#### Step 1.2: Recognize the Curve and Identify Its Key Features
- **Type of curve:** A **shifted ellipse** (both squared terms have positive coefficients, the right-hand side is $+1$, and the denominators $9 \neq 4$ are unequal).
- **Center:** $C = (x_0, y_0) = (1, -2)$ ( located in Quadrant IV).
- **Semiaxes:**
  - Horizontal semi-major axis (parallel to $Ox$): $a = \sqrt{9} = 3$.
  - Vertical semi-minor axis (parallel to $Oy$): $b = \sqrt{4} = 2$.
  - Since $a = 3 > b = 2$, the ellipse is stretched horizontally along the line $y = -2$.
- **Vertices:**
  - Major vertices (left and right from $(1, -2)$ by $a = 3$):
    $$V_1 = (1 - 3, -2) = (-2, -2), \qquad V_2 = (1 + 3, -2) = (4, -2)$$
  - Minor co-vertices (down and up from $(1, -2)$ by $b = 2$):
    $$B_1 = (1, -2 - 2) = (1, -4), \qquad B_2 = (1, -2 + 2) = (1, 0)$$
    *(Note that the upper co-vertex $B_2 = (1, 0)$ lies directly on the $Ox$ axis, so the ellipse is tangent to the $x$-axis at $(1, 0)$!)*
- **Foci:**
  With focal distance $c_f = \sqrt{a^2 - b^2} = \sqrt{9 - 4} = \sqrt{5} \approx 2.24$ along the horizontal major axis $y = -2$:
  $$F_1 = (1 - \sqrt{5}, -2), \qquad F_2 = (1 + \sqrt{5}, -2)$$

#### Step 1.3: Sketch of the Shifted Ellipse
```
                         y
                         ^
                         |       B2(1, 0) [tangent to x-axis]
      <------------------+-------*------------------> x
        -2      -1       0   . - + - . 2       3    4
                         | '     |     '
                  V1     *       C(1,-2) * V2
                (-2,-2)  * - - - + - - - * (4,-2)   (line y = -2)
                         | .     |     .
                         |   ' - * - '
                         |       B1(1, -4)
                         v
```

---

### Part 2: Surface $4x^2 + y^2 = z^2$ (Analyzed First via Cross-Sections)

Following the instruction, we do **not** name the surface yet; instead, we systematically examine its planar cross-sections and their relative scales.

#### Step 2.1: Horizontal Cross-Sections $z = c$ ($c \in \mathbb{R}$)
Substitute $z = c$ into $4x^2 + y^2 = z^2$:
$$4x^2 + y^2 = c^2$$

1. **For $c = 0$ (the plane $z = 0$):**
   $$4x^2 + y^2 = 0 \implies x = 0 \text{ and } y = 0$$
   Because both $4x^2 \ge 0$ and $y^2 \ge 0$, their sum vanishes only at the origin. Thus, the cross-section $z = 0$ is a **single point** $(0, 0, 0)$.

2. **For $c \neq 0$ (any non-zero height $z = c$):**
   Since $c^2 > 0$, we can divide both sides of $4x^2 + y^2 = c^2$ by $c^2$:
   $$\frac{4x^2}{c^2} + \frac{y^2}{c^2} = 1 \iff \frac{x^2}{(c/2)^2} + \frac{y^2}{c^2} = 1$$
   - **Shape of the slice:** For every $c \neq 0$, the cross-section in the plane $z = c$ is an **ellipse** centered on the $Oz$ axis at $(0, 0, c)$.
   - **Different scales along the axes:**
     - Along the **$Ox$ direction**, the semiaxis length is:
       $$a(c) = \frac{|c|}{2}$$
     - Along the **$Oy$ direction**, the semiaxis length is:
       $$b(c) = |c|$$
     Notice that at every height $z = c \neq 0$, we have $b(c) = 2a(c)$: the ellipse is **twice as wide along the $Oy$ axis as it is along the $Ox$ axis**, and both semiaxes grow linearly and proportionally with the distance $|c|$ from the plane $z = 0$.

---

#### Step 2.2: Vertical Coordinate Cross-Sections $x = 0$ and $y = 0$
1. **Cross-section by the plane $x = 0$ (the $yz$-plane):**
   Setting $x = 0$ in $4x^2 + y^2 = z^2$ gives:
   $$y^2 = z^2 \iff z^2 - y^2 = 0 \iff (z - y)(z + y) = 0 \iff z = \pm y \quad (\text{or } y = \pm z)$$
   In the $yz$-plane, the intersection is a **pair of straight lines** passing through the origin $(0, 0, 0)$ with slopes $\frac{dz}{dy} = \pm 1$. At height $|z| = |c|$, the $y$-spread reaches $|y| = |c|$.

2. **Cross-section by the plane $y = 0$ (the $xz$-plane):**
   Setting $y = 0$ in $4x^2 + y^2 = z^2$ gives:
   $$4x^2 = z^2 \iff z^2 - (2x)^2 = 0 \iff (z - 2x)(z + 2x) = 0 \iff z = \pm 2x \quad \left(\text{or } x = \pm \frac{z}{2}\right)$$
   In the $xz$-plane, the intersection is also a **pair of straight lines** passing through the origin $(0, 0, 0)$, but with **steeper slopes** $\frac{dz}{dx} = \pm 2$. Because of the coefficient $4 = 2^2$ multiplying $x^2$, to reach the same height $|z| = |c|$ we only need half the horizontal displacement ($|x| = \frac{|c|}{2}$) compared to the $yz$-plane ($|y| = |c|$). Thus, the V-shaped opening in the $xz$-plane is **narrower (steeper)** than the opening in the $yz$-plane.

---

#### Step 2.3: Identification of the Surface and Sketch
Combining the three families of cross-sections:
- A single apex at $(0, 0, 0)$ for $z = 0$,
- Straight-line generators through the origin in the vertical planes $x = 0$ ($z = \pm y$) and $y = 0$ ($z = \pm 2x$),
- Horizontal cross-sections for $z = c \neq 0$ that are similar ellipses $\frac{x^2}{(c/2)^2} + \frac{y^2}{c^2} = 1$ expanding linearly with $|z|$ and elongated along the $Oy$ axis ($b(c) = |c| > a(c) = |c|/2$).

Therefore, the surface $4x^2 + y^2 = z^2$ is a **double elliptic cone** with vertex (apex) at the origin $(0, 0, 0)$ and axis along $Oz$, elongated in the $y$-direction and compressed by a factor of $2$ in the $x$-direction.

```
  Elliptic Cone: 4x^2 + y^2 = z^2              Horizontal Slice z = c != 0 (in xy-plane)
                   z                                              y
                   ^                                              ^  (0, |c|)
      \   . - - - -|- - - - .   /  z = c                          |    *
       \ '   . - - + - - .   ' /   (wide along y: +-|c|,        . - - -+- - - .
         \         |         /      narrow along x: +-|c|/2)  '   |         '
           \ z=+-2x| z=+-y /                                 *----+---------*---> x
             \     |     /                                (-|c|/2,0)      (|c|/2,0)
               \   |   /                                      .   |         .
      -------------+-------------> y                            ' - - -+- - - '
               /   |   \           z = 0 (apex (0,0,0))           |    *
             /     |     \                                             (0, -|c|)
           /       |       \
         / . - - - + - - - . \                                (Elongated along Oy:
       / '   ' - - | - - '   ' \   z = -c                      b(c) = |c| = 2 a(c))
                 /
                v
               x
```

---

## 4. Verification and Consistency Checks

1. **Part 1 Verification (Checking Vertices and Center of the Shifted Ellipse):**
   - Substituting the upper co-vertex $B_2 = (1, 0)$ into $4x^2 + 9y^2 - 8x + 36y + 4 = 0$:
     $$4(1)^2 + 9(0)^2 - 8(1) + 36(0) + 4 = 4 + 0 - 8 + 0 + 4 = 0 \quad \checkmark$$
   - Substituting the right major vertex $V_2 = (4, -2)$ into $4x^2 + 9y^2 - 8x + 36y + 4 = 0$:
     $$4(4)^2 + 9(-2)^2 - 8(4) + 36(-2) + 4 = 64 + 36 - 32 - 72 + 4 = 104 - 104 = 0 \quad \checkmark$$

2. **Part 2 Verification (Consistency Between Horizontal and Vertical Cross-Sections at $z = 2$):**
   At height $z = 2$:
   - The horizontal ellipse $\frac{x^2}{1^2} + \frac{y^2}{2^2} = 1$ has $x$-vertices $(\pm 1, 0, 2)$ and $y$-vertices $(0, \pm 2, 2)$.
   - In the vertical plane $y = 0$, the lines $z = \pm 2x$ at $z = 2$ give $x = \pm 1 \implies (\pm 1, 0, 2) \checkmark$.
   - In the vertical plane $x = 0$, the lines $z = \pm y$ at $z = 2$ give $y = \pm 2 \implies (0, \pm 2, 2) \checkmark$.
   Both families of cross-sections match at every point of intersection.
