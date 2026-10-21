# Exercise 4: Plane Through Three Points — Solution

## 1. Problem Statement

Find the equation of the plane through
$$A=(1,0,0),\quad B=(0,1,0),\quad C=(0,0,1).$$
First construct two vectors lying in the plane, and then use the cross product. Check the resulting equation on all three points.

---

## 2. Theoretical Background and Concepts

Three non-collinear points $A, B, C \in \mathbb{R}^3$ uniquely determine a plane $\Pi$. To write the equation of $\Pi$ in point-normal or general form, we need a normal vector $n$ perpendicular to the plane.

### Constructing the Normal Vector from Three Points
1. **In-Plane Spanning Vectors:** Because the points $A, B, C$ all lie in $\Pi$, the displacement vectors anchored at $A$,
   $$u = \overrightarrow{AB} = B - A \quad \text{and} \quad w = \overrightarrow{AC} = C - A,$$
   both lie completely inside the plane $\Pi$. When $A, B, C$ are non-collinear, $u$ and $w$ are linearly independent and span the two-dimensional direction space of the plane.
2. **Cross Product as a Normal Generator:** By the fundamental geometric property of the cross product in $\mathbb{R}^3$, the vector
   $$n = u \times w = \overrightarrow{AB} \times \overrightarrow{AC}$$
   is simultaneously perpendicular to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$ (and is non-zero whenever $A, B, C$ are non-collinear). Since $n$ is orthogonal to two independent vectors in $\Pi$, it is orthogonal to every vector in $\Pi$, making $n$ a valid normal vector to the plane.
3. **Plane Equation:** Using $A$ as the base point and $n = (n_x, n_y, n_z)$ as the normal vector, the equation of the plane is:
   $$n \cdot \overrightarrow{AX} = n_x(x - x_A) + n_y(y - y_A) + n_z(z - z_A) = 0.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct Two Vectors Lying in the Plane
Using $A = (1, 0, 0)$ as the common initial point, we compute the displacement vectors to $B = (0, 1, 0)$ and $C = (0, 0, 1)$:
$$\overrightarrow{AB} = B - A = (0 - 1, \, 1 - 0, \, 0 - 0) = (-1, 1, 0),$$
$$\overrightarrow{AC} = C - A = (0 - 1, \, 0 - 0, \, 1 - 0) = (-1, 0, 1).$$

### Step 2: Compute the Normal Vector via the Cross Product
We take the cross product $n = \overrightarrow{AB} \times \overrightarrow{AC}$:
$$\begin{aligned}
n &= \overrightarrow{AB} \times \overrightarrow{AC} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ -1 & 1 & 0 \\ -1 & 0 & 1 \end{vmatrix} \\
&= \mathbf{i}\bigl(1 \cdot 1 - 0 \cdot 0\bigr) - \mathbf{j}\bigl((-1) \cdot 1 - 0 \cdot (-1)\bigr) + \mathbf{k}\bigl((-1) \cdot 0 - 1 \cdot (-1)\bigr) \\
&= 1\mathbf{i} - (-1)\mathbf{j} + 1\mathbf{k} \\
&= (1, 1, 1).
\end{aligned}$$
Since $n = (1, 1, 1) \ne (0, 0, 0)$, the three points are non-collinear and define a unique plane with normal vector $n = (1, 1, 1)$.

### Step 3: Write the Equation of the Plane
Applying the point-normal formula $n \cdot \overrightarrow{AX} = 0$ with base point $A = (1, 0, 0)$ and normal $n = (1, 1, 1)$:
$$1(x - 1) + 1(y - 0) + 1(z - 0) = 0.$$
Simplifying gives the general form of the plane:
$$x + y + z - 1 = 0 \quad (\text{or } x + y + z = 1).$$

---

## 4. Verification and Consistency Checks

### 1. Checking Orthogonality of $n$ with $\overrightarrow{AB}$ and $\overrightarrow{AC}$
- $n \cdot \overrightarrow{AB} = (1, 1, 1) \cdot (-1, 1, 0) = -1 + 1 + 0 = 0. \quad \checkmark$
- $n \cdot \overrightarrow{AC} = (1, 1, 1) \cdot (-1, 0, 1) = -1 + 0 + 1 = 0. \quad \checkmark$

### 2. Checking All Three Points in the Plane Equation $x + y + z = 1$
- **Point $A = (1, 0, 0)$:**
  $$1 + 0 + 0 = 1. \quad \checkmark$$
- **Point $B = (0, 1, 0)$:**
  $$0 + 1 + 0 = 1. \quad \checkmark$$
- **Point $C = (0, 0, 1)$:**
  $$0 + 0 + 1 = 1. \quad \checkmark$$

Geometrically, this plane is the standard **intercept plane** cutting each of the three coordinate axes $Ox, Oy, Oz$ at unit distance $1$ from the origin, so its normal $n = (1, 1, 1)$ makes equal angles with all three positive coordinate axes.
