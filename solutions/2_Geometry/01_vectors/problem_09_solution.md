# Solution: Exercise 9 — Cross Product as a Perpendicular Direction

## 1. Problem Statement
For $u=(1,2,0)$ and $v=(0,1,3)$ compute $u\times v$. Use dot products to check perpendicularity to both vectors, compute $v\times u$, and compare the results.

---

## 2. Theoretical Background and Concepts
For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, their **cross (vector) product** $u \times v$ is defined via the symbolic $3 \times 3$ determinant or $2 \times 2$ minors:
$$u \times v = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ u_1 & u_2 & u_3 \\ v_1 & v_2 & v_3 \end{vmatrix} = \left(u_2 v_3 - u_3 v_2,\; u_3 v_1 - u_1 v_3,\; u_1 v_2 - u_2 v_1\right).$$
Key geometric and algebraic properties of $u \times v$:
1. **Simultaneous Orthogonality:** $u \times v$ is perpendicular to both $u$ and $v$, meaning $(u \times v) \cdot u = 0$ and $(u \times v) \cdot v = 0$. It provides a normal vector to the plane spanned by $u$ and $v$.
2. **Anticommutativity:** Swapping the order of the factors reverses the orientation of the cross product:
   $$v \times u = -(u \times v).$$
   Geometrically, $u \times v$ and $v \times u$ have the exact same magnitude and lie along the same perpendicular line, but point in opposite directions according to the **right-hand rule**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $u \times v$
Given $u = (1, 2, 0)$ and $v = (0, 1, 3)$, we evaluate the cross product using the determinant expansion:
$$u \times v = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 0 \\ 0 & 1 & 3 \end{vmatrix} = \left(\begin{vmatrix} 2 & 0 \\ 1 & 3 \end{vmatrix},\; -\begin{vmatrix} 1 & 0 \\ 0 & 3 \end{vmatrix},\; \begin{vmatrix} 1 & 2 \\ 0 & 1 \end{vmatrix}\right)$$
$$u \times v = \big((2)(3) - (0)(1),\; -[(1)(3) - (0)(0)],\; (1)(1) - (2)(0)\big) = (6, -3, 1).$$

### Step 2: Check perpendicularity to both $u$ and $v$ using dot products
We compute the dot product of $u \times v = (6, -3, 1)$ with $u = (1, 2, 0)$ and with $v = (0, 1, 3)$:
- **With $u$:**
  $$(u \times v) \cdot u = (6, -3, 1) \cdot (1, 2, 0) = (6)(1) + (-3)(2) + (1)(0) = 6 - 6 + 0 = 0.$$
- **With $v$:**
  $$(u \times v) \cdot v = (6, -3, 1) \cdot (0, 1, 3) = (6)(0) + (-3)(1) + (1)(3) = 0 - 3 + 3 = 0.$$

Since both dot products equal $0$, $u \times v = (6, -3, 1)$ is strictly perpendicular to both $u$ and $v$.

### Step 3: Compute $v \times u$
Now we compute $v \times u$ with $v = (0, 1, 3)$ in the first row and $u = (1, 2, 0)$ in the second row:
$$v \times u = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 0 & 1 & 3 \\ 1 & 2 & 0 \end{vmatrix} = \big((1)(0) - (3)(2),\; -[(0)(0) - (3)(1)],\; (0)(2) - (1)(1)\big) = (-6, 3, -1).$$

### Step 4: Compare $u \times v$ and $v \times u$
Comparing $u \times v = (6, -3, 1)$ and $v \times u = (-6, 3, -1)$:
- **Algebraic comparison:** Every component of $v \times u$ has the opposite sign to that of $u \times v$, confirming **anticommutativity**:
  $$v \times u = (-6, 3, -1) = -(6, -3, 1) = -(u \times v).$$
- **Geometric comparison:** Both vectors have the exact same length:
  $$\|u \times v\| = \|v \times u\| = \sqrt{6^2 + (-3)^2 + 1^2} = \sqrt{36 + 9 + 1} = \sqrt{46},$$
  and both lie along the exact same line perpendicular (normal) to the plane spanned by $u$ and $v$. However, they have **opposite orientations** (sense), governed by the right-hand rule: curling the fingers of the right hand from $u$ to $v$ points the thumb along $u \times v$, whereas curling from $v$ to $u$ points the thumb in the opposite direction $v \times u$.

---

## 4. Verification and Consistency Checks

### Lagrange's Identity Check
Lagrange's identity states that $\|u \times v\|^2 = \|u\|^2\|v\|^2 - (u \cdot v)^2$:
- $\|u\|^2 = 1^2 + 2^2 + 0^2 = 5$
- $\|v\|^2 = 0^2 + 1^2 + 3^2 = 10$
- $u \cdot v = (1)(0) + (2)(1) + (0)(3) = 2$
- $\|u\|^2\|v\|^2 - (u \cdot v)^2 = (5)(10) - 2^2 = 50 - 4 = 46$

Since $\|u \times v\|^2 = 6^2 + (-3)^2 + 1^2 = 36 + 9 + 1 = 46$, the magnitude of our cross product is completely verified.
