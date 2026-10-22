# Solution to Problem 12: Complete Model and Computer Verification

## 1. Problem Statement
A museum wants to create a rectangular exhibition room next to an existing straight wall. The side along the wall does not need to be built. The remaining three sides are to be constructed to two different standards: the two sides perpendicular to the wall cost $300\ \mathrm{PLN/m}$ each, while the side parallel to the wall costs $500\ \mathrm{PLN/m}$. The budget is $30\,000\ \mathrm{PLN}$.

Build a model that maximizes the area of the room and prepare a complete analysis containing:

- definition of variables and units,
- mathematical model,
- domain resulting from the problem statement,
- computation of the derivative,
- determination and verification of the optimum,
- interpretation of the result,
- graph of the objective function,
- numerical verification of several values near the optimum found.

Finally, indicate which part of the solution required modeling the problem and which part was only the execution of the calculation. Produce the graph and computer calculations only after completing the mathematical solution, and treat them as verification.

---

## 2. Theoretical Background and Concepts
1. **Constrained Optimization with Asymmetric Unit Costs**:
   When enclosing a rectangular region with unequal costs per unit length on different sides and a fixed total budget $B$:
   - We define state variables for the perpendicular dimensions ($x$ and $y$) with explicit physical units.
   - We formulate the **cost constraint equation** summing the costs of all newly constructed walls and equate it to the available budget $B$.
   - We express one variable in terms of the other to reduce the two-variable **objective function** $A(x, y) = xy$ to a single-variable function $A(x)$ on its feasible geometric and economic domain.
2. **Calculus Optimization Workflow**:
   On an open feasible interval $(a, b)$ where $A(x)$ is twice differentiable:
   - Critical points satisfy $A'(x^*) = 0$.
   - If $A'(x) > 0$ on $(a, x^*)$ and $A'(x) < 0$ on $(x^*, b)$ (or equivalently $A''(x) < 0$ for all $x \in (a, b)$), then $x^*$ is the **unique global maximum**.
3. **Separation of Mathematical Modeling vs. Algorithmic Execution**:
   - **Mathematical modeling** translates a real-world verbal description into formal mathematical structures (selecting variables, encoding geometry and pricing into constraints, establishing physical bounds, and interpreting abstract numbers back in domain terms).
   - **Calculation execution** applies standard symbolic or numerical rules to the already-formulated mathematical objects (differentiating a polynomial, solving a linear equation, evaluating a table).

---

## 3. Detailed Step-by-Step Solution

### 3.1. Definition of Variables and Units
```
      ===================================================  Existing straight wall (0 PLN/m)
              |                                 |
              |                                 |
      x [m]   |    Exhibition Room: A = x * y   |  x [m]
   (300 PLN/m)|                                 | (300 PLN/m)
              |                                 |
              +---------------------------------+
                            y [m]
                         (500 PLN/m)
```

We define the variables and their units as follows:
- **$x\text{ [m]}$**: length of each of the **two sides perpendicular** to the existing wall (unit construction cost: $300\text{ PLN/m}$ each).
- **$y\text{ [m]}$**: length of the **single side parallel** to the existing wall (unit construction cost: $500\text{ PLN/m}$).
- **$C\text{ [PLN]}$**: total construction cost of the three newly built walls, fixed at the budget $C = 30\,000\text{ PLN}$.
- **$A\text{ [m}^2\text{]}$**: floor area of the rectangular exhibition room to be maximized.

Because we want to maximize a continuous, differentiable area function $A(x)$ over a continuous interval of room dimensions, **differential calculus** is the required optimization tool.

---

### 3.2. Mathematical Model
1. **Budget Constraint**:
   - Cost of the two perpendicular walls of length $x$: $2 \times (300x) = 600x\text{ [PLN]}$.
   - Cost of the one parallel wall of length $y$: $500y\text{ [PLN]}$.
   - Cost of the fourth side along the existing wall: $0\text{ [PLN]}$.

   To maximize the enclosed area, the museum utilizes the entire budget of $30\,000\text{ PLN}$:
   $$
   600x + 500y = 30\,000.
   $$
   Dividing both sides by $100$ simplifies the constraint to:
   $$
   6x + 5y = 300 \implies 5y = 300 - 6x \implies y(x) = 60 - \frac{6}{5}x = 60 - 1.2x\text{ [m]}.
   $$

2. **Objective Function (Room Area)**:
   The area of the rectangular room is $A = x \cdot y$. Substituting $y(x) = 60 - \frac{6}{5}x$ yields the single-variable objective function:
   $$
   A(x) = x\left(60 - \frac{6}{5}x\right) = 60x - \frac{6}{5}x^2 = 60x - 1.2x^2\quad [\text{m}^2].
   $$

---

### 3.3. Domain Resulting from the Problem Statement
For a genuine rectangular exhibition room to exist and remain within budget, both side lengths $x$ and $y$ must be strictly positive:
$$
\begin{cases}
x > 0, \\[4pt]
y = 60 - \frac{6}{5}x > 0 \iff \frac{6}{5}x < 60 \iff x < 50.
\end{cases}
$$
Combining these two conditions gives the feasible domain of the objective function:
$$
D_A = (0, 50)\text{ [m]}.
$$
- As $x \to 0^+\text{ m}$, the entire budget is spent on the parallel wall ($y \to 60\text{ m}$), giving a degenerate strip of area $A(0) = 0\text{ m}^2$.
- As $x \to 50^-\text{ m}$, the entire budget is spent on the two perpendicular walls ($2 \times 50\text{ m} \times 300\text{ PLN/m} = 30\,000\text{ PLN}$, so $y \to 0\text{ m}$), again giving $A(50) = 0\text{ m}^2$.

---

### 3.4. Computation of the Derivative
Differentiating the objective function $A(x) = 60x - \frac{6}{5}x^2$ with respect to $x$ on $(0, 50)$:
$$
A'(x) = \frac{d}{dx}\left(60x - \frac{6}{5}x^2\right) = 60 - \frac{12}{5}x = 60 - 2.4x\quad [\text{m}].
$$
The second derivative is:
$$
A''(x) = \frac{d}{dx}\left(60 - \frac{12}{5}x\right) = -\frac{12}{5} = -2.4\quad [\text{dimensionless}].
$$

---

### 3.5. Determination and Verification of the Optimum
To find the critical point(s), we solve $A'(x) = 0$:
$$
60 - \frac{12}{5}x = 0 \implies \frac{12}{5}x = 60 \implies x^* = \frac{60 \times 5}{12} = 25\text{ m}.
$$
Since $x^* = 25\text{ m} \in (0, 50)$, the critical point lies strictly inside the feasible domain.

#### Verification That $x^* = 25\text{ m}$ Is the Global Maximum
1. **First Derivative Sign Analysis**:
   Since $A'(x) = \frac{12}{5}(25 - x)$:
   - For $x \in (0, 25)$, $A'(x) > 0$, so $A(x)$ is **strictly increasing** on $(0, 25]$.
   - For $x \in (25, 50)$, $A'(x) < 0$, so $A(x)$ is **strictly decreasing** on $[25, 50)$.
2. **Second Derivative Test**:
   Since $A''(x) = -\frac{12}{5} = -2.4 < 0$ for all $x \in (0, 50)$, $A(x)$ is strictly concave over the entire domain, proving that $x^* = 25\text{ m}$ is the **unique global maximum**.

#### Corresponding Optimal Length $y^*$ and Maximum Area $A_{\max}$
- Optimal parallel wall length:
  $$
  y^* = 60 - \frac{6}{5}(25) = 60 - 30 = 30\text{ m}.
  $$
- Maximum exhibition room area:
  $$
  A_{\max} = A(25) = 25\text{ m} \times 30\text{ m} = 750\text{ m}^2.
  $$

---

### 3.6. Interpretation of the Result
To obtain the largest possible exhibition room within the $30\,000\text{ PLN}$ budget:
- The museum should build the **two walls perpendicular** to the existing wall to a length of **$x^* = 25\text{ m}$ each** (costing $2 \times 25\text{ m} \times 300\text{ PLN/m} = 15\,000\text{ PLN}$).
- The museum should build the **wall parallel** to the existing wall to a length of **$y^* = 30\text{ m}$** (costing $30\text{ m} \times 500\text{ PLN/m} = 15\,000\text{ PLN}$).
- This yields a **maximum floor area of $750\text{ m}^2$**.
- **Economic Insight (Equal Budget Split)**: Notice that at the optimum, the $30\,000\text{ PLN}$ budget is split **equally ($15\,000\text{ PLN}$ and $15\,000\text{ PLN}$)** between the perpendicular direction ($600x^* = 15\,000\text{ PLN}$) and the parallel direction ($500y^* = 15\,000\text{ PLN}$). Because the two perpendicular walls combined cost $600\text{ PLN}$ per meter of $x$ while the single parallel wall costs $500\text{ PLN}$ per meter of $y$, the optimal room is slightly wider along the wall ($30\text{ m}$) than it is deep ($25\text{ m}$), in the inverse cost ratio $\frac{y^*}{x^*} = \frac{600}{500} = \frac{6}{5}$.

---

## 4. Verification and Consistency Checks (Graph, Numerical Table, and Modeling vs. Calculation Analysis)

*(In accordance with the problem instructions, the following graph and numerical table are produced after completing the analytical solution above, serving as independent verification.)*

### 4.1. Graph of the Objective Function $A(x) = 60x - 1.2x^2$ on $[0, 50]$
The graph is a downward-opening parabola with roots at $(0, 0)$ and $(50, 0)$, axis of symmetry $x = 25\text{ m}$, and vertex (maximum) at $(25, 750)$:

```
  Area A(x) [m^2]
   750 +                         * (25, 750)  <-- Global Maximum: x* = 25 m, A_max = 750 m^2
       |                    .    |    .
   675 +                 *       |       *
       |               .         |         .
   600 +             .           |           .
       |           .             |             .
   480 +         *               |               *
       |       .                 |                 .
   360 +     .                   |                   .
       |    .                    |                    .
   180 +  .                      |                      .
       | .                       |                       .
     0 *----+----+----+----+-----+-----+----+----+----+---*---> x [m]
       0    5   10   15   20    25    30   35   40   45   50
```

---

### 4.2. Numerical Verification Table Near the Optimum $x^* = 25\text{ m}$
We evaluate $y(x) = 60 - 1.2x$, the total construction cost $600x + 500y$, the room area $A(x) = xy = 60x - 1.2x^2$, and the deviation from $A_{\max}$ for several values of $x$ around $x^* = 25\text{ m}$:

| Perpendicular Side $x\text{ [m]}$ | Parallel Side $y = 60 - 1.2x\text{ [m]}$ | Total Cost $600x + 500y\text{ [PLN]}$ | Area $A(x) = xy\text{ [m}^2\text{]}$ | Derivative $A'(x) = 60 - 2.4x$ | Difference $A(x) - 750\text{ [m}^2\text{]}$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| $20.0$ | $36.0$ | $30\,000$ | $720.00$ | $+12.00$ | $-30.00$ |
| $23.0$ | $32.4$ | $30\,000$ | $745.20$ | $+4.80$ | $-4.80$ |
| $24.0$ | $31.2$ | $30\,000$ | $748.80$ | $+2.40$ | $-1.20$ |
| $24.5$ | $30.6$ | $30\,000$ | $749.70$ | $+1.20$ | $-0.30$ |
| **$25.0$** | **$30.0$** | **$30\,000$** | **$750.00$ (Max)** | **$0.00$** | **$0.00$** |
| $25.5$ | $29.4$ | $30\,000$ | $749.70$ | $-1.20$ | $-0.30$ |
| $26.0$ | $28.8$ | $30\,000$ | $748.80$ | $-2.40$ | $-1.20$ |
| $27.0$ | $27.6$ | $30\,000$ | $745.20$ | $-4.80$ | $-4.80$ |
| $30.0$ | $24.0$ | $30\,000$ | $720.00$ | $-12.00$ | $-30.00$ |

The numerical table confirms that every feasible configuration satisfies the $30\,000\text{ PLN}$ budget constraint, that $A(x)$ is symmetric about $x^* = 25\text{ m}$ since $A(25 \pm \delta) = 750 - 1.2\delta^2$, and that $A(25) = 750\text{ m}^2$ is the strict maximum.

---

### 4.3. Distinction Between Mathematical Modeling and Routine Calculation Execution

| Phase of the Solution | Classification | Explanation of Why |
| :--- | :--- | :--- |
| **1. Choosing variables $x, y$ and assigning units ($\text{m}$, $\text{PLN}$)** | **Mathematical Modeling** | Requires abstracting the physical geometry of the exhibition room and identifying which quantities control the design. |
| **2. Formulating the budget constraint $2(300x) + 500y = 30\,000$ and area $A = xy$** | **Mathematical Modeling** | Requires translating the verbal rules ("side along the wall does not need to be built", two perpendicular sides at $300\text{ PLN/m}$, one parallel side at $500\text{ PLN/m}$) into algebraic equations. |
| **3. Determining the feasible domain $D_A = (0, 50)\text{ m}$** | **Mathematical Modeling** | Requires imposing real-world physical non-negativity constraints ($x > 0$ and $y > 0$) that are not inherent to the polynomial $60x - 1.2x^2$ itself (which is defined for all $x \in \mathbb{R}$). |
| **4. Substituting $y = 60 - \frac{6}{5}x$, differentiating $A'(x) = 60 - \frac{12}{5}x$, solving $A'(x) = 0$, and checking $A''(x) = -\frac{12}{5} < 0$** | **Execution of Calculation** | Purely algorithmic symbolic manipulation of a quadratic polynomial using standard differentiation and linear equation rules; could be performed automatically by a CAS without knowing the museum context. |
| **5. Interpreting $(x^*, y^*) = (25\text{ m}, 30\text{ m})$ and $A_{\max} = 750\text{ m}^2$ in the museum context and verifying via table/graph** | **Mathematical Modeling & Verification** | Requires translating the abstract numbers $(25, 30, 750)$ back into actionable architectural dimensions and checking physical/economic consistency. |
