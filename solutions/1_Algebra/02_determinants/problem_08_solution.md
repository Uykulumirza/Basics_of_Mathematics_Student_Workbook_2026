# Solution to Exercise 8: Determinant of a Product

## 1. Problem Statement

Let $A$ and $B$ be square matrices of the same size such that:
$$\det A = 3, \qquad \det B = -5$$

1. Compute $\det(AB)$.
2. Compute $\det(BA)$.
3. Determine whether $A^{-1}B$ exists, and if so, compute $\det(A^{-1}B)$.
4. Explain why $\det(AB) = \det(BA)$ even though matrix multiplication is generally non-commutative ($AB \ne BA$).

---

## 2. Theoretical Background and Concepts

### Multiplicativity of the Determinant (Cauchy-Binet Formula)
For any two square matrices $A, B \in M_n(\mathbb{R})$ of identical dimension:
$$\det(AB) = \det(A) \cdot \det(B)$$

### Determinant of an Inverse Matrix
A square matrix $A$ is invertible if and only if $\det A \ne 0$. Because $A A^{-1} = I$, applying the product theorem yields:
$$\det(A A^{-1}) = \det(A) \cdot \det(A^{-1}) = \det(I) = 1$$
Therefore:
$$\det(A^{-1}) = \frac{1}{\det A}$$

### Scalar Commutativity vs. Non-commutative Matrix Algebra
Matrix multiplication occurs in the matrix ring $M_n(\mathbb{R})$, where composition of linear maps is generally non-commutative ($AB \ne BA$). 

However, the determinant is a multiplicative scalar homomorphism:
$$\det: M_n(\mathbb{R}) \to \mathbb{R}$$
The output values $\det A$ and $\det B$ are real numbers belonging to the field $\mathbb{R}$, where scalar multiplication is strictly commutative: $x \cdot y = y \cdot x$ for all $x, y \in \mathbb{R}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det(AB)$
Using the multiplicativity of the determinant:
$$\det(AB) = \det A \cdot \det B = 3 \cdot (-5) = -15$$

---

### Step 2: Compute $\det(BA)$
Using the multiplicativity of the determinant:
$$\det(BA) = \det B \cdot \det A = (-5) \cdot 3 = -15$$

---

### Step 3: Compute $\det(A^{-1}B)$
First, we check whether $A^{-1}$ exists:
$$\det A = 3 \ne 0$$
Because the determinant of $A$ is non-zero, $A$ is invertible, and $A^{-1}$ exists.
Its determinant is:
$$\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{3}$$

Now, compute the determinant of the product $A^{-1}B$:
$$\det(A^{-1}B) = \det(A^{-1}) \cdot \det B = \frac{1}{3} \cdot (-5) = -\frac{5}{3}$$

---

### Step 4: Explanation of Why $\det(AB) = \det(BA)$
Although the matrix products $AB$ and $BA$ are distinct matrices with different entries (i.e., $AB \ne BA$ in general), their determinants must always be identical:
1. Matrix multiplication is mapped by the determinant function to scalar multiplication in $\mathbb{R}$:
   $$\det(AB) = \det A \cdot \det B$$
   $$\det(BA) = \det B \cdot \det A$$
2. In the field of real numbers $\mathbb{R}$, scalar multiplication is commutative:
   $$\det A \cdot \det B = \det B \cdot \det A$$
3. Therefore:
   $$\det(AB) = \det(BA) = -15$$
Geometrically, the order in which two linear transformations are applied affects the final orientation and shape of the transformed space, but the net scaling factor of oriented $n$-dimensional volume is the product of the two individual volume scaling factors, which is independent of the sequence of transformations.

---

## 4. Verification and Consistency Checks

1. **Concrete Representative Verification:**
   Consider two $2 \times 2$ diagonal matrices with the specified determinants:
   $$A = \begin{pmatrix} 3 & 0 \\ 0 & 1 \end{pmatrix} \implies \det A = 3 \cdot 1 = 3$$
   $$B = \begin{pmatrix} -5 & 0 \\ 0 & 1 \end{pmatrix} \implies \det B = (-5) \cdot 1 = -5$$
   - Product $AB = \begin{pmatrix} -15 & 0 \\ 0 & 1 \end{pmatrix} \implies \det(AB) = -15 \quad \checkmark$
   - Product $BA = \begin{pmatrix} -15 & 0 \\ 0 & 1 \end{pmatrix} \implies \det(BA) = -15 \quad \checkmark$
   - Inverse $A^{-1} = \begin{pmatrix} 1/3 & 0 \\ 0 & 1 \end{pmatrix} \implies A^{-1}B = \begin{pmatrix} -5/3 & 0 \\ 0 & 1 \end{pmatrix} \implies \det(A^{-1}B) = -\frac{5}{3} \quad \checkmark$

2. **Non-commuting Matrix Check:**
   Let $A = \begin{pmatrix} 3 & 1 \\ 0 & 1 \end{pmatrix}$ ($\det A = 3$) and $B = \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix}$ ($\det B = -5$):
   $$AB = \begin{pmatrix} 3 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix} = \begin{pmatrix} 5 & -5 \\ 2 & -5 \end{pmatrix} \implies \det(AB) = 5(-5) - (-5)(2) = -25 + 10 = -15 \quad \checkmark$$
   $$BA = \begin{pmatrix} 1 & 0 \\ 2 & -5 \end{pmatrix} \begin{pmatrix} 3 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 3 & 1 \\ 6 & -3 \end{pmatrix} \implies \det(BA) = 3(-3) - 1(6) = -9 - 6 = -15 \quad \checkmark$$
   Even though $AB \ne BA$, both determinants equal $-15$ exactly.
