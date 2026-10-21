# Solution to Exercise 12: Recognizing a Surface from Cross-Sections

## 1. Problem Statement

A certain surface in $\mathbb{R}^3$ has the following three geometric properties:
- the cross-section by the plane $z = 0$ is a single point,
- for $z > 0$, the horizontal cross-sections $z = \text{const}$ are circles with increasing radius,
- vertical cross-sections by planes passing through the $Oz$ axis are parabolas.

Propose a simple equation for such a surface and justify your choice by verifying each of the three properties.

---

## 2. Theoretical Background and Concepts

### Reconstructing a Surface Equation from Planar Cross-Sections
Just as a surface equation $F(x, y, z) = 0$ determines all of its 2D planar cross-sections, a sufficiently rich family of cross-sections uniquely determines the algebraic structure of the surface:
1. **Rotational Symmetry about $Oz$:** If every horizontal cross-section $z = c$ is a circle centered on the $Oz$ axis, the coordinates $x$ and $y$ can enter the equation only through the rotationally invariant combination:
   $$r^2 = x^2 + y^2$$
   where $r = \sqrt{x^2 + y^2}$ is the radial distance from the $Oz$ axis.
2. **Profile Curve in Vertical Planes through $Oz$:** Any vertical plane containing the $Oz$ axis is parameterized by a fixed polar angle $\theta \in [0, \pi)$ via:
   $$x = t\cos\theta, \qquad y = t\sin\theta, \qquad z = z \qquad (t \in \mathbb{R})$$
   where $|t| = \sqrt{x^2 + y^2} = r$ measures the signed horizontal distance along the plane from the $Oz$ axis. If the intersection of the surface with such a vertical plane is a parabola with vertex at the origin opening upward along $+Oz$, then in the $(t, z)$-plane of that slice the relation between height $z$ and horizontal coordinate $t$ must be quadratic:
   $$z = a t^2 \quad (a > 0)$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Propose the Surface Equation
Substituting $t^2 = x^2 + y^2$ into the parabolic profile relation $z = a t^2$ with the simplest positive constant $a = 1$ gives the canonical equation of a **circular paraboloid**:
$$z = x^2 + y^2$$
*(More generally, any equation of the form $z = a(x^2 + y^2)$ with a constant $a > 0$ satisfies all three conditions; choosing $a = 1$ gives the simplest form.)*

---

### Step 2: Justify How Each Geometric Property Leads to $z = x^2 + y^2$

#### Property 1: The cross-section $z = 0$ is a single point
Setting $z = 0$ in the proposed equation $z = x^2 + y^2$ gives:
$$x^2 + y^2 = 0$$
Because $x^2 \ge 0$ and $y^2 \ge 0$ for all real numbers $x, y \in \mathbb{R}$, their sum equals zero if and only if both terms vanish simultaneously:
$$x^2 = 0 \quad \text{and} \quad y^2 = 0 \iff x = 0 \quad \text{and} \quad y = 0$$
Thus, the intersection of the surface with the plane $z = 0$ consists solely of the **single point** $(0, 0, 0)$ (the vertex of the paraboloid).

---

#### Property 2: For $z > 0$, the cross-sections $z = \text{const}$ are circles with increasing radius
Fix a positive constant height $z = c > 0$. Substituting $z = c$ into $z = x^2 + y^2$ yields:
$$x^2 + y^2 = c \iff x^2 + y^2 = \left(\sqrt{c}\right)^2 \quad (\text{in the plane } z = c)$$
- Since $c > 0$, this is the canonical equation of a **circle** centered at $(0, 0, c)$ on the $Oz$ axis with radius:
  $$R(c) = \sqrt{c}$$
- Because the square-root function $R(c) = \sqrt{c}$ is strictly increasing for $c > 0$ (if $0 < c_1 < c_2$, then $\sqrt{c_1} < \sqrt{c_2}$, with derivative $R'(c) = \frac{1}{2\sqrt{c}} > 0$), the circles have **strictly increasing radius** as the height $z = c$ increases.

---

#### Property 3: Vertical cross-sections through the $Oz$ axis are parabolas
Any vertical plane $\Pi_\theta$ containing the $Oz$ axis makes some angle $\theta$ with the positive $Ox$ axis and is described parametrically using the horizontal coordinate $t \in \mathbb{R}$ within that plane and the vertical coordinate $z \in \mathbb{R}$:
$$x = t\cos\theta, \qquad y = t\sin\theta$$
Substituting this parameterization into $z = x^2 + y^2$ gives:
$$z = (t\cos\theta)^2 + (t\sin\theta)^2 = t^2(\cos^2\theta + \sin^2\theta) = t^2$$
In the two-dimensional coordinate system $(t, z)$ of the vertical plane $\Pi_\theta$, the intersection curve is given by:
$$z = t^2$$
which is a **parabola** for every angle $\theta$ (in particular, for the coordinate planes $y = 0 \implies z = x^2$ and $x = 0 \implies z = y^2$).

---

## 4. Verification and Consistency Checks

1. **Why a Cone $z = \sqrt{x^2 + y^2}$ (or $z^2 = x^2 + y^2$) Fails Property 3:**
   It is instructive to compare $z = x^2 + y^2$ with the upper half-cone $z = \sqrt{x^2 + y^2}$:
   - The upper half-cone *also* has a single point $(0, 0, 0)$ at $z = 0$ (Property 1) and circular cross-sections $x^2 + y^2 = c^2$ of increasing radius $R(c) = c$ for $z = c > 0$ (Property 2).
   - However, slicing $z = \sqrt{x^2 + y^2}$ with a vertical plane $x = t\cos\theta, y = t\sin\theta$ yields $z = |t|$, which is a V-shaped pair of half-lines rather than a smooth parabola.
   - To make the vertical cross-sections **parabolas** ($z = t^2$), $z$ must be proportional to $t^2 = x^2 + y^2$ (first power of $z$), which uniquely selects the paraboloid $z = a(x^2 + y^2)$ ($a > 0$) over the cone.

2. **Explicit Numerical Check of Increasing Radii:**
   For $z = x^2 + y^2$:
   - At $z = 1$: circle $x^2 + y^2 = 1$ of radius $R(1) = 1$.
   - At $z = 4$: circle $x^2 + y^2 = 4$ of radius $R(4) = 2$.
   - At $z = 9$: circle $x^2 + y^2 = 9$ of radius $R(9) = 3$.
    clearly satisfy $0 < R(1) < R(4) < R(9)$, confirming all required geometric properties.
