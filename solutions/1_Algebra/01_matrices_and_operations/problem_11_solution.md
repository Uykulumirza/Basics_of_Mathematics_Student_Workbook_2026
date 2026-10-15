# Solution to Exercise 11: When Do Matrices Commute?

## 1. Problem Statement

Given the matrices:
$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \qquad B = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$

1. Find the necessary and sufficient conditions on the real parameters $a, b, c, d$ under which $A$ and $B$ commute, i.e., $AB = BA$.
2. Describe the general form of all such matrices $B$.
3. Give an algebraic interpretation of the space of commuting matrices (the centralizer of $A$).

---

## 2. Theoretical Background and Concepts

### Matrix Commutator and Centralizer
In general, matrix multiplication is non-commutative ($AB \ne BA$). Two matrices commute if their **commutator** vanishes:
$$[A, B] = AB - BA = 0$$

The set of all matrices in $M_n(\mathbb{R})$ that commute with a given matrix $A$ is called the **centralizer** (or commutant) of $A$, denoted $C(A)$:
$$C(A) = \{ B \in M_n(\mathbb{R}) : AB = BA \}$$

### Properties of the Centralizer
1. $C(A)$ is a vector subspace and a subalgebra of $M_n(\mathbb{R})$.
2. Any scalar multiple of the identity $c I$ always belongs to $C(A)$.
3. Any polynomial in $A$, $p(A) = c_k A^k + \dots + c_1 A + c_0 I$, always commutes with $A$.
4. For non-derogatory matrices (such as Jordan blocks), the centralizer consists *precisely* of the polynomials in $A$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Product $AB$
$$AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$

Compute each entry:
- $(AB)_{11} = 1 \cdot a + 1 \cdot c = a + c$
- $(AB)_{12} = 1 \cdot b + 1 \cdot d = b + d$
- $(AB)_{21} = 0 \cdot a + 1 \cdot c = c$
- $(AB)_{22} = 0 \cdot b + 1 \cdot d = d$

Thus:
$$AB = \begin{pmatrix} a + c & b + d \\ c & d \end{pmatrix}$$

---

### Step 2: Compute the Product $BA$
$$BA = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$

Compute each entry:
- $(BA)_{11} = a \cdot 1 + b \cdot 0 = a$
- $(BA)_{12} = a \cdot 1 + b \cdot 1 = a + b$
- $(BA)_{21} = c \cdot 1 + d \cdot 0 = c$
- $(BA)_{22} = c \cdot 1 + d \cdot 1 = c + d$

Thus:
$$BA = \begin{pmatrix} a & a + b \\ c & c + d \end{pmatrix}$$

---

### Step 3: Set Up and Solve the System of Equations for $AB = BA$
For $AB$ to equal $BA$, their corresponding entries must be equal:
$$\begin{pmatrix} a + c & b + d \\ c & d \end{pmatrix} = \begin{pmatrix} a & a + b \\ c & c + d \end{pmatrix}$$

Equating entries:
1. Entry $(1, 1)$: $a + c = a \implies c = 0$
2. Entry $(2, 1)$: $c = c \implies$ satisfied for any $c$, but condition (1) already requires $c = 0$.
3. Entry $(2, 2)$: $d = c + d \implies c = 0$ (consistent with condition 1).
4. Entry $(1, 2)$: $b + d = a + b \implies d = a$.

Therefore, the necessary and sufficient conditions on the entries are:
$$c = 0 \qquad \text{and} \qquad d = a$$
while $a$ and $b$ can be **any arbitrary real numbers**.

---

### Step 4: Describe the General Form of Matrix $B$
Substituting $c = 0$ and $d = a$ into $B$:
$$B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix}, \qquad \text{for any } a, b \in \mathbb{R}$$

### Step 5: Algebraic Interpretation
We can decompose this general matrix $B$ as:
$$B = \begin{pmatrix} a & 0 \\ 0 & a \end{pmatrix} + \begin{pmatrix} 0 & b \\ 0 & 0 \end{pmatrix} = a \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + b \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$

Since $A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = I + \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$, we have $\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = A - I$.
Substituting this in:
$$B = a I + b(A - I) = (a - b)I + bA$$
This proves that the centralizer of $A$ consists of all linear combinations of $I$ and $A$ (i.e., all degree $\le 1$ polynomials in $A$). The dimension of the commutant subspace is $2$.

---

## 4. Verification and Consistency Checks

1. **Direct Substitution Check:**
   Let $B = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix}$. Compute both products:
   $$AB = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} = \begin{pmatrix} 1(a) + 1(0) & 1(b) + 1(a) \\ 0(a) + 1(0) & 0(b) + 1(a) \end{pmatrix} = \begin{pmatrix} a & a + b \\ 0 & a \end{pmatrix}$$
   $$BA = \begin{pmatrix} a & b \\ 0 & a \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} a(1) + b(0) & a(1) + b(1) \\ 0(1) + a(0) & 0(1) + a(1) \end{pmatrix} = \begin{pmatrix} a & a + b \\ 0 & a \end{pmatrix}$$
   $AB = BA$ holds identically for all values of $a$ and $b$.

2. **Counterexample Check (Violating the Condition):**
   Choose a matrix with $c \ne 0$ or $d \ne a$, for example $B' = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}$ (where $c = 1 \ne 0$):
   $$A B' = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}$$
   $$B' A = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix}$$
   $A B' \ne B' A$, confirming that violating the condition indeed breaks commutativity.

