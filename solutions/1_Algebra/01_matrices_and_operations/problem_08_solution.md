# Solution to Exercise 8: Row Operations and Their Reversibility

## 1. Problem Statement

Given the matrix:
$$A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}$$

Perform the following elementary row operations in order:
1. $R_2 \leftarrow R_2 - 2R_1$
2. $R_3 \leftarrow R_3 + R_1$
3. Interchange $R_2$ and $R_3$ ($R_2 \leftrightarrow R_3$)

Write the resulting matrix after each step. Then, for each of the three operations, specify the elementary row operation that reverses it.

---

## 2. Theoretical Background and Concepts

### Elementary Row Operations
There are three types of elementary row operations:
1. **Row addition (elimination):** Adding a scalar multiple of row $j$ to row $i$ ($R_i \leftarrow R_i + c R_j$, $i \ne j$).
2. **Row scaling:** Multiplying a row by a non-zero scalar ($R_i \leftarrow c R_i$, $c \ne 0$).
3. **Row interchange (permutation):** Swapping two rows ($R_i \leftrightarrow R_j$).

### Reversibility and Invertibility
Elementary row operations are invertible transformations. Each elementary row operation corresponds to multiplying on the left by an elementary matrix $E$. Since elementary matrices are non-singular, every elementary row operation can be undone by its inverse operation:
- The inverse of $R_i \leftarrow R_i + c R_j$ is $R_i \leftarrow R_i - c R_j$.
- The inverse of $R_i \leftarrow c R_i$ ($c \ne 0$) is $R_i \leftarrow \frac{1}{c} R_i$.
- The inverse of $R_i \leftrightarrow R_j$ is $R_i \leftrightarrow R_j$ (it is its own inverse).

If a sequence of operations $E_3 E_2 E_1 A = U$ transforms $A$ into an echelon form $U$, then applying the inverse operations in reverse order $E_1^{-1} E_2^{-1} E_3^{-1} U = A$ recovers the original matrix $A$ exactly.

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix}$$

---

### Step 1: Operation $R_2 \leftarrow R_2 - 2R_1$
Compute the new second row:
$$R_2 = (2, 4, 1)$$
$$2R_1 = 2 \cdot (1, 2, -1) = (2, 4, -2)$$
$$R_2 - 2R_1 = (2 - 2, \; 4 - 4, \; 1 - (-2)) = (0, 0, 3)$$

Replacing row 2 yields matrix $A_1$:
$$A_1 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix}$$

**Inverse Operation:**
To undo subtracting $2R_1$ from $R_2$, add $2R_1$ back to $R_2$:
$$R_2 \leftarrow R_2 + 2R_1$$

---

### Step 2: Operation $R_3 \leftarrow R_3 + R_1$
Applying this to matrix $A_1$, compute the new third row:
$$R_3 = (-1, 1, 3)$$
$$R_1 = (1, 2, -1)$$
$$R_3 + R_1 = (-1 + 1, \; 1 + 2, \; 3 + (-1)) = (0, 3, 2)$$

Replacing row 3 yields matrix $A_2$:
$$A_2 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix}$$

**Inverse Operation:**
To undo adding $R_1$ to $R_3$, subtract $R_1$ from $R_3$:
$$R_3 \leftarrow R_3 - R_1$$

---

### Step 3: Operation $R_2 \leftrightarrow R_3$
Swap the second and third rows of matrix $A_2$:
$$A_3 = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix}$$

**Inverse Operation:**
Swapping the two rows again restores their original positions:
$$R_2 \leftrightarrow R_3$$

Notice that the resulting matrix $A_3$ is now in upper triangular (echelon) form.

---

## 4. Verification and Consistency Checks

We verify that applying the three inverse operations in reverse order to $A_3$ strictly reconstructs the original matrix $A$:

1. **Apply Inverse Step 3 ($R_2 \leftrightarrow R_3$ to $A_3$):**
   $$\begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 2 \\ 0 & 0 & 3 \end{pmatrix} \xrightarrow{R_2 \leftrightarrow R_3} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} = A_2 \quad \checkmark$$

2. **Apply Inverse Step 2 ($R_3 \leftarrow R_3 - R_1$ to $A_2$):**
   $$R_3 = (0, 3, 2) - (1, 2, -1) = (0 - 1, \; 3 - 2, \; 2 - (-1)) = (-1, 1, 3)$$
   $$\begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ 0 & 3 & 2 \end{pmatrix} \xrightarrow{R_3 \leftarrow R_3 - R_1} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} = A_1 \quad \checkmark$$

3. **Apply Inverse Step 1 ($R_2 \leftarrow R_2 + 2R_1$ to $A_1$):**
   $$R_2 = (0, 0, 3) + 2(1, 2, -1) = (0 + 2, \; 0 + 4, \; 3 - 2) = (2, 4, 1)$$
   $$\begin{pmatrix} 1 & 2 & -1 \\ 0 & 0 & 3 \\ -1 & 1 & 3 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 + 2R_1} \begin{pmatrix} 1 & 2 & -1 \\ 2 & 4 & 1 \\ -1 & 1 & 3 \end{pmatrix} = A \quad \checkmark$$

The original matrix $A$ is restored identically, proving the complete reversibility of each operation.

