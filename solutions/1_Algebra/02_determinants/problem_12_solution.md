# Solution to Exercise 12: A Parameter Revealed by a Row Operation

## 1. Problem Statement

Given the parameter-dependent matrix:
$$A(t) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & t \\ 0 & 1 & 1 \end{pmatrix}, \qquad t \in \mathbb{R}$$

1. Perform the elementary row operation $R_2 \leftarrow R_2 - 2R_1$.
2. Use the resulting matrix structure to compute $\det A(t)$.
3. Find all values of $t$ for which the matrix $A(t)$ is not invertible.
4. Explain what special geometric/algebraic relationship occurs between the rows of the matrix for the specific value of $t$ found.

---

## 2. Theoretical Background and Concepts

### Determinant Invariance Under Row Addition
The elementary row operation $R_2 \leftarrow R_2 - 2R_1$ adds a scalar multiple of row 1 to row 2. 
By the properties of determinants:
$$\det(A(t)) = \det(A'(t))$$
where $A'(t)$ is the matrix after the operation.

### Invertibility and Singularity
A square matrix $A(t)$ is **not invertible** if and only if its determinant is zero:
$$A(t) \text{ is singular} \iff \det A(t) = 0$$

### Linear Dependence of Rows
If a parameter value causes one row of a matrix to become a scalar multiple of another, the rows become linearly dependent. Geometrically, this means the rows do not span the full space $\mathbb{R}^3$, the rank drops strictly below $3$, and the volume of the parallelepiped spanned by the row vectors collapses to zero.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Perform the Specified Row Operation
Apply $R_2 \leftarrow R_2 - 2R_1$ to matrix $A(t)$:
- Row 2: $R_2 = (2, 4, t)$
- Multiplied Row 1: $2R_1 = 2(1, 2, 3) = (2, 4, 6)$
- New Row 2:
  $$R_2 - 2R_1 = (2 - 2, \; 4 - 4, \; t - 6) = (0, 0, t - 6)$$

The resulting simplified matrix is:
$$A'(t) = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & t - 6 \\ 0 & 1 & 1 \end{pmatrix}$$

Because this was a row addition operation, the determinant is preserved:
$$\det A(t) = \det A'(t)$$

---

### Step 2: Compute $\det A'(t)$
Notice the structure of $A'(t)$: the first column contains zeros in positions $(2, 1)$ and $(3, 1)$. 
Expanding along the **first column**:
$$\det A'(t) = 1 \cdot \begin{vmatrix} 0 & t - 6 \\ 1 & 1 \end{vmatrix} - 0 \cdot C_{21} + 0 \cdot C_{31}$$

Evaluate the $2 \times 2$ determinant:
$$\begin{vmatrix} 0 & t - 6 \\ 1 & 1 \end{vmatrix} = (0)(1) - (t - 6)(1) = -(t - 6) = 6 - t$$

Thus:
$$\det A(t) = 6 - t$$

---

### Step 3: Determine Values of $t$ for Non-Invertibility
The matrix is not invertible if and only if $\det A(t) = 0$:
$$6 - t = 0 \implies t = 6$$

Therefore, the matrix $A(t)$ is not invertible precisely when:
$$t = 6$$

---

### Step 4: Explanation of the Special Row Relationship for $t = 6$
Substitute $t = 6$ into the original matrix:
$$A(6) = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{pmatrix}$$

Observe the relationship between row 1 and row 2:
$$R_2 = (2, 4, 6) = 2 \cdot (1, 2, 3) = 2 R_1$$

- **Exact Proportionality:** When $t = 6$, the second row becomes an **exact scalar multiple** of the first row ($R_2 = 2R_1$).
- **Row of Zeros:** When the operation $R_2 \leftarrow R_2 - 2R_1$ is performed, the entire second row vanishes into zeros: $(0, 0, 0)$.
- **Rank Deficiency:** Because row 2 provides no new information and is entirely redundant, the row vectors span only a 2-dimensional plane in $\mathbb{R}^3$. The rank of the matrix drops to $2 < 3$, rendering the transformation non-invertible.

---

## 4. Verification and Consistency Checks

1. **Direct Calculation via Sarrus' Rule on $A(t)$:**
   $$\begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 4 & t & 2 & 4 \\
   0 & 1 & 1 & 0 & 1
   \end{array}$$
   - Positive diagonals:
     $$P = (1 \cdot 4 \cdot 1) + (2 \cdot t \cdot 0) + (3 \cdot 2 \cdot 1) = 4 + 0 + 6 = 10$$
   - Negative antidiagonals:
     $$N = (0 \cdot 4 \cdot 3) + (1 \cdot t \cdot 1) + (1 \cdot 2 \cdot 2) = 0 + t + 4 = t + 4$$
   Subtracting:
   $$\det A(t) = P - N = 10 - (t + 4) = 6 - t \quad \checkmark$$

2. **Null Space Check for $t = 6$:**
   Solving $A(6) x = 0$:
   $$\begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} -1 \\ -1 \\ 1 \end{pmatrix} = \begin{pmatrix} -1 - 2 + 3 \\ -2 - 4 + 6 \\ 0 - 1 + 1 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$
   The non-zero vector $x = (-1, -1, 1)^T$ belongs to the kernel, explicitly verifying that $A(6)$ is singular.

