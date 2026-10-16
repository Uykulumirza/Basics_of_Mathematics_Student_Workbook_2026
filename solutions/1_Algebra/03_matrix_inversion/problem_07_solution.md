# Solution to Exercise 7: Inverse of a Product

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$$

1. Compute the product $AB$ and its inverse $(AB)^{-1}$.
2. Compute the individual inverses $A^{-1}$ and $B^{-1}$, and their product in reverse order: $B^{-1}A^{-1}$.
3. Verify that $(AB)^{-1} = B^{-1}A^{-1}$.
4. Provide a clear explanation of why the order of matrices is reversed when inverting a product.

---

## 2. Theoretical Background and Concepts

### The Socks-and-Shoes Property of Inverses
For any two invertible matrices $A, B \in M_n(\mathbb{R})$, their product $AB$ is also invertible, and its inverse is given by:
$$(AB)^{-1} = B^{-1} A^{-1}$$

### Algebraic Proof
To prove that $B^{-1}A^{-1}$ is the inverse of $AB$, test both sides against the definition of the inverse matrix:
1. **Right Multiplication:**
   $$(AB)(B^{-1}A^{-1}) = A(B B^{-1})A^{-1} = A(I)A^{-1} = A A^{-1} = I$$
2. **Left Multiplication:**
   $$(B^{-1}A^{-1})(AB) = B^{-1}(A^{-1}A)B = B^{-1}(I)B = B^{-1}B = I$$

Because matrix multiplication is associative, the inner terms $B$ and $B^{-1}$ (or $A^{-1}$ and $A$) cancel out adjacent to each other. If the order were not reversed:
$$(AB)(A^{-1}B^{-1}) = A(B A^{-1})B^{-1}$$
Since matrices generally do not commute ($B A^{-1} \ne A^{-1} B$), the terms cannot meet, and the product does not simplify to $I$.

### Operational Intuition
In terms of linear transformations, $ABx = A(Bx)$ represents a sequence of actions:
1. First, transformation $B$ acts on $x$.
2. Second, transformation $A$ acts on the intermediate result $Bx$.

To undo this sequence and return to $x$, one must reverse the operations in opposite chronological order:
1. First, undo the most recent operation by applying $A^{-1}$.
2. Second, undo the original operation by applying $B^{-1}$.
Hence, the inverse mapping is $x = B^{-1}(A^{-1}y) = (B^{-1}A^{-1})y$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $AB$ and $(AB)^{-1}$
Multiply $A$ by $B$:
$$AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix} = \begin{pmatrix} 1(2) + 1(0) & 1(0) + 1(3) \\ 0(2) + 1(0) & 0(0) + 1(3) \end{pmatrix} = \begin{pmatrix} 2 & 3 \\ 0 & 3 \end{pmatrix}$$

Compute the determinant of $AB$:
$$\det(AB) = (2)(3) - (3)(0) = 6 - 0 = 6 \ne 0$$

Find $(AB)^{-1}$ using the $2 \times 2$ inversion formula:
$$(AB)^{-1} = \frac{1}{6} \begin{pmatrix} 3 & -3 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{6} & -\frac{3}{6} \\ 0 & \frac{2}{6} \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}$$

---

### Step 2: Compute $A^{-1}$ and $B^{-1}$
1. **Inverse of $A$:**
   $$\det A = (1)(1) - (1)(0) = 1$$
   $$A^{-1} = \frac{1}{1} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$$

2. **Inverse of $B$:**
   Since $B$ is a diagonal matrix, its inverse is obtained by taking the reciprocals of its diagonal entries:
   $$B^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix}$$

---

### Step 3: Compute the Product $B^{-1} A^{-1}$
Multiply $B^{-1}$ by $A^{-1}$:
$$B^{-1} A^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$$

Compute each entry:
- Entry $(1, 1)$: $\frac{1}{2}(1) + 0(0) = \frac{1}{2}$
- Entry $(1, 2)$: $\frac{1}{2}(-1) + 0(1) = -\frac{1}{2}$
- Entry $(2, 1)$: $0(1) + \frac{1}{3}(0) = 0$
- Entry $(2, 2)$: $0(-1) + \frac{1}{3}(1) = \frac{1}{3}$

Thus:
$$B^{-1} A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix}$$

---

### Step 4: Comparison and Conclusion
Comparing the results:
$$(AB)^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix} = B^{-1} A^{-1}$$
The two matrices are completely identical, confirming the theorem $(AB)^{-1} = B^{-1}A^{-1}$.

---

## 4. Verification and Consistency Checks

1. **Non-Reversed Order Contrast ($A^{-1} B^{-1}$):**
   Compute the non-reversed product to confirm that order strictly matters:
   $$A^{-1} B^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} 1\left(\frac{1}{2}\right) & -1\left(\frac{1}{3}\right) \\ 0 & 1\left(\frac{1}{3}\right) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{3} \\ 0 & \frac{1}{3} \end{pmatrix}$$
   Notice that the $(1, 2)$ entry is $-\frac{1}{3} \ne -\frac{1}{2}$. Therefore:
   $$A^{-1} B^{-1} \ne (AB)^{-1}$$
   This explicitly demonstrates why failing to reverse the order yields an incorrect matrix.

2. **Full Product Verification ($AB \cdot B^{-1}A^{-1} = I_2$):**
   $$\begin{pmatrix} 2 & 3 \\ 0 & 3 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & \frac{1}{3} \end{pmatrix} = \begin{pmatrix} 2\left(\frac{1}{2}\right) + 3(0) & 2\left(-\frac{1}{2}\right) + 3\left(\frac{1}{3}\right) \\ 0 + 3(0) & 0 + 3\left(\frac{1}{3}\right) \end{pmatrix} = \begin{pmatrix} 1 & -1 + 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$
