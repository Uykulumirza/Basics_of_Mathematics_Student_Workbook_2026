# Solution to Exercise 9: Ellipsoid and Its Cross-Sections

## 1. Problem Statement

Consider the second-degree surface given by the canonical equation:
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1$$

1. Give the lengths of the three semiaxes of the ellipsoid.
2. Describe the horizontal cross-section by the coordinate plane $z = 0$.
3. Explain how the horizontal cross-sections by the planes $z = c$ change for $|c| < 4$ (and what happens at the boundary values $c = \pm 4$ and beyond $|c| > 4$).

---

## 2. Theoretical Background and Concepts

### Canonical Equation of a Triaxial Ellipsoid
An **ellipsoid** centered at the origin $(0, 0, 0)$ with principal axes aligned along the coordinate axes $Ox$, $Oy$, and $Oz$ has the canonical equation:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_0^2} = 1$$
where $a, b, c_0 > 0$ are the **semiaxis lengths** along the $x$-, $y$-, and $z$-axes respectively. Because each squared term is non-negative, none of the three fractions can exceed $1$, so the entire surface is bounded within the rectangular box $[-a, a] \times [-b, b] \times [-c_0, c_0]$.

### Method of Planar Cross-Sections (Level Curves)
To study a three-dimensional surface $F(x, y, z) = 0$, we intersect it with a family of parallel planes—for example, horizontal planes $z = c$ at constant height $c \in \mathbb{R}$. Substituting $z = c$ reduces the three-variable surface equation to a two-variable equation in $(x, y)$, allowing us to reconstruct the 3D shape as a stack of 2D curves whose size varies continuously with the height $c$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Semiaxis Lengths
Comparing the given equation
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1$$
with the standard canonical form $\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_0^2} = 1$, we read the denominators beneath each squared coordinate:
- **Along the $Ox$ axis:** $a^2 = 9 \implies a = 3$ (intercepts at $(\pm 3, 0, 0)$).
- **Along the $Oy$ axis:** $b^2 = 4 \implies b = 2$ (intercepts at $(0, \pm 2, 0)$).
- **Along the $Oz$ axis:** $c_0^2 = 16 \implies c_0 = 4$ (intercepts at $(0, 0, \pm 4)$).

Since $c_0 = 4 > a = 3 > b = 2$, the ellipsoid is most elongated vertically along the $Oz$ axis and narrowest along the $Oy$ axis.

---

### Step 2: Describe the Equatorial Cross-Section $z = 0$
Setting $z = 0$ in the surface equation gives:
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{0^2}{16} = 1 \iff \frac{x^2}{9} + \frac{y^2}{4} = 1 \quad (\text{in the plane } z = 0)$$

- **Geometric description:** The cross-section in the $xy$-plane ($z = 0$) is an **ellipse** centered at $(0, 0, 0)$ with semiaxes $a = 3$ along the $Ox$ axis and $b = 2$ along the $Oy$ axis.
- **Vertices in the $z = 0$ plane:** $(\pm 3, 0, 0)$ and $(0, \pm 2, 0)$. This is the largest horizontal cross-section ("equator") of the ellipsoid.

---

### Step 3: Analyze the Family of Horizontal Cross-Sections $z = c$ for $|c| < 4$
Now intersect the ellipsoid with a horizontal plane at height $z = c$:
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{c^2}{16} = 1$$
Subtract $\frac{c^2}{16}$ from both sides to isolate the $(x, y)$-terms:
$$\frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16}$$

#### 1. Case $|c| < 4$ (Interior Horizontal Slices)
When $|c| < 4$, we have $c^2 < 16$, so the right-hand side factor $k^2 = 1 - \frac{c^2}{16}$ is strictly positive ($0 < 1 - \frac{c^2}{16} \le 1$). Dividing both sides by $1 - \frac{c^2}{16}$ puts the cross-section into standard 2D canonical form in the plane $z = c$:
$$\frac{x^2}{9\left(1 - \frac{c^2}{16}\right)} + \frac{y^2}{4\left(1 - \frac{c^2}{16}\right)} = 1$$

- **Shape and Semiaxes at height $z = c$:**
  For every $c \in (-4, 4)$, the cross-section is an **ellipse** centered at $(0, 0, c)$ whose semiaxes depend on $c$:
  $$a(c) = 3\sqrt{1 - \frac{c^2}{16}} \qquad \text{and} \qquad b(c) = 2\sqrt{1 - \frac{c^2}{16}}$$
- **How the cross-sections change with $c$:**
  - **Symmetry:** Because $c$ appears only as $c^2$, the cross-sections at heights $+c$ and $-c$ are congruent ellipses.
  - **Monotonic shrinking:** As $|c|$ increases from $0$ toward $4$, the scaling factor $\sqrt{1 - \frac{c^2}{16}}$ decreases smoothly from $1$ toward $0$. Thus, the horizontal ellipses **shrink** as we move either upward or downward away from the equatorial plane $z = 0$.
  - **Constant aspect ratio (similarity):** At every height $|c| < 4$, the ratio of the semiaxes remains constant:
    $$\frac{a(c)}{b(c)} = \frac{3\sqrt{1 - c^2/16}}{2\sqrt{1 - c^2/16}} = \frac{3}{2}$$
    Therefore, all horizontal cross-sections for $|c| < 4$ are **geometrically similar** ellipses, scaled down uniformly from the equatorial ellipse at $z = 0$.

#### 2. Boundary Case $c = \pm 4$ (Poles)
When $c = 4$ or $c = -4$, we have $1 - \frac{c^2}{16} = 0$, so the equation reduces to:
$$\frac{x^2}{9} + \frac{y^2}{4} = 0 \implies x = 0 \text{ and } y = 0$$
The ellipse degenerates to a **single point** (the north pole $(0, 0, 4)$ and south pole $(0, 0, -4)$), where the horizontal planes $z = \pm 4$ are tangent to the ellipsoid.

#### 3. Exterior Case $|c| > 4$
When $|c| > 4$, the right-hand side $1 - \frac{c^2}{16} < 0$ is negative while the left-hand side $\frac{x^2}{9} + \frac{y^2}{4} \ge 0$ is non-negative, so the intersection is **empty** ($\varnothing$).

---

## 4. Verification and Consistency Checks

1. **Explicit Sample Slice at $c = \pm 2$:**
   Substituting $z = \pm 2$ gives $1 - \frac{4}{16} = \frac{3}{4}$, so:
   $$a(\pm 2) = 3 \cdot \frac{\sqrt{3}}{2} \approx 2.60, \qquad b(\pm 2) = 2 \cdot \frac{\sqrt{3}}{2} = \sqrt{3} \approx 1.73$$
   Checking the point $(0, \sqrt{3}, 2)$ in the original equation:
   $$\frac{0^2}{9} + \frac{(\sqrt{3})^2}{4} + \frac{2^2}{16} = 0 + \frac{3}{4} + \frac{1}{4} = 1 \quad \checkmark$$

2. **Recovering $z = 0$ as a Special Case of $z = c$:**
   Setting $c = 0$ in the general formulas $a(c) = 3\sqrt{1 - c^2/16}$ and $b(c) = 2\sqrt{1 - c^2/16}$ yields $a(0) = 3$ and $b(0) = 2$, recovering the equatorial ellipse $\frac{x^2}{9} + \frac{y^2}{4} = 1$.
