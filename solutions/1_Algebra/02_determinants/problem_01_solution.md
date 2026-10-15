# Solution to Exercise 1: Determinant of a 2×2 Matrix

## 1. Problem Statement

Compute the determinants of the following two matrices:
$$A = \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix}$$

Determine which matrix is invertible and justify your answer based on the computed determinants.

---

## 2. Theoretical Background and Concepts

### Determinant of a $2 \times 2$ Matrix
For an arbitrary $2 \times 2$ matrix $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$, the determinant is defined as the difference between the product of the main diagonal entries and the product of the antidiagonal entries:
$$\det M = \begin{vmatrix} a & b \\ c & d \end{vmatrix} = ad - bc$$

### Invertibility Criterion (Non-singularity)
A square matrix $M \in M_n(\mathbb{R})$ is **invertible** (or non-singular) if and only if its determinant is non-zero:
$$M \text{ is invertible} \iff \det M \ne 0$$
- If $\det M \ne 0$, the inverse matrix $M^{-1}$ exists. For a $2 \times 2$ matrix, it is given explicitly by:
  $$M^{-1} = \frac{1}{\det M} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$
- If $\det M = 0$, the matrix is **singular**. Its columns (and rows) are linearly dependent, its rank is strictly less than $n$, and no inverse matrix exists.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$
Given:
$$A = \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix}$$
Here $a = 3$, $b = -2$, $c = 5$, and $d = 4$. Applying the formula:
$$\det A = (3)(4) - (-2)(5) = 12 - (-10) = 12 + 10 = 22$$

### Step 2: Compute $\det B$
Given:
$$B = \begin{pmatrix} 1 & 7 \\ 2 & 14 \end{pmatrix}$$
Here $a = 1$, $b = 7$, $c = 2$, and $d = 14$. Applying the formula:
$$\det B = (1)(14) - (7)(2) = 14 - 14 = 0$$

### Step 3: Determine Invertibility
- **Matrix $A$:**
  $$\det A = 22 \ne 0$$
  Since its determinant is non-zero, **matrix $A$ is invertible**.
  
- **Matrix $B$:**
  $$\det B = 0$$
  Since its determinant equals zero, **matrix $B$ is not invertible** (it is singular).

---

## 4. Verification and Consistency Checks

1. **Explicit Inverse Construction for Matrix $A$:**
   Using the explicit inversion formula for $A$:
   $$A^{-1} = \frac{1}{22} \begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix}$$
   We verify that $A A^{-1} = I$:
   $$A A^{-1} = \begin{pmatrix} 3 & -2 \\ 5 & 4 \end{pmatrix} \cdot \frac{1}{22} \begin{pmatrix} 4 & 2 \\ -5 & 3 \end{pmatrix} = \frac{1}{22} \begin{pmatrix} 3(4) + (-2)(-5) & 3(2) + (-2)(3) \\ 5(4) + 4(-5) & 5(2) + 4(3) \end{pmatrix} = \frac{1}{22} \begin{pmatrix} 22 & 0 \\ 0 & 22 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$$
   The inverse is confirmed.

2. **Linear Dependence Check for Matrix $B$:**
   Notice the relationship between the rows of $B$:
   $$R_2 = \begin{pmatrix} 2 & 14 \end{pmatrix} = 2 \cdot \begin{pmatrix} 1 & 7 \end{pmatrix} = 2 R_1$$
   Because row 2 is a scalar multiple of row 1, the rows are linearly dependent. In any matrix with linearly dependent rows, the determinant is identically zero. This structural dependency independently verifies that $\det B = 0$.
