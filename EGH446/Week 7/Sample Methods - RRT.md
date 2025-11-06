#Algorithms #PathPlanning #Sampling

## Rapidly Exploring Random Trees (RRT)
RRT is an algorithm that efficiently explores continuous spaces using a random search, building a tree structure.
* **Main Idea**: Pick a random point in the search space, find the *nearest* node already in the tree, and create a new tree branch from that node *in the direction* of the random point. Continue until the goal is reached.
* **Algorithm**:
    1.  Start with the initial state `q-init` as the root of the tree.
    2.  Pick a random state (target) in the environment.
    3.  Find the closest node `N` already in the tree.
    4.  Create a new tree branch of a fixed, predefined length, extending from node `N` *toward* the random target.
    5.  Repeat this process until the goal is reached or a limit is exceeded.
    6.  Once a node of the tree is near the goal, the plan is traced back up the tree to the root.

* **Performance**: RRT is efficient in practice, but its performance (e.g., finding the *optimal* path) is not guaranteed.