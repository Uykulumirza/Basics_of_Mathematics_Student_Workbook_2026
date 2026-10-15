# Solution to Exercise 12: Formula for a Matrix Power

## 1. Problem Statement

Let:
$$A = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$

1. Compute $A^2$, $A^3$, and $A^4$.
2. Formulate a general conjecture for the matrix power $A^n$ for all integers $n \ge 1$.
3. Prove the conjecture by mathematical induction (assume the formula is true for $n$, multiply by $A$, and demonstrate that the formula for $n + 1$ is obtained).

---

## 2. Theoretical Background and Concepts

### Matrix Powers and Nilpotent Decompositions
For a square matrix $A \in M_m(\mathbb{R})$, integer powers are defined recursively:
$$A^1 = A, \qquad A^{n+1} = A^n \cdot A \quad \text{for } n \ge 1$$

Matrix $A$ is a standard **unipotent upper triangular matrix** (or a shear matrix), which can be decomposed as:
$$A = I + N, \qquad \text{where } I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \quad N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$$
Notice that $N^2 = \begin{pmatrix} 0 & 0 \\ 0 & 0 \end{pmatrix} = 0$. Because $I$ and $N$ commute, higher-order terms in the binomial expansion vanish.

### Principle of Mathematical Induction
To prove a proposition $P(n)$ holds for all integers $n \ge 1$:
1. **Base Case:** Prove that $P(1)$ is true.
2. **Induction Step:** Assume $P(k)$ is true for an arbitrary integer $k \ge 1$ (the induction hypothesis), and deduce that $P(k+1)$ must also be true.
3. Conclude that $P(n)$ is true for all $n \in \mathbb{N}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Successive Powers
- **Compute $A^2 = A \cdot A$:**
  $$A^2 = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(0) & 1(1) + 1(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}$$

- **Compute $A^3 = A^2 \cdot A$:**
  $$A^3 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 2(0) & 1(1) + 2(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}$$

- **Compute $A^4 = A^3 \cdot A$:**
  $$A^4 = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(1) + 3(0) & 1(1) + 3(1) \\ 0(1) + 1(0) & 0(1) + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}$$

---

### Step 2: Formulate the Conjecture
Observing the sequence:
$$A^1 = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}, \quad A^2 = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \quad A^3 = \begin{pmatrix} 1 & 3 \\ 0 & 1 \end{pmatrix}, \quad A^4 = \begin{pmatrix} 1 & 4 \\ 0 & 1 \end{pmatrix}$$

The diagonal entries remain identically $1$, the lower-left entry remains $0$, and the upper-right entry equals the power exponent $n$.

**Conjecture $P(n)$:** For all integers $n \ge 1$:
$$A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$$

---

### Step 3: Proof by Mathematical Induction

1. **Base Case ($n = 1$):**
   For $n = 1$:
   $$\begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} = A^1$$
   Thus, $P(1)$ is true.

2. **Induction Hypothesis:**
   Assume that the formula holds for an arbitrary integer $k \ge 1$:
   $$A^k = \begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix}$$

3. **Induction Step (Show $P(k+1)$ is true):**
   Using the definition of powers, $A^{k+1} = A^k \cdot A$. Substituting the hypothesis:
   $$A^{k+1} = \begin{pmatrix} 1 & k \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix}$$

   Multiply the two matrices:
   - Row 1, Column 1: $1 \cdot 1 + k \cdot 0 = 1$
   - Row 1, Column 2: $1 \cdot 1 + k \cdot 1 = 1 + k = k + 1$
   - Row 2, Column 1: $0 \cdot 1 + 1 \cdot 0 = 0$
   - Row 2, Column 2: $0 \cdot 1 + 1 \cdot 1 = 1$

   Therefore:
   $$A^{k+1} = \begin{pmatrix} 1 & k+1 \\ 0 & 1 \end{pmatrix}$$
   This is exactly the expression given by $P(n)$ with $n = k+1$.

4. **Conclusion:**
   By the principle of mathematical induction, the formula:
   $$A^n = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$$
   holds for all positive integers $n \ge 1$. $\blacksquare$

---

## 4. Verification and Consistency Checks

1. **Verification via Binomial Expansion:**
   Write $A = I + N$ where $N = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}$.
   Since $N^2 = 0$, $N^k = 0$ for all $k \ge 2$. Because $I$ and $N$ commute:
   $$A^n = (I + N)^n = \binom{n}{0} I^n + \binom{n}{1} I^{n-1} N + \sum_{k=2}^n \binom{n}{k} I^{n-k} N^k = I + n N$$
   $$A^n = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} + n \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} = \begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$$
   The algebraic proof confirms our inductive result.

2. **Geometric Interpretation (Shear Mapping):**
   The matrix $A$ represents a horizontal shear transformation:
   $$\begin{pmatrix} x \\ y \end{pmatrix} \mapsto \begin{pmatrix} x + y \\ y \end{pmatrix}$$
   Applying this shear $n$ times in succession shifts the horizontal coordinate by $y$ at each step, totaling $x + ny$, while the vertical distance $y$ remains unchanged. The transformation matrix for $n$ successive shears is therefore $\begin{pmatrix} 1 & n \\ 0 & 1 \end{pmatrix}$.

