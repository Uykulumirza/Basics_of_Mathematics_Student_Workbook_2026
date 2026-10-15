# Solution to Exercise 1: Matrix Size and Entries

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 2 & -1 & 3 \\ 0 & 4 & 5 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ -2 & 3 \\ 4 & 1 \end{pmatrix}$$

1. State the sizes of matrices $A$ and $B$.
2. Read off the entries $a_{12}$, $a_{23}$, $b_{21}$, and $b_{32}$.
3. Write the second row of $A$ and the first column of $B$ as vectors.

---

## 2. Theoretical Background and Concepts

### Matrix Dimensions
A matrix $M$ of size $m \times n$ consists of $m$ horizontal rows and $n$ vertical columns:
- $m$ is the number of rows (vertical height).
- $n$ is the number of columns (horizontal width).

### Index Notation
An element of a matrix $M$ is typically denoted by $m_{ij}$ (or $M_{i,j}$), where:
- The first index $i \in \{1, 2, \dots, m\}$ specifies the **row index** (counting from top to bottom).
- The second index $j \in \{1, 2, \dots, n\}$ specifies the **column index** (counting from left to right).

### Row and Column Vectors
- A **row vector** corresponding to row $i$ of matrix $M$ is a $1 \times n$ matrix containing all entries along that row:
  $$r_i = \begin{pmatrix} m_{i1} & m_{i2} & \cdots & m_{in} \end{pmatrix}$$
- A **column vector** corresponding to column $j$ of matrix $M$ is an $m \times 1$ matrix containing all entries down that column:
  $$c_j = \begin{pmatrix} m_{1j} \\ m_{2j} \\ \vdots \\ m_{mj} \end{pmatrix}$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determine the Sizes of $A$ and $B$
- Matrix $A$:
  - Counting the rows: row 1 is $(2, -1, 3)$, row 2 is $(0, 4, 5)$ $\implies 2$ rows.
  - Counting the columns: column 1 is $\begin{pmatrix}2\\0\end{pmatrix}$, column 2 is $\begin{pmatrix}-1\\4\end{pmatrix}$, column 3 is $\begin{pmatrix}3\\5\end{pmatrix}$ $\implies 3$ columns.
  - Therefore, the size of matrix $A$ is **$2 \times 3$**.

- Matrix $B$:
  - Counting the rows: row 1 is $(1, 0)$, row 2 is $(-2, 3)$, row 3 is $(4, 1)$ $\implies 3$ rows.
  - Counting the columns: column 1 is $\begin{pmatrix}1\\-2\\4\end{pmatrix}$, column 2 is $\begin{pmatrix}0\\3\\1\end{pmatrix}$ $\implies 2$ columns.
  - Therefore, the size of matrix $B$ is **$3 \times 2$**.

### Step 2: Read Off the Requested Entries
- **$a_{12}$**: Entry in row 1, column 2 of $A$:
  $$A = \begin{pmatrix} 2 & \mathbf{-1} & 3 \\ 0 & 4 & 5 \end{pmatrix} \implies a_{12} = -1$$

- **$a_{23}$**: Entry in row 2, column 3 of $A$:
  $$A = \begin{pmatrix} 2 & -1 & 3 \\ 0 & 4 & \mathbf{5} \end{pmatrix} \implies a_{23} = 5$$

- **$b_{21}$**: Entry in row 2, column 1 of $B$:
  $$B = \begin{pmatrix} 1 & 0 \\ \mathbf{-2} & 3 \\ 4 & 1 \end{pmatrix} \implies b_{21} = -2$$

- **$b_{32}$**: Entry in row 3, column 2 of $B$:
  $$B = \begin{pmatrix} 1 & 0 \\ -2 & 3 \\ 4 & \mathbf{1} \end{pmatrix} \implies b_{32} = 1$$

### Step 3: Write Row and Column Vectors
- **Second row of $A$** ($i = 2$):
  $$r_2(A) = \begin{pmatrix} 0 & 4 & 5 \end{pmatrix} \quad \text{or as an ordered triple } (0, 4, 5)$$

- **First column of $B$** ($j = 1$):
  $$c_1(B) = \begin{pmatrix} 1 \\ -2 \\ 4 \end{pmatrix} \quad \text{or in transposed row notation } (1, -2, 4)^T$$

---

## 4. Verification and Consistency Checks

1. **Dimension Consistency:**
   - Total number of entries in $A$: $2 \times 3 = 6$. The given matrix has 6 entries.
   - Total number of entries in $B$: $3 \times 2 = 6$. The given matrix has 6 entries.

2. **Index Boundary Verification:**
   - For $A \in \mathbb{R}^{2 \times 3}$, valid indices are $i \in \{1, 2\}$ and $j \in \{1, 2, 3\}$.
     - $a_{12}$: $1 \le 1 \le 2$ and $1 \le 2 \le 3$ (valid).
     - $a_{23}$: $1 \le 2 \le 2$ and $1 \le 3 \le 3$ (valid).
   - For $B \in \mathbb{R}^{3 \times 2}$, valid indices are $i \in \{1, 2, 3\}$ and $j \in \{1, 2\}$.
     - $b_{21}$: $1 \le 2 \le 3$ and $1 \le 1 \le 2$ (valid).
     - $b_{32}$: $1 \le 3 \le 3$ and $1 \le 2 \le 2$ (valid).

3. **Vector Dimension Check:**
   - The second row vector of $A$ has 3 components, matching the column count of $A$.
   - The first column vector of $B$ has 3 components, matching the row count of $B$.

