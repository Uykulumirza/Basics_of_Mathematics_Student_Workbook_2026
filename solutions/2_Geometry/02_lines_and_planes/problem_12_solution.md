# Exercise 12: Intersection Line of Two Planes — Solution

## 1. Problem Statement

Find a parametric equation of the line that is the intersection of
$$x+y+z=3,\qquad x-y+z=1.$$
Find its direction vector in two ways: from the system of equations and from the cross product of the normal vectors. Compare the results.

---

## 2. Theoretical Background and Concepts

Two non-parallel planes $\Pi_1: n_1 \cdot X = d_1$ and $\Pi_2: n_2 \cdot X = d_2$ in $\mathbb{R}^3$ intersect along a line $L = \Pi_1 \cap \Pi_2$. We can determine the direction and parametric representation of $L$ via two complementary perspectives:

1. **Algebraic Perspective (Solving the Linear System):**
   The points $(x, y, z) \in L$ are precisely the solutions to the $2 \times 3$ linear system:
   $$\begin{cases} A_1 x + B_1 y + C_1 z = d_1, \\ A_2 x + B_2 y + C_2 z = d_2. \end{cases}$$
   Because the two equations are independent (as $n_1 \nparallel n_2$), the solution space has dimension $3 - 2 = 1$. Introducing one free parameter $t \in \mathbb{R}$ (for instance, setting $z = t$ or $x = t$) expresses $(x, y, z)$ in the form $P_0 + t v_{\text{alg}}$, directly revealing a base point $P_0$ and a direction vector $v_{\text{alg}}$.

2. **Geometric Perspective (Cross Product of Normal Vectors):**
   Because the intersection line $L$ lies inside **both** $\Pi_1$ and $\Pi_2$:
   - Any direction vector $v$ of $L$ lies in $\Pi_1$, so $v \perp n_1$ ($v \cdot n_1 = 0$).
   - Any direction vector $v$ of $L$ also lies in $\Pi_2$, so $v \perp n_2$ ($v \cdot n_2 = 0$).
   Since $v$ must be simultaneously orthogonal to both $n_1$ and $n_2$, the cross product
   $$v_{\text{geom}} = n_1 \times n_2$$
   automatically provides a non-zero direction vector for the intersection line $L$.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Algebraic Solution of the System of Equations
We consider the system of two plane equations:
$$\begin{cases}
x + y + z = 3 & \text{(1)} \\
x - y + z = 1 & \text{(2)}
\end{cases}$$
1. **Eliminate $x$ and $z$ to find $y$:**
   Subtracting equation (2) from equation (1) yields:
   $$(x + y + z) - (x - y + z) = 3 - 1 \implies 2y = 2 \implies y = 1.$$
   Thus, every point on the intersection line has constant $y$-coordinate $y = 1$.
2. **Substitute $y = 1$ back to relate $x$ and $z$:**
   Substituting $y = 1$ into equation (1) gives:
   $$x + 1 + z = 3 \implies x + z = 2 \implies x = 2 - z.$$
3. **Parameterize the line:**
   Choosing $z = t \in \mathbb{R}$ as the free parameter, we obtain:
   $$\begin{cases}
   x = 2 - t, \\
   y = 1, \\
   z = t,
   \end{cases} \quad t \in \mathbb{R},$$
   or in vector parametric form:
   $$L: (x, y, z) = (2, 1, 0) + t(-1, 0, 1), \quad t \in \mathbb{R}.$$
   From this parameterization, we read off the base point $P_0 = (2, 1, 0)$ and the algebraic direction vector:
   $$v_1 = (-1, 0, 1).$$
   *(Note: If instead we set $x = s$, we get $(x, y, z) = (0, 1, 2) + s(1, 0, -1)$ with direction vector $(1, 0, -1) = -v_1$.)*

### Method 2: Cross Product of the Normal Vectors
The normal vectors of the two planes $\Pi_1: x + y + z = 3$ and $\Pi_2: x - y + z = 1$ are:
$$n_1 = (1, 1, 1), \qquad n_2 = (1, -1, 1).$$
Computing their cross product gives a direction vector $v_2$ for the intersection line:
$$\begin{aligned}
v_2 = n_1 \times n_2 &= \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & 1 \\ 1 & -1 & 1 \end{vmatrix} \\
&= \mathbf{i}\bigl((1)(1) - (1)(-1)\bigr) - \mathbf{j}\bigl((1)(1) - (1)(1)\bigr) + \mathbf{k}\bigl((1)(-1) - (1)(1)\bigr) \\
&= \mathbf{i}(1 + 1) - \mathbf{j}(1 - 1) + \mathbf{k}(-1 - 1) \\
&= (2, 0, -2).
\end{aligned}$$

### Comparison of the Results
Comparing the direction vector $v_1 = (-1, 0, 1)$ from Method 1 and $v_2 = (2, 0, -2)$ from Method 2, we observe that:
$$v_2 = (2, 0, -2) = -2(-1, 0, 1) = -2v_1.$$
The two vectors are non-zero scalar multiples of one another (collinear). Because a line's direction is defined up to any non-zero scalar factor, both methods describe the **exact same line direction** in $\mathbb{R}^3$. Specifically, the middle component is $0$ in both ($v_y = 0$), reflecting the geometric fact that $y = 1$ is constant along the line, while the $x$- and $z$-components have equal magnitude and opposite signs ($v_x = -v_z$), reflecting $x + z = 2$.

---

## 4. Verification and Consistency Checks

### 1. Substitution of the Parametric Line into Both Planes
For any $t \in \mathbb{R}$, let $X(t) = (2 - t, \, 1, \, t)$:
- **In $\Pi_1: x + y + z = 3$:**
  $$(2 - t) + 1 + t = 3. \quad \checkmark$$
- **In $\Pi_2: x - y + z = 1$:**
  $$(2 - t) - 1 + t = 1. \quad \checkmark$$

### 2. Orthogonality of $v_1$ and $v_2$ with Both Normal Vectors
- $v_1 \cdot n_1 = (-1, 0, 1) \cdot (1, 1, 1) = -1 + 0 + 1 = 0. \quad \checkmark$
- $v_1 \cdot n_2 = (-1, 0, 1) \cdot (1, -1, 1) = -1 + 0 + 1 = 0. \quad \checkmark$
Both checks confirm that the parametric line lies entirely in both planes.
