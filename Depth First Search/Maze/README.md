Introduction:
Depth First Search (DFS) algorithm traverses a graph in a depthward motion and uses a stack to remember to get the next vertex to start a search, when a dead end occurs in any iteration.
Rule 1
Visit the adjacent unvisited vertex.
If there are several vertices, randomly pick one.
Mark it as visited.
Display it.
Push it in a stack.
Rule 2
If no adjacent vertex is found, pop up a vertex from the stack.
It will pop up all the vertices from the stack, which do not have adjacent vertices.
Rule 3
Repeat Rule 1 and Rule 2 until the stack is empty.

 Manual process:
 ![IMG_2184](https://github.com/Jimmyus2022/Algorithm/assets/119981225/32fb4254-0207-4f13-8150-3bd4a13cce59)


Implement the Python code:

from datetime import datetime
from typing import List
class Solution:
    def hasPath(self, maze: list[list[int]], start: list[int], destination: list[int]) -> bool:
        # Define the directions to move in the maze (up, down, left, right)
        directions = [(0, 1), (0, -1), (1, 0), (-1, 0)]

        # Function to perform DFS
        def dfs(x, y):
            if [x, y] == destination:
                return True

            # Mark the current position as visited
            maze[x][y] = 2

            for dx, dy in directions:
                nx, ny = x + dx, y + dy

                # Keep rolling the ball in the same direction until it hits a wall or goes out of bounds
                while 0 <= nx < len(maze) and 0 <= ny < len(maze[0]) and maze[nx][ny] != 1:
                    nx += dx
                    ny += dy

                # Revert back to the last valid position before the wall or out of bounds
                nx -= dx
                ny -= dy

                # If the new position is not visited, perform DFS from there
                if maze[nx][ny] == 0 and dfs(nx, ny):
                    return True

            return False

        return dfs(start[0], start[1])

# Example 1 
maze = [
    [0, 0, 1, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 1, 0],
    [1, 1, 0, 1, 1],
    [0, 0, 0, 0, 0]
]
start = [0, 4]
destination = [4, 4]

# Create an instance of the Solution class
sol = Solution()

# Check if there is a path from the start to the destination using the class method
print(sol.hasPath(maze, start, destination))  # Output: True

print("----------------------------------------------------------------")

# Example 2 
maze2 = [
    [0, 0, 1, 0, 0],
    [0, 0, 0, 0, 0],
    [0, 0, 0, 1, 0],
    [1, 1, 0, 1, 1],
    [0, 0, 0, 0, 0]
]
start2 = [0, 4]
destination2 = [3, 2]
print(sol.hasPath(maze2, start2, destination2)) 

print("----------------------------------------------------------------")

# Example 3 
maze3 = [
    [0, 0, 0, 0, 0],
    [1, 1, 0, 0, 1],
    [0, 0, 0, 0, 0],
    [0, 1, 0, 0, 1],
    [0, 1, 0, 0, 0]
]
start3 = [4, 3]
destination3 = [0, 1]
print(sol.hasPath(maze3, start3, destination3))  

print("----------------------------------------------------------------")

# output with timestamp
timestamp = datetime.now()
formatted_timestamp = timestamp.strftime("%Y-%m-%d %H:%M:%S")
print (formatted_timestamp)
