# Solution to Exercise 4: Matrix Multiplication and Noncommutativity

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}$$

1. Compute the product $AB$.
2. Compute the product $BA$.
3. Determine whether $AB = BA$.
4. Use this example to explain what noncommutativity of matrix multiplication means.

---

## 2. Theoretical Background and Concepts

### Definition of Matrix Multiplication
For square $2 \times 2$ matrices $M$ and $N$, the entry $(MN)_{ij}$ in row $i$ and column $j$ is the dot product of the $i$-th row of $M$ and the $j$-th column of $N$:
$$(MN)_{ij} = \sum_{k=1}^2 m_{ik} n_{kj} = m_{i1} n_{1j} + m_{i2} n_{2j}$$

### Commutativity vs. Noncommutativity
In ordinary scalar arithmetic, multiplication is commutative: for any real numbers $a, b \in \mathbb{R}$, $a \cdot b = b \cdot a$. 

However, in matrix algebra, multiplication is generally **noncommutative**:
$$AB \ne BA$$
Even when both $A$ and $B$ are square matrices of the exact same size (so that both $AB$ and $BA$ are well-defined and of identical size), the resulting matrices often differ in their entries. Geometrically, this reflects the fact that composing linear transformations (such as shears, rotations, and scalings) depends on the order in which they are applied.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $AB$
$$AB = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix}$$

We compute each of the four entries:
- Entry $(1, 1)$:
  $$(AB)_{11} = 1 \cdot 2 + 2 \cdot 3 = 2 + 6 = 8$$
- Entry $(1, 2)$:
  $$(AB)_{12} = 1 \cdot 0 + 2 \cdot 1 = 0 + 2 = 2$$
- Entry $(2, 1)$:
  $$(AB)_{21} = 0 \cdot 2 + 1 \cdot 3 = 0 + 3 = 3$$
- Entry $(2, 2)$:
  $$(AB)_{22} = 0 \cdot 0 + 1 \cdot 1 = 0 + 1 = 1$$

Thus:
$$AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}$$

### Step 2: Compute $BA$
$$BA = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$$

We compute each of the four entries:
- Entry $(1, 1)$:
  $$(BA)_{11} = 2 \cdot 1 + 0 \cdot 0 = 2 + 0 = 2$$
- Entry $(1, 2)$:
  $$(BA)_{12} = 2 \cdot 2 + 0 \cdot 1 = 4 + 0 = 4$$
- Entry $(2, 1)$:
  $$(BA)_{21} = 3 \cdot 1 + 1 \cdot 0 = 3 + 0 = 3$$
- Entry $(2, 2)$:
  $$(BA)_{22} = 3 \cdot 2 + 1 \cdot 1 = 6 + 1 = 7$$

Thus:
$$BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}$$

### Step 3: Comparison ($AB \stackrel{?}{=} BA$)
Comparing the two matrices:
$$AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix} \qquad \text{and} \qquad BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}$$

- Row 1, column 1: $(AB)_{11} = 8 \ne 2 = (BA)_{11}$
- Row 1, column 2: $(AB)_{12} = 2 \ne 4 = (BA)_{12}$
- Row 2, column 2: $(AB)_{22} = 1 \ne 7 = (BA)_{22}$

Therefore:
$$AB \ne BA$$

### Step 4: Explanation of Noncommutativity
This example demonstrates that matrix multiplication is fundamentally **order-dependent**. 
- In ordinary numbers, the order of factors does not affect the product ($2 \times 3 = 3 \times 2$).
- For matrices, multiplying $A$ by $B$ means applying the rows of $A$ to the columns of $B$. Reversing the order pairs completely different rows and columns together, producing entirely different entries.
- In practical and geometric applications, if $A$ and $B$ represent geometric transformations (e.g., shear and scaling), applying $B$ first and then $A$ (represented by $AB$) generally leads to a different final state than applying $A$ first and then $B$ (represented by $BA$).

---

## 4. Verification and Consistency Checks

1. **Trace Consistency Check:**
   A fundamental theorem of linear algebra states that the trace is invariant under cyclic permutations, i.e., $\operatorname{tr}(AB) = \operatorname{tr}(BA)$.
   - $\operatorname{tr}(AB) = 8 + 1 = 9$
   - $\operatorname{tr}(BA) = 2 + 7 = 9$
   The traces match, confirming an important invariant property.

2. **Determinant Consistency Check:**
   By Cauchy-Binet theorem, $\det(AB) = \det(A)\det(B) = \det(BA)$.
   - $\det(A) = 1 \cdot 1 - 2 \cdot 0 = 1$
   - $\det(B) = 2 \cdot 1 - 0 \cdot 3 = 2$
   - Expected product determinant: $1 \cdot 2 = 2$.
   - $\det(AB) = 8 \cdot 1 - 2 \cdot 3 = 8 - 6 = 2$
   - $\det(BA) = 2 \cdot 7 - 4 \cdot 3 = 14 - 12 = 2$
   Both determinants equal $2$, confirming our arithmetic calculations.

