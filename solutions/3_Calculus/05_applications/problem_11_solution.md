# Solution to Problem 11: Volume of a Solid of Revolution

## 1. Problem Statement
The region under the graph
$$
y=\sqrt{x},\qquad x\in[0,4],
$$
is rotated about the $x$-axis.

1. Construct the integral describing the volume using the disk method.
2. Compute the volume.
3. Explain where the factor $\pi y^2$ in the integral comes from.

---

## 2. Theoretical Background and Concepts
1. **Volume by Cross-Sections (Cavalieri's Principle / Slicing Method)**:
   If a three-dimensional solid extends along the $x$-axis from $x = a$ to $x = b$, and the plane perpendicular to the $x$-axis at coordinate $x$ intersects the solid in a cross-section of area $A(x)$, then—provided $A(x)$ is continuous—the volume $V$ of the solid is the definite integral of its cross-sectional area:
   $$
   V = \int_a^b A(x)\,dx.
   $$
2. **The Disk Method for Rotation About the $x$-Axis**:
   When the planar region bounded by $y = f(x) \ge 0$, the $x$-axis ($y = 0$), $x = a$, and $x = b$ is rotated full circle ($360^\circ$ or $2\pi$ radians) about the $x$-axis, every vertical segment of height $y = f(x)$ sweeps out a **circular disk** of radius $R(x) = y = f(x)$ and area $A(x) = \pi [R(x)]^2 = \pi y^2$. Integrating these disk areas from $a$ to $b$ yields:
   $$
   V = \int_a^b \pi [f(x)]^2\,dx = \pi \int_a^b y^2\,dx.
   $$

---

## 3. Detailed Step-by-Step Solution

### Variable Definitions and Geometric Domain
- $x \in [0, 4]$: coordinate along the axis of rotation (the $x$-axis), with domain $[0, 4]$.
- $y = f(x) = \sqrt{x} \ge 0$: height of the curve above the $x$-axis at position $x$, which becomes the radius $R(x)$ of the circular cross-section after rotation.
- $A(x) = \pi y^2$: cross-sectional area at position $x$.
- $V$: total volume of the solid of revolution (in cubic units).

Because the radius $R(x) = \sqrt{x}$ varies continuously with $x$, we use the **definite integral** to sum the volumes of thin cylindrical disks from $x = 0$ to $x = 4$.

---

### Part 1: Constructing the Volume Integral Using the Disk Method
At each $x \in [0, 4]$, the distance from the axis of rotation ($y = 0$) to the boundary curve $y = \sqrt{x}$ is the disk radius:
$$
R(x) = y = \sqrt{x}.
$$
The area of the circular cross-section at $x$ is:
$$
A(x) = \pi [R(x)]^2 = \pi \left(\sqrt{x}\right)^2 = \pi x, \qquad x \in [0, 4].
$$
Integrating the cross-sectional area from $x = 0$ to $x = 4$ gives the volume integral:
$$
V = \int_0^4 \pi y^2\,dx = \int_0^4 \pi \left(\sqrt{x}\right)^2\,dx = \pi \int_0^4 x\,dx.
$$

---

### Part 2: Computing the Volume
We evaluate the definite integral using the Fundamental Theorem of Calculus (an antiderivative of $x$ is $\frac{x^2}{2}$):
$$
\begin{aligned}
V &= \pi \int_0^4 x\,dx \\
&= \pi \left[\frac{x^2}{2}\right]_0^4 \\
&= \pi \left(\frac{4^2}{2} - \frac{0^2}{2}\right) \\
&= \pi \left(\frac{16}{2} - 0\right) = 8\pi \approx 25.1327.
\end{aligned}
$$
**Interpretation**: The volume of the paraboloid formed by rotating the region under $y = \sqrt{x}$ on $[0, 4]$ about the $x$-axis is **$V = 8\pi$** cubic units (approximately $25.13\text{ units}^3$).

---

### Part 3: Explaining Where the Factor $\pi y^2$ Comes From
The factor $\pi y^2$ arises directly from the **three-dimensional geometry of slicing the rotated solid perpendicular to its axis of rotation**:

1. **Generating a Circle by Rotation**:
   Fix a point $x \in [0, 4]$. Before rotation, the vertical slice of the planar region at coordinate $x$ is a line segment extending from $(x, 0)$ on the $x$-axis up to $(x, y)$ on the graph, so its length is $y = f(x) = \sqrt{x}$.
2. **Cross-Sectional Area Is the Area of a Circle**:
   When the region is rotated $360^\circ$ about the $x$-axis, the point $(x, 0)$ remains fixed at the center while the top endpoint $(x, y)$ traces a circle of **radius $R = y$** in the plane perpendicular to the $x$-axis. Since the area of a circle of radius $R$ is $\pi R^2$, the cross-sectional area of the solid at position $x$ is:
   $$
   A(x) = \pi R^2 = \pi y^2.
   $$
3. **Volume of an Infinitesimal Cylindrical Disk**:
   If we slice the solid by two parallel planes at $x$ and $x + dx$, we obtain a thin cylindrical disk (like a coin) of base area $A(x) = \pi y^2$ and thickness (height) $dx$. The elementary volume of this thin cylinder is:
   $$
   dV = \text{Base Area} \times \text{Thickness} = \left(\pi y^2\right) dx.
   $$
   Summing (integrating) these elementary disk volumes $dV = \pi y^2\,dx$ from $x = 0$ to $x = 4$ yields $V = \int_0^4 \pi y^2\,dx$.

```
                  y ^
                    |              . - ~ ~ - .
                    |          . '     |       ' .
                    |        /         | R = y     \
                    |       |          | = sqrt(x)  |
         (0,0)      |       |          +------------|----> x (axis of rotation)
          *---------+-------|          |<--- dx --->|
                     \       \                     /
                       ' .     ' .             . '
                           ' - . _ ' - ~ ~ - '
                                 Disk at position x:
                                 Radius = y, Area = pi*y^2, Volume = pi*y^2 dx
```

---

## 4. Verification and Consistency Checks

1. **Comparison with Inscribed Cone and Circumscribed Cylinder (Archimedes' Property)**:
   At $x = 4$, the base radius of the paraboloid is $R_{\max} = \sqrt{4} = 2$, and the length (height along the $x$-axis) is $H = 4$:
   - The **circumscribed cylinder** of radius $R_{\max} = 2$ and height $H = 4$ has volume:
     $$
     V_{\text{cylinder}} = \pi R_{\max}^2 H = \pi (2)^2 (4) = 16\pi.
     $$
   - The **inscribed cone** with apex at $(0, 0)$, base radius $2$, and height $4$ has volume:
     $$
     V_{\text{cone}} = \frac{1}{3}\pi R_{\max}^2 H = \frac{16\pi}{3} \approx 5.33\pi.
     $$
   Our paraboloid volume $V = 8\pi$ satisfies $V_{\text{cone}} = \frac{16}{3}\pi < 8\pi < 16\pi = V_{\text{cylinder}}$, and exemplifies Archimedes' theorem that the volume of a paraboloid segment is exactly **half** the volume of its circumscribed cylinder ($\frac{1}{2} \times 16\pi = 8\pi$).

2. **Alternative Verification by the Cylindrical Shell Method (Integrating Along $y$)**:
   As $x$ goes from $0$ to $4$, $y = \sqrt{x}$ goes from $0$ to $2$, and a horizontal strip at height $y$ extends from $x = y^2$ to $x = 4$ (length $4 - y^2$). Rotating about the $x$-axis gives cylindrical shells of radius $y$ and length $4 - y^2$:
   $$
   V = \int_0^2 2\pi y (4 - y^2)\,dy = 2\pi \left[2y^2 - \frac{y^4}{4}\right]_0^2 = 2\pi (8 - 4) = 8\pi,
   $$
   which matches the disk method result identically.
