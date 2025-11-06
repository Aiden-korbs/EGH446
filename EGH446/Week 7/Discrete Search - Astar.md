#Algorithms #PathPlanning #DiscreteSearch

## A* (A-star) Search
* **Purpose**: A best-first search algorithm that finds an optimal path from a start node to a goal node.
* **Method**:
    1.  A* expands in directions of minimum *expected* cost, unlike Dijkstra which searches all nodes.
    2.  It uses a **heuristic** $h(x)$, which is an *estimate* of the cost to go from node `x` to the goal. A common heuristic is the straight-line distance.
    3.  While the goal is not reached, it picks a neighbor node $x'$ that has not been visited and minimises the total expected cost: $f(x') = c(x) + \text{length}(x, x') + h(x')$.
    4.  When the goal is picked, the path is traced back.
* **Result**: Can be very effective and much faster than Dijkstra, *if* the heuristic $h(x)$ is good.