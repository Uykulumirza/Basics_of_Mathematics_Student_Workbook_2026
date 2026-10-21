# Solution: Exercise 12 — A Normal Vector to a Plane

## 1. Problem Statement
Given $A=(1,0,2)$, $B=(2,1,0)$, and $C=(0,3,1)$. Construct two vectors lying in the plane, find a vector perpendicular to both, and check the perpendicularity using dot products.

---

## 2. Theoretical Background and Concepts
Three non-collinear points $A, B, C \in \mathbb{R}^3$ uniquely determine a two-dimensional plane $\Pi$:
- **Spanning (Tangent) Vectors of the Plane:** Anchoring at point $A$, the displacement vectors $\overrightarrow{AB} = B - A$ and $\overrightarrow{AC} = C - A$ both lie entirely within the plane $\Pi$ and span all directions parallel to $\Pi$.
- **Normal Vector to the Plane:** A non-zero vector $n$ is called a **normal vector** to the plane $\Pi$ if it is perpendicular to every vector lying in $\Pi$. Because every vector in $\Pi$ is a linear combination of $\overrightarrow{AB}$ and $\overrightarrow{AC}$, a vector $n$ is perpendicular to the entire plane if and only if it is perpendicular to both $\overrightarrow{AB}$ and $\overrightarrow{AC}$:
  $$n \cdot \overrightarrow{AB} = 0 \quad \text{and} \quad n \cdot \overrightarrow{AC} = 0.$$
  By the fundamental property of the cross product, $n = \overrightarrow{AB} \times \overrightarrow{AC}$ automatically constructs such a normal vector (and is non-zero whenever $A, B, C$ are non-collinear).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct two vectors lying in the plane
Using $A = (1, 0, 2)$ as the reference point and subtracting its coordinates from $B = (2, 1, 0)$ and $C = (0, 3, 1)$:
$$\overrightarrow{AB} = B - A = (2 - 1,\; 1 - 0,\; 0 - 2) = (1, 1, -2),$$
$$\overrightarrow{AC} = C - A = (0 - 1,\; 3 - 0,\; 1 - 2) = (-1, 3, -1).$$
Both $\overrightarrow{AB} = (1, 1, -2)$ and $\overrightarrow{AC} = (-1, 3, -1)$ lie in the plane determined by $A, B, C$.

### Step 2: Find a vector perpendicular to both using the cross product
We compute the normal vector $n = \overrightarrow{AB} \times \overrightarrow{AC}$:
$$n = \overrightarrow{AB} \times \overrightarrow{AC} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & -2 \\ -1 & 3 & -1 \end{vmatrix} = \left(\begin{vmatrix} 1 & -2 \\ 3 & -1 \end{vmatrix},\; -\begin{vmatrix} 1 & -2 \\ -1 & -1 \end{vmatrix},\; \begin{vmatrix} 1 & 1 \\ -1 & 3 \end{vmatrix}\right)$$
$$n = \big((1)(-1) - (-2)(3),\; -[(1)(-1) - (-2)(-1)],\; (1)(3) - (1)(-1)\big)$$
$$n = \big(-1 + 6,\; -[-1 - 2],\; 3 + 1\big) = (5, 3, 4).$$
Since $n = (5, 3, 4) \neq \mathbf{0}$, the points $A, B, C$ are non-collinear and $n = (5, 3, 4)$ is a normal vector to the plane $ABC$.

### Step 3: Check perpendicularity using dot products
We compute the dot products of $n = (5, 3, 4)$ with $\overrightarrow{AB} = (1, 1, -2)$ and $\overrightarrow{AC} = (-1, 3, -1)$:
- **Dot product with $\overrightarrow{AB}$:**
  $$n \cdot \overrightarrow{AB} = (5, 3, 4) \cdot (1, 1, -2) = (5)(1) + (3)(1) + (4)(-2) = 5 + 3 - 8 = 0.$$
- **Dot product with $\overrightarrow{AC}$:**
  $$n \cdot \overrightarrow{AC} = (5, 3, 4) \cdot (-1, 3, -1) = (5)(-1) + (3)(3) + (4)(-1) = -5 + 9 - 4 = 0.$$

Both dot products equal $0$, confirming that $n = (5, 3, 4)$ is strictly perpendicular to both spanning vectors and therefore normal to the plane $ABC$.

---

## 4. Verification and Consistency Checks

### Orthogonality to the Third Side $\overrightarrow{BC}$
The third side of the triangle, $\overrightarrow{BC} = C - B = (0 - 2, 3 - 1, 1 - 0) = (-2, 2, 1)$, also lies in the plane $ABC$ (since $\overrightarrow{BC} = \overrightarrow{AC} - \overrightarrow{AB}$). Checking its dot product with $n = (5, 3, 4)$:
$$n \cdot \overrightarrow{BC} = (5)(-2) + (3)(2) + (4)(1) = -10 + 6 + 4 = 0.$$

### Plane Equation Check
With normal $n = (5, 3, 4)$ and point $A = (1, 0, 2)$, the Cartesian equation of the plane is $5(x - 1) + 3(y - 0) + 4(z - 2) = 0 \implies 5x + 3y + 4z = 13$. Substituting all three given points:
- For $A(1, 0, 2)$: $5(1) + 3(0) + 4(2) = 5 + 0 + 8 = 13$
- For $B(2, 1, 0)$: $5(2) + 3(1) + 4(0) = 10 + 3 + 0 = 13$
- For $C(0, 3, 1)$: $5(0) + 3(3) + 4(1) = 0 + 9 + 4 = 13$

All three points satisfy the plane equation identically.
