# Solution to Exercise 8: Inverse of a Geometric Transformation

## 1. Problem Statement

Given the scaling matrix:
$$S = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix}$$

1. Find the inverse matrix $S^{-1}$.
2. Explain geometrically what the transformation $S$ does to the plane, and what the inverse transformation $S^{-1}$ does.
3. Test and verify the sequential action of the pair $S$ and $S^{-1}$ on a simple concrete vector.

---

## 2. Theoretical Background and Concepts

### Geometric Interpretations of Matrix Transformations
A $2 \times 2$ matrix $M$ acts on coordinates $(x, y)^T \in \mathbb{R}^2$ as a linear map:
$$T_M\begin{pmatrix} x \\ y \end{pmatrix} = M \begin{pmatrix} x \\ y \end{pmatrix}$$

For a diagonal matrix $D = \begin{pmatrix} k_1 & 0 \\ 0 & k_2 \end{pmatrix}$:
$$D \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} k_1 x \\ k_2 y \end{pmatrix}$$
- The coordinate axes act as invariant directions (eigenvectors).
- The factor $k_1$ represents non-uniform scaling (stretching/compressing) along the $x$-axis.
- The factor $k_2$ represents non-uniform scaling along the $y$-axis.

### The Inverse as an "Undoing" Operation
The inverse matrix $M^{-1}$ represents the geometric operation that restores every point to its original position:
$$(T_{M^{-1}} \circ T_M)(v) = M^{-1}(M v) = I v = v$$
For diagonal scaling with non-zero factors, inverting the map means scaling by the reciprocal factors $\frac{1}{k_1}$ and $\frac{1}{k_2}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the Inverse Matrix $S^{-1}$
Matrix $S$ is diagonal with non-zero diagonal entries:
$$s_{11} = 2, \qquad s_{22} = \frac{1}{2}$$

The inverse of a diagonal matrix is formed by inverting each diagonal entry:
$$S^{-1} = \begin{pmatrix} \frac{1}{s_{11}} & 0 \\ 0 & \frac{1}{s_{22}} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{1/2} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix}$$

We can also confirm this via the $2 \times 2$ formula:
$$\det S = (2)\left(\frac{1}{2}\right) - (0)(0) = 1$$
$$S^{-1} = \frac{1}{1} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix}$$

---

### Step 2: Geometric Explanation

1. **Action of Transformation $S$:**
   Applying $S$ to a generic point $(x, y)^T$:
   $$S \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2x \\ \frac{1}{2}y \end{pmatrix}$$
   - **Horizontal Action:** Stretches the plane horizontally by a factor of $2$ (doubling the distance of every point from the $y$-axis).
   - **Vertical Action:** Compresses the plane vertically by a factor of $\frac{1}{2}$ (halving the distance of every point from the $x$-axis).
   - **Area Preservation:** Since $\det S = 1$, the transformation preserves areas (e.g., transforming a circle into an ellipse of identical area).

2. **Action of Inverse Transformation $S^{-1}$:**
   Applying $S^{-1}$ to a point $(u, v)^T$:
   $$S^{-1} \begin{pmatrix} u \\ v \end{pmatrix} = \begin{pmatrix} \frac{1}{2}u \\ 2v \end{pmatrix}$$
   - **Horizontal Action:** Compresses the plane horizontally by a factor of $\frac{1}{2}$ (halving horizontal coordinates).
   - **Vertical Action:** Stretches the plane vertically by a factor of $2$ (doubling vertical coordinates).
   - **Net Effect:** Undoes the horizontal stretching and vertical compression performed by $S$, exactly restoring the original geometric shape and location.

---

### Step 3: Test on a Concrete Vector

Choose the vector $v = \begin{pmatrix} 3 \\ 4 \end{pmatrix} \in \mathbb{R}^2$.

1. **Apply the Forward Transformation $S$:**
   $$v' = S v = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} 2(3) \\ \frac{1}{2}(4) \end{pmatrix} = \begin{pmatrix} 6 \\ 2 \end{pmatrix}$$
   The point $(3, 4)$ is mapped to $(6, 2)$ — horizontally stretched from $3$ to $6$, vertically compressed from $4$ to $2$.

2. **Apply the Inverse Transformation $S^{-1}$ to $v'$:**
   $$v'' = S^{-1} v' = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 6 \\ 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(6) \\ 2(2) \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} = v$$

The original vector $v = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$ is recovered identically.

---

## 4. Verification and Consistency Checks

1. **Matrix Product Verification:**
   $$S S^{-1} = \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2\left(\frac{1}{2}\right) & 0 \\ 0 & \left(\frac{1}{2}\right)(2) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$
   $$S^{-1} S = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & \frac{1}{2} \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$

2. **Action on Basis Vectors (Unit Square):**
   - $e_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \xrightarrow{S} \begin{pmatrix} 2 \\ 0 \end{pmatrix} \xrightarrow{S^{-1}} \begin{pmatrix} 1 \\ 0 \end{pmatrix} = e_1$
   - $e_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \xrightarrow{S} \begin{pmatrix} 0 \\ 1/2 \end{pmatrix} \xrightarrow{S^{-1}} \begin{pmatrix} 0 \\ 1 \end{pmatrix} = e_2$
   The unit square $[0, 1] \times [0, 1]$ transforms under $S$ into the rectangle $[0, 2] \times [0, 1/2]$ (both having area $1$), and $S^{-1}$ maps this rectangle back to the unit square.
