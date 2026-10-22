# Solution to Problem 2: Maximum Area of a Rectangle

## 1. Problem Statement
A rectangle has perimeter $40$.

1. Write its area as a function of the length of one side.
2. Determine the domain of this function resulting from the geometry of the problem.
3. Find the dimensions that give the maximum area.
4. Justify that the point found actually gives a maximum.

---

## 2. Theoretical Background and Concepts
A constrained geometric optimization problem consists of:
1. **State Variables**: The geometric dimensions of the figure (here, the side lengths $x$ and $y$ of a rectangle).
2. **Constraint Equation**: A fixed condition linking the variables (here, the constant perimeter $P = 2x + 2y = 40$), which allows us to express one variable in terms of the other and reduce the problem to a single variable.
3. **Objective Function and Geometric Domain**: The quantity to be maximized or minimized (here, the area $A(x)$), restricted to the set of values of $x$ for which all geometric dimensions are strictly positive.
4. **Extrema via Differential Calculus**:
   - **Fermat's Theorem (Critical Points)**: If a differentiable function $A(x)$ attains a local extremum at an interior point $x^*$ of its domain, then $A'(x^*) = 0$.
   - **First Derivative Test**: If $A'(x) > 0$ for $x < x^*$ and $A'(x) < 0$ for $x > x^*$ across the entire domain, then $A(x)$ increases up to $x^*$ and decreases thereafter, proving that $x^*$ is the **unique global maximum**.
   - **Second Derivative Test**: If $A'(x^*) = 0$ and $A''(x^*) < 0$, then $x^*$ is a strict local maximum; if $A''(x) < 0$ on the entire interval (strict concavity), any critical point is the unique global maximum.

---

## 3. Detailed Step-by-Step Solution

### Choosing Variables and Building the Model
Let:
- $x$ denote the length of one side of the rectangle (in length units, e.g., $\text{units}$).
- $y$ denote the length of the adjacent side of the rectangle (in length units).
- $A$ denote the area of the rectangle (in square length units, $\text{units}^2$).

Since we seek the maximum of a continuous, differentiable area function over an open interval of feasible side lengths, **differential calculus** (finding critical points via the derivative) is the appropriate tool.

---

### Part 1: Area as a Function of One Side Length
The perimeter of a rectangle with side lengths $x$ and $y$ is $P = 2x + 2y$. Using the given perimeter constraint $P = 40$:
$$
2x + 2y = 40 \implies x + y = 20 \implies y = 20 - x.
$$
The area of the rectangle is $A = x \cdot y$. Substituting $y = 20 - x$ yields the area as a single-variable function of $x$:
$$
A(x) = x(20 - x) = 20x - x^2.
$$

---

### Part 2: Geometric Domain of the Function
For a non-degenerate rectangle to exist geometrically, both side lengths must be strictly positive:
$$
\begin{cases}
x > 0, \\
y = 20 - x > 0 \iff x < 20.
\end{cases}
$$
Combining these two inequalities gives the **geometric domain**:
$$
D_A = (0, 20).
$$
*(Note: At the boundary values $x = 0$ and $x = 20$, the rectangle degenerates into a line segment of zero width and area $A(0) = A(20) = 0$.)*

---

### Part 3: Dimensions Giving the Maximum Area
We differentiate the objective function $A(x) = 20x - x^2$ on the open interval $(0, 20)$:
$$
A'(x) = \frac{d}{dx}\left(20x - x^2\right) = 20 - 2x.
$$
To find the critical point(s), we set $A'(x) = 0$:
$$
20 - 2x = 0 \implies 2x = 20 \implies x^* = 10.
$$
Since $x^* = 10 \in (0, 20)$, this critical point lies strictly inside the geometric domain.

The corresponding second dimension $y^*$ is:
$$
y^* = 20 - x^* = 20 - 10 = 10.
$$
The resulting maximum area is:
$$
A_{\max} = A(10) = 10 \times (20 - 10) = 10 \times 10 = 100\text{ [square units]}.
$$
**Interpretation**: Among all rectangles of perimeter $40$, the one with the largest area is a **square** of dimensions **$10 \times 10$**, with area **$100$** square units.

---

### Part 4: Rigorous Justification of the Maximum
We provide three independent, mutually reinforcing justifications that $x^* = 10$ gives the global maximum of $A(x)$ on $(0, 20)$:

1. **First Derivative Test (Sign Change of $A'(x)$ on the Entire Domain)**:
   Since $A'(x) = 20 - 2x = 2(10 - x)$:
   - For $x \in (0, 10)$, we have $10 - x > 0 \implies A'(x) > 0$, so $A(x)$ is **strictly increasing** on $(0, 10]$.
   - For $x \in (10, 20)$, we have $10 - x < 0 \implies A'(x) < 0$, so $A(x)$ is **strictly decreasing** on $[10, 20)$.

   Because $A(x)$ increases up to $x = 10$ and decreases for all $x > 10$, $x^* = 10$ is the **unique global maximum** on $(0, 20)$.

2. **Second Derivative Test (Strict Concavity)**:
   Computing the second derivative gives:
   $$
   A''(x) = \frac{d}{dx}(20 - 2x) = -2 < 0 \quad \text{for all } x \in (0, 20).
   $$
   Since $A'(10) = 0$ and $A''(10) = -2 < 0$ (and in fact $A$ is strictly concave over the entire domain), $x^* = 10$ is a strict global maximum.

3. **Algebraic Verification (Completing the Square / AM-GM Inequality)**:
   Completing the square for $A(x) = 20x - x^2$ gives:
   $$
   A(x) = -(x^2 - 20x + 100) + 100 = 100 - (x - 10)^2.
   $$
   Since $(x - 10)^2 \ge 0$ for all real $x$, with equality if and only if $x = 10$, we have $A(x) \le 100$ for all $x \in (0, 20)$, and $A(x) = 100$ uniquely at $x = 10$.

---

## 4. Verification and Consistency Checks

1. **Boundary Behavior Check**:
   As $x \to 0^+$ or $x \to 20^-$, the area approaches zero:
   $$
   \lim_{x \to 0^+} A(x) = 0, \qquad \lim_{x \to 20^-} A(x) = 0,
   $$
   while at the midpoint $x = 10$, $A(10) = 100 > 0$.

2. **Numerical Comparison with Neighboring Rectangles of Perimeter $40$**:
   | Side $x$ | Side $y = 20 - x$ | Perimeter $2x + 2y$ | Area $A(x) = xy$ | Derivative $A'(x) = 20 - 2x$ |
   | :---: | :---: | :---: | :---: | :---: |
   | $5$ | $15$ | $40$ | $75$ | $+10 > 0$ |
   | $9$ | $11$ | $40$ | $99$ | $+2 > 0$ |
   | **$10$** | **$10$** | **$40$** | **$100$ (Max)** | **$0$** |
   | $11$ | $9$ | $40$ | $99$ | $-2 < 0$ |
   | $15$ | $5$ | $40$ | $75$ | $-10 < 0$ |

   Every perturbation $x = 10 \pm \delta$ ($\delta \ne 0$) yields $A(10 \pm \delta) = (10 + \delta)(10 - \delta) = 100 - \delta^2 < 100$, confirming that $10 \times 10$ is the unique global maximizer.
