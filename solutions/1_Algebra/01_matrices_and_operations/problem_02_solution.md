# Solution to Exercise 2: Addition and Scalar Multiplication

## 1. Problem Statement

For the matrices:
$$A = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix}, \qquad B = \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix}$$

1. Compute $A + B$.
2. Compute $A - B$.
3. Compute $3A - 2B$.
4. Explain why matrix addition is possible only for matrices of the same size.

---

## 2. Theoretical Background and Concepts

### Matrix Addition and Subtraction
Given two matrices $A, B \in \mathbb{R}^{m \times n}$ of the exact same size, their sum $S = A + B$ and difference $D = A - B$ are defined component-wise for every row index $i \in \{1, \dots, m\}$ and column index $j \in \{1, \dots, n\}$:
$$(A + B)_{ij} = a_{ij} + b_{ij}$$
$$(A - B)_{ij} = a_{ij} - b_{ij}$$

### Scalar Multiplication
Given a scalar $c \in \mathbb{R}$ and a matrix $A \in \mathbb{R}^{m \times n}$, the scalar product $c A$ is obtained by multiplying each individual element of $A$ by $c$:
$$(cA)_{ij} = c \cdot a_{ij}$$

### Compatibility Condition for Addition
Matrix addition is defined as an element-by-element operation. There must be a one-to-one correspondence between the entries of $A$ and $B$. If the matrices have differing row counts or differing column counts, at least one entry would lack a corresponding partner with which to add, rendering the operation undefined.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $A + B$
Both $A$ and $B$ are $2 \times 2$ matrices, so addition is well-defined:
$$A + B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} + \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 + 4 & 2 + (-2) \\ -1 + 0 & 3 + 5 \end{pmatrix} = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix}$$

### Step 2: Compute $A - B$
Using element-wise subtraction:
$$A - B = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} - \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 1 - 4 & 2 - (-2) \\ -1 - 0 & 3 - 5 \end{pmatrix} = \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix}$$

### Step 3: Compute $3A - 2B$
First, perform the scalar multiplications:
$$3A = 3 \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 3 \cdot 1 & 3 \cdot 2 \\ 3 \cdot (-1) & 3 \cdot 3 \end{pmatrix} = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix}$$

$$2B = 2 \begin{pmatrix} 4 & -2 \\ 0 & 5 \end{pmatrix} = \begin{pmatrix} 2 \cdot 4 & 2 \cdot (-2) \\ 2 \cdot 0 & 2 \cdot 5 \end{pmatrix} = \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix}$$

Now subtract $2B$ from $3A$:
$$3A - 2B = \begin{pmatrix} 3 & 6 \\ -3 & 9 \end{pmatrix} - \begin{pmatrix} 8 & -4 \\ 0 & 10 \end{pmatrix} = \begin{pmatrix} 3 - 8 & 6 - (-4) \\ -3 - 0 & 9 - 10 \end{pmatrix} = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}$$

### Step 4: Explanation of Size Requirement
Matrix addition is defined as an entry-wise operation: the entry in row $i$, column $j$ of the sum is the sum of the entries at that exact position $(i, j)$ in the two summands. 

If matrix $A$ has size $m_1 \times n_1$ and matrix $B$ has size $m_2 \times n_2$ with $m_1 \ne m_2$ or $n_1 \ne n_2$, there is no natural pairing for entries in rows or columns that exist in one matrix but not in the other. Therefore, to ensure that every entry $a_{ij}$ has a uniquely defined counterpart $b_{ij}$, addition requires that the matrices have identical dimensions.

---

## 4. Verification and Consistency Checks

1. **Sum and Difference Consistency Check:**
   By algebraic identity, $(A + B) + (A - B) = 2A$.
   $$(A + B) + (A - B) = \begin{pmatrix} 5 & 0 \\ -1 & 8 \end{pmatrix} + \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix} = \begin{pmatrix} 5 - 3 & 0 + 4 \\ -1 - 1 & 8 - 2 \end{pmatrix} = \begin{pmatrix} 2 & 4 \\ -2 & 6 \end{pmatrix}$$
   Computing $2A$:
   $$2A = 2 \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} = \begin{pmatrix} 2 & 4 \\ -2 & 6 \end{pmatrix}$$
   The results are identical, confirming both $A + B$ and $A - B$.

2. **Alternative Calculation for $3A - 2B$:**
   Notice that $3A - 2B = A + 2(A - B)$:
   $$A + 2(A - B) = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} + 2 \begin{pmatrix} -3 & 4 \\ -1 & -2 \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ -1 & 3 \end{pmatrix} + \begin{pmatrix} -6 & 8 \\ -2 & -4 \end{pmatrix} = \begin{pmatrix} -5 & 10 \\ -3 & -1 \end{pmatrix}$$
   This matches our previous result for $3A - 2B$ exactly.

