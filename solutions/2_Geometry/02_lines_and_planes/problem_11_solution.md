# Exercise 11: Plane Containing a Line and a Point — Solution

## 1. Problem Statement

Find the equation of the plane containing
$$(x,y,z)=(1,0,2)+t(1,1,-1)$$
and the point $P=(0,2,1)$. Check that both the entire line and the point lie in the plane you obtain.

---

## 2. Theoretical Background and Concepts

A line $L: X(t) = P_0 + t v$ and an external point $P \notin L$ uniquely determine a plane $\Pi$ in $\mathbb{R}^3$.

### Constructing Two Independent In-Plane Directions
To write the general equation of $\Pi$, we need a normal vector $n$ orthogonal to the plane, which we can obtain as the cross product of **two linearly independent vectors lying in $\Pi$**:
1. **First in-plane vector ($v$):** Since the entire line $L$ lies inside the plane $\Pi$, the direction vector $v$ of the line $L$ is automatically parallel to $\Pi$.
2. **Second in-plane vector ($u$):** Since both the line's base point $P_0 \in L \subset \Pi$ and the given point $P \in \Pi$ belong to the plane, the displacement vector joining them,
   $$u = \overrightarrow{P_0 P} = P - P_0,$$
   also lies completely inside the plane $\Pi$. (Because $P \notin L$, $u$ is not parallel to $v$.)

Taking their cross product produces a normal vector to $\Pi$:
$$n = v \times u = v \times \overrightarrow{P_0 P} \neq \mathbf{0}.$$
With the normal vector $n$ and either $P_0$ or $P$ as the reference point, the plane equation is $n \cdot (X - P_0) = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify Two Vectors in the Plane
From the line equation $L: (x, y, z) = (1, 0, 2) + t(1, 1, -1)$:
- Base point on $L$: $P_0 = (1, 0, 2)$,
- First in-plane direction vector: $v = (1, 1, -1)$.

Using the external point $P = (0, 2, 1)$, we construct the second in-plane vector $u = \overrightarrow{P_0 P}$:
$$u = \overrightarrow{P_0 P} = P - P_0 = (0 - 1, \, 2 - 0, \, 1 - 2) = (-1, 2, -1).$$

### Step 2: Compute the Normal Vector via the Cross Product
We compute the cross product $n = v \times u$:
$$\begin{aligned}
n &= v \times u = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & -1 \\ -1 & 2 & -1 \end{vmatrix} \\
&= \mathbf{i}\bigl((1)(-1) - (-1)(2)\bigr) - \mathbf{j}\bigl((1)(-1) - (-1)(-1)\bigr) + \mathbf{k}\bigl((1)(2) - (1)(-1)\bigr) \\
&= \mathbf{i}(-1 + 2) - \mathbf{j}(-1 - 1) + \mathbf{k}(2 + 1) \\
&= 1\mathbf{i} - (-2)\mathbf{j} + 3\mathbf{k} \\
&= (1, 2, 3).
\end{aligned}$$
Since $n = (1, 2, 3) \neq (0, 0, 0)$, the vectors $v$ and $u$ are linearly independent (confirming $P \notin L$), and $n = (1, 2, 3)$ is a normal vector to the unique plane containing $L$ and $P$.

### Step 3: Write the Equation of the Plane
Using the point-normal form $n \cdot (X - P_0) = 0$ with $P_0 = (1, 0, 2)$ and $n = (1, 2, 3)$:
$$1(x - 1) + 2(y - 0) + 3(z - 2) = 0.$$
Expanding and simplifying:
$$x - 1 + 2y + 3z - 6 = 0 \iff x + 2y + 3z - 7 = 0 \quad (\text{or } x + 2y + 3z = 7).$$

---

## 4. Verification and Consistency Checks

### 1. Checking That the Point $P = (0, 2, 1)$ Lies in the Plane
Substituting $x = 0, y = 2, z = 1$ into $x + 2y + 3z = 7$:
$$0 + 2(2) + 3(1) = 0 + 4 + 3 = 7. \quad \checkmark$$

### 2. Checking That the Entire Line $L$ Lies in the Plane
An arbitrary point on the line $L$ has coordinates $(x(t), y(t), z(t)) = (1 + t, \, t, \, 2 - t)$ for $t \in \mathbb{R}$. Substituting these coordinates into the left-hand side of $x + 2y + 3z = 7$:
$$\begin{aligned}
x(t) + 2y(t) + 3z(t) &= (1 + t) + 2(t) + 3(2 - t) \\
&= 1 + t + 2t + 6 - 3t \\
&= (1 + 6) + (1 + 2 - 3)t \\
&= 7 + 0t \\
&= 7. \quad \checkmark
\end{aligned}$$
Because the parameter $t$ cancels out completely ($v \cdot n = 1 + 2 - 3 = 0$) and the constant equals $7$ ($P_0 \cdot n = 1 + 0 + 6 = 7$), every point on $L$ for every $t \in \mathbb{R}$ satisfies the plane equation $x + 2y + 3z = 7$.
