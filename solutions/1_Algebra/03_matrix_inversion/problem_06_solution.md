# Solution to Exercise 6: Solving a Linear System Using Matrix Inversion

## 1. Problem Statement

Given the linear system in matrix form:
$$Ax = b$$
where:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 5 \\ 7 \end{pmatrix}$$

1. Compute the inverse matrix $A^{-1}$.
2. Solve for the unknown vector $x$ using the matrix relation $x = A^{-1}b$.
3. Substitute the resulting vector $x$ back into the original system $Ax$ to verify that it reproduces the right-hand side vector $b$.

---

## 2. Theoretical Background and Concepts

### Matrix Form of a Linear System
A system of $n$ linear equations in $n$ variables can be written compactly as:
$$Ax = b$$
where $A \in M_n(\mathbb{R})$ is the coefficient matrix, $x \in \mathbb{R}^n$ is the column vector of unknowns, and $b \in \mathbb{R}^n$ is the column vector of constants.

### Solving via the Matrix Inverse
If $A$ is non-singular ($\det A \ne 0$), the unique inverse matrix $A^{-1}$ exists. Multiplying both sides of the matrix equation on the left by $A^{-1}$ preserves equality:
$$A^{-1}(Ax) = A^{-1}b$$

Using the associative property and the definition of the inverse:
$$(A^{-1}A)x = A^{-1}b \implies I_n x = A^{-1}b \implies x = A^{-1}b$$

This provides an explicit closed-form algebraic solution for $x$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Determinant of $A$
For $A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}$:
$$\det A = ad - bc = (2)(3) - (1)(1) = 6 - 1 = 5$$

Since $\det A = 5 \ne 0$, matrix $A$ is invertible.

---

### Step 2: Compute the Inverse Matrix $A^{-1}$
Using the $2 \times 2$ inverse formula:
$$A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{5} & -\frac{1}{5} \\ -\frac{1}{5} & \frac{2}{5} \end{pmatrix}$$

---

### Step 3: Compute the Solution Vector $x = A^{-1}b$
Multiply $A^{-1}$ by the vector $b = \begin{pmatrix} 5 \\ 7 \end{pmatrix}$:
$$x = A^{-1}b = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 5 \\ 7 \end{pmatrix}$$

Perform matrix-vector multiplication:
$$\begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 5 \\ 7 \end{pmatrix} = \begin{pmatrix} 3(5) + (-1)(7) \\ -1(5) + 2(7) \end{pmatrix} = \begin{pmatrix} 15 - 7 \\ -5 + 14 \end{pmatrix} = \begin{pmatrix} 8 \\ 9 \end{pmatrix}$$

Multiplying by the scalar $\frac{1}{5}$ gives:
$$x = \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 1.6 \\ 1.8 \end{pmatrix}$$

---

### Step 4: Back-Substitution and Direct Check
Substitute $x = \begin{pmatrix} 8/5 \\ 9/5 \end{pmatrix}$ directly into $Ax$:
$$Ax = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} \frac{8}{5} \\ \frac{9}{5} \end{pmatrix}$$

Compute each component:
- Component 1: $2\left(\frac{8}{5}\right) + 1\left(\frac{9}{5}\right) = \frac{16 + 9}{5} = \frac{25}{5} = 5$
- Component 2: $1\left(\frac{8}{5}\right) + 3\left(\frac{9}{5}\right) = \frac{8 + 27}{5} = \frac{35}{5} = 7$

Thus:
$$Ax = \begin{pmatrix} 5 \\ 7 \end{pmatrix} = b \quad \checkmark$$

---

## 4. Verification and Consistency Checks

1. **Cramer's Rule Independent Verification:**
   Compute determinant of the system matrix: $D = \det A = 5$.
   Replace column 1 with $b$:
   $$D_1 = \det \begin{pmatrix} 5 & 1 \\ 7 & 3 \end{pmatrix} = (5)(3) - (1)(7) = 15 - 7 = 8 \implies x_1 = \frac{D_1}{D} = \frac{8}{5}$$
   Replace column 2 with $b$:
   $$D_2 = \det \begin{pmatrix} 2 & 5 \\ 1 & 7 \end{pmatrix} = (2)(7) - (5)(1) = 14 - 5 = 9 \implies x_2 = \frac{D_2}{D} = \frac{9}{5}$$
   Cramer's rule produces the identical solution vector $x = \begin{pmatrix} 8/5 \\ 9/5 \end{pmatrix}$.

2. **Gaussian Elimination Verification:**
   Augmented matrix:
   $$\left(\begin{array}{cc|c} 2 & 1 & 5 \\ 1 & 3 & 7 \end{array}\right) \xrightarrow{R_1 \leftrightarrow R_2} \left(\begin{array}{cc|c} 1 & 3 & 7 \\ 2 & 1 & 5 \end{array}\right) \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left(\begin{array}{cc|c} 1 & 3 & 7 \\ 0 & -5 & -9 \end{array}\right)$$
   From row 2: $-5x_2 = -9 \implies x_2 = \frac{9}{5}$.
   From row 1: $x_1 + 3\left(\frac{9}{5}\right) = 7 \implies x_1 = \frac{35}{5} - \frac{27}{5} = \frac{8}{5}$.
   All methods agree.
