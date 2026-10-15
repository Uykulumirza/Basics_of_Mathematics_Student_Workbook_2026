# Solution to Exercise 9: Area and the Determinant

## 1. Problem Statement

The vectors:
$$u = \begin{pmatrix} 3 \\ 1 \end{pmatrix}, \qquad v = \begin{pmatrix} 1 \\ 4 \end{pmatrix}$$
span a parallelogram in the Cartesian plane $\mathbb{R}^2$.

1. Compute the area of this parallelogram using a determinant.
2. Form the matrix with the vectors in reverse order and compute its determinant.
3. Explain what changes in the determinant and what does not change in the geometric area.

---

## 2. Theoretical Background and Concepts

### Geometric Interpretation of the $2 \times 2$ Determinant
For two vectors $u = \begin{pmatrix} u_1 \\ u_2 \end{pmatrix}$ and $v = \begin{pmatrix} v_1 \\ v_2 \end{pmatrix}$ in $\mathbb{R}^2$, the determinant of the matrix $M = \begin{pmatrix} u & v \end{pmatrix} = \begin{pmatrix} u_1 & v_1 \\ u_2 & v_2 \end{pmatrix}$ represents the **signed (oriented) area** of the parallelogram spanned by $u$ and $v$:
$$\det(u, v) = u_1 v_2 - u_2 v_1$$

### Oriented Area vs. Geometric Area
- **Geometric Area:** Physical area is a non-negative scalar quantity defined as the absolute value of the determinant:
  $$\text{Area} = \left|\det(u, v)\right|$$
- **Orientation (Sign):**
  - $\det(u, v) > 0$: The ordered pair $(u, v)$ forms a **positive (counterclockwise)** orientation (moving from $u$ to $v$ corresponds to a counterclockwise rotation through an angle in $(0, \pi)$).
  - $\det(u, v) < 0$: The ordered pair $(u, v)$ forms a **negative (clockwise)** orientation.
- **Alternating Property:** Swapping the two column vectors reverses the orientation, negating the sign of the determinant:
  $$\det(v, u) = -\det(u, v)$$
  while leaving the absolute magnitude (the physical area) completely invariant.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Area using Matrix $M_1 = \begin{pmatrix} u & v \end{pmatrix}$
Arrange vectors $u$ and $v$ as column vectors:
$$M_1 = \begin{pmatrix} 3 & 1 \\ 1 & 4 \end{pmatrix}$$

Compute the determinant:
$$\det M_1 = (3)(4) - (1)(1) = 12 - 1 = 11$$

Since the determinant is positive, the geometric area of the parallelogram is:
$$\text{Area} = |\det M_1| = 11$$

---

### Step 2: Compute Determinant with Reversed Vector Order
Reverse the order of vectors to form matrix $M_2 = \begin{pmatrix} v & u \end{pmatrix}$:
$$M_2 = \begin{pmatrix} 1 & 3 \\ 4 & 1 \end{pmatrix}$$

Compute the determinant:
$$\det M_2 = (1)(1) - (3)(4) = 1 - 12 = -11$$

The geometric area computed from $M_2$ is:
$$\text{Area} = |\det M_2| = |-11| = 11$$

---

### Step 3: Explanation of What Changes and What Remains Invariant

1. **What changes:**
   - **The sign of the determinant:** The value flips from $+11$ to $-11$.
   - **The orientation of the basis:** In $M_1$, rotating from vector $u = (3, 1)$ to vector $v = (1, 4)$ follows a **counterclockwise** direction, which corresponds to the standard positive orientation of the Cartesian plane. In $M_2$, rotating from $v = (1, 4)$ to $u = (3, 1)$ follows a **clockwise** direction, producing a negative sign.

2. **What does not change:**
   - **The geometric area:** The physical shape, boundary, and area enclosed by the parallelogram on the plane remain strictly identical:
     $$\text{Area} = 11$$
   The area of a physical 2D region depends only on the geometry of the spanning vectors, completely independent of the order in which they are labeled or arranged in a matrix.

---

## 4. Verification and Consistency Checks

1. **Verification via the Cross Product Formula:**
   Embedding vectors $u$ and $v$ into $\mathbb{R}^3$ as $u = (3, 1, 0)$ and $v = (1, 4, 0)$:
   $$u \times v = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 3 & 1 & 0 \\ 1 & 4 & 0 \end{vmatrix} = \mathbf{k}(3 \cdot 4 - 1 \cdot 1) = 11 \mathbf{k}$$
   The area of the parallelogram is the norm of the cross product vector:
   $$\text{Area} = \|u \times v\| = \|11 \mathbf{k}\| = 11 \quad \checkmark$$

2. **Verification via Geometric Base $\times$ Height:**
   - Length of base $u$: $\|u\| = \sqrt{3^2 + 1^2} = \sqrt{10}$.
   - Projection of $v$ onto $u$:
     $$v_{\parallel} = \frac{u \cdot v}{\|u\|^2} u = \frac{3(1) + 1(4)}{10} u = \frac{7}{10} \begin{pmatrix} 3 \\ 1 \end{pmatrix} = \begin{pmatrix} 2.1 \\ 0.7 \end{pmatrix}$$
   - Height vector: $v_{\perp} = v - v_{\parallel} = (1, 4) - (2.1, 0.7) = (-1.1, 3.3)$.
   - Height: $\|v_{\perp}\| = \sqrt{(-1.1)^2 + 3.3^2} = \sqrt{1.21 + 10.89} = \sqrt{12.1} = \frac{11}{\sqrt{10}}$.
   - Area: $\|u\| \cdot \|v_{\perp}\| = \sqrt{10} \cdot \frac{11}{\sqrt{10}} = 11 \quad \checkmark$.

