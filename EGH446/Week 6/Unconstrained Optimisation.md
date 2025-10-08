#Optimisation #Calculus #StationaryPoints

**Unconstrained optimisation** is the process of finding the minimum or maximum of a function without any constraints on the input variables.

> [!NOTE] Definition
> Optimisation is the process of determining the **best element** (with regard to some cost criterion) from a set of **candidate elements**.

## Key Features of an Optimisation Problem

1.  **A Cost Function $J(x)$**: A mathematical function that quantifies how "good" a particular solution $x$ is. The goal is to either minimise or maximise this function.
2.  **Design Choices $x$**: The set of input variables or parameters that we can change to affect the outcome of the cost function.
3.  **Constraints (optional)**: Rules or limits that the design choices $x$ must obey. For example, a constraint might be $|x| < 10$. This note focuses on problems *without* constraints.

## The Role of Stationary Points

In unconstrained problems, local and global optima (minimums or maximums) occur at **stationary points**.

A stationary point is a location where the gradient (first derivative) of the function is zero:
$$
\frac{dJ}{dx} = 0
$$

### Types of Stationary Points

We can classify stationary points by checking the **second derivative**, $\frac{d^{2}J}{dx^{2}}$.

* **Local Minimum**: The function curves upwards.
    * $\frac{dJ}{dx} = 0$ and $\frac{d^{2}J}{dx^{2}} > 0$.
* **Local Maximum**: The function curves downwards.
    * $\frac{dJ}{dx} = 0$ and $\frac{d^{2}J}{dx^{2}} < 0$.
* **Saddle Point**: The function is flat but is not a minimum or maximum.
    * $\frac{dJ}{dx} = 0$ and $\frac{d^{2}J}{dx^{2}} = 0$.

### Global vs. Local Optima

* A function can have multiple local minimums or maximums.
* The **global minimum** is the smallest of all the local minimums.
* The **global maximum** is the largest of all the local maximums.

## Optimisation in Higher Dimensions

The same core ideas apply when optimising a function with multiple inputs, like $f(x, y)$. Instead of finding a point where the slope is zero, we look for a "flat surface" where all **partial derivatives** are zero. For a stationary point, we need:
$$
\frac{\partial f}{\partial x} = 0 \quad \text{and} \quad \frac{\partial f}{\partial y} = 0
$$