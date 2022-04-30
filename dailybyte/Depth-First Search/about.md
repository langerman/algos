# Intro to Depth-First Search

## Depth-first Search

Depth-first search is a graph traversal algorithm that explores as far as possible along each branch before beginning backtracking. Because depth-first search traverses the entirety of a graph it runs in O(N) time where N is the number of nodes in the graph. Depth-first search is typically performed using recursion but can also be performed iteratively using a stack. Opting for an iterative approach can be helpful in certain cases where your graph is very large to help avoid a stack overflow from your recursive calls.

## What to Know for Interviews

Depth-first search can be particularly helpful during interviews when answering questions like the following…

“Does there exist a path between x and y?”
“Generate all combinations of…”
“Find a path that…”
“Is it possible to…”

Because depth-first search traverses as far as possible along each branch a typical DFS will look like the following (assuming that your DFS is trying to traverse its four neighboring cells in a graph).

    // Traverse cell below current cell.
    dfs(graph, i+1, j);
    // Traverse cell above current cell.
    dfs(graph, i-1, j);
    // Traverse cell right of the current cell.
    dfs(graph, i, j+1);
    // Traverse cell left of the current cell.
    dfs(graph, i, j-1);

Fun fact: if you ever need to solve a maze, keep your hand against the right wall and you’ll eventually find your way out. Why? Because you’re performing a depth-first search on the maze!