## Question
Given an `m x n` 2D binary grid `grid` which represents a map of `'1'`s (land) and `'0'`s (water), return _the number of islands_.

An **island** is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Example 1:**

**Input:** grid = [
  ["1","1","1","1","0"],
  ["1","1","0","1","0"],
  ["1","1","0","0","0"],
  ["0","0","0","0","0"]
]
**Output:** 1

**Example 2:**

**Input:** grid = [
  ["1","1","0","0","0"],
  ["1","1","0","0","0"],
  ["0","0","1","0","0"],
  ["0","0","0","1","1"]
]
**Output:** 3

**Constraints:**

- `m == grid.length`
- `n == grid[i].length`
- `1 <= m, n <= 300`
- `grid[i][j]` is `'0'` or `'1'`.

##  Solution - Recursive DFS

``` java
public class NumberOfIslands {  
    public int numIslands(char[][] grid) {  
        int islands = 0;  
        int row = grid.length;  
        int column = grid[0].length;  
  
        for (int X = 0; X < row; X++ ) {
            for (int Y = 0; Y  < column; Y++){
                if (grid[X][Y] == '1') {  
                    islands++;  
                    dfs(grid, X, Y);  
                }
            }        
        }        
        return islands;  
    }  
    private void dfs(char[][] grid, int X, int Y) {  
        // check if is outside of bounds  
        if (isNotValid(grid, X, Y)|| grid[X][Y] == '0') {  
            return;  
        }  
        // otherwise, mark cell as visited  
        grid[X][Y] = '0';  
  
        dfs(grid, X - 1, Y);  
        dfs(grid, X + 1, Y);  
        dfs(grid, X, Y - 1);  
        dfs(grid, X, Y + 1);  
    }  
    private boolean isNotValid(char[][] grid, int X, int Y) {  
        return X < 0 || X >= grid.length || Y < 0 || Y >= grid[0].length;  
    }  
}
```