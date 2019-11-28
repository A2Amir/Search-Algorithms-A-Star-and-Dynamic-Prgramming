# Search-Algorithms (A-Star and Dynamic-Prgramming)

 In this repository we will learn some of the foundational search algorithms (A* and dynamic Prgramming) used in discrete path planning. Path planning can be explained in the self-driving car as how the vehicle generates safe drivable trajectories to get where we want it to go. 

The path planning block uses all of  data (data from computer vision and sensor fusion in order to understand the environment around us and data from localization to understand precisely where we are in that environment) to decide which maneuver to take next then it constructs a trajectory for the controller to execute. 

This lesson covers discrete path planning and even though the real world is continuous, there are many situations where discretizing the world makes it easier and computationally faster to solve path planning problems.

In addition to the practical benefits of these algorithms, it's also conceptually useful to learn about them because they deal with some of the same concepts that we will keep coming back to in this lesson. Those concepts include:

* Cost functions and how to include human insights (like "it's easier to make right turns than left turns") into our planning algorithms.
* Optimality and the tradeoffs associated with finding the best solution vs finding a solution that is good enough.
* Online vs Offline algorithms and how we can avoid complex computation on the road by precomputing best paths whenever possible.

<p align="right"> <img src="./img/1.jpg" style="right;" alt=" Pseudocode" width="600" height="400"> </p> 
