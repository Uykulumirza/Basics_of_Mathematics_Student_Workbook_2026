# Exercise 9: Distances — Solution

## 1. Problem Statement

Compute:
1. the distance from $P=(2,3)$ to the line $3x+4y-10=0$,
2. the distance from $Q=(2,-1,3)$ to the plane $2x-2y+z-4=0$.

Compare the two formulas and explain their common connection with the normal direction.

---

## 2. Theoretical Background and Concepts

### 1. Distance Formulas in $\mathbb{R}^2$ and $\mathbb{R}^3$
- **Point-to-Line Distance in $\mathbb{R}^2$:**
  Given a point $P = (x_0, y_0) \in \mathbb{R}^2$ and a line $L: ax + by + c = 0$ with normal vector $n = (a, b) \neq (0, 0)$, the perpendicular distance from $P$ to $L$ is:
  $$d(P, L) = \frac{|ax_0 + by_0 + c|}{\sqrt{a^2 + b^2}} = \frac{|n \cdot P + c|}{\|n\|}.$$
- **Point-to-Plane Distance in $\mathbb{R}^3$:**
  Given a point $Q = (x_0, y_0, z_0) \in \mathbb{R}^3$ and a plane $\Pi: Ax + By + Cz + D = 0$ with normal vector $n = (A, B, C) \neq (0, 0, 0)$, the perpendicular distance from $Q$ to $\Pi$ is:
  $$d(Q, \Pi) = \frac{|Ax_0 + By_0 + Cz_0 + D|}{\sqrt{A^2 + B^2 + C^2}} = \frac{|n \cdot Q + D|}{\|n\|}.$$

### 2. Common Geometric Mechanism: Orthogonal Projection onto the Unit Normal
Why do both formulas have the exact same algebraic structure $\frac{|n \cdot X_0 + c|}{\|n\|}$?
Both a line in $\mathbb{R}^2$ and a plane in $\mathbb{R}^3$ are **hyperplanes** defined by a single linear equation $n \cdot X + c = 0$, where $n$ is a normal vector perpendicular to the hyperplane.
Let $X_1$ be any reference point lying on the hyperplane, so $n \cdot X_1 + c = 0 \iff c = -n \cdot X_1$.
To find the shortest distance from an external point $X_0$ to the hyperplane, we must measure the component of the displacement vector $\overrightarrow{X_1 X_0} = X_0 - X_1$ purely along the **perpendicular (normal) direction**—any movement parallel to the hyperplane is orthogonal to $n$ and gets annihilated by the dot product with $n$.
Taking the absolute scalar projection of $\overrightarrow{X_1 X_0}$ onto the unit normal vector $\hat{n} = \frac{n}{\|n\|}$ yields:
$$d = \bigl|\overrightarrow{X_1 X_0} \cdot \hat{n}\bigr| = \frac{|(X_0 - X_1) \cdot n|}{\|n\|} = \frac{|n \cdot X_0 - n \cdot X_1|}{\|n\|} = \frac{|n \cdot X_0 + c|}{\|n\|}.$$
Thus:
- The **numerator** $|n \cdot X_0 + c|$ measures how far $X_0$ fails to satisfy the hyperplane equation (scaled by $\|n\|$).
- The **denominator** $\|n\|$ normalizes the normal vector $n$ to unit length so that the result is the true Euclidean distance.

---

## 3. Detailed Step-by-Step Solution

### Part 1: Distance from $P = (2, 3)$ to the Line $L: 3x + 4y - 10 = 0$
1. **Identify parameters:**
   - Point coordinates: $x_0 = 2, \, y_0 = 3$.
   - Line coefficients: $a = 3, \, b = 4, \, c = -10$, so the normal vector is $n_L = (3, 4)$.
2. **Compute the norm of the normal vector:**
   $$\|n_L\| = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5.$$
3. **Evaluate the distance formula:**
   $$d(P, L) = \frac{|3(2) + 4(3) - 10|}{\sqrt{3^2 + 4^2}} = \frac{|6 + 12 - 10|}{5} = \frac{|8|}{5} = \frac{8}{5} = 1.6.$$

### Part 2: Distance from $Q = (2, -1, 3)$ to the Plane $\Pi: 2x - 2y + z - 4 = 0$
1. **Identify parameters:**
   - Point coordinates: $x_0 = 2, \, y_0 = -1, \, z_0 = 3$.
   - Plane coefficients: $A = 2, \, B = -2, \, C = 1, \, D = -4$, so the normal vector is $n_\Pi = (2, -2, 1)$.
2. **Compute the norm of the normal vector:**
   $$\|n_\Pi\| = \sqrt{2^2 + (-2)^2 + 1^2} = \sqrt{4 + 4 + 1} = \sqrt{9} = 3.$$
3. **Evaluate the distance formula:**
   $$d(Q, \Pi) = \frac{|2(2) - 2(-1) + 1(3) - 4|}{\sqrt{2^2 + (-2)^2 + 1^2}} = \frac{|4 + 2 + 3 - 4|}{3} = \frac{|5|}{3} = \frac{5}{3}.$$

---

## 4. Verification and Consistency Checks

### 1. Verification of Part 1 via Explicit Orthogonal Projection in $\mathbb{R}^2$
Pick a point on $L: 3x + 4y - 10 = 0$, for example $P_1 = (2, 1)$ (since $3(2) + 4(1) - 10 = 0$).
The displacement vector from $P_1$ to $P = (2, 3)$ is:
$$\overrightarrow{P_1 P} = (2 - 2, \, 3 - 1) = (0, 2).$$
Projecting $\overrightarrow{P_1 P}$ onto the unit normal $\hat{n}_L = \frac{1}{5}(3, 4)$ gives:
$$d(P, L) = \bigl|\overrightarrow{P_1 P} \cdot \hat{n}_L\bigr| = \left|(0, 2) \cdot \left(\frac{3}{5}, \frac{4}{5}\right)\right| = \frac{8}{5}. \quad \checkmark$$

### 2. Verification of Part 2 via Explicit Orthogonal Projection in $\mathbb{R}^3$
Pick a point on $\Pi: 2x - 2y + z - 4 = 0$, for example $Q_1 = (2, 0, 0)$ (since $2(2) - 0 + 0 - 4 = 0$).
The displacement vector from $Q_1$ to $Q = (2, -1, 3)$ is:
$$\overrightarrow{Q_1 Q} = (2 - 2, \, -1 - 0, \, 3 - 0) = (0, -1, 3).$$
Projecting $\overrightarrow{Q_1 Q}$ onto the unit normal $\hat{n}_\Pi = \frac{1}{3}(2, -2, 1)$ gives:
$$d(Q, \Pi) = \bigl|\overrightarrow{Q_1 Q} \cdot \hat{n}_\Pi\bigr| = \left|(0, -1, 3) \cdot \left(\frac{2}{3}, -\frac{2}{3}, \frac{1}{3}\right)\right| = \left|0 + \frac{2}{3} + \frac{3}{3}\right| = \frac{5}{3}. \quad \checkmark$$
Both geometric projections reproduce the formula values $\frac{8}{5}$ and $\frac{5}{3}$ identically.
