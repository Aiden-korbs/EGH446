## How is path planning done?
There are three basic classifications for path planning algorithms:

1.  **Potential Field (Navigation Functions)**
    * Models the platform as a particle in an artificial potential field.
    * Obstacles create **repulsive forces** and the goal creates an **attractive force**.
    * The path is found by gradient descent (like a ball rolling down the surface).
    * **Limitation**: Can get stuck in local minima.
    

2.  **Discrete Planning Methods**
    * Divides the "world" into a grid and enumerates actions for moving between points.
    * Searches for a feasible path from start to end.
    * Examples: [[Discrete Search - Dijkstra|Dijkstra]], [[Discrete Search - Astar|A*]].

3.  **Sample Path Methods**
    * Used for planning in continuous space without a grid.
    * Examples: [[Sample Methods - PRM|Probabilistic Roadmaps (PRM)]], [[Sample Methods - RRT|Rapidly Exploring Random Trees (RRT)]].