# Exercise 10: Projection of a Point onto a Plane — Solution

## 1. Problem Statement

Find the orthogonal projection of $P=(2,1,3)$ onto the plane $x+y+z=3$, and then find the reflection of $P$ across this plane. Check that the midpoint of the segment joining the point and its reflection lies on the plane.

---

## 2. Theoretical Background and Concepts

Let $\Pi: Ax + By + Cz = d$ be a plane in $\mathbb{R}^3$ with normal vector $n = (A, B, C)$, and let $P \in \mathbb{R}^3$ be a given point.

### 1. Orthogonal Projection $P'$ of $P$ onto $\Pi$
The **orthogonal projection** $P'$ of $P$ onto $\Pi$ is the foot of the perpendicular dropped from $P$ to the plane $\Pi$ (which is also the point on $\Pi$ closest to $P$).
Geometrically, to travel from $P$ to $P'$, we must move along the line passing through $P$ in the direction perpendicular to $\Pi$—that is, along the **normal line** $L_\perp$ whose direction vector is the plane's normal $n$:
$$L_\perp: X(t) = P + t n, \quad t \in \mathbb{R}.$$
The projection $P' = L_\perp \cap \Pi$ is found by substituting $X(t) = P + t n$ into the plane equation $n \cdot X = d$, solving for the unique parameter $t^*$, and computing $P' = P + t^* n$.

### 2. Reflection $P''$ of $P$ Across $\Pi$
The **reflection** (mirror image) $P''$ of $P$ across the plane $\Pi$ lies on the same normal line $L_\perp$ on the opposite side of $\Pi$ at the exact same perpendicular distance from $\Pi$ as $P$.
In vector terms:
- Reaching the plane from $P$ requires the displacement vector $\overrightarrow{PP'} = P' - P = t^* n$.
- Continuing across the plane to the mirror image $P''$ requires doubling this displacement:
  $$\overrightarrow{PP''} = 2\overrightarrow{PP'} \implies P'' = P + 2(P' - P) = 2P' - P = P + 2t^* n.$$
Equivalently, $P'$ is the **midpoint** of the segment $PP''$:
$$P' = \frac{P + P''}{2}.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct the Normal Line Through $P$
The plane $\Pi: x + y + z = 3$ has normal vector:
$$n = (1, 1, 1).$$
The normal line $L_\perp$ passing through $P = (2, 1, 3)$ with direction vector $n = (1, 1, 1)$ has the parametric equation:
$$(x, y, z) = (2, 1, 3) + t(1, 1, 1) = (2 + t, \, 1 + t, \, 3 + t), \quad t \in \mathbb{R}.$$

### Step 2: Intersect the Normal Line with the Plane to Find the Orthogonal Projection $P'$
We substitute the parametric coordinates of $L_\perp$ into the plane equation $x + y + z = 3$:
$$(2 + t) + (1 + t) + (3 + t) = 3.$$
Combining like terms:
$$6 + 3t = 3 \implies 3t = 3 - 6 = -3 \implies t = -1.$$
Substituting $t = -1$ into the normal line equation gives the orthogonal projection $P'$:
$$P' = (2 + (-1), \, 1 + (-1), \, 3 + (-1)) = (1, 0, 2).$$

### Step 3: Compute the Reflection $P''$ Across the Plane
The displacement vector from $P$ to its projection $P'$ on the plane is:
$$\overrightarrow{PP'} = P' - P = (1 - 2, \, 0 - 1, \, 2 - 3) = (-1, -1, -1).$$
To reach the reflected point $P''$, we add $2\overrightarrow{PP'}$ to $P$ (or compute $P'' = 2P' - P$):
$$\begin{aligned}
P'' &= P + 2\overrightarrow{PP'} \\
&= (2, 1, 3) + 2(-1, -1, -1) \\
&= (2 - 2, \, 1 - 2, \, 3 - 2) \\
&= (0, -1, 1).
\end{aligned}$$
Thus:
- **Orthogonal projection:** $P' = (1, 0, 2)$,
- **Reflection across $\Pi$:** $P'' = (0, -1, 1)$.

---

## 4. Verification and Consistency Checks

### 1. Midpoint Check
Let $M$ be the midpoint of the segment joining $P = (2, 1, 3)$ and its reflection $P'' = (0, -1, 1)$:
$$M = \frac{P + P''}{2} = \left(\frac{2 + 0}{2}, \, \frac{1 + (-1)}{2}, \, \frac{3 + 1}{2}\right) = (1, 0, 2) = P'.$$
Substituting the coordinates of $M = (1, 0, 2)$ into the plane equation $x + y + z = 3$:
$$1 + 0 + 2 = 3. \quad \checkmark$$
This confirms that the midpoint $M$ coincides with the orthogonal projection $P'$ and lies on the plane $\Pi$.

### 2. Perpendicularity Check of Segment $PP''$
The vector joining $P$ to $P''$ is:
$$\overrightarrow{PP''} = P'' - P = (0 - 2, \, -1 - 1, \, 1 - 3) = (-2, -2, -2) = -2(1, 1, 1) = -2n.$$
Since $\overrightarrow{PP''}$ is a scalar multiple of the normal vector $n = (1, 1, 1)$, the segment $PP''$ is perpendicular to the plane $\Pi$, and the plane $\Pi$ is the perpendicular bisector of the segment $PP''$.
