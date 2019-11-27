# Search-Algorithms (A-Star and Dynamic-Prgramming)
 In the repository we will learn some of the foundational search algorithms(A* and dynamic Prgramming) used in discrete path planning.

Path planning is how the vehicle generates safe drivable trajectories to get where we want it to go.
We'll use data from computer vision and sensor fusion in order to understand the environment around us. We'll also use data from localization to understand precisely where we are in that environment.

The path planning block uses all of that data to decide which maneuver to take next then it constructs a trajectory for the controller to execute. 
In the first lesson we will learn some of the foundational search algorithms used in discrete path planning. Then you will learn about prediction, which is where we use the data from sensor fusion to generate predictions about what all the other objects around us are likely to do. Then we will study about behavior planning. This is where we decide at a high level what the car shall do in the next 10 seconds or so. Finally we will learn about trajectory generation which is where we create smooth, drivable and collision-free trajectories for the motion controller to follow. In the project at the end of this module you'll implement a path planner for a vehicle driving on a highway. Our vehicle will be able to avoid collisions, maintain safe distances between other traffic and even pass other vehicles to get where it's going faster.

This lesson covers discrete path planning. Even though the real world is continuous, there are many situations where discretizing the world makes it easier and computationally faster to solve path planning problems.

In addition to the practical benefits of these algorithms, it's also conceptually useful to learn about them because they deal with some of the same concepts that we will keep coming back to in this lesson. Those concepts include:
•	Cost functions and how to include human insights (like "it's easier to make right turns than left turns") into our planning algorithms.
•	Optimality and the tradeoffs associated with finding the best solution vs finding a solution that is good enough.
•	Online vs Offline algorithms and how we can avoid complex computation on the road by precomputing best paths whenever possible.

The fundamental problem in motion planning is that a robot might live in a world like below and it might want to find its way to a goal and has to device a plan to get to the goal. This same problem occurs for a self driving car that might live in a city near a highway on a network of streets. It has to find its way around and navigate to its target location.
If we look at the intersection in figure, a car coming from A (Start) that wishes to go over B (goal). To take a left turn (C) on the intersection, this car would have to turn right first (D), engage in a lane shift (F) and then take the left turn(C) to the goal location. B

<p align="right"> <img src="./img/1.png" style="right;" alt=" Pseudocode" width="600" height="400"> </p> 
