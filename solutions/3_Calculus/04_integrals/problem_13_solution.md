# Solution to Problem 13: An Integral Depending on the Upper Limit

## 1. Problem Statement

Let
$$F(x)=\int_0^x(t^2+1)\,dt.$$
Determine $F(x)$, compute $F'(x)$, and compare the result with the integrand. Explain in your own words why the height of the function describes the local rate of increase of the accumulated area.

> **Why this problem:** it connects differentiation and integration through the idea of accumulation.

---

## 2. Theoretical Background and Concepts

### The Area Accumulation Function and the Fundamental Theorem of Calculus (Part 1)
Let $f: I \to \mathbb{R}$ be a continuous function on an interval $I$ containing $a$. The **accumulation function** defined by integrating $f(t)$ from a fixed lower limit $t = a$ to a variable upper limit $t = x \in I$ is:
$$F(x) = \int_a^x f(t)\,dt.$$
*(Note: A dummy variable of integration $t$ is used inside the integral so as not to conflict with the upper limit $x$, which is the independent variable of $F$.)*

**Fundamental Theorem of Calculus, Part 1 (FTC I):** If $f$ is continuous on $I$, then the accumulation function $F(x) = \int_a^x f(t)\,dt$ is differentiable at every $x \in I$, and its derivative is obtained simply by evaluating the integrand $f(t)$ at the upper limit $t = x$:
$$F'(x) = \frac{d}{dx}\int_a^x f(t)\,dt = f(x).$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determining the Explicit Formula for $F(x)$
The integrand inside $F(x) = \int_0^x (t^2 + 1)\,dt$ is the polynomial $f(t) = t^2 + 1$ with respect to the integration variable $t$.
First, we find an antiderivative $G(t)$ of $f(t) = t^2 + 1$ with respect to $t$ using the power rule:
$$G(t) = \int (t^2 + 1)\,dt = \frac{t^3}{3} + t.$$
*(Verification with respect to $t$: $G'(t) = \frac{d}{dt}\left(\frac{t^3}{3} + t\right) = t^2 + 1$.)*

Now, evaluating the definite integral from the lower limit $t = 0$ to the upper limit $t = x$:
$$\begin{aligned}
F(x) &= \int_0^x (t^2 + 1)\,dt \\
&= \left[\frac{t^3}{3} + t\right]_{t=0}^{t=x} \\
&= \left(\frac{x^3}{3} + x\right) - \left(\frac{0^3}{3} + 0\right) \\
&= \frac{x^3}{3} + x.
\end{aligned}$$

### Step 2: Computing $F'(x)$ and Comparing with the Integrand
Differentiating the explicit expression $F(x) = \frac{x^3}{3} + x$ with respect to $x$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{x^3}{3} + x\right) \\
&= \frac{3x^2}{3} + 1 \\
&= x^2 + 1.
\end{aligned}$$
**Comparison with the integrand:**
The derivative $F'(x) = x^2 + 1$ is **identically equal to the integrand $f(t) = t^2 + 1$ evaluated at the upper limit $t = x$**:
$$F'(x) = f(x) = x^2 + 1.$$
This provides a direct concrete verification of the First Fundamental Theorem of Calculus: differentiating the accumulation integral $\int_0^x f(t)\,dt$ with respect to its upper limit $x$ undoes the integration and returns the integrand $f(x)$.

### Step 3: Intuitive Geometric Explanation — Why the Height $f(x)$ Equals the Local Rate of Area Accumulation $F'(x)$
For $x \ge 0$, since $f(t) = t^2 + 1 > 0$, $F(x) = \int_0^x (t^2+1)\,dt$ represents the **accumulated geometric area** under the curve $y = t^2 + 1$ from $t = 0$ to $t = x$.

Suppose we move the right boundary slightly from $x$ to $x + \Delta x$ (where $\Delta x > 0$ is very small):
1. **Change in accumulated area ($\Delta F$):**
   The additional area swept out by moving the vertical boundary from $x$ to $x + \Delta x$ is the narrow vertical strip:
   $$\Delta F = F(x + \Delta x) - F(x) = \int_x^{x+\Delta x} (t^2 + 1)\,dt.$$
2. **Approximating the narrow strip by a rectangle:**
   Over the tiny interval $[x, x + \Delta x]$ of width $\Delta x$, the continuous curve $y = f(t) = t^2 + 1$ barely changes its height; its height throughout this narrow strip is essentially $f(x) = x^2 + 1$. Therefore, the area $\Delta F$ of the thin vertical strip is approximately the area of a rectangle of **height $f(x)$** and **width $\Delta x$**:
   $$\Delta F \approx \underbrace{f(x)}_{\text{height}} \times \underbrace{\Delta x}_{\text{width}} = (x^2 + 1)\,\Delta x.$$
3. **Dividing by $\Delta x$ and taking the limit $\Delta x \to 0$:**
   Dividing both sides by the width $\Delta x$ gives the average rate of increase of area per unit shift in $x$:
   $$\frac{\Delta F}{\Delta x} = \frac{F(x + \Delta x) - F(x)}{\Delta x} \approx f(x) = x^2 + 1.$$
   As the strip becomes infinitesimally thin ($\Delta x \to 0$), the approximation becomes exact because $\min_{[x, x+\Delta x]} f(t)$ and $\max_{[x, x+\Delta x]} f(t)$ both converge to $f(x)$:
   $$F'(x) = \lim_{\Delta x \to 0} \frac{\Delta F}{\Delta x} = f(x) = x^2 + 1.$$
In plain words: **how fast a region gains area when its right-hand wall moves to the right is proportional to the height of the wall at that instant.** Where the curve is tall ($f(x)$ is large), a tiny horizontal step $\Delta x$ sweeps out a tall strip with a large area; where the curve is low ($f(x)$ is small), the same step $\Delta x$ sweeps out a short strip with a small area.

---

## 4. Verification and Consistency Checks

1. **Initial Value Check at $x = 0$:** At $x = 0$, the integral $\int_0^0 (t^2+1)\,dt = 0$ has zero width, and our formula gives $F(0) = \frac{0^3}{3} + 0 = 0$.
2. **Consistency with Problem 10 at $x = 2$:** Evaluating $F(x) = \frac{x^3}{3} + x$ at $x = 2$ gives $F(2) = \frac{8}{3} + 2 = \frac{14}{3}$, which matches the definite integral $\int_0^2 (x^2+1)\,dx = \frac{14}{3}$ computed in Problem 10.
