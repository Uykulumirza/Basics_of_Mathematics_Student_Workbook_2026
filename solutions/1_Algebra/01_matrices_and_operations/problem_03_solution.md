# Solution to Exercise 3: When Can Matrices Be Multiplied?

## 1. Problem Statement

The sizes of four matrices are given as follows:
$$A_{2\times3}, \qquad B_{3\times4}, \qquad C_{4\times2}, \qquad D_{2\times2}$$

For each of the following matrix products:
$$AB, \quad BA, \quad BC, \quad CB, \quad AC, \quad CA, \quad AD, \quad DA$$

Determine whether the product is defined. If defined, state the size of the resulting matrix. Justify each decision using the dimension compatibility condition.

---

## 2. Theoretical Background and Concepts

### Dimension Compatibility for Matrix Multiplication
Let $M$ and $N$ be two matrices. The product $MN$ is defined **if and only if** the number of columns in the left matrix $M$ is equal to the number of rows in the right matrix $N$.

Formally:
- If $M$ is of size $m \times k$ and $N$ is of size $k \times p$, the "inner dimensions" $k$ match.
- The resulting matrix $P = MN$ has size given by the "outer dimensions":
  $$\text{size}(MN) = m \times p$$
- If the number of columns of $M$ does not equal the number of rows of $N$, the dot products between rows of $M$ and columns of $N$ cannot be formed, and the product is **undefined**.

---

## 3. Detailed Step-by-Step Solution

We analyze each of the eight products systematically:

### 1. Product $AB$
- Dimensions: $A$ is $2 \times 3$, $B$ is $3 \times 4$.
- Compatibility check: Number of columns of $A$ ($3$) equals number of rows of $B$ ($3$).
- **Status:** **Defined**.
- **Resulting size:** **$2 \times 4$**.

### 2. Product $BA$
- Dimensions: $B$ is $3 \times 4$, $A$ is $2 \times 3$.
- Compatibility check: Number of columns of $B$ ($4$) $\ne$ number of rows of $A$ ($2$).
- **Status:** **Undefined**.

### 3. Product $BC$
- Dimensions: $B$ is $3 \times 4$, $C$ is $4 \times 2$.
- Compatibility check: Number of columns of $B$ ($4$) equals number of rows of $C$ ($4$).
- **Status:** **Defined**.
- **Resulting size:** **$3 \times 2$**.

### 4. Product $CB$
- Dimensions: $C$ is $4 \times 2$, $B$ is $3 \times 4$.
- Compatibility check: Number of columns of $C$ ($2$) $\ne$ number of rows of $B$ ($3$).
- **Status:** **Undefined**.

### 5. Product $AC$
- Dimensions: $A$ is $2 \times 3$, $C$ is $4 \times 2$.
- Compatibility check: Number of columns of $A$ ($3$) $\ne$ number of rows of $C$ ($4$).
- **Status:** **Undefined**.

### 6. Product $CA$
- Dimensions: $C$ is $4 \times 2$, $A$ is $2 \times 3$.
- Compatibility check: Number of columns of $C$ ($2$) equals number of rows of $A$ ($2$).
- **Status:** **Defined**.
- **Resulting size:** **$4 \times 3$**.

### 7. Product $AD$
- Dimensions: $A$ is $2 \times 3$, $D$ is $2 \times 2$.
- Compatibility check: Number of columns of $A$ ($3$) $\ne$ number of rows of $D$ ($2$).
- **Status:** **Undefined**.

### 8. Product $DA$
- Dimensions: $D$ is $2 \times 2$, $A$ is $2 \times 3$.
- Compatibility check: Number of columns of $D$ ($2$) equals number of rows of $A$ ($2$).
- **Status:** **Defined**.
- **Resulting size:** **$2 \times 3$**.

---

## 4. Verification and Consistency Checks

### Summary Table

| Product | Left Matrix Size ($m \times k$) | Right Matrix Size ($k' \times p$) | Inner Compatibility ($k \stackrel{?}{=} k'$) | Defined? | Resulting Size ($m \times p$) |
| :---: | :---: | :---: | :---: | :---: | :---: |
| $AB$ | $2 \times 3$ | $3 \times 4$ | $3 = 3$ | **Yes** | $2 \times 4$ |
| $BA$ | $3 \times 4$ | $2 \times 3$ | $4 \ne 2$ | **No** | — |
| $BC$ | $3 \times 4$ | $4 \times 2$ | $4 = 4$ | **Yes** | $3 \times 2$ |
| $CB$ | $4 \times 2$ | $3 \times 4$ | $2 \ne 3$ | **No** | — |
| $AC$ | $2 \times 3$ | $4 \times 2$ | $3 \ne 4$ | **No** | — |
| $CA$ | $4 \times 2$ | $2 \times 3$ | $2 = 2$ | **Yes** | $4 \times 3$ |
| $AD$ | $2 \times 3$ | $2 \times 2$ | $3 \ne 2$ | **No** | — |
| $DA$ | $2 \times 2$ | $2 \times 3$ | $2 = 2$ | **Yes** | $2 \times 3$ |

### Structural Observations
- Notice that while $AB$ is defined, $BA$ is not defined. Even when both products of two matrices are defined (e.g. if we consider $A$ and $C$: $CA$ is defined but $AC$ is not), commutativity of existence generally fails for rectangular matrices.
- The results are fully consistent with the linear mapping interpretation: $A: \mathbb{R}^3 \to \mathbb{R}^2$, $B: \mathbb{R}^4 \to \mathbb{R}^3$, $C: \mathbb{R}^2 \to \mathbb{R}^4$, and $D: \mathbb{R}^2 \to \mathbb{R}^2$. A composition $M \circ N$ is valid if and only if the codomain of $N$ matches the domain of $M$.

