#Optimisation #Algorithms #NumericalMethods

There are three main approaches to finding the optimal solution for unconstrained optimisation problems.

## 1. Brute Force Search

This is the simplest method. The idea is to compute the function's value at a large number of locations within a specified range and then select the location that gives the best (e.g., smallest) value.

* **How it works**:
    1.  Define a grid of candidate values for $x$.
    2.  Calculate the cost function $J(x)$ for every point on the grid.
    3.  The optimal $x$ is the one that results in the minimum $J(x)$.
* **Limitations**:
    * You need to know a reasonable range to search over.
    * The solution's accuracy depends on how fine your grid is.
    * It can be computationally very expensive, especially in higher dimensions.

## 2. Gradient-Based Search (Smart Search)

Instead of searching everywhere, this method starts with an initial guess and iteratively improves it by moving in a "smart" direction—specifically, the direction suggested by the negative gradient. Think of it like a ball rolling downhill to find the bottom of a valley.

* **Algorithm**: Start with an initial guess $\hat{x}_{0}$ and update it using the rule:
    $$
    \hat{x}_{k+1} = \hat{x}_{k} - \gamma \frac{dJ}{dx}(\hat{x}_{k})
    $$
    where $\gamma$ is a positive **step size** that controls how far you move at each iteration.
* **Limitations**:
    * **Can get stuck**: It can converge to a *local* minimum, which might not be the *global* minimum.
    * **Sensitive to initialisation**: The starting point ($\hat{x}_{0}$) can determine which local minimum the search finds.
* **MATLAB Tool**: `fminunc` is a common function used for this type of numerical optimisation.

## 3. Calculus-Based Approach

For functions that are simple enough to differentiate, this is often the easiest and most precise method. It uses the principle that an optimum must occur at a stationary point where $\frac{dJ}{dx}=0$.

* **How it works**:
    1.  Analytically find the first and second derivatives: $\frac{dJ}{dx}$ and $\frac{d^{2}J}{dx^{2}}$.
    2.  Find all stationary points by solving the equation $\frac{dJ}{dx} = 0$ for $x$.
    3.  Classify each stationary point by checking the sign of the second derivative. If $\frac{d^{2}J}{dx^{2}} > 0$, it's a local minimum.
    4.  Evaluate the cost function $J(x)$ at all local minima. The one that gives the smallest value is the **global minimum**.