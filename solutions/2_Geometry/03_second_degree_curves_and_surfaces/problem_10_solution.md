# Solution to Exercise 10: Paraboloids

## 1. Problem Statement

Compare the two second-degree surfaces:
$$z = x^2 + y^2 \qquad \text{and} \qquad z = x^2 - y^2$$
For each surface, describe the vertical cross-sections $x = 0$ and $y = 0$, as well as the horizontal cross-sections $z = c$ (for $c < 0$, $c = 0$, and $c > 0$). Then make a qualitative sketch of both surfaces.

---

## 2. Theoretical Background and Concepts

### Elliptic vs. Hyperbolic Paraboloids
A **paraboloid** is a quadric surface in which one coordinate ($z$) appears to the **first power** while the other two coordinates ($x$ and $y$) appear to the **second power**:
$$z = \frac{x^2}{a^2} \pm \frac{y^2}{b^2}$$
The relative sign between the two quadratic terms determines the global geometry of the surface:
1. **Elliptic Paraboloid ($+$ sign, e.g., $z = x^2 + y^2$):** Both quadratic terms have the same sign. Every vertical coordinate plane slices the surface in a parabola opening in the **same** direction (upward), and horizontal slices above the vertex are ellipses (or circles when $a = b$). The surface is bowl-shaped and has a global minimum at its vertex.
2. **Hyperbolic Paraboloid ($-$ sign, e.g., $z = x^2 - y^2$):** The quadratic terms have opposite signs. The vertical coordinate planes slice the surface in parabolas opening in **opposite** directions (one upward, one downward), while horizontal slices are hyperbolas. The surface is saddle-shaped, with a saddle point at the origin.

---

## 3. Detailed Step-by-Step Solution

### Part A: Surface 1 — Circular (Elliptic) Paraboloid $z = x^2 + y^2$

#### 1. Vertical Cross-Sections ($x = 0$ and $y = 0$)
- **Plane $x = 0$ (the $yz$-plane):**
  Substituting $x = 0$ gives:
  $$z = y^2 \quad (x = 0)$$
  This is a **parabola** in the $yz$-plane with vertex at $(0, 0, 0)$, symmetric about the $Oz$ axis, opening **upward** toward $+z$.
- **Plane $y = 0$ (the $xz$-plane):**
  Substituting $y = 0$ gives:
  $$z = x^2 \quad (y = 0)$$
  This is an identical **parabola** in the $xz$-plane with vertex at $(0, 0, 0)$, also opening **upward** toward $+z$.

#### 2. Horizontal Cross-Sections ($z = c$)
Substituting $z = c$ yields the planar equation $x^2 + y^2 = c$:
- **For $c < 0$:** Since $x^2 + y^2 \ge 0$ for all real $(x, y)$, the equation $x^2 + y^2 = c < 0$ has **no real solutions** (empty set $\varnothing$). The surface does not extend below the $xy$-plane.
- **For $c = 0$:** $x^2 + y^2 = 0 \implies (x, y) = (0, 0)$. The cross-section is a **single point**, the vertex $(0, 0, 0)$, where the plane $z = 0$ is tangent to the bowl.
- **For $c > 0$:** $x^2 + y^2 = (\sqrt{c})^2$ is a **circle** centered on the $Oz$ axis at $(0, 0, c)$ with radius $r(c) = \sqrt{c}$, which grows as $c$ increases.

---

### Part B: Surface 2 — Hyperbolic Paraboloid (Saddle) $z = x^2 - y^2$

#### 1. Vertical Cross-Sections ($x = 0$ and $y = 0$)
- **Plane $x = 0$ (the $yz$-plane):**
  Substituting $x = 0$ gives:
  $$z = -y^2 \quad (x = 0)$$
  This is a **parabola** in the $yz$-plane with vertex at $(0, 0, 0)$, opening **downward** toward $-z$ (it has a local maximum at the origin along the $Oy$ direction).
- **Plane $y = 0$ (the $xz$-plane):**
  Substituting $y = 0$ gives:
  $$z = x^2 \quad (y = 0)$$
  This is a **parabola** in the $xz$-plane with vertex at $(0, 0, 0)$, opening **upward** toward $+z$ (it has a local minimum at the origin along the $Ox$ direction).

#### 2. Horizontal Cross-Sections ($z = c$)
Substituting $z = c$ yields the equation $x^2 - y^2 = c$:
- **For $c > 0$:** Dividing by $c$ gives $\frac{x^2}{c} - \frac{y^2}{c} = 1$, which is a **rectangular hyperbola** in the plane $z = c$ whose branches open along the **$x$-axis** (vertices at $(\pm\sqrt{c}, 0, c)$).
- **For $c = 0$:** $x^2 - y^2 = 0 \iff (x - y)(x + y) = 0 \iff y = x \text{ or } y = -x$. The cross-section in the plane $z = 0$ is a **pair of intersecting lines** passing through the origin $(0, 0, 0)$, which also serve as the asymptotes when the hyperbolas for $c \neq 0$ are projected onto the $xy$-plane.
- **For $c < 0$:** Writing $c = -|c|$ and dividing by $-|c|$ gives $\frac{y^2}{|c|} - \frac{x^2}{|c|} = 1$, which is a **conjugate rectangular hyperbola** in the plane $z = c$ whose branches open along the **$y$-axis** (vertices at $(0, \pm\sqrt{|c|}, c)$).

---

### Part C: Summary Comparison and Qualitative Sketches

| Feature | $z = x^2 + y^2$ (Circular Paraboloid) | $z = x^2 - y^2$ (Hyperbolic Paraboloid) |
| :--- | :--- | :--- |
| **Cross-section $x = 0$** | Upward parabola $z = y^2$ | Downward parabola $z = -y^2$ |
| **Cross-section $y = 0$** | Upward parabola $z = x^2$ | Upward parabola $z = x^2$ |
| **Cross-section $z = c > 0$** | Circle $x^2 + y^2 = c$ (radius $\sqrt{c}$) | Hyperbola $x^2 - y^2 = c$ (along $Ox$) |
| **Cross-section $z = 0$** | Single point $(0, 0, 0)$ | Pair of intersecting lines $y = \pm x$ |
| **Cross-section $z = c < 0$** | Empty set $\varnothing$ | Hyperbola $y^2 - x^2 = |c|$ (along $Oy$) |
| **Global shape** | Upward-opening circular bowl ($z \ge 0$) | Saddle surface extending to all $z \in \mathbb{R}$ |

```
  SURFACE 1: Circular Paraboloid (z = x^2 + y^2)         Level Curves (z = c in xy-plane)
                     z                                                   y
                     ^                                                   ^
            . - - - -|- - - - .   <-- circle z = c > 0                   |
          '    . - - + - - .    '                                    . - * - .   (c > 0)
         *           |           *                                 '   . + .   '
          *   z=x^2  |  z=y^2   *                                *   (   |   )   *
            *        |        *                              ----*---(---*---)---*----> x
               '  .  |  .  '                                     *   ( (0,0) )   *
      ---------------+---------------> y                           '   ' + '   '
                    / (0,0,0) vertex                                 ' - * - '
                   v                                                     |
                  x                                           c=0: origin, c>0: concentric circles

  SURFACE 2: Hyperbolic Paraboloid (z = x^2 - y^2)       Level Curves (z = c in xy-plane)
                     z                                                   y
                     ^                                                   ^
         *           |           *  (rises along x: z = x^2)        \    |    /
          *          |          *                                    \ . * . /   (c < 0)
            ' .      |      . '                                       \  |  /
                ' .  |  . '   Saddle point (0,0,0)                 \   \ | /   /
      -------.-------+-------.-------> y                     -------*----X----*-------> x
           '    .    |    .    '                              (c>0) /   / | \   \  (c>0)
         *       '   |   '       *  (drops along y: z = -y^2)          /  |  \
                   v                                                  / ' * ' \  (c < 0)
                  x                                                  /    |    \
                                                              lines y = +-x meet at (0,0)
```

---

## 4. Verification and Consistency Checks

1. **Test Points at $(x, y) = (1, 1)$ and $(1, 0)$:**
   - For $z = x^2 + y^2$: at $(1, 0)$, $z = 1$; at $(0, 1)$, $z = 1$; at $(1, 1)$, $z = 2 > 0$. All points outside the origin have $z > 0$, confirming the bowl shape.
   - For $z = x^2 - y^2$: at $(1, 0)$, $z = +1 > 0$ (upward along $Ox$); at $(0, 1)$, $z = -1 < 0$ (downward along $Oy$); at $(1, 1)$, $z = 1^2 - 1^2 = 0$, confirming that the line $y = x$ lies entirely in the horizontal plane $z = 0$ on the saddle.
2. **Rotational Invariance Check:**
   Writing $x^2 + y^2 = r^2$ in polar coordinates $(r, \theta)$ shows that $z = r^2$ is independent of the angle $\theta$, confirming that $z = x^2 + y^2$ is a surface of revolution obtained by revolving the parabola $z = x^2$ around the $Oz$ axis.
