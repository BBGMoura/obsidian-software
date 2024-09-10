
## Maze Problem
This problem includes a start coordinate and end coordinate. A path between the two has to be found. There are two ways to do this:

- DFS - finds if it _can_ reach endpoint 
- BFS - finds _fastest_ way to reach endpoint

Maze class example:

``` Java
public class Maze {  
  
    private final boolean[][] vacantCells;  
    private final int width;  
    private final int height;  
  
    Maze(boolean[][] vacantCells, int width, int height) {  
        this.vacantCells = vacantCells;  
        this.width = width;  
        this.height = height;  
    }  
    /**  
     * Returns true if the cell in the maze at x,y is empty     */    public boolean canMoveInto(int x, int y) {  
        return x >= 0 && x < width && y >= 0 && y < height && vacantCells[x][y];  
    }  
    /**  
     * Returns how wide the maze is, i.e. how many cells there are on the x-axis     */    public int getWidth() {  
        return width;  
    }  
    /**  
     * Returns how high the maze is, i.e. how many cells there are on the y-axis     */    public int getHeight() {  
        return height;  
    }
}

// Example Maze:
" #      ",  
" ####   ",  
"  ##  ##",  
" ##     ",  
"    ##  ",  
"#####   ",  
"  #   ##",  
"####    "
```

## Depth-first Search
Depth-first (DFS) is an algorithm for traversing or searching tree or graph data structures.
The DFS starts at a node, then goes deep in each branch before moving to explore another branch.

#### Key Characteristics:
-  **Uses Stack (LIFO)**: Last in, first out. The `Stack` structure ensures that the most recently discovered node is processed first.
- **Deep Exploration**: DFS explores deeply before moving to another branch.

#### Implementation:
**Data Structure**: 
A `Stack` is best for this implementation. Java has a `Stack` class, however, this is a legacy class as it has a overhead since it is thread safe. Therefore, it is best to use the `Deque` Interface.

``` java
Deque<Integer> stack = new ArrayDeque<>();

//LIFO - last in, first out
stack.push("A");
stack.push("B");

stack.peek(); // shows top element in stack "B"
stack.pop(); // removes top element in stack "B"

```

 **Algorithm**:
 - Push starting node onto the stack
 - Pop a node from the stack to process it
 - Push all its unvisited neighbours onto the stack
 - Mark each node as visited when it is pushed onto the stack
 - Repeat till stack is empty or target node is found

``` Java
@Override  
public boolean canMoveBetweenPointsOnMaze(Maze maze, int startX, int startY, int endX, int endY) {  
    //return if start or end value is invalid  
    if(!maze.canMoveInto(startX, startY) || !maze.canMoveInto(endX, endY)) {  
        return false;  
    }  
    // record the coordinates that have been visited  
    final boolean[][] visited = new boolean[maze.getWidth()][maze.getHeight()];  
  
    //set current point visited  
    visited[startX][startY] = true;  
  
    // records the current value  
    final Deque<Coordinate> pointer = new ArrayDeque<>();  
    pointer.add(new Coordinate(startX, startY));  
  
    while (!pointer.isEmpty()) {  
        //retrieve current pointer  
        Coordinate current = pointer.pop();  
  
        if(current.getX() == endX && current.getY() == endY) {  
            return true;  
        }  
        // up, down left, right  
        // up, down left, right  
		final int[][] directions = {{0, -1}, {0, 1}, {-1, 0}, {1, 0}};  
  
		for (int[] direction : directions) {  
		    int newX = current.getX() + direction[0];  
		    int newY = current.getY() + direction[1];
  
            if (maze.canMoveInto(newX, newY) && !visited[newX][newY]) {  
                pointer.push(new Coordinate(newX, newY));  
                visited[newX][newY] = true;  
            }        }    }  
    return false;  
}
```

## Breadth-first Search
Breadth-first Search (BFS) algorithm for traversing or searching tree or graph structures. It starts at a given node and explores all neighbours at the present depth level before moving to nodes at the next depth level.

#### Key Characteristics:
- **Uses Queue (FIFO)**: The `Queue` structure ensures that nodes are processed in order they are discovered. 
- **Level-wise Exploration**: BFS explores nodes level by level.

#### Implementation
**Data Structure**:
Use Queue interface for this. The best implementation for this is `LinkedList` as we maintain two pointers, front and rear. 

``` Java
Queue<Integer> queue = new LinkedList<>();

// enqueue -> add element at the rear 
queue.offer("A");
queue.offer("B"); // B,A

// dequeue -> remove from the front
queue.poll(); // front element "A"
```

**Algorithm**:
- Enqueue (add element to the rear) the starting node
- Dequeue (remove element from the front) and process it
- Enqueue all its unvisited neighbours
- Mark each node as visited when it is enqueued
- Repeat until queue is empty or the target node is found



## Note
`LinkedList` implements both the `Queue` and `Dequeue` interfaces. It supports FIFO operations for queues (`addLast()`, `removeFirst()`) and LIFO operations for stacks (`push()`, `pop()`). However, Deque is preferred for DFS as LinkedList has a higher overhead.