# Solution to Problem 9: Minimizing the Material Used for a Can

## 1. Problem Statement
A closed cylinder has fixed volume $V$.

1. Write the volume constraint.
2. Eliminate one of the variables.
3. Express the surface area as a function of the radius $r$.
4. Find the relation between the height $h$ and the radius $r$ for which the material usage is minimal.

Interpret the obtained relation geometrically.

---

## 2. Theoretical Background and Concepts
In constrained three-dimensional optimization problems:
1. **Geometry of a Right Circular Cylinder**:
   For a closed cylinder of base radius $r > 0$ and height $h > 0$:
   - **Volume**: $V = \text{Base Area} \times \text{Height} = \pi r^2 h$.
   - **Total Surface Area** (representing sheet-metal material usage for a **closed** can): the sum of the areas of the two circular lids (top and bottom, each of area $\pi r^2$) and the lateral curved wall (which unrolls into a rectangle of circumference $2\pi r$ and height $h$):
     $$
     S(r, h) = 2\pi r^2 + 2\pi r h.
     $$
2. **Reduction to a Single Variable via the Constraint**:
   Because the volume $V > 0$ is a fixed positive constant, the constraint equation $\pi r^2 h = V$ determines $h$ uniquely as a function of $r$, reducing $S(r, h)$ to a single-variable objective function $S(r)$ on the open domain $r \in (0, \infty)$.
3. **Global Minimum Verification**:
   If $S(r)$ is twice differentiable on $(0, \infty)$ with a unique critical point $r^*$ satisfying $S'(r^*) = 0$, and $S''(r) > 0$ for all $r > 0$ (strict convexity), then $r^*$ is the **unique global minimum** on $(0, \infty)$.

---

## 3. Detailed Step-by-Step Solution

### Variable Definitions and Geometric Domain
- $r > 0$: radius of the circular base of the cylinder (in length units, e.g., $\text{cm}$).
- $h > 0$: height of the cylinder (in length units, e.g., $\text{cm}$).
- $V > 0$: fixed, given volume of the cylinder (a positive constant, in $\text{cm}^3$).
- $S$: total surface area of the closed cylinder (in $\text{cm}^2$), which measures the amount of material used.

Since any positive radius $r > 0$ can be paired with a corresponding positive height $h = \frac{V}{\pi r^2} > 0$ to achieve volume $V$, the geometric domain of $r$ is the open interval:
$$
D_S = (0, \infty).
$$
To find the dimensions that minimize the continuous differentiable surface area function $S(r)$, we use **differential calculus**.

---

### Part 1: Volume Constraint
The volume $V$ of a right circular cylinder with base radius $r$ and height $h$ is given by the constraint equation:
$$
\pi r^2 h = V, \qquad r > 0,\ h > 0.
$$

---

### Part 2: Eliminating One of the Variables
Since $r > 0$, we can divide both sides of the volume constraint $\pi r^2 h = V$ by $\pi r^2$ to express the height $h$ in terms of the radius $r$ (and the constant $V$):
$$
h = \frac{V}{\pi r^2}.
$$
*(Eliminating $h$ rather than $r$ is advantageous because $h$ appears linearly in both the volume and surface area formulas, avoiding square roots.)*

---

### Part 3: Expressing the Surface Area as a Function of the Radius $r$
A closed cylindrical can consists of:
- Two circular bases (top and bottom lids): area $= 2 \times \pi r^2 = 2\pi r^2$.
- One lateral cylindrical wall: area $= 2\pi r h$.

Thus, the total surface area is:
$$
S = 2\pi r^2 + 2\pi r h.
$$
Substituting $h = \frac{V}{\pi r^2}$ from Part 2 into the surface area formula gives $S$ as a function of $r$ alone:
$$
S(r) = 2\pi r^2 + 2\pi r \left(\frac{V}{\pi r^2}\right) = 2\pi r^2 + \frac{2V}{r}, \qquad r \in (0, \infty).
$$

---

### Part 4: Finding the Relation Between $h$ and $r$ for Minimal Material Usage
We differentiate $S(r) = 2\pi r^2 + 2V r^{-1}$ with respect to $r$ on $(0, \infty)$:
$$
S'(r) = \frac{d}{dr}\left(2\pi r^2 + 2V r^{-1}\right) = 4\pi r - \frac{2V}{r^2} = \frac{4\pi r^3 - 2V}{r^2}.
$$
Setting $S'(r) = 0$ to find the critical point(s) in $(0, \infty)$:
$$
4\pi r - \frac{2V}{r^2} = 0 \iff 4\pi r^3 = 2V \iff V = 2\pi r^3.
$$
This gives the unique critical radius:
$$
r^* = \sqrt[3]{\frac{V}{2\pi}}.
$$
To find the direct relation between the optimal height $h$ and radius $r$ without needing the numerical value of $V$, we substitute the volume expression $V = \pi r^2 h$ into the optimality condition $V = 2\pi r^3$:
$$
\pi r^2 h = 2\pi r^3.
$$
Dividing both sides by $\pi r^2 > 0$ yields the fundamental optimal relation:
$$
h = 2r \quad \left(\text{with } r^* = \sqrt[3]{\frac{V}{2\pi}} \text{ and } h^* = 2\sqrt[3]{\frac{V}{2\pi}} = \sqrt[3]{\frac{4V}{\pi}}\right).
$$

#### Verification That $h = 2r$ Gives the Global Minimum
1. **First Derivative Sign Analysis**:
   Since $S'(r) = \frac{2(2\pi r^3 - V)}{r^2}$:
   - For $0 < r < r^*$, we have $2\pi r^3 < V \implies S'(r) < 0$, so $S(r)$ is **strictly decreasing**.
   - For $r > r^*$, we have $2\pi r^3 > V \implies S'(r) > 0$, so $S(r)$ is **strictly increasing**.
2. **Second Derivative Test**:
   $$
   S''(r) = \frac{d}{dr}\left(4\pi r - 2V r^{-2}\right) = 4\pi + \frac{4V}{r^3} > 0 \quad \text{for all } r > 0.
   $$
   Since $S''(r) > 0$ everywhere on $(0, \infty)$, $S(r)$ is strictly convex and $r^* = \sqrt[3]{\frac{V}{2\pi}}$ (where $h = 2r$) is the **unique global minimum**.

---

### Geometric Interpretation of the Result $h = 2r$
Since $d = 2r$ is the **diameter** of the circular base of the cylinder, the condition
$$
h = 2r = d
$$
means that **a closed cylindrical can of fixed volume uses the least amount of material when its height equals the diameter of its base**. Equivalently:
- If you slice the optimal cylinder vertically through its central axis of symmetry, the resulting **axial cross-section is a square** of side length $2r \times 2r$.
- Viewed from the side, the silhouette of the most material-efficient closed cylinder is a perfect square, and it can be inscribed exactly inside a cube of side $2r$ (or circumscribed around a sphere of radius $r$).

```
          |<---- d = 2r ---->|
          +------------------+  ---
          |        .         |   ^
          |        .         |   |
          |        .         |  h = 2r  (Axial cross-section is a square!)
          |        .  <- r ->|   |
          |        .         |   v
          +------------------+  ---
```

---

## 4. Verification and Consistency Checks

1. **Boundary Behavior Check ($r \to 0^+$ and $r \to \infty$)**:
   - As $r \to 0^+$ (an extremely thin, tall pipe with $h = \frac{V}{\pi r^2} \to \infty$): $\lim_{r \to 0^+} \left(2\pi r^2 + \frac{2V}{r}\right) = +\infty$ because the lateral area $\frac{2V}{r}$ blows up.
   - As $r \to \infty$ (an extremely wide, flat disk with $h \to 0$): $\lim_{r \to \infty} \left(2\pi r^2 + \frac{2V}{r}\right) = +\infty$ because the top and bottom lid area $2\pi r^2$ blows up.
   Between these two extremes, $S(r)$ attains its unique minimum $S_{\min} = 6\pi (r^*)^2 = 3\sqrt[3]{2\pi V^2}$ when $h = 2r$.

2. **AM-GM Inequality Verification (Independent of Calculus)**:
   Splitting the lateral area term $\frac{2V}{r} = \frac{V}{r} + \frac{V}{r}$ and applying the Arithmetic Mean–Geometric Mean (AM-GM) inequality to the three positive quantities $2\pi r^2$, $\frac{V}{r}$, and $\frac{V}{r}$:
   $$
   S(r) = 2\pi r^2 + \frac{V}{r} + \frac{V}{r} \ge 3\sqrt[3]{\left(2\pi r^2\right) \cdot \left(\frac{V}{r}\right) \cdot \left(\frac{V}{r}\right)} = 3\sqrt[3]{2\pi V^2}.
   $$
   Equality holds if and only if the three terms are equal: $2\pi r^2 = \frac{V}{r} = \frac{\pi r^2 h}{r} = \pi r h \iff h = 2r$. At this optimum, the lateral wall area ($2\pi r h = 4\pi r^2$) is exactly twice the combined area of the two circular lids ($2\pi r^2$).
