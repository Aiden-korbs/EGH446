#Algorithms #PathPlanning #Sampling

## Probabilistic Roadmap Methods (PRM)
PRM is a method for path planning in a continuous space by building a graph (a "roadmap") of feasible paths.
* **Method**:
    1.  **Sample**: Sample a large number of random locations (nodes) in the environment.
    2.  **Filter Samples**: Remove any samples that are in "forbidden regions" (i.e., inside obstacles).
    3.  **Link Nodes**: Link each remaining sample to its *K* nearest neighbors.
    4.  **Filter Links**: Remove any links (edges) that cross forbidden regions.
    5.  **Search**: The resulting graph is the PRM. Link the `q_start` and `q_goal` to this graph and use a search algorithm (like A*) to find the optimal path.