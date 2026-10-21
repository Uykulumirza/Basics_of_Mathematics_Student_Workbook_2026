# Exercise 7: A Line Relative to a Plane — Solution

## 1. Problem Statement

For
$$L:(x,y,z)=(1,1,0)+t(1,-1,0),\qquad \Pi:x+y+z=2,$$
determine whether the line intersects the plane at one point, is parallel to it, or lies in it. Explain the role of the dot product of the direction vector and the normal vector.

---

## 2. Theoretical Background and Concepts

Consider a line $L: X(t) = P_0 + t v$ with base point $P_0 = (x_0, y_0, z_0)$ and direction vector $v = (v_x, v_y, v_z)$, and a plane $\Pi: n \cdot X = d$ with normal vector $n = (A, B, C)$.

### The Role of the Dot Product $v \cdot n$
Substituting the parametric point $X(t) = P_0 + t v$ into the plane equation $n \cdot X = d$ yields a single linear equation for the parameter $t$:
$$n \cdot (P_0 + t v) = d \iff (v \cdot n)\,t = d - n \cdot P_0.$$
Here, the dot product $v \cdot n$ is the **leading coefficient** of $t$, and it has a clear geometric meaning:
- **Remember that $n$ is perpendicular to $\Pi$, while $v$ is parallel to $L$.**
- If **$v \cdot n \neq 0$**, the direction vector $v$ is not perpendicular to the normal $n$, meaning $v$ has a non-zero component along the normal to the plane. As $t$ varies, the point $P_0 + t v$ moves toward or away from $\Pi$ at a non-zero rate $v \cdot n$, so the line **pierces the plane at a unique point** $t^* = \frac{d - n \cdot P_0}{v \cdot n}$.
- If **$v \cdot n = 0$**, the direction vector $v$ is orthogonal to the normal $n$, which means $v$ is **parallel to the plane $\Pi$**. Moving along the line changes the normal coordinate $n \cdot X(t)$ by $(v \cdot n)t = 0$, so every point on $L$ maintains a constant signed distance from $\Pi$. This splits into two subcases depending on the base point $P_0$:
  1. If $n \cdot P_0 = d$ (i.e., $P_0 \in \Pi$), then $0 \cdot t = 0$ holds for **all** $t \in \mathbb{R}$, so the **entire line $L$ lies in the plane $\Pi$** ($L \subset \Pi$).
  2. If $n \cdot P_0 \neq d$ (i.e., $P_0 \notin \Pi$), then $0 \cdot t = d - n \cdot P_0 \neq 0$ has **no solution**, so the line is **strictly parallel to the plane** ($L \cap \Pi = \emptyset$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Extract the Characteristic Vectors and Point
- From the line $L: (x, y, z) = (1, 1, 0) + t(1, -1, 0)$:
  - Base point: $P_0 = (1, 1, 0)$,
  - Direction vector: $v = (1, -1, 0)$.
- From the plane $\Pi: x + y + z = 2$:
  - Normal vector: $n = (1, 1, 1)$,
  - Right-hand constant: $d = 2$.

### Step 2: Compute the Dot Product $v \cdot n$
We evaluate the dot product of the line's direction vector $v$ and the plane's normal vector $n$:
$$v \cdot n = (1, -1, 0) \cdot (1, 1, 1) = (1)(1) + (-1)(1) + (0)(1) = 1 - 1 + 0 = 0.$$
Because $v \cdot n = 0$, the direction vector $v$ is orthogonal to the plane's normal $n$. Geometrically, this tells us immediately that the direction of $L$ is parallel to the plane $\Pi$, so $L$ cannot intersect $\Pi$ at a single point—it either lies completely inside $\Pi$ or is strictly parallel to $\Pi$ with no points in common.

### Step 3: Check Whether the Base Point $P_0$ Lies in the Plane $\Pi$
To distinguish between $L \subset \Pi$ and $L \cap \Pi = \emptyset$, we substitute the base point $P_0 = (1, 1, 0)$ into the plane equation $x + y + z = 2$:
$$n \cdot P_0 = 1 + 1 + 0 = 2 = d.$$
Since the coordinates of $P_0 = (1, 1, 0)$ satisfy the equation of $\Pi$, the base point $P_0$ lies on the plane $\Pi$.

### Step 4: Conclusion
Because the line $L$ passes through a point $P_0 \in \Pi$ and moves in a direction $v$ parallel to $\Pi$ ($v \cdot n = 0$), **the entire line $L$ lies in the plane $\Pi$** ($L \subset \Pi$).

---

## 4. Verification and Consistency Checks

### Direct Algebraic Substitution of a General Point on $L$ into $\Pi$
Any point on $L$ has coordinates $(x(t), y(t), z(t)) = (1 + t, \, 1 - t, \, 0)$ for $t \in \mathbb{R}$. Substituting these expressions into the left-hand side of $\Pi: x + y + z = 2$:
$$\begin{aligned}
x(t) + y(t) + z(t) &= (1 + t) + (1 - t) + 0 \\
&= (1 + 1 + 0) + (1 - 1)t \\
&= 2 + 0t \\
&= 2. \quad \checkmark
\end{aligned}$$
Notice how the coefficient of $t$ is $(1 - 1 + 0) = v \cdot n = 0$, and the constant term is $(1 + 1 + 0) = n \cdot P_0 = 2$. Because the equation $2 = 2$ is an identity satisfied for **every** $t \in \mathbb{R}$, every point of $L$ belongs to $\Pi$.
