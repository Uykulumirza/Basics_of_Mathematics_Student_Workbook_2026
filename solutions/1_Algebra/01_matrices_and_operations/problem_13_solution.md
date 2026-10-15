# Solution to Exercise 13: A Recurrence Written in Matrix Form

## 1. Problem Statement

Let:
$$F = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}$$

1. Compute the powers $F^2$, $F^3$, $F^4$, and $F^5$.
2. Compare the entries obtained with the Fibonacci sequence:
   $$0, 1, 1, 2, 3, 5, 8, 13, \dots$$
   and describe the relationship observed.
3. Compute the product:
   $$F \begin{pmatrix} a \\ b \end{pmatrix}$$
4. Explain how this multiplication performs one recurrence step: creating the sum of two consecutive terms and keeping one of them for the next step.

---

## 2. Theoretical Background and Concepts

### Linear Difference Equations (Recurrence Relations)
A second-order linear recurrence relation expresses the next term in a sequence as a linear combination of the two preceding terms:
$$f_{n+1} = c_1 f_n + c_0 f_{n-1}$$
For the classic **Fibonacci sequence**, $c_1 = 1, c_0 = 1$ with initial conditions $f_0 = 0$ and $f_1 = 1$:
$$f_{n+1} = f_n + f_{n-1}, \quad \text{for } n \ge 1$$
The first few terms are:
$$f_0 = 0, \quad f_1 = 1, \quad f_2 = 1, \quad f_3 = 2, \quad f_4 = 3, \quad f_5 = 5, \quad f_6 = 8, \quad f_7 = 13, \dots$$

### Companion Matrix and State-Space Representation
Any scalar second-order recurrence can be converted into a first-order system of vector equations using a state vector $v_n = \begin{pmatrix} f_n \\ f_{n-1} \end{pmatrix}$ for $n \ge 1$:
$$v_{n+1} = \begin{pmatrix} f_{n+1} \\ f_n \end{pmatrix} = \begin{pmatrix} f_n + f_{n-1} \\ f_n \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} f_n \\ f_{n-1} \end{pmatrix} = F v_n$$
Starting from the base state vector:
$$v_1 = \begin{pmatrix} f_1 \\ f_0 \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$
repeated application of the matrix multiplication yields the $n$-th state vector directly for all $n \ge 1$:
$$v_n = F^{n-1} v_1$$


---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute Powers of $F$
- **Compute $F^2 = F \cdot F$:**
  $$F^2 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 1(1) + 1(1) & 1(1) + 1(0) \\ 1(1) + 0(1) & 1(1) + 0(0) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix}$$

- **Compute $F^3 = F^2 \cdot F$:**
  $$F^3 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 2(1) + 1(1) & 2(1) + 1(0) \\ 1(1) + 1(1) & 1(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix}$$

- **Compute $F^4 = F^3 \cdot F$:**
  $$F^4 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 3(1) + 2(1) & 3(1) + 2(0) \\ 2(1) + 1(1) & 2(1) + 1(0) \end{pmatrix} = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix}$$

- **Compute $F^5 = F^4 \cdot F$:**
  $$F^5 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 5(1) + 3(1) & 5(1) + 3(0) \\ 3(1) + 2(1) & 3(1) + 2(0) \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix}$$

---

### Step 2: Compare with the Fibonacci Sequence
Let $f_0 = 0, f_1 = 1, f_2 = 1, f_3 = 2, f_4 = 3, f_5 = 5, f_6 = 8, \dots$.
Let us tabulate the entries of $F^n$:
- $F^1 = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} f_2 & f_1 \\ f_1 & f_0 \end{pmatrix}$
- $F^2 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} = \begin{pmatrix} f_3 & f_2 \\ f_2 & f_1 \end{pmatrix}$
- $F^3 = \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} = \begin{pmatrix} f_4 & f_3 \\ f_3 & f_2 \end{pmatrix}$
- $F^4 = \begin{pmatrix} 5 & 3 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} f_5 & f_4 \\ f_4 & f_3 \end{pmatrix}$
- $F^5 = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} = \begin{pmatrix} f_6 & f_5 \\ f_5 & f_4 \end{pmatrix}$

**Observed General Relationship:**
For any integer $n \ge 1$:
$$F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$$
Every entry of the matrix power $F^n$ corresponds to a Fibonacci number, where the power exponent $n$ dictates the index of the Fibonacci term.

---

### Step 3: Compute $F \begin{pmatrix} a \\ b \end{pmatrix}$
$$F \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} 1 \cdot a + 1 \cdot b \\ 1 \cdot a + 0 \cdot b \end{pmatrix} = \begin{pmatrix} a + b \\ a \end{pmatrix}$$

---

### Step 4: Explanation of the Recurrence Step
Let the current state vector be $v_k = \begin{pmatrix} a \\ b \end{pmatrix} = \begin{pmatrix} f_k \\ f_{k-1} \end{pmatrix}$, containing two consecutive terms of the sequence.
When we multiply by $F$:
1. **First row operation ($a + b$):** The first row of $F$ computes the sum of the current term ($a = f_k$) and the previous term ($b = f_{k-1}$). By definition of the Fibonacci recurrence, this produces the subsequent term:
   $$a + b = f_k + f_{k-1} = f_{k+1}$$
2. **Second row operation ($a$):** The second row of $F$ simply preserves the previous current term ($a = f_k$) and stores it in the second coordinate of the new vector.

The resulting vector is:
$$\begin{pmatrix} f_{k+1} \\ f_k \end{pmatrix}$$
This vector now contains the new pair of consecutive terms ready for the next iteration. Thus, multiplying by $F$ exactly executes one step of the recurrence relation.

---

## 4. Verification and Consistency Checks

1. **Verification via Cassini's Identity:**
   Using the determinant property $\det(F^n) = (\det F)^n$:
   - $\det(F) = 1 \cdot 0 - 1 \cdot 1 = -1$
   - $\det(F^n) = (-1)^n$
   Using our formula $F^n = \begin{pmatrix} f_{n+1} & f_n \\ f_n & f_{n-1} \end{pmatrix}$:
   $$\det(F^n) = f_{n+1} f_{n-1} - f_n^2$$
   Equating the two yields **Cassini's Identity**:
   $$f_{n+1} f_{n-1} - f_n^2 = (-1)^n$$
   Testing for $n = 4$:
   $$f_5 f_3 - f_4^2 = 5 \cdot 2 - 3^2 = 10 - 9 = 1 = (-1)^4 \quad \checkmark$$
   Testing for $n = 5$:
   $$f_6 f_4 - f_5^2 = 8 \cdot 3 - 5^2 = 24 - 25 = -1 = (-1)^5 \quad \checkmark$$

2. **Associativity / Power-Sum Check:**
   $F^5 = F^2 \cdot F^3$:
   $$F^2 \cdot F^3 = \begin{pmatrix} 2 & 1 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 3 & 2 \\ 2 & 1 \end{pmatrix} = \begin{pmatrix} 2(3)+1(2) & 2(2)+1(1) \\ 1(3)+1(2) & 1(2)+1(1) \end{pmatrix} = \begin{pmatrix} 8 & 5 \\ 5 & 3 \end{pmatrix} = F^5 \quad \checkmark$$

