# Solution to Exercise 15: Two Methods for Solving the Same Linear System

## 1. Problem Statement

Given the linear system $Ax = b$ with:
$$A = \begin{pmatrix} 2 & 1 \\ 1 & 3 \end{pmatrix}, \qquad b = \begin{pmatrix} 7 \\ 8 \end{pmatrix}$$

1. Solve the system using the inverse matrix method: $x = A^{-1}b$.
2. Solve the system using Gaussian elimination with back-substitution.
3. Compare both solutions, analyze the number of essential computational steps, and determine which method is simpler and more efficient in this specific example.

---

## 2. Theoretical Background and Concepts

### Solving Linear Systems: Matrix Inversion vs. Gaussian Elimination
When solving a non-singular $n \times n$ linear system $Ax = b$:

1. **Matrix Inversion Method ($x = A^{-1}b$):**
   - Requires computing the determinant $\det A$, forming the adjugate matrix, and scaling by $1/\det A$ (or applying it after multiplying by $b$).
   - Once $A^{-1}$ is explicitly available, solving for a right-hand side $b$ reduces to a matrix-vector multiplication.
   - However, computing $A^{-1}$ from scratch involves extra steps compared to direct elimination. Even when solving $Ax = b$ for multiple right-hand sides $b_1, \dots, b_k$, a reusable $LU$ (or row-reduction) factorization of $A$ achieves the same $O(n^2)$ per-vector solve cost with less preprocessing and better numerical stability than forming $A^{-1}$ explicitly; explicit inversion is mainly advantageous when the entries of $A^{-1}$ are already given or needed directly.

2. **Gaussian Elimination:**
   - Operates directly on the augmented matrix $[A \mid b]$.
   - Reduces the system to row echelon form using elementary row operations, followed by back-substitution.
   - Avoids the overhead of constructing all four entries of $A^{-1}$ when only the single solution vector $x$ is needed.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Solution via Matrix Inversion ($x = A^{-1}b$)

1. **Compute the Determinant of $A$:**
   $$\det A = (2)(3) - (1)(1) = 6 - 1 = 5 \ne 0$$

2. **Compute the Inverse Matrix $A^{-1}$:**
   Using the $2 \times 2$ formula:
   $$A^{-1} = \frac{1}{\det A} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} \frac{3}{5} & -\frac{1}{5} \\ -\frac{1}{5} & \frac{2}{5} \end{pmatrix}$$

3. **Compute the Solution Vector $x = A^{-1}b$:**
   $$x = \frac{1}{5} \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix} \begin{pmatrix} 7 \\ 8 \end{pmatrix}$$

   Perform matrix-vector multiplication:
   $$\begin{pmatrix} 3(7) + (-1)(8) \\ -1(7) + 2(8) \end{pmatrix} = \begin{pmatrix} 21 - 8 \\ -7 + 16 \end{pmatrix} = \begin{pmatrix} 13 \\ 9 \end{pmatrix}$$

   Multiplying by the scalar factor $\frac{1}{5}$:
   $$x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\ 1.8 \end{pmatrix}$$

---

### Method 2: Solution via Gaussian Elimination

1. **Set Up the Augmented Matrix:**
   $$[A \mid b] = \left(\begin{array}{cc|c} 2 & 1 & 7 \\ 1 & 3 & 8 \end{array}\right)$$

2. **Row Swap for a Unit Pivot:**
   Swap row 1 and row 2 to place the leading $1$ into the pivot position $(1, 1)$:
   $$R_1 \leftrightarrow R_2 \implies \left(\begin{array}{cc|c} 1 & 3 & 8 \\ 2 & 1 & 7 \end{array}\right)$$

3. **Forward Elimination:**
   Eliminate the entry $2$ in position $(2, 1)$ using the elementary row operation:
   $$R_2 \leftarrow R_2 - 2R_1$$

   Compute the new row 2:
   $$(2, 1 \mid 7) - 2(1, 3 \mid 8) = (2 - 2, 1 - 6 \mid 7 - 16) = (0, -5 \mid -9)$$

   The augmented matrix in row echelon form is:
   $$\left(\begin{array}{cc|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array}\right)$$

4. **Back-Substitution:**
   - From row 2:
     $$-5x_2 = -9 \implies x_2 = \frac{9}{5}$$
   - Substitute $x_2 = \frac{9}{5}$ into row 1:
     $$x_1 + 3x_2 = 8 \implies x_1 = 8 - 3\left(\frac{9}{5}\right) = \frac{40 - 27}{5} = \frac{13}{5}$$

Thus, Gaussian elimination yields:
$$x = \begin{pmatrix} \frac{13}{5} \\ \frac{9}{5} \end{pmatrix} = \begin{pmatrix} 2.6 \\ 1.8 \end{pmatrix}$$

---

### Step 3: Comparison and Stage-by-Stage Analysis

**Counting Convention:** We count each non-trivial scalar addition/subtraction, multiplication, division, and sign negation made in the demonstrated calculations above (excluding the known zero created at the pivot column $(2,1)$ during row elimination, where $2 - 2(1) = 0$ by construction):

- **Method 1 (via $\frac{1}{\det A}\operatorname{adj}(A)b$, scaling at the end):**
  1. *Determinant $\det A = 2(3) - 1(1) = 5$:* $2$ multiplications and $1$ subtraction ($3$ ops).
  2. *Adjugate construction $\operatorname{adj}(A) = \begin{pmatrix} 3 & -1 \\ -1 & 2 \end{pmatrix}$:* $1$ diagonal swap and $2$ sign negations ($2$ sign ops). (If $A^{-1}$ is scaled entry-by-entry first, that adds $4$ divisions by $5$.)
  3. *Product $\operatorname{adj}(A)b = \begin{pmatrix} 3(7)+(-1)(8) \\ (-1)(7)+2(8) \end{pmatrix} = \begin{pmatrix} 13 \\ 9 \end{pmatrix}$:* $4$ multiplications and $2$ additions ($6$ ops).
  4. *Final scaling by $1/5$:* $2$ divisions by $5$ to obtain $(13/5, 9/5)^T$ ($2$ ops).
  - **Total for Method 1:** $3 + 2 + 6 + 2 = 13$ scalar operations ($11$ arithmetic ops $+ 2$ sign negations).

- **Method 2 (Gaussian Elimination on $[A \mid b]$):**
  1. *Row swap $R_1 \leftrightarrow R_2$:* structural re-indexing to use the unit pivot $1$ ($0$ arithmetic ops, avoiding a division to find the multiplier $m = 2/1 = 2$).
  2. *Forward elimination $R_2 \leftarrow R_2 - 2R_1$ on the remaining two columns:* $2$ multiplications ($2 \cdot 3 = 6$, $2 \cdot 8 = 16$) and $2$ subtractions ($1 - 6 = -5$, $7 - 16 = -9$) ($4$ ops; $6$ ops if the explicit pivot-column check $2 - 2(1) = 0$ is also counted).
  3. *Back-substitution:* $1$ division ($x_2 = (-9)/(-5) = 9/5$), $1$ multiplication ($3 \cdot \frac{9}{5} = \frac{27}{5}$), and $1$ subtraction ($8 - \frac{27}{5} = \frac{13}{5}$) ($3$ ops).
  - **Total for Method 2:** $4 + 3 = 7$ scalar operations ($9$ if the pivot-column zero check is included).

| Stage / Aspect | Method 1: Matrix Inversion ($x = A^{-1}b$) | Method 2: Gaussian Elimination |
| :--- | :--- | :--- |
| **Final Solution** | $x = (13/5, 9/5)^T$ | $x = (13/5, 9/5)^T$ |
| **Intermediate Object** | Determinant $\det A = 5$ and full matrix $\operatorname{adj}(A)$ / $A^{-1}$ | Upper-triangular augmented system $\left(\begin{array}{cc\|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array}\right)$ |
| **Essential Stages** | 1. Compute $\det A$<br>2. Swap diagonal & negate off-diagonals<br>3. Multiply $\operatorname{adj}(A)b$<br>4. Divide both entries by $\det A = 5$ | 1. Swap rows for unit pivot<br>2. Eliminate $x_1$ from Row 2<br>3. Solve Row 2 for $x_2$, then substitute into Row 1 for $x_1$ |
| **Scalar Operations (Demonstrated)** | **13 ops** ($3$ for $\det A$, $2$ sign changes, $6$ for $\operatorname{adj}(A)b$, $2$ divisions by $5$) | **7 ops** ($4$ in non-pivot elimination columns, $3$ in back-substitution) |

### Conclusion on Which Method is Simpler
- **For this single demonstrated system:** **Gaussian elimination is simpler and more direct.** Swapping rows immediately provides a unit pivot ($1$), so only one row update and a two-step back-substitution are required ($7$ operations), whereas the inversion method must first compute $\det A$, form the adjugate, perform a full $2 \times 2$ matrix-vector product, and divide both components by $5$ ($13$ operations).
- **When each approach is appropriate:** Explicit multiplication by $A^{-1}$ is only shorter if $A^{-1}$ has *already* been computed and provided in advance (reducing the work to the $6$ operations of $A^{-1}b$). Even when solving $Ax = b$ for multiple right-hand sides $b_1, \dots, b_k$, recording the elimination multipliers in an $LU$ factorization ($PA = LU$) allows each new right-hand side to be solved by forward/back-substitution without explicitly forming $A^{-1}$.

---

## 4. Verification and Consistency Checks

1. **Direct Substitution into Original Equations:**
   Substitute $x_1 = \frac{13}{5}$ and $x_2 = \frac{9}{5}$ into the original system:
   - Equation 1:
     $$2x_1 + x_2 = 2\left(\frac{13}{5}\right) + \frac{9}{5} = \frac{26 + 9}{5} = \frac{35}{5} = 7 = b_1 \quad \checkmark$$
   - Equation 2:
     $$x_1 + 3x_2 = \frac{13}{5} + 3\left(\frac{9}{5}\right) = \frac{13 + 27}{5} = \frac{40}{5} = 8 = b_2 \quad \checkmark$$

2. **Cramer's Rule Verification:**
   $$D = \det A = 5$$
   $$D_1 = \det \begin{pmatrix} 7 & 1 \\ 8 & 3 \end{pmatrix} = 21 - 8 = 13 \implies x_1 = \frac{D_1}{D} = \frac{13}{5} \quad \checkmark$$
   $$D_2 = \det \begin{pmatrix} 2 & 7 \\ 1 & 8 \end{pmatrix} = 16 - 7 = 9 \implies x_2 = \frac{D_2}{D} = \frac{9}{5} \quad \checkmark$$
