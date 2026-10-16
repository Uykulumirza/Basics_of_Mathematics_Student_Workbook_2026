# Solution to Exercise 13: Undoing a Composite Transformation

## 1. Problem Statement

Given the transformation matrices:
$$S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \quad (\text{non-uniform horizontal scaling}), \qquad H = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \quad (\text{horizontal shear})$$

Let $T = HS$ be their composition.
1. Find $T^{-1}$ by first computing $T$ directly and then inverting it.
2. Find $T^{-1}$ using the product formula $(HS)^{-1} = S^{-1}H^{-1}$.
3. Compare the two results.
4. Additionally, compute the reverse-order product $H^{-1}S^{-1}$ and demonstrate that it produces an incorrect, different matrix.
5. Explain the geometric and physical intuition behind the rule: *"When undoing a composition of operations, we must undo them from the end."*

---

## 2. Theoretical Background and Concepts

### Composition and Inversion of Transformations
Matrix multiplication corresponds to the composition of linear transformations:
$$(T_H \circ T_S)(x) = H(Sx) = (HS)x$$
In the product $T = HS$, the matrix written on the right ($S$) acts **first**, and the matrix on the left ($H$) acts **second**.

### Inverting a Composition
To invert a chain of operations:
$$(A_1 A_2 \cdots A_k)^{-1} = A_k^{-1} \cdots A_2^{-1} A_1^{-1}$$
The last operation performed is the outermost layer of modification; therefore, it must be the very first operation undone. Attempting to undo an inner operation while the outer modification is still applied creates severe distortion because the inner operation acts on the wrong geometric coordinate configuration.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Compute $T$ First, Then Invert $T$

1. **Compute the composite matrix $T = HS$:**
   $$T = \begin{pmatrix} 1 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1(2) + 1(0) & 1(0) + 1(1) \\ 0(2) + 1(0) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix}$$

2. **Compute the determinant of $T$:**
   $$\det T = (2)(1) - (1)(0) = 2 \ne 0$$

3. **Invert $T$ using the $2 \times 2$ formula:**
   $$T^{-1} = \frac{1}{\det T} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 & -1 \\ 0 & 2 \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}$$

---

### Method 2: Invert Components First, Then Use $(HS)^{-1} = S^{-1} H^{-1}$

1. **Compute $S^{-1}$:**
   Matrix $S$ is diagonal:
   $$S^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix}$$

2. **Compute $H^{-1}$:**
   $$\det H = (1)(1) - (1)(0) = 1$$
   $$H^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix}$$

3. **Compute the product $S^{-1} H^{-1}$:**
   $$S^{-1} H^{-1} = \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(1) + 0 & \frac{1}{2}(-1) + 0 \\ 0 + 1(0) & 0 + 1(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}$$

---

### Step 3: Comparison of Results
Comparing Method 1 and Method 2:
$$T^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix} = S^{-1} H^{-1}$$
Both methods produce the exact same matrix, verifying the algebraic rule.

---

### Step 4: Compute the Incorrect Order $H^{-1} S^{-1}$
Multiply $H^{-1}$ by $S^{-1}$:
$$H^{-1} S^{-1} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 1\left(\frac{1}{2}\right) + (-1)(0) & 1(0) + (-1)(1) \\ 0\left(\frac{1}{2}\right) + 1(0) & 0(0) + 1(1) \end{pmatrix} = \begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix}$$

**Observation:**
Comparing $H^{-1} S^{-1}$ with the true inverse $T^{-1}$:
$$\begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix} \ne \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} \\ 0 & 1 \end{pmatrix}$$
The entry at position $(1, 2)$ is $-1$ instead of $-\frac{1}{2}$.
Multiplying $T$ by this incorrect candidate yields:
$$T (H^{-1} S^{-1}) = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 2(1/2) + 1(0) & 2(-1) + 1(1) \\ 0 & 0 + 1(1) \end{pmatrix} = \begin{pmatrix} 1 & -1 \\ 0 & 1 \end{pmatrix} \ne I_2$$
This conclusively proves that failing to reverse the order does not invert the transformation.

---

### Step 5: Geometric Explanation of the Rule

Consider a point $(x, y) \in \mathbb{R}^2$ undergoing the transformation $T = HS$:
1. **Step 1 ($S$ acts first):** The point is stretched horizontally by a factor of $2$, yielding $(2x, y)$.
2. **Step 2 ($H$ acts second):** The shear adds the current vertical coordinate $y$ to the new horizontal coordinate:
   $$\begin{pmatrix} x' \\ y' \end{pmatrix} = \begin{pmatrix} 2x + y \\ y \end{pmatrix}$$

**To reverse this process and recover $(x, y)$:**
- The current $x'$ contains a mixture of the stretched $x$ coordinate and the shear displacement $+y$.
- If we mistakenly try to "unscale" first (dividing $x'$ by $2$ via $S^{-1}$), we would divide the added shear $y$ by $2$ as well, distorting the shear offset to $\frac{y}{2}$.
- Therefore, we **must first remove the shear** (applying $H^{-1}$: $x' - y = (2x + y) - y = 2x$).
- Now that the horizontal coordinate is purely the scaled value $2x$, we can **safely undo the scaling** (applying $S^{-1}$: dividing $2x$ by $2$ to obtain $x$).

This is why we must always undo sequential operations **from the end** (LIFO: Last In, First Out).

---

## 4. Verification and Consistency Checks

1. **Concrete Coordinate Tracking Check:**
   Let $v = \begin{pmatrix} 3 \\ 4 \end{pmatrix}$.
   - Forward pass:
     $$S \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 \\ 4 \end{pmatrix}$$
     $$H \begin{pmatrix} 6 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 + 4 \\ 4 \end{pmatrix} = \begin{pmatrix} 10 \\ 4 \end{pmatrix}$$
     $$T v = \begin{pmatrix} 2 & 1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 3 \\ 4 \end{pmatrix} = \begin{pmatrix} 10 \\ 4 \end{pmatrix} \quad \checkmark$$

   - Reverse pass with correct inverse $T^{-1} = S^{-1}H^{-1}$:
     $$H^{-1} \begin{pmatrix} 10 \\ 4 \end{pmatrix} = \begin{pmatrix} 10 - 4 \\ 4 \end{pmatrix} = \begin{pmatrix} 6 \\ 4 \end{pmatrix}$$
     $$S^{-1} \begin{pmatrix} 6 \\ 4 \end{pmatrix} = \begin{pmatrix} 6/2 \\ 4 \end{pmatrix} = \begin{pmatrix} 3 \\ 4 \end{pmatrix} = v \quad \checkmark$$

   - Reverse pass with incorrect candidate $H^{-1}S^{-1}$:
     $$\begin{pmatrix} \frac{1}{2} & -1 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 10 \\ 4 \end{pmatrix} = \begin{pmatrix} \frac{1}{2}(10) - 4 \\ 4 \end{pmatrix} = \begin{pmatrix} 5 - 4 \\ 4 \end{pmatrix} = \begin{pmatrix} 1 \\ 4 \end{pmatrix} \ne \begin{pmatrix} 3 \\ 4 \end{pmatrix}$$
     The incorrect order fails to recover the original vector.
