# Solution to Exercise 5: A 3×3 Matrix Inversion via Gauss–Jordan

## 1. Problem Statement

Given the $3 \times 3$ matrix:
$$A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{pmatrix}$$

1. Use the Gauss–Jordan elimination method to compute the inverse matrix $A^{-1}$.
2. Check the validity of the computed inverse by performing explicit matrix multiplication with $A$.

---

## 2. Theoretical Background and Concepts

### Gauss–Jordan Inversion for $3 \times 3$ Matrices
To compute the inverse of a $3 \times 3$ matrix:
1. Construct the block augmented matrix $[A \mid I_3]$ of size $3 \times 6$:
   $$[A \mid I_3] = \left(\begin{array}{ccc|ccc} a_{11} & a_{12} & a_{13} & 1 & 0 & 0 \\ a_{21} & a_{22} & a_{23} & 0 & 1 & 0 \\ a_{31} & a_{32} & a_{33} & 0 & 0 & 1 \end{array}\right)$$
2. Apply elementary row operations in two systematic phases:
   - **Forward Elimination:** Create zeros below all diagonal pivot elements to achieve upper-triangular echelon form.
   - **Back-Substitution:** Normalize diagonal pivots to $1$ and create zeros above all diagonal pivots.
3. If the left $3 \times 3$ block successfully transforms into $I_3$, the right $3 \times 3$ block is the unique inverse matrix $A^{-1}$. If an entire row of zeros appears on the left block during elimination, $\operatorname{rank}(A) < 3$ and $A$ is singular (non-invertible).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Initialize the Augmented Matrix
Write matrix $A$ augmented with the identity matrix $I_3$:
$$[A \mid I_3] = \left(\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 1 & 0 & 1 & 0 & 0 & 1 \end{array}\right)$$

---

### Step 2: Clear Column 1 Below the First Pivot
The pivot at $(1, 1)$ is $1$. The entry at $(2, 1)$ is already $0$.
Eliminate the entry at $(3, 1)$ by performing:
$$R_3 \leftarrow R_3 - R_1$$

Row calculation:
$$(1, 0, 1 \mid 0, 0, 1) - (1, 1, 0 \mid 1, 0, 0) = (0, -1, 1 \mid -1, 0, 1)$$

The augmented matrix becomes:
$$\left(\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & -1 & 1 & -1 & 0 & 1 \end{array}\right)$$

---

### Step 3: Clear Column 2 Below the Second Pivot
The pivot at $(2, 2)$ is $1$. Eliminate the entry at $(3, 2)$ by performing:
$$R_3 \leftarrow R_3 + R_2$$

Row calculation:
$$(0, -1, 1 \mid -1, 0, 1) + (0, 1, 1 \mid 0, 1, 0) = (0, 0, 2 \mid -1, 1, 1)$$

The augmented matrix becomes:
$$\left(\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 2 & -1 & 1 & 1 \end{array}\right)$$

---

### Step 4: Normalize the Third Pivot
Scale row 3 to make the third pivot equal to $+1$:
$$R_3 \leftarrow \frac{1}{2} R_3$$

Row calculation:
$$\frac{1}{2}(0, 0, 2 \mid -1, 1, 1) = \left(0, 0, 1 \;\middle|\; -\frac{1}{2}, \frac{1}{2}, \frac{1}{2}\right)$$

The augmented matrix becomes:
$$\left(\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right)$$

---

### Step 5: Clear Column 3 Above the Third Pivot
The entry at $(1, 3)$ is already $0$. Eliminate the entry at $(2, 3)$ using:
$$R_2 \leftarrow R_2 - R_3$$

Row calculation:
$$(0, 1, 1 \mid 0, 1, 0) - \left(0, 0, 1 \;\middle|\; -\frac{1}{2}, \frac{1}{2}, \frac{1}{2}\right) = \left(0, 1, 0 \;\middle|\; \frac{1}{2}, \frac{1}{2}, -\frac{1}{2}\right)$$

The augmented matrix becomes:
$$\left(\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right)$$

---

### Step 6: Clear Column 2 Above the Second Pivot
Eliminate the entry at $(1, 2)$ using:
$$R_1 \leftarrow R_1 - R_2$$

Row calculation:
$$(1, 1, 0 \mid 1, 0, 0) - \left(0, 1, 0 \;\middle|\; \frac{1}{2}, \frac{1}{2}, -\frac{1}{2}\right) = \left(1, 0, 0 \;\middle|\; \frac{1}{2}, -\frac{1}{2}, \frac{1}{2}\right)$$

The matrix is now in fully reduced row echelon form $[I_3 \mid A^{-1}]$:
$$\left(\begin{array}{ccc|ccc} 1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right)$$

---

### Step 7: State the Inverse Matrix
Extracting the right-hand block:
$$A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Direct Multiplication Check ($A A^{-1} = I_3$):**
   $$A A^{-1} = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 1 & 0 & 1 \end{pmatrix} \cdot \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}$$
   Factor out $\frac{1}{2}$ and multiply:
   $$\frac{1}{2} \begin{pmatrix} 1(1) + 1(1) + 0(-1) & 1(-1) + 1(1) + 0(1) & 1(1) + 1(-1) + 0(1) \\ 0(1) + 1(1) + 1(-1) & 0(-1) + 1(1) + 1(1) & 0(1) + 1(-1) + 1(1) \\ 1(1) + 0(1) + 1(-1) & 1(-1) + 0(1) + 1(1) & 1(1) + 0(-1) + 1(1) \end{pmatrix}$$
   $$= \frac{1}{2} \begin{pmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} = I_3 \quad \checkmark$$

2. **Cofactor / Adjugate Matrix Verification:**
   Compute $\det A$ via row 1 expansion:
   $$\det A = 1(1 - 0) - 1(0 - 1) + 0 = 1 + 1 = 2$$
   The cofactor matrix $C$ entries are:
   - $C_{11} = +(1 - 0) = 1$, $C_{12} = -(0 - 1) = 1$, $C_{13} = +(0 - 1) = -1$
   - $C_{21} = -(1 - 0) = -1$, $C_{22} = +(1 - 0) = 1$, $C_{23} = -(0 - 1) = 1$
   - $C_{31} = +(1 - 0) = 1$, $C_{32} = -(1 - 0) = -1$, $C_{33} = +(1 - 0) = 1$

   $$C = \begin{pmatrix} 1 & 1 & -1 \\ -1 & 1 & 1 \\ 1 & -1 & 1 \end{pmatrix} \implies \operatorname{adj}(A) = C^T = \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}$$
   Then:
   $$A^{-1} = \frac{1}{\det A} \operatorname{adj}(A) = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}$$
   The adjugate method yields the exact same matrix, confirming zero computational error.
