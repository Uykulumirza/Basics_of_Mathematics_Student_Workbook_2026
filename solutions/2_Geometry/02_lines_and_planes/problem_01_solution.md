# Exercise 1: Line Through Two Points — Solution

## 1. Problem Statement

Find the equation of the line through $A=(1,2)$ and $B=(4,-1)$ in parametric and general form. Identify a direction vector and an example of a normal vector. Check that both points satisfy the equation you obtain.

---

## 2. Theoretical Background and Concepts

In the Euclidean plane $\mathbb{R}^2$, a line $L$ can be described in two fundamental ways that reflect complementary geometric perspectives:

1. **Parametric Form (Point + Direction):**
   Given a base point $P_0 = (x_0, y_0)$ on the line and a non-zero **direction vector** $v = (v_x, v_y)$ parallel to the line, every point $X = (x, y) \in L$ is obtained by translating $P_0$ by a scalar multiple of $v$:
   $$(x, y) = (x_0, y_0) + t(v_x, v_y), \quad t \in \mathbb{R},$$
   or in coordinate components:
   $$\begin{cases} x(t) = x_0 + t v_x, \\ y(t) = y_0 + t v_y, \end{cases} \quad t \in \mathbb{R}.$$
   If the line is specified by two distinct points $A$ and $B$, the displacement vector $\overrightarrow{AB} = B - A$ serves directly as a direction vector (as does any non-zero scalar multiple of $\overrightarrow{AB}$).

2. **General (Implicit) Form (Point + Normal):**
   Given a non-zero **normal vector** $n = (a, b)$ perpendicular to the line, a point $X = (x, y)$ lies on $L$ if and only if the displacement vector $\overrightarrow{P_0 X} = (x - x_0, y - y_0)$ is orthogonal to $n$:
   $$n \cdot \overrightarrow{P_0 X} = a(x - x_0) + b(y - y_0) = 0 \iff ax + by + c = 0,$$
   where $c = -(a x_0 + b y_0)$.
   In $\mathbb{R}^2$, if $v = (v_x, v_y)$ is a direction vector, rotating $v$ by $90^\circ$ produces a normal vector $n = (-v_y, v_x)$ (or $(v_y, -v_x)$), since their dot product vanishes:
   $$v \cdot n = v_x(-v_y) + v_y(v_x) = 0.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify a Direction Vector
The line passes through $A = (1, 2)$ and $B = (4, -1)$. The displacement vector from $A$ to $B$ lies along the line and therefore defines a direction vector $v$:
$$v = \overrightarrow{AB} = B - A = (4 - 1, -1 - 2) = (3, -3).$$
Since any non-zero scalar multiple of a direction vector defines the same line direction, we can also factor out $3$ to obtain a simpler, collinear direction vector:
$$v_{\text{simp}} = \frac{1}{3}v = (1, -1).$$

### Step 2: Construct the Parametric Form
Choosing $A = (1, 2)$ as the initial (base) point and using $v = (3, -3)$, the vector parametric equation of the line is:
$$(x, y) = (1, 2) + t(3, -3), \quad t \in \mathbb{R},$$
which in component form reads:
$$\begin{cases} x = 1 + 3t, \\ y = 2 - 3t, \end{cases} \quad t \in \mathbb{R}.$$
Equivalently, using the simplified direction vector $v_{\text{simp}} = (1, -1)$ with parameter $s = 3t \in \mathbb{R}$:
$$(x, y) = (1, 2) + s(1, -1) \iff \begin{cases} x = 1 + s, \\ y = 2 - s, \end{cases} \quad s \in \mathbb{R}.$$

### Step 3: Identify a Normal Vector
A normal vector $n = (a, b)$ must be orthogonal to the direction vector ($n \cdot v_{\text{simp}} = 0$). Using $v_{\text{simp}} = (1, -1)$, we swap the coordinates and change one sign:
$$n = (1, 1).$$
Indeed, $n \cdot v_{\text{simp}} = 1(1) + 1(-1) = 0$. (Using $v = (3, -3)$ directly gives the proportional normal vector $n' = (3, 3) = 3(1, 1)$.)

### Step 4: Construct the General Form
Using the point-normal condition $n \cdot \overrightarrow{AX} = 0$ with $A = (1, 2)$ and $n = (1, 1)$:
$$1(x - 1) + 1(y - 2) = 0.$$
Expanding and collecting constants yields the general form of the line:
$$x + y - 3 = 0 \quad (\text{or } x + y = 3).$$
Note that eliminating the parameter $s$ from the parametric equations $x = 1 + s$ and $y = 2 - s$ by adding them together gives $x + y = (1 + s) + (2 - s) = 3$, leading to the exact same equation $x + y - 3 = 0$.

---

## 4. Verification and Consistency Checks

### 1. Checking Both Points in the Parametric Form
- **Point $A = (1, 2)$:**
  - In $(x, y) = (1, 2) + t(3, -3)$, setting $t = 0$ gives $(1 + 0, 2 - 0) = (1, 2) = A$.
  - In $(x, y) = (1, 2) + s(1, -1)$, setting $s = 0$ gives $(1, 2) = A$.
- **Point $B = (4, -1)$:**
  - In $(x, y) = (1, 2) + t(3, -3)$, setting $t = 1$ gives $(1 + 3(1), 2 - 3(1)) = (4, -1) = B$.
  - In $(x, y) = (1, 2) + s(1, -1)$, setting $s = 3$ gives $(1 + 3, 2 - 3) = (4, -1) = B$.

### 2. Checking Both Points in the General Form
Substituting the coordinates into $x + y - 3 = 0$:
- **For $A = (1, 2)$:**
  $$1 + 2 - 3 = 3 - 3 = 0. \quad \checkmark$$
- **For $B = (4, -1)$:**
  $$4 + (-1) - 3 = 3 - 3 = 0. \quad \checkmark$$

### 3. Orthogonality Check Between Direction and Normal Vectors
$$v \cdot n = (3, -3) \cdot (1, 1) = 3(1) + (-3)(1) = 0. \quad \checkmark$$
Both descriptions are completely consistent and describe the unique line passing through $A$ and $B$.
