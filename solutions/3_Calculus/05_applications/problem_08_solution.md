# Solution to Problem 8: Number of Requests Handled by a Server

## 1. Problem Statement
The rate at which requests arrive at a server during the first 5 minutes is described by the function
$$
r(t)=100+20t\quad [\text{requests/min}],\qquad 0\le t\le5.
$$

1. Compute the total number of requests that arrived during this time.
2. Compute the average rate of incoming requests over this interval.
3. Compare the average rate with the values $r(0)$ and $r(5)$.

---

## 2. Theoretical Background and Concepts
1. **Integrating a Rate of Arrival (Accumulation)**:
   If $N(t)$ denotes the cumulative number of requests that have arrived at a server up to time $t$, then the instantaneous arrival rate is the derivative $r(t) = N'(t) = \frac{dN}{dt}$ (in requests per minute). By the Fundamental Theorem of Calculus (Net Change Theorem), integrating the arrival rate $r(t)$ over a time interval $[t_1, t_2]$ gives the total number of requests arriving during that interval:
   $$
   N_{\text{total}} = N(t_2) - N(t_1) = \int_{t_1}^{t_2} r(t)\,dt.
   $$
2. **Average Value of a Rate Function**:
   The average arrival rate $r_{\text{avg}}$ over $[t_1, t_2]$ is the total number of requests divided by the duration of the time interval:
   $$
   r_{\text{avg}} = \frac{1}{t_2 - t_1}\int_{t_1}^{t_2} r(t)\,dt = \frac{N_{\text{total}}}{t_2 - t_1}.
   $$
3. **Average of a Linear Function**:
   For any linear function $r(t) = \alpha + \beta t$ on $[a, b]$, the graph is a straight line segment, so its integral average over $[a, b]$ equals the arithmetic mean of its endpoint values, $\frac{r(a) + r(b)}{2}$, and is attained at the midpoint $t_{\text{mid}} = \frac{a+b}{2}$.

---

## 3. Detailed Step-by-Step Solution

### Variable Definitions and Domain
- $t \in [0, 5]\text{ [min]}$: time elapsed during the 5-minute observation window.
- $r(t) = 100 + 20t\text{ [requests/min]}$: instantaneous rate of incoming server requests at time $t$.
- $N_{\text{total}}\text{ [requests]}$: total number of requests arriving over $t \in [0, 5]\text{ min}$.
- $r_{\text{avg}}\text{ [requests/min]}$: average request arrival rate over $t \in [0, 5]\text{ min}$.

Because the arrival rate $r(t)$ varies continuously with time $t$, we use the **definite integral** to sum the infinitesimal request counts $r(t)\,dt$ over $[0, 5]$.

---

### Part 1: Total Number of Requests Arriving in $[0, 5]$ Minutes
Integrating the arrival rate function $r(t) = 100 + 20t$ from $t = 0$ to $t = 5$:
$$
N_{\text{total}} = \int_0^5 r(t)\,dt = \int_0^5 (100 + 20t)\,dt.
$$
An antiderivative of $100 + 20t$ is $100t + 10t^2$. Applying the Fundamental Theorem of Calculus:
$$
\begin{aligned}
N_{\text{total}} &= \left[100t + 10t^2\right]_0^5 \\
&= \left(100(5) + 10(5)^2\right) - \left(100(0) + 10(0)^2\right) \\
&= (500 + 250) - 0 = 750\text{ requests}.
\end{aligned}
$$
**Interpretation**: A total of **$750\text{ requests}$** arrived at the server during the first $5$ minutes (consisting of $500$ baseline requests at $100\text{ req/min}$ plus $250$ additional requests due to the linear traffic ramp-up of $20t\text{ req/min}$).

---

### Part 2: Average Rate of Incoming Requests Over $[0, 5]$
Applying the average value formula over the interval $[0, 5]$ of length $5 - 0 = 5\text{ min}$:
$$
r_{\text{avg}} = \frac{1}{5 - 0}\int_0^5 r(t)\,dt = \frac{N_{\text{total}}}{5} = \frac{750\text{ requests}}{5\text{ min}} = 150\text{ requests/min}.
$$
**Interpretation**: A server receiving requests at a constant rate of **$150\text{ requests/min}$** for $5$ minutes would handle the exact same total workload ($150 \times 5 = 750\text{ requests}$) as the server experiencing the linearly increasing load $r(t) = 100 + 20t$.

---

### Part 3: Comparison of $r_{\text{avg}}$ with $r(0)$ and $r(5)$
Evaluating the arrival rate at the endpoints $t = 0$ and $t = 5$:
- Initial rate at $t = 0$:
  $$
  r(0) = 100 + 20(0) = 100\text{ requests/min}.
  $$
- Final rate at $t = 5$:
  $$
  r(5) = 100 + 20(5) = 100 + 100 = 200\text{ requests/min}.
  $$

Comparing $r_{\text{avg}} = 150\text{ requests/min}$ with $r(0) = 100\text{ requests/min}$ and $r(5) = 200\text{ requests/min}$, we observe that:
1. $r_{\text{avg}}$ lies strictly halfway between the initial and final rates:
   $$
   r(0) = 100 < r_{\text{avg}} = 150 < r(5) = 200.
   $$
2. Specifically, $r_{\text{avg}}$ is equal to the **arithmetic mean** of the endpoint values $r(0)$ and $r(5)$, and equals the instantaneous rate at the **midpoint** $t = 2.5\text{ min}$:
   $$
   r_{\text{avg}} = \frac{r(0) + r(5)}{2} = \frac{100 + 200}{2} = 150\text{ requests/min} = r(2.5).
   $$
3. **Why this holds**: Because $r(t) = 100 + 20t$ is a **linear function** (its rate of growth $r'(t) = 20\text{ req/min}^2$ is constant), the deficit below $150\text{ req/min}$ during the first half of the interval $[0, 2.5]$ is symmetric to and exactly balanced by the excess above $150\text{ req/min}$ during the second half $[2.5, 5]$.

---

## 4. Verification and Consistency Checks

1. **Geometric Trapezoid Area Check**:
   The graph of $r(t) = 100 + 20t$ on $[0, 5]$ forms a right trapezoid of width $\Delta t = 5\text{ min}$ and parallel vertical bases $b_1 = r(0) = 100$ and $b_2 = r(5) = 200$. The area of this trapezoid is:
   $$
   \text{Area} = \frac{b_1 + b_2}{2} \times \Delta t = \frac{100 + 200}{2} \times 5 = 150 \times 5 = 750\text{ requests},
   $$
   which matches the definite integral in Part 1 and the average rate formula in Parts 2–3.

2. **Dimensional (Unit) Analysis**:
   - For $N_{\text{total}}$: $[r(t)] \cdot [dt] = \left[\frac{\text{requests}}{\text{min}}\right] \cdot [\text{min}] = \text{requests}$.
   - For $r_{\text{avg}}$: $\frac{[N_{\text{total}}]}{[\Delta t]} = \frac{\text{requests}}{\text{min}}$.
   Both results have the exact physical units required by the problem context.
