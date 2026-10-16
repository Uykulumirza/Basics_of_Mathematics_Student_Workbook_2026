# Solution to Exercise 9: Matrix Equation

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}$$

1. Decide on which side of the matrix equation $AX = B$ the inverse $A^{-1}$ must be multiplied.
2. Solve the equation for the unknown matrix $X$.
3. Check the solution by explicitly computing the product $AX$.

---

## 2. Theoretical Background and Concepts

### Non-Commutativity of Matrix Multiplication
In ordinary scalar arithmetic, $ax = b \implies x = a^{-1}b = ba^{-1}$.
However, in matrix algebra, matrix multiplication is strictly **non-commutative**:
$$M N \ne N M \quad \text{in general}$$

Therefore, the placement (left vs. right) of the inverse matrix is of paramount importance:
- For $AX = B$: To eliminate $A$, which is multiplied to the **left** of $X$, one must multiply both sides on the **left** by $A^{-1}$:
  $$A^{-1}(AX) = A^{-1}B \implies (A^{-1}A)X = A^{-1}B \implies X = A^{-1}B$$
- If one mistakenly multiplied on the right by $A^{-1}$:
  $$(AX)A^{-1} = BA^{-1}$$
  Because $X$ and $A^{-1}$ do not commute, $AXA^{-1}$ cannot be simplified to $X$.
- Conversely, for an equation of the form $XA = B$, one would multiply on the **right** by $A^{-1}$:
  $$(XA)A^{-1} = BA^{-1} \implies X(AA^{-1}) = BA^{-1} \implies X = BA^{-1}$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Decision on Multiplication Side
In the equation:
$$AX = B$$
the matrix $A$ appears on the left of the unknown matrix $X$.
To cancel $A$ using $A^{-1}A = I_2$, we must multiply both sides of the equation by $A^{-1}$ on the **left**:
$$A^{-1}(AX) = A^{-1}B \implies X = A^{-1}B$$

---

### Step 2: Compute $A^{-1}$
For the upper triangular shear matrix $A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$:
$$\det A = (1)(1) - (2)(0) = 1 \ne 0$$

Using the $2 \times 2$ inverse formula:
$$A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{1} \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix}$$

---

### Step 3: Compute $X = A^{-1}B$
Multiply $A^{-1}$ by $B$:
$$X = \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix}$$

Compute each entry:
- Entry $(1, 1)$: $1(3) + (-2)(2) = 3 - 4 = -1$
- Entry $(1, 2)$: $1(1) + (-2)(4) = 1 - 8 = -7$
- Entry $(2, 1)$: $0(3) + 1(2) = 0 + 2 = 2$
- Entry $(2, 2)$: $0(1) + 1(4) = 0 + 4 = 4$

Thus:
$$X = \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix}$$

---

### Step 4: Verification via Computing $AX$
Multiply matrix $A$ by the calculated $X$:
$$AX = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix}$$

Evaluate each element:
- Position $(1, 1)$: $1(-1) + 2(2) = -1 + 4 = 3$
- Position $(1, 2)$: $1(-7) + 2(4) = -7 + 8 = 1$
- Position $(2, 1)$: $0(-1) + 1(2) = 0 + 2 = 2$
- Position $(2, 2)$: $0(-7) + 1(4) = 0 + 4 = 4$

Thus:
$$AX = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix} = B \quad \checkmark$$

The matrix $X$ correctly satisfies the equation $AX = B$.

---

## 4. Verification and Consistency Checks

1. **Incorrect Multiplication Comparison ($X_{\text{wrong}} = B A^{-1}$):**
   To demonstrate the vital importance of multiplication order, calculate $B A^{-1}$:
   $$B A^{-1} = \begin{pmatrix} 3 & 1 \\ 2 & 4 \end{pmatrix} \begin{pmatrix} 1 & -2 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 3(1) + 1(0) & 3(-2) + 1(1) \\ 2(1) + 4(0) & 2(-2) + 4(1) \end{pmatrix} = \begin{pmatrix} 3 & -5 \\ 2 & 0 \end{pmatrix}$$
   Notice that $B A^{-1} = \begin{pmatrix} 3 & -5 \\ 2 & 0 \end{pmatrix} \ne \begin{pmatrix} -1 & -7 \\ 2 & 4 \end{pmatrix} = X$.
   Checking $A(BA^{-1})$:
   $$\begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 & -5 \\ 2 & 0 \end{pmatrix} = \begin{pmatrix} 7 & -5 \\ 2 & 0 \end{pmatrix} \ne B$$
   This reinforces that multiplying on the wrong side produces an invalid solution.

2. **Column-by-Column System Check:**
   Writing $X = \begin{pmatrix} x_1 & x_2 \end{pmatrix}$:
   - Column 1: $\begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -1 \\ 2 \end{pmatrix} = \begin{pmatrix} 3 \\ 2 \end{pmatrix} = \text{Col}_1(B) \checkmark$
   - Column 2: $\begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -7 \\ 4 \end{pmatrix} = \begin{pmatrix} 1 \\ 4 \end{pmatrix} = \text{Col}_2(B) \checkmark$
