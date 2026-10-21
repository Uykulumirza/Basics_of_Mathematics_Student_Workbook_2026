# Exercise 14: Contrast: Intersection and Parallelism — Solution

## 1. Problem Statement

From the point $P=(0,0,1)$, two lines are drawn with direction vectors
$$v_1=(2,1,-1),\qquad v_2=(2,1,0).$$
For each line, analyze its position relative to the plane $z=0$.

For the line that intersects the plane, find the intersection point. For the other line, explain how you can recognize parallelism without solving an equation.

---

## 2. Theoretical Background and Concepts

The plane $\Pi: z = 0$ is the horizontal **$xy$-coordinate plane** in $\mathbb{R}^3$. Its normal vector is the standard unit vector along the vertical axis:
$$n = \mathbf{k} = (0, 0, 1).$$
For any line $L: (x, y, z) = P + t v$ starting from $P = (x_0, y_0, z_0)$ with direction vector $v = (v_x, v_y, v_z)$, the dot product with the normal vector $n = (0, 0, 1)$ simply extracts the **$z$-component (vertical rate of change)** of the direction vector:
$$v \cdot n = (v_x, v_y, v_z) \cdot (0, 0, 1) = v_z.$$
Consequently, the height $z(t)$ of a point on the line above the $xy$-plane evolves according to:
$$z(t) = z_0 + t v_z.$$
This provides an immediate, transparent geometric interpretation:
- **Case 1 ($v_z \neq 0$):** The direction vector has a non-zero vertical component, so the line rises and falls as $t$ varies. It must cross every horizontal plane—in particular $z = 0$—at a unique point.
- **Case 2 ($v_z = 0$):** The direction vector is purely horizontal ($v \cdot n = 0$). Moving along the line changes $x$ and $y$ while keeping the altitude $z(t) = z_0$ completely constant. If the starting point has $z_0 \neq 0$, the line stays forever at height $z_0$ and never touches the plane $z = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Write the Parametric Equations of Both Lines
Both lines pass through the initial point $P = (0, 0, 1)$, which sits at height $z_0 = 1$ above the plane $z = 0$:
1. **First line $L_1$** (with direction vector $v_1 = (2, 1, -1)$):
   $$L_1: (x, y, z) = (0, 0, 1) + t(2, 1, -1) = (2t, \, t, \, 1 - t), \quad t \in \mathbb{R}.$$
2. **Second line $L_2$** (with direction vector $v_2 = (2, 1, 0)$):
   $$L_2: (x, y, z) = (0, 0, 1) + s(2, 1, 0) = (2s, \, s, \, 1), \quad s \in \mathbb{R}.$$

### Step 2: Analyze $L_1$ and Find Its Intersection Point with $z = 0$
For $L_1$, the direction vector $v_1 = (2, 1, -1)$ has vertical component $v_{1,z} = v_1 \cdot n = -1 \neq 0$. Because $v_1$ has a non-zero vertical component, $L_1$ is not parallel to the plane $z = 0$ and intersects it at a single point.

Setting the $z$-coordinate of $L_1$ equal to $0$:
$$z(t) = 1 - t = 0 \implies t = 1.$$
Substituting $t = 1$ into the parametric equation of $L_1$ gives the intersection point $Q_1$:
$$Q_1 = (2(1), \, 1, \, 1 - 1) = (2, 1, 0).$$

### Step 3: Analyze $L_2$ and Recognize Parallelism Without Solving an Equation
For $L_2$, the direction vector is $v_2 = (2, 1, 0)$. We can recognize immediately—**without setting up or solving any equation**—that $L_2$ is strictly parallel to the plane $z = 0$ for two equivalent geometric reasons:
1. **Via the third coordinate (altitude invariance):** The third component of $v_2 = (2, 1, 0)$ is zero ($v_{2,z} = 0$). This means moving along $L_2$ produces zero change in the $z$-coordinate. Since the line starts at $P = (0, 0, 1)$ where $z = 1$, every point on $L_2$ lies in the horizontal plane $z = 1$, which is parallel to $z = 0$ at a constant vertical distance of $1$.
2. **Via the normal vector:** The normal to the plane $z = 0$ is $n = (0, 0, 1)$. By inspection, $v_2 \cdot n = (2, 1, 0) \cdot (0, 0, 1) = 0$, so $v_2$ is orthogonal to $n$ (hence parallel to the plane $z = 0$), while the starting point $P = (0, 0, 1)$ does not lie in $z = 0$ since $1 \neq 0$.

Thus, **$L_2$ is strictly parallel to the plane $z = 0$** and has no intersection points with it ($L_2 \cap \Pi = \emptyset$).

---

## 4. Verification and Consistency Checks

### 1. Verification of the Intersection Point $Q_1 = (2, 1, 0)$ for $L_1$
- **On $L_1$:** Setting $t = 1$ in $(0, 0, 1) + t(2, 1, -1)$ yields $(0 + 2, 0 + 1, 1 - 1) = (2, 1, 0) = Q_1$. $\checkmark$
- **On the plane $z = 0$:** The $z$-coordinate of $Q_1 = (2, 1, 0)$ is $z = 0$. $\checkmark$

### 2. Verification of No Intersection for $L_2$
For any $s \in \mathbb{R}$, a point on $L_2$ is $(2s, s, 1)$. Attempting to impose the plane condition $z = 0$ yields $1 = 0$, an immediate contradiction independent of $s$, confirming $L_2 \cap \{z = 0\} = \emptyset$.
