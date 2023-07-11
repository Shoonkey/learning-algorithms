# Backtracking

Backtracking is a technique that's useful to look through all possible solutions of a problem given some constraint.
It's called backtracking because it goes through every possible option/permutation of a problem and when it reaches a point where a given permutation does not satisfy the problem constraint, it discards it and goes to the next, thus going back to a new permutation (i.e. backtracking).

Imagine you're playing a game of chess and you move your knight. Some moves later, you realize that was not a good option because you moved it to a place where it's attacked. So in an ideal world, you could undo and try another move. Simulations can be ideal worlds, and in them we can backtrack to look for optimal solutions.

It uses recursion to find solutions by building them step by step, increasing levels with time. Every step goes further into a search tree (called a *state-space tree*) where each branch is a variable and each level is a solution. It does a depth-first search exploring all solutions, checking if the result matches a constraint and it it does, it moves on with it and else it eliminates it and backtracks to the previous level.

Because it eliminates solutions as soon as they don't fit a constraint and builds solutions incrementally, it is an optimization of a naive brute force solution that goes through with all possible solutions and test them one by one after.

## Applications

- The *knight's tour problem*: Calculating a path for a chess knight such that it visits every square of a board exactly once. 
- Given a configuration of a maze (empty spaces, dead ends, starting point, goal point), calculating a path.
- The *N-Queen problem*: In chess, given a NxN board, placing N queens on it such that no two queens attack each other.
- Solving a sudoku puzzle.