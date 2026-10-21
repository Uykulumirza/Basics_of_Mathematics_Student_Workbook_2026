# Solution to Exercise 13: Intersection of a Sphere and a Plane

## 1. Problem Statement

Given the sphere
$$x^2 + y^2 + z^2 = 25$$
and the horizontal plane $z = 3$, find the equation of the intersection curve and its radius. Then describe completely what happens to the intersection with the horizontal plane $z = c$ depending on the real parameter $c \in \mathbb{R}$.

---

## 2. Theoretical Background and Concepts

### Algebraic and Geometric Views of Sphere–Plane Intersection
1. **Algebraic Substitution:**
   A point $(x, y, z) \in \mathbb{R}^3$ lies on the intersection of the sphere $x^2 + y^2 + z^2 = R^2$ and the horizontal plane $z = c$ if and only if its coordinates satisfy both equations simultaneously:
   $$\begin{cases} x^2 + y^2 = R^2 - c^2 \\ z = c \end{cases}$$
2. **Geometric Right-Triangle Relation (Pythagorean Theorem):**
   The given sphere $x^2 + y^2 + z^2 = 25 = 5^2$ is centered at the origin $O = (0, 0, 0)$ with radius $R = 5$. The perpendicular distance from the center $O$ to the horizontal plane $z = c$ is $d = |c|$, with the foot of the perpendicular at $C_c = (0, 0, c)$.
   For any point $P = (x, y, c)$ on the intersection, the triangle $\triangle O C_c P$ has a right angle at $C_c$, hypotenuse $OP = R = 5$, and vertical leg $O C_c = |c|$. By the Pythagorean theorem, the horizontal distance $r = C_c P = \sqrt{x^2 + y^2}$ satisfies:
   $$r^2 + c^2 = R^2 \implies r = \sqrt{R^2 - c^2} = \sqrt{25 - c^2}$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Intersection Curve and Radius for $z = 3$
Substitute $z = 3$ into the sphere's equation $x^2 + y^2 + z^2 = 25$:
$$x^2 + y^2 + 3^2 = 25$$
$$x^2 + y^2 + 9 = 25$$
Subtracting $9$ from both sides yields:
$$x^2 + y^2 = 16 \quad (\text{in the plane } z = 3)$$

- **Equation of the intersection curve in $\mathbb{R}^3$:**
  $$\begin{cases} x^2 + y^2 = 16 \\ z = 3 \end{cases}$$
- **Geometric description and radius:**
  In the horizontal plane $z = 3$, the equation $x^2 + y^2 = 4^2$ describes a **circle** centered at $C_3 = (0, 0, 3)$ with radius:
  $$r = \sqrt{16} = 4$$
  *(Notice the classic $3\text{–}4\text{–}5$ right triangle formed by the plane height $c = 3$, the circle radius $r = 4$, and the sphere radius $R = 5$.)*

---

### Step 2: Classification of the Intersection for General $z = c$
Substituting $z = c$ ($c \in \mathbb{R}$) into $x^2 + y^2 + z^2 = 25$ produces the equation:
$$x^2 + y^2 = 25 - c^2 \quad (\text{in the plane } z = c)$$

Because $x^2 + y^2 \ge 0$ for all real $(x, y)$, the nature of the intersection depends on the sign of $25 - c^2$:

#### Case 1: $|c| < 5$ (i.e., $-5 < c < 5$) — A Circle (Secant Plane)
When $|c| < 5$, we have $c^2 < 25$, so $25 - c^2 > 0$.
- The plane $z = c$ slices through the interior of the sphere, and the intersection is a **circle** centered at $(0, 0, c)$ with positive radius:
  $$r(c) = \sqrt{25 - c^2}$$
- **Special subcase $c = 0$ (Great Circle / Equator):** At $z = 0$, the radius attains its maximum value $r(0) = \sqrt{25 - 0} = 5 = R$.
- As $|c|$ increases from $0$ toward $5$, the circle's radius $r(c) = \sqrt{25 - c^2}$ shrinks monotonically toward $0$.

#### Case 2: $c = 5$ or $c = -5$ (i.e., $|c| = 5$) — A Single Tangent Point
When $c = \pm 5$, we have $c^2 = 25$, so $25 - c^2 = 0$, and the equation becomes:
$$x^2 + y^2 = 0 \implies x = 0 \text{ and } y = 0$$
- The plane $z = 5$ (or $z = -5$) is **tangent** to the sphere at the north pole $(0, 0, 5)$ (or south pole $(0, 0, -5)$).
- The intersection is a **single point** $(0, 0, \pm 5)$, which can be viewed as a degenerate circle of radius $r(\pm 5) = 0$.

#### Case 3: $|c| > 5$ (i.e., $c > 5$ or $c < -5$) — Empty Intersection
When $|c| > 5$, we have $c^2 > 25$, so the right-hand side $25 - c^2 < 0$ is strictly negative while the left-hand side $x^2 + y^2 \ge 0$ is non-negative.
- No real pair $(x, y)$ satisfies the equation; the plane $z = c$ passes completely above or below the sphere without touching it.
- The intersection is the **empty set** $\varnothing$.

---

### Summary Table Across All Values of $c$

| Parameter Range | Sign of $25 - c^2$ | Geometric Intersection in $\mathbb{R}^3$ | Radius $r(c)$ |
| :--- | :--- | :--- | :--- |
| $c = 0$ | $25 > 0$ | Great circle $x^2 + y^2 = 25$ in $z = 0$ | $r(0) = 5$ (maximum) |
| $0 < |c| < 5$ | $25 - c^2 > 0$ | Circle $x^2 + y^2 = 25 - c^2$ in $z = c$ | $r(c) = \sqrt{25 - c^2} \in (0, 5)$ |
| $c = \pm 5$ | $25 - c^2 = 0$ | Single tangent point $(0, 0, \pm 5)$ | $r(\pm 5) = 0$ |
| $|c| > 5$ | $25 - c^2 < 0$ | Empty set $\varnothing$ (no real points) | Does not exist |

---

## 4. Verification and Consistency Checks

1. **Checking Four Cardinal Points of the Circle at $z = 3$:**
   In the plane $z = 3$, the circle $x^2 + y^2 = 16$ has cardinal points $(\pm 4, 0, 3)$ and $(0, \pm 4, 3)$. Substituting into $x^2 + y^2 + z^2 = 25$:
   $$(\pm 4)^2 + 0^2 + 3^2 = 16 + 0 + 9 = 25 \quad \checkmark, \qquad 0^2 + (\pm 4)^2 + 3^2 = 0 + 16 + 9 = 25 \quad \checkmark$$
2. **Continuity of the Radius Function $r(c) = \sqrt{25 - c^2}$:**
   At $c = 3$, the general formula gives $r(3) = \sqrt{25 - 9} = 4$, matching Step 1; as $c \to 5^-$, $\lim_{c \to 5^-} \sqrt{25 - c^2} = 0$, matching the tangent point at $c = 5$.
