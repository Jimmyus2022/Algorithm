Approach 1: Legged robots move in a Hotel: BFS
The ball can only move one cell at a time.

Approach 2: Wheeled robots move in a Hotel: BFS
The ball can go through the empty spaces by rolling right, left, up, down, but it won't stop rolling until hitting a wall. When the ball stops, it could choose the next direction.

Approach : Breadth First Search
The same search space tree can also be explored in a Breadth First Search manner.
In this case, we try to explore the search space on a level by level basis.
i.e., we try to move in all the directions at every step.
When all the directions have been explored and we still don't reach the destination, then only we proceed to the new set of traversals from the new positions obtained.
In order to implement this, we make use of a queue.
We start with the ball at the start position.
For every current position, we add all the new positions possible by traversing in all the four directions(till reaching the wall or boundary) into the queue to act as the new start positions and mark these positions as True in the visited array.
When all the directions have been covered up, we remove a position value, ss, from the front of the queue and again continue the same process with ss acting as the new start position.
Further, in order to choose the direction of travel, we make use of a dir array, which contains 4 entries.
Each entry represents a one-dimensional direction of travel.
To travel in a particular direction, we keep on adding the particular entry of the dirs array till we hit a wall or a boundary.
For a particular start position, we do this process of dir addition for all all the four directions possible.
If we hit the destination position at any moment, we return a True directly indicating that the destinationdestination position can be reached starting from the start position.
![ball_gate](https://github.com/Jimmyus2022/Algorithm/assets/119981225/77b34596-88e6-430f-861d-73b869315b7a)
![ball_gate_1](https://github.com/Jimmyus2022/Algorithm/assets/119981225/dc5d699c-03b8-4157-b71f-d1a999ab75bd)

Visited:  0
0
Queue:
-----------------------------------------
Visited:  0
1
Queue:  0
-----------------------------------------
Visited:  0
1
Queue:  
Print:   0
-----------------------------------------
Visited:  0  C  K
1  1  1
Queue:  C K
Print:   0
-----------------------------------------
Visited:  0  C  K
1  1  1
Queue:  K
Print:   0  C
-----------------------------------------


Visited:  0  C  K  G
1  1  1  1
Queue:  K G
Print:   0  C
-----------------------------------------
Visited:  0  C  K  G
1  1  1  1
Queue:  G
Print:   0  C  K
-----------------------------------------
Visited:  0  C  K  G
1  1  1  1
Queue:  
Print:   0  C  K  G
-----------------------------------------
Visited:  0  C  K  G  D
1  1  1  1   1
Queue:  D
Print:   0  C  K  G
-----------------------------------------
Visited:  0  C  K  G  D
1  1  1  1   1
Queue:  
Print:   0  C  K  G  D
-----------------------------------------
Visited:  0  C  K  G  D A  I
1  1  1  1   1  1  1
Queue:  A I
Print:   0  C  K  G  D
-----------------------------------------
Visited:  0  C  K  G  D A  I
1  1  1  1   1  1  1
Queue:   I
Print:   0  C  K  G  D  A
-----------------------------------------
Visited:  0  C  K  G  D A  I  B
1  1  1  1   1  1  1
Queue:   I  B
Print:   0  C  K  G  D  A
-----------------------------------------
Visited:  0  C  K  G  D A  I  B
1  1  1  1   1  1  1
Queue:    B
Print:   0  C  K  G  D  A  I
-----------------------------------------
Visited:  0  C  K  G  D A  I  B U
1  1  1  1   1  1  1
Queue:    B U
Print:   0  C  K  G  D  A  I
-----------------------------------------
Visited:  0  C  K  G  D A  I  B U
1  1  1  1   1  1  1
Queue:    U
Print:   0  C  K  G  D  A  I  B
-----------------------------------------
Visited:  0  C  K  G  D A  I  B U
1  1  1  1   1  1  1
Queue:    
Print:   0  C  K  G  D  A  I  B  U
-----------------------------------------
Because the R is on the path to U, it stops here.


![Screenshot 2023-08-12 at 10 43 37 AM](https://github.com/Jimmyus2022/Algorithm/assets/119981225/5cd8998b-9274-428c-82c1-1bc7d55999dc)

![Screenshot 2023-08-12 at 10 44 40 AM](https://github.com/Jimmyus2022/Algorithm/assets/119981225/33ee5180-4dfe-4334-9629-3f92d933532a)

![Screenshot 2023-08-12 at 10 44 27 AM](https://github.com/Jimmyus2022/Algorithm/assets/119981225/75d6feb1-441b-46bb-ba8f-f8e90888f51e)



