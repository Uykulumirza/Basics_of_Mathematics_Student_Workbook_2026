# Exercise 3: Plane Through a Point with a Given Normal Vector — Solution

## 1. Problem Statement

Find the equation of the plane through $P=(1,-2,3)$ and perpendicular to $n=(2,1,-1)$. Check the result by substituting the point $P$ and explain the role of the normal vector.

---

## 2. Theoretical Background and Concepts

In three-dimensional Euclidean space $\mathbb{R}^3$, a plane $\Pi$ is uniquely determined by:
1. A fixed **reference point** $P = (x_0, y_0, z_0)$ lying in the plane, and
2. A non-zero **normal vector** $n = (A, B, C)$ that is perpendicular (orthogonal) to the plane.

### Geometric Role of the Normal Vector
Unlike a line in $\mathbb{R}^3$ (which has a single one-dimensional direction), a plane is two-dimensional and contains infinitely many non-collinear directions. However, all directions perpendicular to a plane in $\mathbb{R}^3$ are parallel to a single line—the normal direction.

Specifically, an arbitrary point $X = (x, y, z) \in \mathbb{R}^3$ lies in the plane $\Pi$ if and only if the displacement vector $\overrightarrow{PX} = X - P = (x - x_0, y - y_0, z - z_0)$ lying along the plane is perpendicular to the normal vector $n$. Expressed via the dot product, this orthogonality condition is:
$$n \cdot \overrightarrow{PX} = 0.$$
In coordinates, this produces the **point-normal form** of the plane equation:
$$A(x - x_0) + B(y - y_0) + C(z - z_0) = 0,$$
which expands to the **general form**:
$$Ax + By + Cz + D = 0 \quad (\text{or } Ax + By + Cz = d),$$
where $D = -(Ax_0 + By_0 + Cz_0)$ and $d = -D = n \cdot P$. Notice that the coefficients $(A, B, C)$ of $(x, y, z)$ in the general equation immediately display the coordinates of the normal vector $n$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Point-Normal Form
Let $X = (x, y, z)$ be an arbitrary point on the plane $\Pi$. Given the base point $P = (1, -2, 3)$, the displacement vector from $P$ to $X$ is:
$$\overrightarrow{PX} = X - P = (x - 1, \, y - (-2), \, z - 3) = (x - 1, \, y + 2, \, z - 3).$$
Since the plane is perpendicular to $n = (2, 1, -1)$, we impose the orthogonality condition $n \cdot \overrightarrow{PX} = 0$:
$$(2, 1, -1) \cdot (x - 1, \, y + 2, \, z - 3) = 0$$
$$2(x - 1) + 1(y + 2) - 1(z - 3) = 0.$$

### Step 2: Expand to the General Form
Distributing the coefficients and combining the constant terms:
$$2x - 2 + y + 2 - z + 3 = 0$$
$$2x + y - z + 3 = 0,$$
or equivalently:
$$2x + y - z = -3.$$

---

## 4. Verification and Consistency Checks

### 1. Substitution of the Point $P = (1, -2, 3)$
We substitute $x = 1$, $y = -2$, $z = 3$ into the general equation $2x + y - z + 3 = 0$:
$$\begin{aligned}
2(1) + 1(-2) - 1(3) + 3 &= 2 - 2 - 3 + 3 \\
&= 0. \quad \checkmark
\end{aligned}$$
Similarly, in $2x + y - z = -3$, the left-hand side evaluates to $2 - 2 - 3 = -3$, which matches the right-hand side. This confirms that $P = (1, -2, 3)$ lies on the plane.

### 2. Checking Orthogonality with an In-Plane Displacement Vector
Let us pick another point $Q$ that satisfies $2x + y - z = -3$, for instance $Q = (0, 0, 3)$ (since $2(0) + 0 - 3 = -3$). The displacement vector between $P$ and $Q$ in the plane is:
$$\overrightarrow{PQ} = Q - P = (0 - 1, \, 0 - (-2), \, 3 - 3) = (-1, 2, 0).$$
Taking its dot product with the normal vector $n = (2, 1, -1)$:
$$n \cdot \overrightarrow{PQ} = 2(-1) + 1(2) + (-1)(0) = -2 + 2 + 0 = 0. \quad \checkmark$$
This confirms that vectors connecting points on the plane are orthogonal to $n = (2, 1, -1)$.
