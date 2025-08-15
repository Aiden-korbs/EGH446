## Purpose
Find an optimal path for a vehicle to travel from start to goal, possibly visiting intermediate points.

## Common Problems
- **TSP (Travelling Salesman Problem)** – Visit all points with minimum distance.
- **Dubins Paths** – Shortest path for vehicles with a minimum turning radius.
- **Non-holonomic Constraints** – Restrictions on movement (e.g., cars can’t move sideways).

## Planning Methods
- Graph search (Dijkstra, A*)
- Sampling-based (RRT, PRM)
- Optimization-based

## PGNC Integration
- Planner generates route.
- Guidance turns route into commands.
- Navigation estimates state.
- Control tracks commands.

## Example: Dubins Path
Shortest path between two configurations given turning radius $R_{\min}$ consists of 3 segments: combinations of curves (C) and straight lines (S), e.g., CSC or CCC.
