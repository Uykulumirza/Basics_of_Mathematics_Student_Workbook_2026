# Solution to Exercise 15: Two Methods for Solving the Same Linear System

## 1. Problem Statement

Given the linear system $Ax = b$ with:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 7 \\ 8 \end{pmatrix}$$

1. Solve the system using the inverse matrix method: $x = A^{-1}b$.
2. Solve the system using Gaussian elimination with back-substitution.
3. Compare both solutions, analyze the number of essential computational steps, and determine which method is simpler and more efficient in this specific example.

---

## 2. Theoretical Background and Concepts

### Solving Linear Systems: Matrix Inversion vs. Gaussian Elimination
When solving a non-singular $n \times n$ linear system $Ax = b$:

1. **Matrix Inversion Method ($x = A^{-1}b$):**
   - Requires computing the full inverse matrix $A^{-1}$.
   - Once $A^{-1}$ is known, the solution for any right-hand side $b$ is obtained via a single matrix-vector multiplication.
   - Computational cost for an $n \times n$ system: $\sim n^3$ operations to compute $A^{-1}$ plus $n^2$ operations to compute $A^{-1}b$.
   - Highly advantageous when solving $Ax = b$ repeatedly for many different vectors $b$.

2. **Gaussian Elimination:**
   - Operates directly on the augmented matrix $[A \mid b]$.
   - Reduces the system to row echelon form using elementary row operations, followed by back-substitution.
   - Computational cost for an $n \times n$ system: $\sim \frac{1}{3}n^3 + n^2$ operations.
   - Avoids the redundant overhead of computing the full matrix inverse $A^{-1}$.
   - Best suited for solving a single linear system with one specific right-hand side $b$.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Solution via Matrix Inversion ($x = A^{-1}b$)

1. **Compute the Determinant of $A$:**
   $$\det A = (2)(3) - (1)(1) = 6 - 1 = 5 \ne 0$$

2. **Compute the Inverse Matrix $A^{-1}$:**
   Using the $2 \times 2$ formula:
   $$A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{5} & -\frac{1}{5} \\ -\frac{1}{5} & \frac{2}{5} \end{pmatrix}$$

3. **Compute the Solution Vector $x = A^{-1}b$:**
   $$x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 7 \\ 8 \end{pmatrix}$$

   Perform matrix-vector multiplication:
   $$\begin{pmatrix} 3(7) + (-1)(8) \\ -1(7) + 2(8) \end{pmatrix} = \begin{pmatrix} 21 - 8 \\ -7 + 16 \end{pmatrix} = \begin{pmatrix} 13 \\ 9 \end{pmatrix}$$

   Multiplying by the scalar factor $\frac{1}{5}$:
   $$x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\ 1.8 \end{pmatrix}$$

---

### Method 2: Solution via Gaussian Elimination

1. **Set Up the Augmented Matrix:**
   $$[A \mid b] = \left(\begin{array}{cc|c} 2 & 1 & 7 \\ 1 & 3 & 8 \end{array}\right)$$

2. **Row Swap for a Unit Pivot:**
   Swap row 1 and row 2 to place the leading $1$ into the pivot position $(1, 1)$:
   $$R_1 \leftrightarrow R_2 \implies \left(\begin{array}{cc|c} 1 & 3 & 8 \\ 2 & 1 & 7 \end{array}\right)$$

3. **Forward Elimination:**
   Eliminate the entry $2$ in position $(2, 1)$ using the elementary row operation:
   $$R_2 \leftarrow R_2 - 2R_1$$

   Compute the new row 2:
   $$(2, 1 \mid 7) - 2(1, 3 \mid 8) = (2 - 2, 1 - 6 \mid 7 - 16) = (0, -5 \mid -9)$$

   The augmented matrix in row echelon form is:
   $$\left(\begin{array}{cc|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array}\right)$$

4. **Back-Substitution:**
   - From row 2:
     $$-5x_2 = -9 \implies x_2 = \frac{9}{5}$$
   - Substitute $x_2 = \frac{9}{5}$ into row 1:
     $$x_1 + 3x_2 = 8 \implies x_1 = 8 - 3\left(\frac{9}{5}\right) = \frac{40 - 27}{5} = \frac{13}{5}$$

Thus, Gaussian elimination yields:
$$x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\ 1.8 \end{pmatrix}$$

---

### Step 3: Comparison and Complexity Analysis

| Metric | Method 1: Matrix Inversion ($A^{-1}b$) | Method 2: Gaussian Elimination |
| :--- | :--- | :--- |
| **Result** | $x = (13/5, 9/5)^T$ | $x = (13/5, 9/5)^T$ |
| **Intermediate Object** | Computes all 4 entries of $A^{-1}$ | Direct triangular reduction of $[A \mid b]$ |
| **Essential Steps** | 1 determinant, 1 matrix inversion, 1 matrix-vector product | 1 row swap, 1 row elimination, 1 back-substitution |
| **Arithmetic Operations** | $2$ mult, $1$ sub (det) + $4$ mult ($A^{-1}b$) + $2$ adds = **9 ops** | $2$ mult, $2$ sub (elim) + $1$ div, $1$ mult, $1$ sub (back-sub) = **7 ops** |

### Conclusion on Which Method is Simpler
- **For this specific single problem:** **Gaussian elimination is simpler.** It acts directly on the target numbers without computing the intermediate matrix $A^{-1}$, requiring fewer arithmetic steps and minimizing fraction manipulations.
- **Contextual Superiority:** Matrix inversion would only be preferred if we were given multiple different right-hand side vectors $b_1, b_2, \dots, b_k$, in which case $A^{-1}$ is computed once and reused for immediate matrix-vector multiplications.

---

## 4. Verification and Consistency Checks

1. **Direct Substitution into Original Equations:**
   Substitute $x_1 = \frac{13}{5}$ and $x_2 = \frac{9}{5}$ into the original system:
   - Equation 1:
     $$2x_1 + x_2 = 2\left(\frac{13}{5}\right) + \frac{9}{5} = \frac{26 + 9}{5} = \frac{35}{5} = 7 = b_1 \quad \checkmark$$
   - Equation 2:
     $$x_1 + 3x_2 = \frac{13}{5} + 3\left(\frac{9}{5}\right) = \frac{13 + 27}{5} = \frac{40}{5} = 8 = b_2 \quad \checkmark$$

2. **Cramer's Rule Verification:**
   $$D = \det A = 5$$
   $$D_1 = \det \begin{pmatrix} 7 & 1 \\ 8 & 3 \end{pmatrix} = 21 - 8 = 13 \implies x_1 = \frac{D_1}{D} = \frac{13}{5} \quad \checkmark$$
   $$D_2 = \det \begin{pmatrix} 2 & 7 \\ 1 & 8 \end{pmatrix} = 16 - 7 = 9 \implies x_2 = \frac{D_2}{D} = \frac{9}{5} \quad \checkmark$$
