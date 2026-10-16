# Solution to Exercise 1: Definition of the Inverse

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}$$

1. Check, without using an inversion formula, whether $B = A^{-1}$.
2. Compute the matrix products $AB$ and $BA$.
3. Relate the computational results directly to the formal definition of the matrix inverse.

---

## 2. Theoretical Background and Concepts

### Definition of an Invertible Matrix
Let $A$ be an $n \times n$ square matrix over a field (such as $\mathbb{R}$). An $n \times n$ matrix $B$ is called the **inverse** of $A$ (denoted $A^{-1}$) if and only if it satisfies the two-sided condition:
$$AB = I_n \qquad \text{and} \qquad BA = I_n$$
where $I_n$ is the $n \times n$ identity matrix.

### Key Conceptual Aspects
1. **Uniqueness:** If an inverse exists, it is unique. If both $B$ and $C$ satisfy the definition for $A$, then:
   $$B = B I = B(AC) = (BA)C = I C = C$$
2. **Verification via Definition:** Inverting a matrix using formulas or algorithms (such as the adjugate formula or Gauss–Jordan elimination) is not required to confirm that a proposed candidate $B$ is indeed the inverse. One simply computes the products $AB$ and $BA$. If both equal the identity matrix $I$, the claim $B = A^{-1}$ is established conclusively by definition.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Product $AB$
We multiply $A$ by $B$ using the standard row-by-column rule:
$$AB = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix}$$

Compute each entry:
- Entry $(1, 1)$: $\text{Row}_1(A) \cdot \text{Col}_1(B) = 2(1) + 1(-1) = 2 - 1 = 1$
- Entry $(1, 2)$: $\text{Row}_1(A) \cdot \text{Col}_2(B) = 2(-1) + 1(2) = -2 + 2 = 0$
- Entry $(2, 1)$: $\text{Row}_2(A) \cdot \text{Col}_1(B) = 1(1) + 1(-1) = 1 - 1 = 0$
- Entry $(2, 2)$: $\text{Row}_2(A) \cdot \text{Col}_2(B) = 1(-1) + 1(2) = -1 + 2 = 1$

Thus:
$$AB = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$

---

### Step 2: Compute the Product $BA$
We reverse the order and multiply $B$ by $A$:
$$BA = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}$$

Compute each entry:
- Entry $(1, 1)$: $\text{Row}_1(B) \cdot \text{Col}_1(A) = 1(2) + (-1)(1) = 2 - 1 = 1$
- Entry $(1, 2)$: $\text{Row}_1(B) \cdot \text{Col}_2(A) = 1(1) + (-1)(1) = 1 - 1 = 0$
- Entry $(2, 1)$: $\text{Row}_2(B) \cdot \text{Col}_1(A) = -1(2) + 2(1) = -2 + 2 = 0$
- Entry $(2, 2)$: $\text{Row}_2(B) \cdot \text{Col}_2(A) = -1(1) + 2(1) = -1 + 2 = 1$

Thus:
$$BA = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$

---

### Step 3: Relation to the Definition of the Inverse
By definition, a matrix $B$ is the inverse of $A$ if and only if:
$$AB = I_2 \qquad \text{and} \qquad BA = I_2$$
Both matrix products yield the identity matrix $I_2$. Therefore:
$$B = A^{-1} \qquad \text{and} \qquad A = B^{-1}$$

This confirms that $B$ is indeed the inverse of $A$ strictly through the foundational definition, without invoking any determinant or cofactor formulas.

---

## 4. Verification and Consistency Checks

1. **Determinant Multiplicativity Check:**
   Compute the determinants of $A$ and $B$:
   $$\det A = (2)(1) - (1)(1) = 2 - 1 = 1$$
   $$\det B = (1)(2) - (-1)(-1) = 2 - 1 = 1$$
   Since $\det(AB) = \det(A)\det(B) = 1 \cdot 1 = 1 = \det(I_2)$, the determinants are completely consistent. Furthermore, $\det A \ne 0$, confirming $A$ is non-singular.

2. **$2 \times 2$ Formula Cross-Check:**
   For a $2 \times 2$ matrix $M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$ with $\det M = ad - bc \ne 0$:
   $$M^{-1} = \frac{1}{\det M} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$
   Applying this formula to $A$:
   $$A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ -1 & 2 \end{pmatrix} = B$$
   The formula perfectly reproduces matrix $B$, corroborating the result.
