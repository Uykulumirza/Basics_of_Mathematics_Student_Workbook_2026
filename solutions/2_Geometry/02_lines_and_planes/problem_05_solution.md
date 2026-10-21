# Exercise 5: Relative Position of Two Lines — Solution

## 1. Problem Statement

Analyze the position of
$$L_1:(x,y,z)=(1,1,0)+t(1,2,1),$$
$$L_2:(x,y,z)=(2,0,1)+s(0,1,-1).$$
If they intersect, give the intersection point. If not, determine whether they are parallel or skew. Justify the classification.

---

## 2. Theoretical Background and Concepts

In three-dimensional space $\mathbb{R}^3$, two lines $L_1: P_1 + t v_1$ and $L_2: P_2 + s v_2$ can have four possible relative positions, organized into two main families:

1. **Collinear Direction Vectors ($v_1 \parallel v_2$, i.e., $v_1 = \lambda v_2$ or $v_1 \times v_2 = \mathbf{0}$):**
   - **Coincident (Identical) Lines:** The lines share the same direction and have at least one point in common (so $P_1 \in L_2$).
   - **Strictly Parallel Lines:** The lines share the same direction but have no points in common (they lie in a common plane at a constant positive distance).

2. **Non-Collinear Direction Vectors ($v_1 \nparallel v_2$, i.e., $v_1 \times v_2 \ne \mathbf{0}$):**
   - **Intersecting Lines:** There exists a unique pair of parameters $(t, s) \in \mathbb{R}^2$ such that $P_1 + t v_1 = P_2 + s v_2$. The two lines meet at a single point and span a common plane.
   - **Skew Lines:** No pair $(t, s)$ satisfies $P_1 + t v_1 = P_2 + s v_2$ (the system of 3 equations in 2 unknowns is inconsistent), and the direction vectors are not parallel. Skew lines do not lie in any common plane; equivalently, the scalar triple product $\overrightarrow{P_1 P_2} \cdot (v_1 \times v_2) \ne 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Base Points and Direction Vectors
From the parametric descriptions:
- For $L_1$: base point $P_1 = (1, 1, 0)$ and direction vector $v_1 = (1, 2, 1)$.
- For $L_2$: base point $P_2 = (2, 0, 1)$ and direction vector $v_2 = (0, 1, -1)$.

### Step 2: Test for Parallelism
We check whether $v_1$ and $v_2$ are proportional ($v_1 = \lambda v_2$):
$$(1, 2, 1) = \lambda (0, 1, -1) = (0, \lambda, -\lambda).$$
Comparing the first components gives $1 = 0$, which is impossible. (Equivalently, $v_1 \times v_2 = (-3, 1, 1) \ne (0, 0, 0)$.)
Thus, $v_1$ and $v_2$ are **not parallel**, which immediately rules out the cases where $L_1$ and $L_2$ are parallel or coincident. The lines must be either **intersecting** or **skew**.

### Step 3: Test for Intersection
We equate the coordinates of a general point on $L_1$ (parameter $t$) and a general point on $L_2$ (parameter $s$):
$$(1 + t, \, 1 + 2t, \, t) = (2, \, s, \, 1 - s).$$
This gives a system of three linear equations in two unknowns $t$ and $s$:
$$\begin{cases}
1 + t = 2 & \text{(1)} \\
1 + 2t = s & \text{(2)} \\
t = 1 - s & \text{(3)}
\end{cases}$$

We solve the first two equations and substitute into the third:
1. From equation (1):
   $$1 + t = 2 \implies t = 1.$$
2. Substituting $t = 1$ into equation (2):
   $$s = 1 + 2(1) = 3.$$
3. Substituting $t = 1$ and $s = 3$ into equation (3) to check consistency:
   $$\text{LHS} = t = 1, \qquad \text{RHS} = 1 - s = 1 - 3 = -2.$$
   Since $1 \ne -2$, equation (3) is violated!

### Step 4: Classification
Because the system of equations has **no solution**, the lines $L_1$ and $L_2$ have no common point ($L_1 \cap L_2 = \emptyset$). Since we already established in Step 2 that their direction vectors $v_1$ and $v_2$ are not parallel, we conclude that the lines $L_1$ and $L_2$ are **skew**.

---

## 4. Verification and Consistency Checks

### 1. Coordinate Comparison at $t = 1$ and $s = 3$
- On $L_1$ at $t = 1$: $(x, y, z) = (1, 1, 0) + 1(1, 2, 1) = (2, 3, 1)$.
- On $L_2$ at $s = 3$: $(x, y, z) = (2, 0, 1) + 3(0, 1, -1) = (2, 3, -2)$.
At the unique parameter pair where both the $x$- and $y$-coordinates match ($x = 2, y = 3$), the $z$-coordinates differ ($z_1 = 1$ vs. $z_2 = -2$), meaning one line passes directly above the other without touching.

### 2. Scalar Triple Product (Coplanarity) Check
Two lines are coplanar if and only if the vectors $\overrightarrow{P_1 P_2}$, $v_1$, and $v_2$ are coplanar, i.e., their scalar triple product is zero.
Here:
- $\overrightarrow{P_1 P_2} = P_2 - P_1 = (2 - 1, \, 0 - 1, \, 1 - 0) = (1, -1, 1)$.
- $v_1 \times v_2 = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 1 \\ 0 & 1 & -1 \end{vmatrix} = (-2 - 1, \, -( -1 - 0), \, 1 - 0) = (-3, 1, 1)$.
- Scalar triple product:
  $$\overrightarrow{P_1 P_2} \cdot (v_1 \times v_2) = (1, -1, 1) \cdot (-3, 1, 1) = -3 - 1 + 1 = -3 \ne 0.$$
Because the scalar triple product is non-zero ($-3 \ne 0$), the vectors do not lie in a common plane, confirming independently that $L_1$ and $L_2$ are **skew lines**.
