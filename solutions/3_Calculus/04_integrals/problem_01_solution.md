# Solution to Problem 1: Antiderivative and Verification

## 1. Problem Statement

For
$$f(x)=3x^2-4x+5$$
find one antiderivative $F(x)$. Write the entire family of antiderivatives, verify the result by differentiation, and explain the meaning of the constant $C$.

> **Why this problem:** it introduces integration as the inverse operation to differentiation.

---

## 2. Theoretical Background and Concepts

### Definition of an Antiderivative
Let $f: I \to \mathbb{R}$ be a function defined on an open interval $I \subseteq \mathbb{R}$. A differentiable function $F: I \to \mathbb{R}$ is called an **antiderivative** (or **primitive function**) of $f$ on $I$ if:
$$F'(x) = f(x) \quad \text{for all } x \in I.$$

### The Indefinite Integral and the Constant of Integration
By the Mean Value Theorem, if $F_1$ and $F_2$ are any two antiderivatives of the same function $f$ on a connected interval $I$, then their difference $G(x) = F_1(x) - F_2(x)$ satisfies:
$$G'(x) = F_1'(x) - F_2'(x) = f(x) - f(x) = 0 \quad \text{for all } x \in I.$$
A function whose derivative is identically zero on an interval is constant on that interval. Therefore, there exists a real constant $C \in \mathbb{R}$ such that $F_1(x) = F_2(x) + C$. The set of all antiderivatives of $f$ is called the **indefinite integral** of $f$ and is denoted by:
$$\int f(x)\,dx = F_0(x) + C, \quad C \in \mathbb{R},$$
where $F_0(x)$ is any particular antiderivative of $f(x)$.

### Power Rule and Linearity for Antiderivatives
For any real exponent $n \neq -1$, since $\frac{d}{dx}\left(\frac{x^{n+1}}{n+1}\right) = x^n$, the reversed power rule states:
$$\int x^n\,dx = \frac{x^{n+1}}{n+1} + C.$$
Together with linearity, $\int [\alpha f(x) + \beta g(x)]\,dx = \alpha \int f(x)\,dx + \beta \int g(x)\,dx$, any polynomial can be integrated term by term on $\mathbb{R}$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Recognizing the Integration Method
The given function $f(x) = 3x^2 - 4x + 5$ is a polynomial of degree $2$ defined on the entire real line $I = (-\infty, \infty)$. Because differentiation of polynomials is a linear operation that reduces the degree of each power by $1$, finding an antiderivative requires **direct term-by-term integration** using the reversed power rule $\int x^n\,dx = \frac{x^{n+1}}{n+1}$ for $n = 2, 1, 0$.

### Step 2: Finding One Specific Antiderivative $F_0(x)$
We look for a specific function $F_0(x)$ whose derivative produces each term of $f(x) = 3x^2 - 4x + 5$:
1. **Quadratic term ($3x^2$):** Applying the power rule for $n = 2$:
   $$\text{An antiderivative of } 3x^2 \text{ is } 3 \cdot \frac{x^{2+1}}{2+1} = 3 \cdot \frac{x^3}{3} = x^3.$$
2. **Linear term ($-4x$):** Applying the power rule for $n = 1$:
   $$\text{An antiderivative of } -4x \text{ is } -4 \cdot \frac{x^{1+1}}{1+1} = -4 \cdot \frac{x^2}{2} = -2x^2.$$
3. **Constant term ($5 = 5x^0$):** Applying the power rule for $n = 0$:
   $$\text{An antiderivative of } 5 \text{ is } 5 \cdot \frac{x^{0+1}}{0+1} = 5x.$$

Combining these terms (corresponding to choosing the integration constant $C = 0$), one specific antiderivative is:
$$F_0(x) = x^3 - 2x^2 + 5x.$$

### Step 3: Writing the Full Family of Antiderivatives
Adding an arbitrary real constant $C \in \mathbb{R}$ to the particular antiderivative $F_0(x)$ gives the complete family of antiderivatives (the indefinite integral) on $\mathbb{R}$:
$$F(x) = \int (3x^2 - 4x + 5)\,dx = x^3 - 2x^2 + 5x + C, \quad C \in \mathbb{R}.$$

### Step 4: Verification by Differentiation
To confirm that $F(x) = x^3 - 2x^2 + 5x + C$ is the valid family of antiderivatives, we differentiate $F(x)$ with respect to $x$ using the sum, constant multiple, and power rules of differentiation:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(x^3 - 2x^2 + 5x + C\right) \\
&= \frac{d}{dx}(x^3) - 2\frac{d}{dx}(x^2) + 5\frac{d}{dx}(x) + \frac{d}{dx}(C) \\
&= 3x^{3-1} - 2(2x^{2-1}) + 5(1) + 0 \\
&= 3x^2 - 4x + 5 \\
&= f(x).
\end{aligned}$$
Since $F'(x) = f(x)$ for every $x \in \mathbb{R}$ and every $C \in \mathbb{R}$, the antiderivative family is verified.

### Step 5: Explaining the Analytical and Geometric Meaning of the Constant $C$
1. **Analytical Meaning:**
   - **Forward direction (differentiation loses constant information):** The derivative measures the instantaneous rate of change of a function. Because a constant term $C$ does not change as $x$ varies, $\frac{d}{dx}(C) = 0$. Consequently, infinitely many functions—such as $x^3-2x^2+5x$, $x^3-2x^2+5x+7$, and $x^3-2x^2+5x-\pi$—all share the exact same derivative $f(x) = 3x^2-4x+5$.
   - **Completeness on an interval:** If $F_1(x)$ and $F_2(x)$ are any two antiderivatives of $f(x)$ on the connected interval $\mathbb{R}$, then $(F_1 - F_2)'(x) = F_1'(x) - F_2'(x) = f(x) - f(x) = 0$ for all $x \in \mathbb{R}$. By the zero-derivative corollary of the Mean Value Theorem, $F_1(x) - F_2(x) = C$ for some constant $C \in \mathbb{R}$. Thus, the single parameter $C$ captures **all** possible antiderivatives on $\mathbb{R}$, and fixing a single point value (an initial condition $F(x_0) = y_0$) uniquely selects one member of the family (for example, $C = F(0)$ represents the $y$-intercept of the antiderivative).

2. **Geometric Meaning:**
   - Graphically, adding $C \in \mathbb{R}$ to $F_0(x)$ performs a **vertical translation** (shift upward if $C > 0$, downward if $C < 0$) of the curve $y = F_0(x)$.
   - Shifting a curve vertically does not change its steepness at any horizontal coordinate: at any fixed $x = x_0$, the tangent lines to all curves in the family $y = x^3 - 2x^2 + 5x + C$ are **parallel** to one another, each having the exact same slope $m = f(x_0) = 3x_0^2 - 4x_0 + 5$.

---

## 4. Verification and Consistency Checks

1. **Pointwise Slope Check:**
   - At $x = 0$: $f(0) = 5$, and $F'(0) = 3(0)^2 - 4(0) + 5 = 5$. Moreover, $F(0) = C$, confirming that $C$ is the vertical intercept of each curve in the family.
   - At $x = 1$: $f(1) = 3(1) - 4(1) + 5 = 4$, and $F'(1) = 3(1)^2 - 4(1) + 5 = 4$.
2. **Degree and Leading Coefficient Check:** Integrating a polynomial of degree $2$ must yield a polynomial of degree $2 + 1 = 3$ with leading coefficient $\frac{3}{3} = 1$, which matches $x^3 - 2x^2 + 5x + C$.
