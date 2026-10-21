# Exercise 13: Closest Point on a Plane — Solution

## 1. Problem Statement

Find the point on the plane $x+2y+2z=4$ closest to $P=(3,0,0)$. Give the distance and check that the segment joining the two points is perpendicular to the plane.

---

## 2. Theoretical Background and Concepts

Given a plane $\Pi: Ax + By + Cz = d$ with normal vector $n = (A, B, C)$ and an external point $P \in \mathbb{R}^3$, what point $Q \in \Pi$ minimizes the Euclidean distance $\|X - P\|$ among all points $X \in \Pi$?

### Geometric Principle (Pythagorean Theorem in $\mathbb{R}^3$)
Let $Q$ be the **orthogonal projection** of $P$ onto $\Pi$, meaning $Q \in \Pi$ and the vector $\overrightarrow{PQ} = Q - P$ is perpendicular to the plane $\Pi$ (so $\overrightarrow{PQ} \parallel n$).
For any other point $X \in \Pi$, the vector $\overrightarrow{QX} = X - Q$ lies inside the plane $\Pi$ and is therefore orthogonal to $\overrightarrow{PQ}$ ($\overrightarrow{PQ} \cdot \overrightarrow{QX} = 0$). By the Pythagorean theorem applied to the right triangle $\triangle PQX$:
$$\|X - P\|^2 = \|\overrightarrow{PQ} + \overrightarrow{QX}\|^2 = \|\overrightarrow{PQ}\|^2 + \|\overrightarrow{QX}\|^2.$$
Since $\|\overrightarrow{QX}\|^2 \ge 0$ with equality if and only if $X = Q$, the unique point on $\Pi$ closest to $P$ is the orthogonal projection $Q$.

### Computational Procedure
1. Form the **normal line** through $P$ in the direction of the normal $n$: $L_\perp: X(t) = P + t n$.
2. Intersect $L_\perp$ with $\Pi$ to find the parameter $t^*$ and the closest point $Q = P + t^* n$.
3. Compute the minimum distance as $\|\overrightarrow{PQ}\| = |t^*|\,\|n\|$, which coincides with the point-to-plane distance formula $d(P, \Pi) = \frac{|n \cdot P - d|}{\|n\|}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Write the Parametric Equation of the Normal Line Through $P$
From the plane equation $\Pi: x + 2y + 2z = 4$, we read off the normal vector:
$$n = (1, 2, 2).$$
The line $L_\perp$ passing through $P = (3, 0, 0)$ in the direction of $n = (1, 2, 2)$ has the parametric form:
$$(x, y, z) = (3, 0, 0) + t(1, 2, 2) = (3 + t, \, 2t, \, 2t), \quad t \in \mathbb{R}.$$

### Step 2: Intersect the Normal Line with the Plane to Find the Closest Point $Q$
Substituting $x = 3 + t$, $y = 2t$, and $z = 2t$ into the plane equation $x + 2y + 2z = 4$:
$$(3 + t) + 2(2t) + 2(2t) = 4$$
$$3 + t + 4t + 4t = 4$$
$$3 + 9t = 4 \implies 9t = 1 \implies t = \frac{1}{9}.$$
Substituting $t = \frac{1}{9}$ back into the normal line gives the coordinates of the closest point $Q$:
$$Q = \left(3 + \frac{1}{9}, \, 2\left(\frac{1}{9}\right), \, 2\left(\frac{1}{9}\right)\right) = \left(\frac{28}{9}, \, \frac{2}{9}, \, \frac{2}{9}\right).$$

### Step 3: Compute the Distance Between $P$ and the Plane
The displacement vector from $P = (3, 0, 0)$ to $Q = \left(\frac{28}{9}, \frac{2}{9}, \frac{2}{9}\right)$ is:
$$\overrightarrow{PQ} = Q - P = \left(\frac{28}{9} - 3, \, \frac{2}{9} - 0, \, \frac{2}{9} - 0\right) = \left(\frac{1}{9}, \, \frac{2}{9}, \, \frac{2}{9}\right) = \frac{1}{9}(1, 2, 2).$$
Taking its Euclidean norm gives the shortest distance from $P$ to $\Pi$:
$$d(P, \Pi) = \|\overrightarrow{PQ}\| = \frac{1}{9}\sqrt{1^2 + 2^2 + 2^2} = \frac{1}{9}\sqrt{1 + 4 + 4} = \frac{\sqrt{9}}{9} = \frac{3}{9} = \frac{1}{3}.$$

---

## 4. Verification and Consistency Checks

### 1. Checking That $Q$ Lies on the Plane $\Pi$
Substituting $Q = \left(\frac{28}{9}, \frac{2}{9}, \frac{2}{9}\right)$ into $x + 2y + 2z = 4$:
$$\frac{28}{9} + 2\left(\frac{2}{9}\right) + 2\left(\frac{2}{9}\right) = \frac{28 + 4 + 4}{9} = \frac{36}{9} = 4. \quad \checkmark$$

### 2. Checking That the Segment $PQ$ Is Perpendicular to the Plane
From Step 3, the vector joining $P$ and $Q$ is:
$$\overrightarrow{PQ} = \left(\frac{1}{9}, \, \frac{2}{9}, \, \frac{2}{9}\right) = \frac{1}{9}(1, 2, 2) = \frac{1}{9}n.$$
Because $\overrightarrow{PQ}$ is a scalar multiple of the plane's normal vector $n = (1, 2, 2)$, for every vector $w$ lying in the plane $\Pi$ (which satisfies $n \cdot w = 0$), we have:
$$\overrightarrow{PQ} \cdot w = \frac{1}{9}(n \cdot w) = 0.$$
Alternatively, using the cross product:
$$\overrightarrow{PQ} \times n = \left(\frac{1}{9}n\right) \times n = \mathbf{0}. \quad \checkmark$$
Thus, the segment $PQ$ is perpendicular to the plane $\Pi$.

### 3. Cross-Checking with the Point-to-Plane Distance Formula
Applying the direct formula $d(P, \Pi) = \frac{|Ax_0 + By_0 + Cz_0 - d|}{\sqrt{A^2 + B^2 + C^2}}$ to $P = (3, 0, 0)$ and $x + 2y + 2z - 4 = 0$:
$$d(P, \Pi) = \frac{|1(3) + 2(0) + 2(0) - 4|}{\sqrt{1^2 + 2^2 + 2^2}} = \frac{|3 - 4|}{\sqrt{9}} = \frac{|-1|}{3} = \frac{1}{3}. \quad \checkmark$$
Both methods yield the exact same distance $\frac{1}{3}$.
