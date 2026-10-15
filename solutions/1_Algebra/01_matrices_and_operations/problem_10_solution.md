# Solution to Exercise 10: Columns of a Matrix Product

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}$$

Denote the columns of $B$ by $b_1$ and $b_2$:
$$b_1 = \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}, \qquad b_2 = \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}$$

1. Compute $Ab_1$ and $Ab_2$.
2. Compute the matrix product $AB$.
3. Compare the results and explain why the columns of $AB$ are exactly the vectors $Ab_1$ and $Ab_2$.

---

## 2. Theoretical Background and Concepts

### Column-by-Column Interpretation of Matrix Multiplication
Let $A \in \mathbb{R}^{m \times k}$ and let $B \in \mathbb{R}^{k \times n}$ be partitioned into its column vectors:
$$B = \begin{pmatrix} b_1 & b_2 & \cdots & b_n \end{pmatrix}$$
where each $b_j \in \mathbb{R}^k$.

When multiplying $A$ by $B$, each column of the resulting product matrix is produced by multiplying $A$ onto the corresponding column of $B$:
$$AB = A \begin{pmatrix} b_1 & b_2 & \cdots & b_n \end{pmatrix} = \begin{pmatrix} Ab_1 & Ab_2 & \cdots & Ab_n \end{pmatrix}$$

### Why This Holds (Index Formulation)
By definition of matrix multiplication, the entry in row $i$ and column $j$ of the product $C = AB$ is:
$$C_{ij} = \sum_{r=1}^k a_{ir} b_{rj}$$
For a fixed column index $j$, the entire $j$-th column of $C$ has entries:
$$\begin{pmatrix} C_{1j} \\ C_{2j} \\ \vdots \\ C_{mj} \end{pmatrix} = \begin{pmatrix} \sum_{r=1}^k a_{1r} b_{rj} \\ \sum_{r=1}^k a_{2r} b_{rj} \\ \vdots \\ \sum_{r=1}^k a_{mr} b_{rj} \end{pmatrix} = A b_j$$
Thus, matrix multiplication can be viewed as applying the linear transformation represented by $A$ simultaneously to each column vector of $B$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $Ab_1$ and $Ab_2$
- **Compute $Ab_1$:**
  $$Ab_1 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ -1 \\ 3 \end{pmatrix}$$
  - First component: $1(1) + 2(-1) + 0(3) = 1 - 2 + 0 = -1$
  - Second component: $0(1) + 1(-1) + 1(3) = 0 - 1 + 3 = 2$
  $$Ab_1 = \begin{pmatrix} -1 \\ 2 \end{pmatrix}$$

- **Compute $Ab_2$:**
  $$Ab_2 = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 \\ 0 \\ 1 \end{pmatrix}$$
  - First component: $1(2) + 2(0) + 0(1) = 2 + 0 + 0 = 2$
  - Second component: $0(2) + 1(0) + 1(1) = 0 + 0 + 1 = 1$
  $$Ab_2 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$$

---

### Step 2: Compute the Matrix Product $AB$
The dimensions are $A \in \mathbb{R}^{2 \times 3}$ and $B \in \mathbb{R}^{3 \times 2}$, so $AB \in \mathbb{R}^{2 \times 2}$:
$$AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 \\ -1 & 0 \\ 3 & 1 \end{pmatrix}$$

We compute each entry via row-by-column:
- Entry $(1, 1)$: $1 \cdot 1 + 2 \cdot (-1) + 0 \cdot 3 = 1 - 2 + 0 = -1$
- Entry $(1, 2)$: $1 \cdot 2 + 2 \cdot 0 + 0 \cdot 1 = 2 + 0 + 0 = 2$
- Entry $(2, 1)$: $0 \cdot 1 + 1 \cdot (-1) + 1 \cdot 3 = 0 - 1 + 3 = 2$
- Entry $(2, 2)$: $0 \cdot 2 + 1 \cdot 0 + 1 \cdot 1 = 0 + 0 + 1 = 1$

Thus:
$$AB = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}$$

---

### Step 3: Comparison and Explanation
Observe the structure of the resulting matrix $AB$:
- The first column of $AB$ is $\begin{pmatrix} -1 \\ 2 \end{pmatrix}$, which is identical to $Ab_1$.
- The second column of $AB$ is $\begin{pmatrix} 2 \\ 1 \end{pmatrix}$, which is identical to $Ab_2$.

Therefore:
$$AB = \begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix} = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix}$$

**Explanation:**
When computing the $j$-th column of $AB$, the row operations of $A$ act strictly on the numbers located in the $j$-th column of $B$ (which form the vector $b_j$). The entries of other columns of $B$ play no role in determining column $j$ of the product. Therefore, multiplying a matrix $A$ by a full matrix $B$ is identical to performing separate matrix-vector multiplications $A b_j$ for each column of $B$ and arranging the resulting column vectors side by side.

---

## 4. Verification and Consistency Checks

1. **Direct Matrix Identity Verification:**
   $$\begin{pmatrix} Ab_1 & Ab_2 \end{pmatrix} = \begin{pmatrix} \begin{pmatrix} -1 \\ 2 \end{pmatrix} & \begin{pmatrix} 2 \\ 1 \end{pmatrix} \end{pmatrix} = \begin{pmatrix} -1 & 2 \\ 2 & 1 \end{pmatrix} = AB \quad \checkmark$$

2. **Linear Combination Form Check:**
   Expressing each $Ab_j$ as linear combinations of columns of $A$ ($a_1, a_2, a_3$):
   - $Ab_1 = 1 \begin{pmatrix} 1 \\ 0 \end{pmatrix} - 1 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 3 \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 1 - 2 + 0 \\ 0 - 1 + 3 \end{pmatrix} = \begin{pmatrix} -1 \\ 2 \end{pmatrix} \quad \checkmark$
   - $Ab_2 = 2 \begin{pmatrix} 1 \\ 0 \end{pmatrix} + 0 \begin{pmatrix} 2 \\ 1 \end{pmatrix} + 1 \begin{pmatrix} 0 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 + 0 + 0 \\ 0 + 0 + 1 \end{pmatrix} = \begin{pmatrix} 2 \\ 1 \end{pmatrix} \quad \checkmark$
   Both column-combination calculations match the product columns exactly.

