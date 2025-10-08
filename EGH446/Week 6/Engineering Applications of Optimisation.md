 #Engineering #Design #SystemID

Any design problem that has a set of choices and a mathematical measure of "goodness" (a cost function) can be framed as an optimisation problem. Optimisation is widely used for:

* **Parameter Estimation / System Identification**
* **System Design**
* **Decision Making & Process Optimisation**

## 1. Parameter Estimation (System Identification)

In this problem, the goal is to find a model that most closely matches collected data. The "design choices" are the model's parameters ($\theta$), and the "cost" is the error between the model's output and the real data.

* **Cost Function**: A common choice is the **Sum of Squared Error (SSE)**. Let $y_k^d$ be the measured data at time $k$ and $y_k^\theta$ be the model's prediction. The error is $e_k = y_k^\theta - y_k^d$. The cost function is:
    $$
    J(\theta) = \sum_{k} (e_k)^2 = \sum_{k} (y_k^\theta - y_k^d)^2
    $$
    Minimising this cost function makes the model's response as close as possible to the data. This is known as the **least squares** method.

* **Example**: We have step response data from a servo motor and a model $y^{m}(\alpha,k_{m},k+1)=\alpha y^{m}(\alpha,k_{m},k)+k_{m}u(t)$. We can use optimisation to find the parameters $\alpha$ and $k_m$ that best fit the data by minimising $J(\alpha,k_{m})=\sum_{k}(y^{m}(\alpha,k_{m},k)-y^{d}(k))^{2}$.

## 2. System Design

If we can write a mathematical expression that connects design choices to a performance metric, we can solve the design task as an optimisation problem.

* **Example**: Design a rectangular paddock with the maximum possible area for a fixed length of fencing, $T$.
    * **Design Choices**: Length $L$ and Width $W$.
    * **Constraint**: $2L + 2W = T$.
    * **Cost Function (to maximise)**: $J = \text{Area} = L \cdot W$.
    * By substituting the constraint, we can write this as a function of $L$ only: $J(L) = L(T-2L)/2$.
    * **Solution**: Taking the derivative and setting it to zero ($\frac{dJ}{dL} = T/2 - 2L = 0$) shows the optimal design is a **square** where $L = W = T/4$.

## 3. Operational or Process Optimisation

This involves making automated choices from a discrete set of options to optimise a process. These problems often have complex constraints and non-continuous cost functions, which means calculus-based methods can't be used.

* **Example**: The **lift ride allocation problem**.
    * **Goal**: Assign lifts to passengers to minimise the average wait time.
    * **Design Choice**: The set of rules, or policy, used to assign a lift.
    * **Challenge**: It's very difficult to write a simple cost function because of the problem's complexity (e.g., random passenger arrivals).
    * **Outcome**: While an explicit optimal solution is hard to find, the *principles* of optimisation can guide a human designer to create a good heuristic or rule-based system that performs well.