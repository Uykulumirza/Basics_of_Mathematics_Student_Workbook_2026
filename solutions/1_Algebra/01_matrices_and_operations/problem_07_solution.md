# Solution to Exercise 7: Identity Matrix, Zero Matrix, and Powers

## 1. Problem Statement

Given the matrix:
$$A = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix}$$

1. Compute $AI$, $IA$, and $A + 0$, where $I$ and $0$ are the $2 \times 2$ identity matrix and zero matrix, respectively.
2. Compute the powers $A^2$ and $A^3$.
3. Explain the roles of the matrices $I$ and $0$.
4. Describe the pattern observed in successive powers of $A$.

---

## 2. Theoretical Background and Concepts

### Neutral Elements in Matrix Algebra
- **Identity Matrix ($I$):** The multiplicative identity matrix $I_n \in \mathbb{R}^{n \times n}$ has ones along the main diagonal and zeros elsewhere ($I_{ij} = \delta_{ij}$). For any square matrix $M \in \mathbb{R}^{n \times n}$:
  $$M I = I M = M$$
- **Zero Matrix ($0$):** The additive identity matrix $0 \in \mathbb{R}^{n \times n}$ contains only zeros in all entries. For any matrix $M \in \mathbb{R}^{n \times n}$:
  $$M + 0 = 0 + M = M \quad \text{and} \quad M \cdot 0 = 0 \cdot M = 0$$

### Matrix Powers and Nilpotence
For a square matrix $A$, positive integer powers are defined recursively:
$$A^1 = A, \qquad A^{k+1} = A^k \cdot A$$
When a matrix can be decomposed as $A = \lambda I + N$, where $N$ is a **nilpotent matrix** (meaning $N^k = 0$ for some positive integer $k$), powers of $A$ can be computed using the Binomial Theorem because the scalar matrix $\lambda I$ commutes with every matrix:
$$A^n = (\lambda I + N)^n = \sum_{k=0}^n \binom{n}{k} (\lambda I)^{n-k} N^k$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $AI$, $IA$, and $A + 0$
Here $I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$ and $0 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix}$.

- **Multiplication $AI$:**
  $$AI = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2 \cdot 1 + 1 \cdot 0 & 2 \cdot 0 + 1 \cdot 1 \\ 0 \cdot 1 + 2 \cdot 0 & 0 \cdot 0 + 2 \cdot 1 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$$

- **Multiplication $IA$:**
  $$IA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 1 \cdot 2 + 0 \cdot 0 & 1 \cdot 1 + 0 \cdot 2 \\ 0 \cdot 2 + 1 \cdot 0 & 0 \cdot 1 + 1 \cdot 2 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$$

- **Addition $A + 0$:**
  $$A + 0 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} + \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 2 + 0 & 1 + 0 \\ 0 + 0 & 2 + 0 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = A$$

### Step 2: Compute Powers $A^2$ and $A^3$
- **Compute $A^2 = A \cdot A$:**
  $$A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2 \cdot 2 + 1 \cdot 0 & 2 \cdot 1 + 1 \cdot 2 \\ 0 \cdot 2 + 2 \cdot 0 & 0 \cdot 1 + 2 \cdot 2 \end{pmatrix} = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix}$$

- **Compute $A^3 = A^2 \cdot A$:**
  $$A^3 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 4 \cdot 2 + 4 \cdot 0 & 4 \cdot 1 + 4 \cdot 2 \\ 0 \cdot 2 + 4 \cdot 0 & 0 \cdot 1 + 4 \cdot 2 \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$$

### Step 3: Explanation of the Roles of $I$ and $0$
- **The Identity Matrix $I$** acts as the multiplicative neutral element in the ring of square matrices, directly analogous to the number $1$ in real arithmetic. It leaves any compatible matrix unchanged upon multiplication from either the left or right ($IA = AI = A$).
- **The Zero Matrix $0$** acts as the additive neutral element, directly analogous to the number $0$ in real arithmetic. Adding $0$ to any matrix leaves the matrix unchanged ($A + 0 = A$).

### Step 4: Pattern in Successive Powers of $A$
Let us inspect the values for $n = 1, 2, 3$:
- $A^1 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} 2^1 & 1 \cdot 2^0 \\ 0 & 2^1 \end{pmatrix}$
- $A^2 = \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} 2^2 & 2 \cdot 2^1 \\ 0 & 2^2 \end{pmatrix}$
- $A^3 = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix} = \begin{pmatrix} 2^3 & 3 \cdot 2^2 \\ 0 & 2^3 \end{pmatrix}$

**Observed General Pattern:**
For any positive integer $n \ge 1$:
$$A^n = \begin{pmatrix} 2^n & n \cdot 2^{n-1} \\ 0 & 2^n \end{pmatrix}$$

**Algebraic Explanation:**
Notice $A$ can be decomposed as:
$$A = 2I + N, \qquad \text{where } N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$
Observe that $N^2 = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = 0$. Since $2I$ commutes with $N$, the Binomial Theorem applies:
$$A^n = (2I + N)^n = (2I)^n + \binom{n}{1}(2I)^{n-1} N + \sum_{k=2}^n \binom{n}{k} (2I)^{n-k} \underbrace{N^k}_{= 0} = 2^n I + n 2^{n-1} N = \begin{pmatrix} 2^n & n 2^{n-1} \\ 0 & 2^n \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Associativity of Matrix Power Check ($A^3 = A \cdot A^2$):**
   $$A \cdot A^2 = \begin{pmatrix} 2 & 1 \\ 0 & 2 \end{pmatrix} \begin{pmatrix} 4 & 4 \\ 0 & 4 \end{pmatrix} = \begin{pmatrix} 2 \cdot 4 + 1 \cdot 0 & 2 \cdot 4 + 1 \cdot 4 \\ 0 \cdot 4 + 2 \cdot 0 & 0 \cdot 4 + 2 \cdot 4 \end{pmatrix} = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$$
   This matches $A^2 \cdot A = \begin{pmatrix} 8 & 12 \\ 0 & 8 \end{pmatrix}$, confirming associativity.

2. **Determinant Power Rule Check ($\det(A^k) = (\det A)^k$):**
   - $\det(A) = 2 \cdot 2 - 1 \cdot 0 = 4$.
   - $\det(A^2) = 4 \cdot 4 - 4 \cdot 0 = 16 = 4^2$.
   - $\det(A^3) = 8 \cdot 8 - 12 \cdot 0 = 64 = 4^3$.
   The determinant formula holds precisely.

