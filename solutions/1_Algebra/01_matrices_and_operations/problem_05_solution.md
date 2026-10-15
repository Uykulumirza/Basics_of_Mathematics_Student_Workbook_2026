# Solution to Exercise 5: Matrix Times Vector

## 1. Problem Statement

Let:
$$A = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix}, \qquad x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$$

1. Compute $Ax$ using the standard row-by-column method.
2. Express $Ax$ as a linear combination of the columns of $A$, with coefficients coming from the vector $x$.
3. Show that both representations yield identical results.

---

## 2. Theoretical Background and Concepts

### Dual Perspectives of Matrix-Vector Multiplication
For a matrix $A \in \mathbb{R}^{m \times n}$ with columns $a_1, a_2, \dots, a_n \in \mathbb{R}^m$ and a vector $x \in \mathbb{R}^n$:

1. **Row Perspective (Inner Product View):**
   Each entry $i$ of the product vector $Ax$ is the dot product of the $i$-th row of $A$ with the vector $x$:
   $$(Ax)_i = \sum_{j=1}^n a_{ij} x_j$$

2. **Column Perspective (Linear Combination View):**
   The product vector $Ax$ is mathematically equivalent to the linear combination of the columns of $A$, weighted by the corresponding scalar entries of $x$:
   $$Ax = x_1 a_1 + x_2 a_2 + \cdots + x_n a_n$$

This column perspective is fundamental to linear algebra, forming the basis for understanding column spaces, linear independence, systems of linear equations, and the range of linear transformations.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Standard Row-by-Column Computation
Compute $Ax$ by taking the dot product of each row of $A$ with $x$:
$$Ax = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix} \begin{pmatrix} 4 \\ 2 \end{pmatrix}$$

- **First component (Row 1 $\cdot$ $x$):**
  $$(Ax)_1 = 2 \cdot (4) + (-1) \cdot (2) = 8 - 2 = 6$$

- **Second component (Row 2 $\cdot$ $x$):**
  $$(Ax)_2 = 1 \cdot (4) + 3 \cdot (2) = 4 + 6 = 10$$

Thus:
$$Ax = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$

### Step 2: Linear Combination of Columns
Identify the columns of matrix $A$:
$$a_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}, \qquad a_2 = \begin{pmatrix} -1 \\ 3 \end{pmatrix}$$

The coefficients from vector $x = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$ are:
$$x_1 = 4, \qquad x_2 = 2$$

Now, form the linear combination:
$$x_1 a_1 + x_2 a_2 = 4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2 \begin{pmatrix} -1 \\ 3 \end{pmatrix}$$

Perform the scalar multiplications:
$$4 \begin{pmatrix} 2 \\ 1 \end{pmatrix} = \begin{pmatrix} 4 \cdot 2 \\ 4 \cdot 1 \end{pmatrix} = \begin{pmatrix} 8 \\ 4 \end{pmatrix}$$
$$2 \begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 2 \cdot (-1) \\ 2 \cdot 3 \end{pmatrix} = \begin{pmatrix} -2 \\ 6 \end{pmatrix}$$

Add the resulting vectors:
$$\begin{pmatrix} 8 \\ 4 \end{pmatrix} + \begin{pmatrix} -2 \\ 6 \end{pmatrix} = \begin{pmatrix} 8 + (-2) \\ 4 + 6 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Equivalence of Both Approaches:**
   - Row-by-column method: $\begin{pmatrix} 6 \\ 10 \end{pmatrix}$
   - Column linear combination method: $\begin{pmatrix} 6 \\ 10 \end{pmatrix}$
   Both results are identical, confirming the column-combination theorem:
   $$Ax = \begin{pmatrix} 2 & -1 \\ 1 & 3 \end{pmatrix}\begin{pmatrix} 4 \\ 2 \end{pmatrix} = 4\begin{pmatrix} 2 \\ 1 \end{pmatrix} + 2\begin{pmatrix} -1 \\ 3 \end{pmatrix} = \begin{pmatrix} 6 \\ 10 \end{pmatrix}$$

2. **Dimension Verification:**
   - Matrix $A$ has size $2 \times 2$.
   - Vector $x$ has size $2 \times 1$.
   - The product $Ax$ has size $2 \times 1$.
   - The columns $a_1, a_2$ are vectors in $\mathbb{R}^2$, and any linear combination of vectors in $\mathbb{R}^2$ remains in $\mathbb{R}^2$.

