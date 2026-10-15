# Solution to Exercise 15: Associativity of Multiplication and Different Calculation Paths

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}, \qquad C = \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}$$

1. Compute the product $(AB)C$.
2. Compute the product $A(BC)$.
3. Compare the results and verify the associative property: $(AB)C = A(BC)$.
4. Compare the computational complexity (number of intermediate scalar operations) between both calculation paths.
5. Explain what associativity of matrix multiplication means in this context.

---

## 2. Theoretical Background and Concepts

### Associativity of Matrix Multiplication
For any three matrices $A \in \mathbb{R}^{m \times k}$, $B \in \mathbb{R}^{k \times p}$, and $C \in \mathbb{R}^{p \times n}$, matrix multiplication is **associative**:
$$(AB)C = A(BC)$$
This property ensures that the product $ABC$ is unambiguously defined without needing parentheses to specify the order of pairwise groupings.

### Computational Complexity (Matrix Chain Multiplication)
Multiplying an $m \times k$ matrix by a $k \times p$ matrix requires:
- $m \cdot k \cdot p$ scalar multiplications,
- $m \cdot (k - 1) \cdot p$ scalar additions.

Although $(AB)C$ and $A(BC)$ produce mathematically identical matrices, the two grouping paths can require differing numbers of arithmetic operations depending on the dimensions of the intermediate matrices. Choosing the optimal parenthesization is the subject of the classical *Matrix Chain Multiplication problem* in computer science.

---

## 3. Detailed Step-by-Step Solution

The dimensions of the given matrices are:
- $A$ is $2 \times 3$
- $B$ is $3 \times 2$
- $C$ is $2 \times 2$

---

### Step 1: Path 1 — Compute $(AB)C$

#### Part 1A: Compute $AB$
$A$ is $2 \times 3$ and $B$ is $3 \times 2$, so $AB$ is a $2 \times 2$ matrix:
$$AB = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}$$

- Entry $(1, 1) = 1(1) + 2(2) + 0(-1) = 1 + 4 + 0 = 5$
- Entry $(1, 2) = 1(0) + 2(1) + 0(3) = 0 + 2 + 0 = 2$
- Entry $(2, 1) = 0(1) + 1(2) + 1(-1) = 0 + 2 - 1 = 1$
- Entry $(2, 2) = 0(0) + 1(1) + 1(3) = 0 + 1 + 3 = 4$

$$AB = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix}$$

#### Part 1B: Multiply by $C$ to obtain $(AB)C$
$(AB)$ is $2 \times 2$ and $C$ is $2 \times 2$:
$$(AB)C = \begin{pmatrix} 5 & 2 \\ 1 & 4 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}$$

- Entry $(1, 1) = 5(2) + 2(0) = 10 + 0 = 10$
- Entry $(1, 2) = 5(1) + 2(-1) = 5 - 2 = 3$
- Entry $(2, 1) = 1(2) + 4(0) = 2 + 0 = 2$
- Entry $(2, 2) = 1(1) + 4(-1) = 1 - 4 = -3$

$$(AB)C = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}$$

---

### Step 2: Path 2 — Compute $A(BC)$

#### Part 2A: Compute $BC$
$B$ is $3 \times 2$ and $C$ is $2 \times 2$, so $BC$ is a $3 \times 2$ matrix:
$$BC = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 0 & -1 \end{pmatrix}$$

- Entry $(1, 1) = 1(2) + 0(0) = 2 + 0 = 2$
- Entry $(1, 2) = 1(1) + 0(-1) = 1 + 0 = 1$
- Entry $(2, 1) = 2(2) + 1(0) = 4 + 0 = 4$
- Entry $(2, 2) = 2(1) + 1(-1) = 2 - 1 = 1$
- Entry $(3, 1) = (-1)(2) + 3(0) = -2 + 0 = -2$
- Entry $(3, 2) = (-1)(1) + 3(-1) = -1 - 3 = -4$

$$BC = \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}$$

#### Part 2B: Multiply $A$ by $(BC)$ to obtain $A(BC)$
$A$ is $2 \times 3$ and $BC$ is $3 \times 2$:
$$A(BC) = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 4 & 1 \\ -2 & -4 \end{pmatrix}$$

- Entry $(1, 1) = 1(2) + 2(4) + 0(-2) = 2 + 8 + 0 = 10$
- Entry $(1, 2) = 1(1) + 2(1) + 0(-4) = 1 + 2 + 0 = 3$
- Entry $(2, 1) = 0(2) + 1(4) + 1(-2) = 0 + 4 - 2 = 2$
- Entry $(2, 2) = 0(1) + 1(1) + 1(-4) = 0 + 1 - 4 = -3$

$$A(BC) = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix}$$

---

### Step 3: Comparison and Verification
Comparing the two computed matrices:
$$(AB)C = \begin{pmatrix} 10 & 3 \\ 2 & -3 \end{pmatrix} = A(BC)$$
The results are identical in every single entry.

---

### Step 4: Comparison of Computational Work (Number of Operations)

Let us count the scalar multiplications required in each path:

1. **Path 1: $(AB)C$**
   - Computing $AB$ ($2 \times 3 \times 2$): $2 \times 3 \times 2 = 12$ multiplications.
   - Computing $(AB)C$ ($2 \times 2 \times 2$): $2 \times 2 \times 2 = 8$ multiplications.
   - **Total scalar multiplications:** $12 + 8 = \mathbf{20}$.

2. **Path 2: $A(BC)$**
   - Computing $BC$ ($3 \times 2 \times 2$): $3 \times 2 \times 2 = 12$ multiplications.
   - Computing $A(BC)$ ($2 \times 3 \times 2$): $2 \times 3 \times 2 = 12$ multiplications.
   - **Total scalar multiplications:** $12 + 12 = \mathbf{24}$.

**Observation:** Path 1 requires **20 multiplications**, whereas Path 2 requires **24 multiplications**. Parenthesizing as $(AB)C$ is computationally more efficient than $A(BC)$ by 4 scalar multiplications (a 16.7% reduction).

---

### Step 5: Meaning of Associativity
Associativity means that when composing multiple consecutive linear transformations:
$$x \xrightarrow{C} Cx \xrightarrow{B} B(Cx) \xrightarrow{A} A(B(Cx))$$
the grouping of the operations does not change the final mapping. Whether we view the composite process as:
- First combining $A$ and $B$ into a single macro-operator $AB$ and then applying it to $Cx$, or
- First combining $B$ and $C$ into an operator $BC$ and then following it by $A$,
the resulting end-to-end transformation is strictly identical.

---

## 4. Verification and Consistency Checks

1. **Trace Consistency:**
   $$\operatorname{tr}((AB)C) = 10 + (-3) = 7$$
   $$\operatorname{tr}(A(BC)) = 10 + (-3) = 7 \quad \checkmark$$

2. **Determinant Consistency:**
   $$\det((AB)C) = 10(-3) - 3(2) = -30 - 6 = -36$$
   We can also verify this using the determinant multiplicativity $\det(AB) \cdot \det(C)$:
   - $\det(AB) = 5(4) - 2(1) = 20 - 2 = 18$
   - $\det(C) = 2(-1) - 1(0) = -2$
   - $\det(AB) \cdot \det(C) = 18 \cdot (-2) = -36 \quad \checkmark$
   Both calculations yield identical determinants of $-36$.

