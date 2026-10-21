# Solution to Exercise 11: Two Similar Surfaces

## 1. Problem Statement

Compare the two second-degree surfaces:
$$x^2 + y^2 - z^2 = 1 \qquad \text{and} \qquad x^2 + y^2 - z^2 = -1$$
For several explicit values of $z = c$, check whether the horizontal cross-section exists and determine its radius. Based on this analysis, describe qualitatively the geometric difference between the two surfaces and make sketches.

---

## 2. Theoretical Background and Concepts

### Hyperboloids of Revolution
Both equations have two positive quadratic terms ($+x^2 + y^2$) and one negative quadratic term ($-z^2$), differing only in the sign of the constant on the right-hand side ($\pm 1$). In cylindrical coordinates $(r, \theta, z)$ where $r^2 = x^2 + y^2$, both surfaces depend only on $r^2$ and $z^2$, meaning both are **surfaces of revolution** around the $Oz$ axis, and every non-empty horizontal cross-section $z = c$ is a circle (or a degenerate point).

However, changing the right-hand side from $+1$ to $-1$ fundamentally alters the connectivity of the surface:
- **Hyperboloid of One Sheet ($x^2 + y^2 - z^2 = 1$):** Moving $-z^2$ to the right gives $x^2 + y^2 = 1 + z^2 \ge 1 > 0$, which is strictly positive for **every** $z \in \mathbb{R}$. The surface is a single connected tube (cooling-tower shape) with a narrowest circular waist at $z = 0$.
- **Hyperboloid of Two Sheets ($x^2 + y^2 - z^2 = -1$, or $z^2 - x^2 - y^2 = 1$):** Moving $-z^2$ to the right gives $x^2 + y^2 = z^2 - 1$, which is non-negative only when $|z| \ge 1$. For $|z| < 1$ there are no real points, splitting the surface into two separate bowls ("sheets"), one for $z \ge 1$ and one for $z \le -1$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: General Formula for Horizontal Cross-Sections $z = c$

1. **Surface 1 ($x^2 + y^2 - z^2 = 1$):**
   Substituting $z = c$ and isolating $x^2 + y^2$ gives:
   $$x^2 + y^2 = 1 + c^2$$
   Since $1 + c^2 \ge 1 > 0$ for all real $c \in \mathbb{R}$, the cross-section **always exists** and is a **circle** centered at $(0, 0, c)$ with radius:
   $$r_1(c) = \sqrt{1 + c^2}$$

2. **Surface 2 ($x^2 + y^2 - z^2 = -1$):**
   Substituting $z = c$ and isolating $x^2 + y^2$ gives:
   $$x^2 + y^2 = c^2 - 1$$
   Because $x^2 + y^2 \ge 0$, real solutions exist if and only if $c^2 - 1 \ge 0 \iff |c| \ge 1$:
   - For $|c| < 1$: $c^2 - 1 < 0$, so **no cross-section exists** (empty set $\varnothing$).
   - For $c = \pm 1$: $x^2 + y^2 = 0$, giving a **single point** $(0, 0, \pm 1)$ (degenerate circle of radius $r_2(\pm 1) = 0$).
   - For $|c| > 1$: $c^2 - 1 > 0$, giving a **circle** centered at $(0, 0, c)$ with radius:
     $$r_2(c) = \sqrt{c^2 - 1}$$

---

### Step 2: Explicit Evaluation at Several Heights $z = c$

Let us evaluate both cross-sections at $c = 0, \pm\frac{1}{2}, \pm 1, \pm 2, \pm 3$:

| Plane $z = c$ | Surface 1: $x^2 + y^2 = 1 + c^2$ | Radius $r_1(c) = \sqrt{1 + c^2}$ | Surface 2: $x^2 + y^2 = c^2 - 1$ | Radius $r_2(c) = \sqrt{c^2 - 1}$ |
| :--- | :--- | :--- | :--- | :--- |
| $z = 0$ | $x^2 + y^2 = 1$ (circle, waist) | $r_1(0) = 1$ | $x^2 + y^2 = -1$ (**does not exist**, $\varnothing$) | None |
| $z = \pm \frac{1}{2}$ | $x^2 + y^2 = \frac{5}{4}$ (circle) | $r_1(\pm\frac{1}{2}) = \frac{\sqrt{5}}{2} \approx 1.12$ | $x^2 + y^2 = -\frac{3}{4}$ (**does not exist**, $\varnothing$) | None |
| $z = \pm 1$ | $x^2 + y^2 = 2$ (circle) | $r_1(\pm 1) = \sqrt{2} \approx 1.41$ | $x^2 + y^2 = 0$ (**single point** $(0,0,\pm 1)$) | $r_2(\pm 1) = 0$ |
| $z = \pm 2$ | $x^2 + y^2 = 5$ (circle) | $r_1(\pm 2) = \sqrt{5} \approx 2.24$ | $x^2 + y^2 = 3$ (circle) | $r_2(\pm 2) = \sqrt{3} \approx 1.73$ |
| $z = \pm 3$ | $x^2 + y^2 = 10$ (circle) | $r_1(\pm 3) = \sqrt{10} \approx 3.16$ | $x^2 + y^2 = 8$ (circle) | $r_2(\pm 3) = \sqrt{8} = 2\sqrt{2} \approx 2.83$ |

---

### Step 3: Qualitative Difference Between the Two Surfaces

1. **Connectivity (One Sheet vs. Two Sheets):**
   - **Surface 1 ($x^2 + y^2 - z^2 = 1$, One-Sheeted Hyperboloid):** Because horizontal circles exist for every height $z \in (-\infty, \infty)$, the surface forms **one connected piece** (a single sheet). At $z = 0$, the radius attains its positive minimum $r_1(0) = 1$ (the "neck" or "waist" circle), and as $|z|$ increases either upward or downward, the circular cross-sections flare outward with radius $\sqrt{1 + z^2}$.
   - **Surface 2 ($x^2 + y^2 - z^2 = -1$, Two-Sheeted Hyperboloid):** Because no points exist in the horizontal slab $-1 < z < 1$, the surface is split by an empty gap of height $2$ into **two disconnected components (two sheets)**: an upper cup for $z \ge 1$ with vertex at $(0, 0, 1)$, and a lower inverted cup for $z \le -1$ with vertex at $(0, 0, -1)$.
2. **Vertical Profile Curves ($x = 0$ or $y = 0$):**
   - Setting $y = 0$ in Surface 1 gives the hyperbola $x^2 - z^2 = 1$ opening horizontally along $\pm x$. Revolving this hyperbola around the $Oz$ axis sweeps out a connected hourglass/cooling-tower tube.
   - Setting $y = 0$ in Surface 2 gives the hyperbola $z^2 - x^2 = 1$ opening vertically along $\pm z$. Revolving its two separate top and bottom branches around the $Oz$ axis produces two separate bowls.

---

### Step 4: Qualitative Sketches

```
  SURFACE 1: One-Sheeted Hyperboloid                   SURFACE 2: Two-Sheeted Hyperboloid
         x^2 + y^2 - z^2 = 1                                  x^2 + y^2 - z^2 = -1

                  z                                                    z
                  ^                                                    ^
        \   . - - | - - .   /  z = 2 (r = sqrt(5))           \   . - - | - - .   /  z = 2 (r = sqrt(3))
         \ ' . - -+- - . ' /                                  \ ' . - -+- - . ' /
          *       |       *    z = 1 (r = sqrt(2))              *      |      *
           *  . - + - .  *                                        ' .  +  . '       z = 1 (vertex (0,0,1))
      -----+-(    |    )-+-----> y                           ----------+----------> y (EMPTY GAP for |z| < 1)
           *  ' - + - '  *     z = 0 (waist r = 1)                . '  +  ' .       z = -1 (vertex (0,0,-1))
          *       |       *    z = -1 (r = sqrt(2))             *      |      *
         / . - - -+- - - . \                                  / . - - -+- - - . \
        /   ' - - | - - '   \  z = -2 (r = sqrt(5))          /   ' - - | - - '   \  z = -2 (r = sqrt(3))
                /                                                    /
               v                                                    v
              x                                                    x
```

---

## 4. Verification and Consistency Checks

1. **Asymptotic Cone Comparison for Large $|z|$:**
   For large $|c|$, both radii approach $|c|$ from opposite sides of the cone $x^2 + y^2 = z^2$ (whose radius is $r_{\text{cone}}(c) = |c|$):
   $$r_2(c) = \sqrt{c^2 - 1} < |c| < \sqrt{c^2 + 1} = r_1(c) \quad \text{for all } |c| \ge 1$$
   Moreover, $r_1(c)^2 - r_2(c)^2 = (c^2 + 1) - (c^2 - 1) = 2$, which implies $r_1(c) - r_2(c) = \frac{2}{\sqrt{c^2+1}+\sqrt{c^2-1}} \to 0$ as $|c| \to \infty$. Geometrically, both hyperboloids approach the same asymptotic cone $x^2 + y^2 = z^2$ at infinity: the one-sheeted hyperboloid wraps around the **outside** of the cone, while the two sheets of the two-sheeted hyperboloid sit **inside** the upper and lower nappes of the cone.
