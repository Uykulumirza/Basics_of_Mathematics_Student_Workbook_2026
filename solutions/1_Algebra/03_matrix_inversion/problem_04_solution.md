# Solution to Exercise 4: Gauss–Jordan Inversion

## 1. Problem Statement

Given the matrix:
$$A = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix}$$

1. Find the inverse matrix $A^{-1}$ using the Gauss–Jordan elimination method.
2. Show the augmented matrix $[A \mid I]$ explicitly after each successive elementary row operation.
3. Explain fundamentally why obtaining the identity matrix $I$ on the left side necessarily produces $A^{-1}$ on the right side.

---

## 2. Theoretical Background and Concepts

### The Gauss–Jordan Elimination Method
The Gauss–Jordan method is an algorithmic technique for inverting an $n \times n$ matrix by performing elementary row operations on the block augmented matrix:
$$[A \mid I_n]$$

The three types of elementary row operations are:
1. Multiplying a row by a non-zero scalar ($R_i \leftarrow c R_i$, $c \ne 0$).
2. Adding a scalar multiple of one row to another ($R_i \leftarrow R_i + c R_j$).
3. Swapping two rows ($R_i \leftrightarrow R_j$).

### Why the Method Works: Elementary Matrices
Each elementary row operation performed on a matrix is algebraically equivalent to multiplying the matrix on the left by an invertible **elementary matrix** $E$:
$$\text{Operation } k \iff E_k M$$

If a sequence of $m$ elementary row operations reduces $A$ to the identity matrix $I_n$:
$$(E_m \cdots E_2 E_1) A = I_n$$

Let $P = E_m \cdots E_2 E_1$ denote the product of these elementary matrices. Then:
$$P A = I_n \implies P = A^{-1}$$

Because the augmented matrix $[A \mid I_n]$ undergoes the exact same sequence of operations:
$$(E_m \cdots E_2 E_1) [A \mid I_n] = [P A \mid P I_n] = [I_n \mid P] = [I_n \mid A^{-1}]$$

Hence, whatever sequence of operations transforms $A$ into $I_n$ simultaneously transforms $I_n$ into $A^{-1}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up the Augmented Matrix
Write matrix $A$ augmented by the $2 \times 2$ identity matrix $I_2$:
$$[A \mid I] = \left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array}\right)$$

---

### Step 2: Eliminate Below the First Pivot
The pivot in column 1 is already $1$ at position $(1, 1)$. Eliminate the entry $3$ at position $(2, 1)$ using the row operation:
$$R_2 \leftarrow R_2 - 3R_1$$

Compute the new row 2:
- Entry $(2, 1)$: $3 - 3(1) = 0$
- Entry $(2, 2)$: $5 - 3(2) = 5 - 6 = -1$
- Entry $(2, 3)$: $0 - 3(1) = -3$
- Entry $(2, 4)$: $1 - 3(0) = 1$

The augmented matrix becomes:
$$\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array}\right)$$

---

### Step 3: Normalize the Second Pivot
Make the leading coefficient in row 2 equal to $+1$ by multiplying row 2 by $-1$:
$$R_2 \leftarrow -R_2$$

Compute the new row 2:
$$-(0, -1 \mid -3, 1) = (0, 1 \mid 3, -1)$$

The augmented matrix becomes:
$$\left(\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array}\right)$$

---

### Step 4: Eliminate Above the Second Pivot
Eliminate the entry $2$ at position $(1, 2)$ using the row operation:
$$R_1 \leftarrow R_1 - 2R_2$$

Compute the new row 1:
- Entry $(1, 1)$: $1 - 2(0) = 1$
- Entry $(1, 2)$: $2 - 2(1) = 0$
- Entry $(1, 3)$: $1 - 2(3) = 1 - 6 = -5$
- Entry $(1, 4)$: $0 - 2(-1) = 0 + 2 = 2$

The augmented matrix is now in reduced row echelon form $[I_2 \mid A^{-1}]$:
$$\left(\begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array}\right)$$

---

### Step 5: Read Off the Inverse Matrix
The right-hand block is the inverse:
$$A^{-1} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Direct Matrix Multiplication ($A A^{-1} = I$):**
   $$A A^{-1} = \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix} \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix} = \begin{pmatrix} 1(-5) + 2(3) & 1(2) + 2(-1) \\ 3(-5) + 5(3) & 3(2) + 5(-1) \end{pmatrix} = \begin{pmatrix} -5 + 6 & 2 - 2 \\ -15 + 15 & 6 - 5 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$

2. **Reverse Multiplication ($A^{-1} A = I$):**
   $$A^{-1} A = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 3 & 5 \end{pmatrix} = \begin{pmatrix} -5(1) + 2(3) & -5(2) + 2(5) \\ 3(1) + (-1)(3) & 3(2) + (-1)(5) \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$

3. **$2 \times 2$ Inversion Formula Check:**
   $$\det A = (1)(5) - (2)(3) = 5 - 6 = -1$$
   $$A^{-1} = \frac{1}{-1} \begin{pmatrix} 5 & -2 \\ -3 & 1 \end{pmatrix} = \begin{pmatrix} -5 & 2 \\ 3 & -1 \end{pmatrix} \quad \checkmark$$
   The formula matches the Gauss–Jordan result identically.
