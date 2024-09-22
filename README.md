8-Puzzle Problem Solving Using BFS, DFS, and DFID
This code solves an 8-puzzle problem using three search algorithms:

Breadth-First Search (BFS)
Depth-First Search (DFS)
Depth-First Iterative Deepening (DFID)
  The problem involves moving the blank tile (represented by the number 9) in a 3x3 grid to reach a goal configuration. The algorithms generate new puzzle states     by moving the blank tile in four possible directions (up, down, left, and right) and search for the goal state.

# Code Structure
## Helper Functions
### Makepairs(NewNode, NodePair)
  Purpose: This function creates pairs of the current node with its parent node. 
  Arguments:
           NewNode: List of new nodes generated after moving the blank tile.
           NodePair: The current node that acts as the parent of the new nodes.
  Returns: A list of pairs of new nodes and their parent node.
    
### RemoveSeen(Closed, children)
  Purpose: Removes nodes that have already been visited (i.e., nodes in the Closed list) from the newly generated nodes.
  Arguments:
        Closed: List of nodes that have already been visited.
        children: List of new nodes generated.
  Returns: A list of nodes that haven't been visited yet.

### Reverse(lst)
  Purpose: Reverses a list.
  Arguments:
          lst: A list to reverse.
  Returns: The reversed list.
    
### ReconstructPath(NodePair, Closed)
  Purpose: Reconstructs the path from the initial node to the goal node by tracing back through the parent nodes.
  Arguments:
        NodePair: The goal node or current node.
        Closed: List of all nodes and their parents.
  Returns: A list representing the path from the start node to the goal node.
  
### swap(Nodepair, ni, nj, i, j)
  Purpose: Swaps two tiles in the puzzle.
  Arguments:
        Nodepair: The current puzzle configuration.
        ni, nj: Coordinates of the first tile.
        i, j: Coordinates of the second tile.
  Returns: The updated puzzle configuration after the swap.

### MoveGen(Nodepair, i, j)
  Purpose: Generates new nodes by moving the blank tile in four possible directions (right, left, up, down).
  Arguments:
          Nodepair: The current puzzle configuration.
          i, j: Coordinates of the blank tile (9).
  Returns: A list of new puzzle configurations.
        
### func(NodePair)
  Purpose: Finds the position of the blank tile (9) in the current puzzle configuration.
  Arguments:
        NodePair: The current puzzle configuration.
  Returns: The coordinates (i, j) of the blank tile.

      
# Search Algorithms

### db_dfs(OpenNode, GoalNode, depth)
   Purpose: Performs depth-bounded DFS. Searches for the goal node while limiting the search to a specified depth.
   Arguments:
            OpenNode: The initial node.
            GoalNode: The goal configuration.  
            depth: The current depth limit.
   Returns: The path to the goal node if found, otherwise None.

### DFID(OpenNode, GoalNode)
  Purpose: Performs Depth-First Iterative Deepening (DFID), where depth-limited DFS is run repeatedly with increasing depth until the goal is found.
  Arguments:
            OpenNode: The initial node.
            GoalNode: The goal configuration.
  Returns: The path to the goal node.

### DFS(OpenNode, GoalNode)
  Purpose: Performs Depth-First Search (DFS).
  Arguments:
          OpenNode: The initial node.
          GoalNode: The goal configuration.
  Returns: The path to the goal node.

### BFS(OpenNode, GoalNode)
  Purpose: Performs Breadth-First Search (BFS).
  Arguments:
          OpenNode: The initial node.
          GoalNode: The goal configuration.
  Returns: The path to the goal node.
