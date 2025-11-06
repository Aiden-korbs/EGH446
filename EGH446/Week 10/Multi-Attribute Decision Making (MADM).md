#DecisionMaking #Models #MADM

**Multi-Attribute Decision Making (MADM)** is used when a decision must be made from a *finite* set of alternatives, based on a *finite* set of criteria (or attributes).

## Weighted Sum Model (WSM)
This is a simple and common MADM method. It calculates a score for each alternative by multiplying the value of each attribute by its weight and summing the results.

The formula is:
$$
A_{i}^{WSM-score} = \sum_{j=1}^{n} w_{j} a_{ij}, \text{ for } i=1, 2, 3, ..., m
$$
Where:
* $A_{i}$ is the alternative being scored.
* $w_{j}$ is the weight (importance) of the $j^{th}$ criterion.
* $a_{ij}$ is the performance value (attribute) of the $i^{th}$ alternative for the $j^{th}$ criterion.

## Example 1: Emergency Landing
An aircraft has a failure and must make an emergency landing. An onboard system has detected three possible landing sites and must decide the best one.

**Criteria, Weights, and Alternatives:**

|  alt   | area (w=0.3) | length (w=0.3) | slope (w=0.1) | distance (w=0.3) |
| :----: | :----------: | :------------: | :-----------: | :--------------: |
| site 1 |      25      |       30       |      20       |        30        |
| site 2 |      10      |       20       |       5       |        10        |
| site 3 |      30      |       10       |      30       |        10        |

**Calculation:**
* **Site 1 Score** = (0.3 * 25) + (0.3 * 30) + (0.1 * 20) + (0.3 * 30) = 7.5 + 9 + 2 + 9 = **27.5**
* **Site 2 Score** = (0.3 * 10) + (0.3 * 20) + (0.1 * 5) + (0.3 * 10) = 3 + 6 + 0.5 + 3 = **12.5**
* **Site 3 Score** = (0.3 * 30) + (0.3 * 10) + (0.1 * 30) + (0.3 * 10) = 9 + 3 + 3 + 3 = **18.0**

**Decision:** Site 1 has the highest score and is the best alternative.

**Note**: You must be careful with maximization vs. minimization. In this example, higher numbers are assumed better for all attributes. If "distance" or "slope" were costs (where lower is better), they would need to be inverted (e.g., 1/distance) or handled differently.

---
## Example 2: Ground Robot
A ground robot must decide its next action based on sensor readings.

**Criteria, Weights, and Alternatives:**
(Weights are all equal: 0.25)

| actions | attr 1 (w=0.25) | attr 2 (w=0.25) | attr 3 (w=0.25) | attr 4 (w=0.25) |
| :---: | :---: | :---: | :---: | :---: |
| turn left | 25 | 19 | 20 | 10 |
| continue | 10 | 20 | 5 | 24 |
| turn right | 27 | 10 | 30 | 45 |
| turn back | 26 | 25 | 24 | 78 |

**Calculation:**
* **Turn Left Score** = 0.25 * (25 + 19 + 20 + 10) = 0.25 * 74 = **18.5**
* **Continue Score** = 0.25 * (10 + 20 + 5 + 24) = 0.25 * 59 = **14.75**
* **Turn Right Score** = 0.25 * (27 + 10 + 30 + 45) = 0.25 * 112 = **28.0**
* **Turn Back Score** = 0.25 * (26 + 25 + 24 + 78) = 0.25 * 153 = **38.25**

**Decision:** "Turn Back" has the highest score.