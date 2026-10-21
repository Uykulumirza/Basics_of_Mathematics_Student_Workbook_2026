# Solution to Exercise 14: Cone and Cylinder

## 1. Problem Statement

Compare the two second-degree surfaces:
$$x^2 + y^2 = z^2 \qquad \text{and} \qquad x^2 + y^2 = 4$$
For each surface, describe the horizontal cross-sections $z = c$ and the vertical coordinate cross-sections $x = 0$ and $y = 0$, make a geometric sketch, and explain why the radius of the horizontal cross-section depends on $z$ in the first case but remains constant in the second.

---

## 2. Theoretical Background and Concepts

### Cones vs. Cylinders in $\mathbb{R}^3$
1. **Right Circular Cone ($x^2 + y^2 = z^2$):**
   A second-degree homogeneous equation in $(x, y, z)$ where $x^2 + y^2$ is equated to $z^2$ represents a double circular cone with vertex (apex) at the origin $(0, 0, 0)$ and axis along $Oz$. Every point $(x, y, z)$ on the surface satisfies $\sqrt{x^2 + y^2} = |z|$, meaning the radial distance from the $Oz$ axis equals the vertical distance from the $xy$-plane.
2. **Right Circular Cylinder ($x^2 + y^2 = R^2$):**
   When an equation in three-dimensional space $\mathbb{R}^3$ involves only two of the three coordinates—such as $F(x, y) = 0$, with $z$ completely absent—the missing variable $z$ is a **free variable**. If $(x_0, y_0)$ satisfies $F(x_0, y_0) = 0$ in the $xy$-plane, then $(x_0, y_0, z)$ satisfies the equation in $\mathbb{R}^3$ for **every** $z \in \mathbb{R}$. Geometrically, translating the planar curve $x^2 + y^2 = R^2$ vertically along lines parallel to the $Oz$ axis generates an infinite circular cylinder.

---

## 3. Detailed Step-by-Step Solution

### Part A: Cross-Sections of the Circular Cone $x^2 + y^2 = z^2$

#### 1. Horizontal Cross-Sections ($z = c$, $c \in \mathbb{R}$)
Substituting $z = c$ gives $x^2 + y^2 = c^2$:
- **For $c = 0$:** $x^2 + y^2 = 0 \implies (x, y) = (0, 0)$. The cross-section is a **single point**, the apex $(0, 0, 0)$ where the upper and lower nappes meet.
- **For $c \neq 0$:** $x^2 + y^2 = |c|^2$ is a **circle** centered at $(0, 0, c)$ with radius:
  $$r_{\text{cone}}(c) = |c|$$
  As $|c|$ increases, the circle's radius grows linearly with the height $|c|$.

#### 2. Vertical Cross-Sections ($x = 0$ and $y = 0$)
- **Plane $x = 0$ (the $yz$-plane):**
  Substituting $x = 0$ gives:
  $$y^2 = z^2 \iff z^2 - y^2 = 0 \iff (z - y)(z + y) = 0 \iff z = y \text{ or } z = -y$$
  This is a **pair of intersecting straight lines** ($z = \pm y$) in the $yz$-plane crossing at the origin $(0, 0, 0)$ at $45^\circ$ to the axes.
- **Plane $y = 0$ (the $xz$-plane):**
  Substituting $y = 0$ gives:
  $$x^2 = z^2 \iff z = x \text{ or } z = -x$$
  This is an identical **pair of intersecting straight lines** ($z = \pm x$) in the $xz$-plane crossing at $(0, 0, 0)$.

---

### Part B: Cross-Sections of the Circular Cylinder $x^2 + y^2 = 4$

#### 1. Horizontal Cross-Sections ($z = c$, $c \in \mathbb{R}$)
Substituting $z = c$ into $x^2 + y^2 = 4$ leaves the equation unchanged because $z$ does not appear in it:
$$x^2 + y^2 = 4 = 2^2 \quad (\text{in the plane } z = c)$$
- For **every** $c \in \mathbb{R}$ (including $c = 0$), the cross-section is a **circle** centered at $(0, 0, c)$ with constant radius:
  $$r_{\text{cyl}}(c) = 2$$

#### 2. Vertical Cross-Sections ($x = 0$ and $y = 0$)
- **Plane $x = 0$ (the $yz$-plane):**
  Substituting $x = 0$ gives:
  $$y^2 = 4 \iff y = 2 \text{ or } y = -2 \quad (z \in \mathbb{R} \text{ arbitrary})$$
  In the $yz$-plane, this is a **pair of parallel vertical lines** ($x = 0, y = 2$ and $x = 0, y = -2$) running parallel to the $Oz$ axis at distance $2$ from it.
- **Plane $y = 0$ (the $xz$-plane):**
  Substituting $y = 0$ gives:
  $$x^2 = 4 \iff x = 2 \text{ or } x = -2 \quad (z \in \mathbb{R} \text{ arbitrary})$$
  In the $xz$-plane, this is a **pair of parallel vertical lines** ($x = \pm 2, y = 0$) running parallel to the $Oz$ axis at distance $2$ from it.

---

### Part C: Why the Radius Depends on $z$ for the Cone vs. Constant for the Cylinder

The algebraic reason is immediate from comparing the right-hand sides of $x^2 + y^2 = z^2$ and $x^2 + y^2 = 4$:
- In $x^2 + y^2 = r^2$, the quantity $\sqrt{x^2 + y^2}$ is the horizontal radial distance $r$ of a point $(x, y, z)$ from the vertical axis $Oz$.
- **In the first equation ($x^2 + y^2 = z^2$):** The variable $z$ **explicitly appears** on the right-hand side as $z^2$. Fixing the height at $z = c$ forces the squared radius $x^2 + y^2$ to equal $c^2$, coupling the horizontal spread to the vertical coordinate via $r = |z|$.
- **In the second equation ($x^2 + y^2 = 4$):** The variable $z$ **does not appear in the equation at all** ($z$ is an unconstrained free variable, equivalent to $x^2 + y^2 + 0\cdot z^2 = 4$). Because the equation places no restriction on $z$ and no coupling between $(x, y)$ and $z$, fixing $z = c$ always leaves the exact same circle equation $x^2 + y^2 = 4$ with constant radius $r = 2$ at every height $c \in \mathbb{R}$.

---

### Part D: Qualitative Sketches

```
  SURFACE 1: Circular Cone (x^2 + y^2 = z^2)           SURFACE 2: Circular Cylinder (x^2 + y^2 = 4)

                  z                                                    z
                  ^                                                    ^
        \   . - - | - - .   /  z = c (r = |c|)               |   . - - | - - .   |  z = c (r = 2)
         \ ' . - -+- - . ' /                                 |  ' . - -+- - . '  |
           \      |      /     lines z = +-y                 |  |      |      |  |  parallel lines
             \    |    /       and z = +-x                   |  |      |      |  |  y = +-2, x = +-2
               \  |  /                                       |  | . - -|- - . |  |
      ------------+------------> y                     ------+--+-'----+----'-+--+-----> y
               /  |  \         z = 0 (apex (0,0,0))          |  |  ' - + - '  |  |  z = 0 (r = 2)
             /    |    \                                     |  |      |      |  |
           /      |      \                                   |  | . - -|- - . |  |
         / . - - -+- - - . \                                 |  ' . - -+- - . '  |
        /   ' - - | - - '   \  z = -c (r = |c|)              |   ' - - | - - '   |  z = -c (r = 2)
                /                                                    /
               v                                                    v
              x                                                    x
```

---

## 4. Verification and Consistency Checks

1. **Intersection of the Cone and the Cylinder:**
   Where do the cone $x^2 + y^2 = z^2$ and the cylinder $x^2 + y^2 = 4$ intersect? Substituting $x^2 + y^2 = 4$ into $x^2 + y^2 = z^2$ yields $z^2 = 4 \implies z = \pm 2$. Indeed, at heights $z = 2$ and $z = -2$, the cone's radius $r_{\text{cone}}(\pm 2) = |\pm 2| = 2$ equals the cylinder's constant radius $r_{\text{cyl}} = 2$, so the two surfaces intersect along the two circles $x^2 + y^2 = 4$ at $z = \pm 2$.
2. **Sample Points Check:**
   - On the cone: $(0, 0, 0)$ gives $0 + 0 = 0 \checkmark$; $(0, 3, -3)$ gives $0 + 9 = 9 \checkmark$.
   - On the cylinder: $(2, 0, 0)$, $(2, 0, 5)$, and $(2, 0, -100)$ all give $2^2 + 0^2 = 4 \checkmark$ regardless of $z$.
