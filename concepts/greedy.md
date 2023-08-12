# Greedy algorithms

Greedy algorithms are algorithms that find the solution in the shortest time possible, following the heuristic of making the locally optimal choice at each stage without regard for the overall optimization or accuracy of the solution. For that reason they are fast ($O(n)$, $O(n\ log\ n)$) but don't always produce the optimal solution.

It is an algorithmic approach for optimization problems, like *dynamic programming* but is often simpler and faster and doesn't always produce the optimal solution, differently from dynamic programming, which does.

They are ideal if the problem has two properties:
1. **Greedy choice property**: An optimal solution can be found by choosing the local best choice at each step without ever reconsidering past choices.
2. **Optimal substructure property**: An optimal solution to the problem contains optimal solutions to the sub-problems.

> The difference between the two is not clear to me yet. I will revisit this later.