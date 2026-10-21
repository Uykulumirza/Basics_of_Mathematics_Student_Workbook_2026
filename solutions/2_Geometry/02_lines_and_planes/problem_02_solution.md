# Exercise 2: A Line in Space — Solution

## 1. Problem Statement

Given
$$L:(x,y,z)=(2,-1,3)+t(1,2,-2).$$
State a point on the line and its direction vector, check whether $P=(4,3,-1)$ lies on $L$, and find the point corresponding to $t=-1$.

---

## 2. Theoretical Background and Concepts

In three-dimensional space $\mathbb{R}^3$, a single linear equation defines a plane rather than a line. Consequently, the most direct way to represent a line $L \subset \mathbb{R}^3$ is the **vector parametric form**:
$$(x, y, z) = P_0 + t v = (x_0, y_0, z_0) + t(v_x, v_y, v_z), \quad t \in \mathbb{R}.$$
- **Geometric meaning of $P_0 = (x_0, y_0, z_0)$:** This is the **initial (or base) point** on the line corresponding to the parameter value $t = 0$.
- **Geometric meaning of $v = (v_x, v_y, v_z)$:** This is the **direction vector** of the line. For each unit increment in $t$, the position on the line shifts by the vector $v$.
- **Point membership test:** A point $P = (x_P, y_P, z_P)$ lies on the line $L$ if and only if there exists a **single, consistent** real parameter $t \in \mathbb{R}$ that simultaneously satisfies all three coordinate equations:
  $$\begin{cases} x_0 + t v_x = x_P, \\ y_0 + t v_y = y_P, \\ z_0 + t v_z = z_P. \end{cases}$$
  Geometrically, this condition is equivalent to requiring that the displacement vector $\overrightarrow{P_0 P} = P - P_0$ is a scalar multiple of the direction vector $v$, i.e., $\overrightarrow{P_0 P} = t v$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify a Point on the Line and the Direction Vector
Comparing the given equation
$$L: (x, y, z) = (2, -1, 3) + t(1, 2, -2)$$
with the standard template $(x, y, z) = P_0 + t v$:
- **Initial (base) point on $L$ (at $t = 0$):**
  $$P_0 = (2, -1, 3).$$
- **Direction vector of $L$:**
  $$v = (1, 2, -2).$$

### Step 2: Check Whether $P = (4, 3, -1)$ Lies on $L$
Writing the parametric equation of $L$ in coordinate form gives:
$$\begin{cases} x(t) = 2 + t, \\ y(t) = -1 + 2t, \\ z(t) = 3 - 2t. \end{cases}$$
We equate $(x(t), y(t), z(t))$ to the coordinates of $P = (4, 3, -1)$:
$$\begin{cases} 2 + t = 4 & \text{(1)} \\ -1 + 2t = 3 & \text{(2)} \\ 3 - 2t = -1 & \text{(3)} \end{cases}$$
Solving each equation for $t$:
1. From equation (1):
   $$2 + t = 4 \implies t = 4 - 2 = 2.$$
2. From equation (2):
   $$-1 + 2t = 3 \implies 2t = 4 \implies t = 2.$$
3. From equation (3):
   $$3 - 2t = -1 \implies -2t = -4 \implies t = 2.$$

Because all three coordinate equations yield the **exact same parameter value** $t = 2$, the system is consistent. Therefore, **yes, the point $P = (4, 3, -1)$ lies on the line $L$** (specifically, at $t = 2$).

### Step 3: Find the Point Corresponding to $t = -1$
Substituting $t = -1$ into the parametric equation of $L$:
$$\begin{aligned}
P_{-1} &= (2, -1, 3) + (-1)(1, 2, -2) \\
&= (2 - 1, \, -1 - 2, \, 3 - (-2)) \\
&= (1, -3, 5).
\end{aligned}$$
Thus, the point on $L$ corresponding to $t = -1$ is $P_{-1} = (1, -3, 5)$.

---

## 4. Verification and Consistency Checks

### 1. Collinearity Check for $P = (4, 3, -1)$
The displacement vector from the base point $P_0 = (2, -1, 3)$ to $P = (4, 3, -1)$ is:
$$\overrightarrow{P_0 P} = P - P_0 = (4 - 2, \, 3 - (-1), \, -1 - 3) = (2, 4, -4).$$
Comparing $\overrightarrow{P_0 P}$ with the direction vector $v = (1, 2, -2)$, we observe:
$$\overrightarrow{P_0 P} = (2, 4, -4) = 2(1, 2, -2) = 2v.$$
This confirms geometrically that moving from $P_0$ by twice the direction vector $v$ lands directly on $P$.

### 2. Collinearity Check for $P_{-1} = (1, -3, 5)$
The displacement vector from $P_0 = (2, -1, 3)$ to $P_{-1} = (1, -3, 5)$ is:
$$\overrightarrow{P_0 P_{-1}} = (1 - 2, \, -3 - (-1), \, 5 - 3) = (-1, -2, 2) = -1 \cdot (1, 2, -2) = -v,$$
confirming that $P_{-1}$ is reached from $P_0$ by stepping one unit in the direction opposite to $v$.
