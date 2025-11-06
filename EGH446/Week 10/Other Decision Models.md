#DecisionMaking #Models #AI

Besides Markov Decision Processes and Multi-Attribute Decision Making, several other models are used:

* **Human Decision Making**: Based on mathematical models from psychology and neuroscience that try to emulate how the human brain functions.
* **Machine Learning**: Uses previous experience (training data) to make decisions when new information is presented.
* **Game Theory**:
    * Uses game trees (graphs) that list actions and their consequences, similar to path planning.
    * It also studies models of cooperation and conflict between *multiple* decision-makers.
* **FUZZY Systems**:
    * A system based on "fuzzy logic" that maps states and alternatives to consequences.
    * A **decision function** `D` then reflects the preference structure of the decision-maker to apply an ordering to the consequences.
    * **Example**: A car driving on a road.
        * **States ($\Theta$)**: {slippery road, not slippery road}
        * **Actions (A)**: {brake soft, brake hard}
        * **Consequences ($\epsilon$)**: {slip and hit tree, hit dog slightly, do not hit anything}
    * A fuzzy system maps the (Action, State) pairs to a consequence, and the decision function `D` ranks those consequences to select the best action.