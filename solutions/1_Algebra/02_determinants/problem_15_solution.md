# Solution to Exercise 15: Combining Determinant Properties

## 1. Problem Statement

Let $A$ and $B$ be invertible $2 \times 2$ matrices with known determinants:
$$\det A = -2, \qquad \det B = 3$$

Without constructing or knowing the specific numerical entries of matrices $A$ and $B$:
1. Compute the determinant:
   $$\det\left(B^{-1} A^T B\right)$$
2. State all determinant properties used, in the exact order of their application.
3. Explain geometrically and algebraically why the factors involving matrix $B$ cancel out completely.

---

## 2. Theoretical Background and Concepts

### 1. Multiplicative Property of Determinants
For any finite collection of $n \times n$ square matrices $X_1, X_2, \dots, X_k$:
$$\det(X_1 X_2 \cdots X_k) = \det(X_1) \cdot \det(X_2) \cdots \det(X_k)$$

### 2. Determinant of an Inverse Matrix
Because $B B^{-1} = I_n$ and $\det(I_n) = 1$:
$$\det(B) \cdot \det(B^{-1}) = 1 \implies \det(B^{-1}) = \frac{1}{\det B}$$
This formula is well-defined because $B$ is invertible ($\det B \ne 0$).

### 3. Transposition Invariance
Transposing a matrix does not alter its determinant:
$$\det(M^T) = \det(M)$$

### 4. Similarity Invariance
Two square matrices $M$ and $N$ are **similar** if there exists an invertible matrix $P$ such that $N = P^{-1} M P$.
Similar matrices represent the identical underlying linear operator under different coordinate bases. Because the determinant represents the coordinate-free scaling factor of oriented volume, the determinant is an **invariant under similarity**:
$$\det(P^{-1} M P) = \det(P^{-1}) \det(M) \det(P) = \frac{1}{\det P} \det(M) \det P = \det(M)$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Apply Multiplicativity of the Determinant
Express the determinant of the product as the product of the individual determinants:
$$\det\left(B^{-1} A^T B\right) = \det\left(B^{-1}\right) \cdot \det\left(A^T\right) \cdot \det(B)$$

---

### Step 2: Apply the Inverse Property to $\det(B^{-1})$
Since $B$ is invertible with $\det B = 3 \ne 0$:
$$\det\left(B^{-1}\right) = \frac{1}{\det B} = \frac{1}{3}$$

---

### Step 3: Apply the Transposition Invariance to $\det(A^T)$
Transposition preserves the determinant:
$$\det\left(A^T\right) = \det A = -2$$

---

### Step 4: Substitute Values and Simplify
Substitute the scalar results back into the expanded expression:
$$\det\left(B^{-1} A^T B\right) = \left(\frac{1}{\det B}\right) \cdot \det\left(A^T\right) \cdot \det B = \left(\frac{1}{3}\right) \cdot (-2) \cdot 3$$

Because scalar multiplication in $\mathbb{R}$ is commutative and associative:
$$\det\left(B^{-1} A^T B\right) = \left(\frac{1}{3} \cdot 3\right) \cdot (-2) = 1 \cdot (-2) = -2$$

Thus:
$$\det\left(B^{-1} A^T B\right) = -2$$

---

### Step 5: Explanation of Why Factors Involving $B$ Cancel
1. **Algebraic Explanation:**
   The determinant maps matrices to real numbers. In $\mathbb{R}$, multiplication is commutative. Therefore, the scalar factors $\det(B^{-1}) = \frac{1}{\det B}$ and $\det(B)$ can be grouped together:
   $$\det(B^{-1}) \cdot \det(B) = \frac{\det B}{\det B} = 1$$
   Because $\det B \ne 0$, they are exact multiplicative inverses of each other in $\mathbb{R}$ and cancel to $1$.

2. **Geometric (Coordinate-Free) Explanation:**
   The mapping $M \mapsto B^{-1} M B$ (with $M = A^T$) represents a **change of basis** applied to the linear transformation $M$.
   - First, $B$ maps the coordinates from the new basis back to the original basis, scaling oriented volume by $\det B$.
   - Second, $M$ acts in the original basis, scaling oriented volume by $\det M$.
   - Third, $B^{-1}$ converts the output back to the new basis, scaling oriented volume by $\frac{1}{\det B}$.
   The expansion by $\det B$ upon entering the original basis is perfectly neutralized by the compression $\frac{1}{\det B}$ upon returning to the new basis. Consequently, the net volume distortion depends exclusively on the intrinsic map $M = A^T$, making the choice of basis matrix $B$ completely irrelevant.

---

## 4. Verification and Consistency Checks

1. **Concrete Representative Verification:**
   Let us select two simple $2 \times 2$ matrices matching the given determinants:
   - Choose $A = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \implies \det A = -2 \cdot 1 = -2$.
     Then $A^T = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix}$.
   - Choose $B = \begin{pmatrix} 1 & 1 \\ 0 & 3 \end{pmatrix} \implies \det B = 1 \cdot 3 = 3$.
     Then $B^{-1} = \frac{1}{3} \begin{pmatrix} 3 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1/3 \\ 0 & 1/3 \end{pmatrix}$.

2. **Compute Matrix Product Explicitly:**
   - First, compute $A^T B$:
     $$A^T B = \begin{pmatrix} -2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} -2 & -2 \\ 0 & 3 \end{pmatrix}$$
   - Next, compute $B^{-1} (A^T B)$:
     $$B^{-1} A^T B = \begin{pmatrix} 1 & -1/3 \\ 0 & 1/3 \end{pmatrix} \begin{pmatrix} -2 & -2 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} 1(-2) + 0 & 1(-2) + (-1/3)(3) \\ 0 & (1/3)(3) \end{pmatrix} = \begin{pmatrix} -2 & -3 \\ 0 & 1 \end{pmatrix}$$
   - Finally, compute its determinant:
     $$\det\left(B^{-1} A^T B\right) = (-2)(1) - (-3)(0) = -2 \quad \checkmark$$
   The direct numerical calculation on an explicit pair of matrices confirms $\det(B^{-1} A^T B) = -2$.
