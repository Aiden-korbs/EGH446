#Algorithms #PathPlanning #DiscreteSearch

## Dijkstra's Algorithm
* **Purpose**: Finds the optimal (e.g., shortest) path from *every node* on a grid to the goal node.
* **Method**:
    1.  Creates a grid of nodes `Q` and an unvisited set `U`.
    2.  Sets the cost `c(x)` for all nodes to infinity, except the `start_node` (`c(start_node) = 0`).
    3.  While `U` is not empty, it selects the node `x` in `U` with the minimum cost.
    4.  For each neighbor $x'$ of `x`, it calculates a new cost: `newdist = c(x) + length(x, x')`.
    5.  If `newdist` is less than $c(x')$, it updates $c(x')$ and records `x` as the best node to come from.
    6.  Removes `x` from `U`.
* **Result**: Guaranteed to find the optimal cost $c^*(x)$.
* **Limitation**: Can be slow because it searches *all* nodes.