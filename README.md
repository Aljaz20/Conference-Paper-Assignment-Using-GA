# Optimizing Conference Paper Assignment Using Genetic Algorithms

## Objective
The goal of this project was to develop a system for optimizing the assignment of conference papers to reviewers using genetic algorithms. 
The system was designed to maximize overall satisfaction by aligning reviewer preferences while satisfying several constraints. 
This task plays a crucial role in automating the conference paper-review process, ensuring fairness and efficiency.

## Problem Description
The project tackled the following constraints:
- **Reviewer Capacity**: Each reviewer was limited to reviewing a specific number of papers.
- **Review Requirements**: Each paper required a specific number of reviews.
- **Friendship Constraints**: Friends could not review the same paper to avoid bias.
- **Authorship Constraints**: Reviewers could not review papers they had authored.

## Approach
### Representation
I created a structured representation for the **preference matrix**, **friendship matrix**, and **authorship constraints**, which were modeled to capture 
relationships between reviewers and papers effectively. Assignments were represented as matrices, where each cell indicated whether a reviewer was assigned to a 
specific paper. A fitness function was implemented to evaluate assignments based on preference scores while minimizing constraint violations.

### Genetic Algorithm
I adapted and implemented a genetic algorithm to generate optimized assignments:
- Customized **crossover and mutation** functions ensured that offspring assignments adhered to constraints.
- The algorithm penalized violations such as exceeding reviewer capacities or assigning friends to the same paper.
- Libraries such as PyGAD were utilized and extended to suit the problem's requirements.

### Diversity and Complexity
To explore a broader solution space, I incorporated diversity-enhancing strategies within the algorithm. This ensured that the solution set included various feasible assignments, reducing the likelihood of stagnation in local optima.

### Evaluation
Extensive testing was performed using multiple datasets to evaluate the algorithm's robustness and efficiency. The results were analyzed to compare the impact of different configurations, such as mutation rates and selection criteria. Visualizations were created to demonstrate runtime performance and constraint satisfaction.

## Example Dataset
The system was tested on several datasets. Below are examples of how data was structured:

### Preference Matrix:
Indicates reviewer preferences for papers (higher values indicate stronger preferences).
| Reviewer \\ Paper | Paper 1 | Paper 2 | Paper 3 | Paper 4 | Paper 5 |
|-------------------|---------|---------|---------|---------|---------|
| Reviewer 1       | 5       | 4       | 5       | 3       | 4       |
| Reviewer 2       | 4       | 5       | 4       | 5       | 3       |

### Friendship Matrix:
Shows if reviewers are friends (1 = friends, 0 = not friends).
| Reviewer \\ Reviewer | Rev 1 | Rev 2 | Rev 3 | Rev 4 | Rev 5 |
|-----------------------|-------|-------|-------|-------|-------|
| Reviewer 1           | 0     | 1     | 0     | 0     | 0     |
| Reviewer 2           | 1     | 0     | 1     | 0     | 0     |

### Authorship Matrix:
Indicates if a reviewer is the author of a paper (1 = author, 0 = not author).
| Reviewer \\ Paper | Paper 1 | Paper 2 | Paper 3 | Paper 4 | Paper 5 |
|-------------------|---------|---------|---------|---------|---------|
| Reviewer 1       | 1       | 0       | 0       | 0       | 0       |
| Reviewer 2       | 0       | 1       | 0       | 0       | 0       |

## Tools and Skills
- **Languages**: Python
- **Techniques**: Genetic algorithms, optimization
- **Libraries**: Numpy, PyGAD (optional)