# Solution to Exercise 6: Transpose

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}$$

1. Compute the transpose $A^T$.
2. Compute the transpose $B^T$.
3. Compute the matrix product $AB$.
4. Compute $(AB)^T$ and $B^T A^T$, and verify that:
   $$(AB)^T = B^T A^T$$

---

## 2. Theoretical Background and Concepts

### Matrix Transpose
The transpose of an $m \times n$ matrix $M$, denoted $M^T$, is an $n \times m$ matrix formed by interchanging its rows and columns:
$$(M^T)_{ij} = M_{ji}$$
Geometrically, transposition is a reflection across the main diagonal.

### Transpose of a Product (The Order-Reversing Property)
For any two matrices $A$ and $B$ where the product $AB$ is defined:
$$(AB)^T = B^T A^T$$

**Why does the order reverse?**
Consider the $(i, j)$-entry of $AB$:
$$(AB)_{ij} = \sum_{k} a_{ik} b_{kj}$$
By definition of the transpose, the $(i, j)$-entry of $(AB)^T$ corresponds to the $(j, i)$-entry of $AB$:
$$\left((AB)^T\right)_{ij} = (AB)_{ji} = \sum_{k} a_{jk} b_{ki}$$
Since scalar multiplication is commutative ($a_{jk} b_{ki} = b_{ki} a_{jk}$), and recognizing $b_{ki} = (B^T)_{ik}$ and $a_{jk} = (A^T)_{kj}$:
$$\left((AB)^T\right)_{ij} = \sum_{k} (B^T)_{ik} (A^T)_{kj} = (B^T A^T)_{ij}$$
Hence, $(AB)^T = B^T A^T$. Furthermore, notice that if $A$ is $m \times k$ and $B$ is $k \times n$, $A^T B^T$ is of sizes $(k \times m)(n \times k)$, which is generally not even defined when $m \ne n$, whereas $B^T A^T$ has compatible dimensions $(n \times k)(k \times m) = n \times m$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $A^T$
Matrix $A$ has size $2 \times 3$. Its transpose $A^T$ has size $3 \times 2$, formed by making the rows of $A$ become the columns of $A^T$:
$$A^T = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}^T = \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}$$

### Step 2: Compute $B^T$
Matrix $B$ has size $3 \times 2$. Its transpose $B^T$ has size $2 \times 3$:
$$B^T = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix}$$

### Step 3: Compute $AB$
$A$ is $2 \times 3$ and $B$ is $3 \times 2$, so $AB$ is a $2 \times 2$ matrix:
$$AB = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}$$

We calculate each entry:
- $(AB)_{11} = 1 \cdot 1 + 2 \cdot 2 + 3 \cdot (-1) = 1 + 4 - 3 = 2$
- $(AB)_{12} = 1 \cdot 0 + 2 \cdot 1 + 3 \cdot 3 = 0 + 2 + 9 = 11$
- $(AB)_{21} = 4 \cdot 1 + 5 \cdot 2 + 6 \cdot (-1) = 4 + 10 - 6 = 8$
- $(AB)_{22} = 4 \cdot 0 + 5 \cdot 1 + 6 \cdot 3 = 0 + 5 + 18 = 23$

Thus:
$$AB = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}$$

### Step 4: Compute $(AB)^T$ and $B^T A^T$
First, take the transpose of $AB$:
$$(AB)^T = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}$$

Now, compute the product $B^T A^T$:
$$B^T A^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix} \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}$$

We calculate each entry:
- $(B^T A^T)_{11} = 1 \cdot 1 + 2 \cdot 2 + (-1) \cdot 3 = 1 + 4 - 3 = 2$
- $(B^T A^T)_{12} = 1 \cdot 4 + 2 \cdot 5 + (-1) \cdot 6 = 4 + 10 - 6 = 8$
- $(B^T A^T)_{21} = 0 \cdot 1 + 1 \cdot 2 + 3 \cdot 3 = 0 + 2 + 9 = 11$
- $(B^T A^T)_{22} = 0 \cdot 4 + 1 \cdot 5 + 3 \cdot 6 = 0 + 5 + 18 = 23$

Thus:
$$B^T A^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Identity Verification:**
   $$(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix} = B^T A^T$$
   The matrices are identical entry-by-entry, confirming the theorem $(AB)^T = B^T A^T$.

2. **Dimension Consistency Check:**
   - $\text{size}(A) = 2 \times 3$, $\text{size}(B) = 3 \times 2 \implies \text{size}(AB) = 2 \times 2$.
   - $\text{size}\left((AB)^T\right) = 2 \times 2$.
   - $\text{size}(B^T) = 2 \times 3$, $\text{size}(A^T) = 3 \times 2 \implies \text{size}(B^T A^T) = 2 \times 2$.
   All dimension relationships are valid.

