# Search-Algorithms (A-Star and Dynamic-Prgramming)

 In this repository we will learn some of the foundational search algorithms (A* and dynamic Prgramming) used in discrete path planning. Path planning can be explained in the self-driving car as how the vehicle generates safe drivable trajectories to get where we want it to go. 

The path planning block uses all of  data (data from computer vision and sensor fusion in order to understand the environment around us and data from localization to understand precisely where we are in that environment) to decide which maneuver to take next then it constructs a trajectory for the controller to execute. 

This lesson covers discrete path planning and even though the real world is continuous, there are many situations where discretizing the world makes it easier and computationally faster to solve path planning problems.

In addition to the practical benefits of these algorithms, it's also conceptually useful to learn about them because they deal with some of the same concepts that we will keep coming back to in this lesson. Those concepts include:

* Cost functions and how to include human insights (like "it's easier to make right turns than left turns") into our planning algorithms.
* Optimality and the tradeoffs associated with finding the best solution vs finding a solution that is good enough.
* Online vs Offline algorithms and how we can avoid complex computation on the road by precomputing best paths whenever possible.


The fundamental problem in motion planning is that a robot might live in a world like below and it might want to find its way to a goal and has to device a plan to get to the goal. This same problem occurs for a self driving car that might live in a city near a highway on a network of streets. It has to find its way around and navigate to its target location which need to pan a path.

If we look at the intersection in figure below, a car coming from A (Start) that wishes to go to B (goal). To take a left turn (C) on the intersection, this car would have to turn right first (D), engage in a lane shift (F) and then take the left turn(C) to the goal location (B).

<p align="right"> <img src="./img/1.jpg" style="right;" alt=" Pseudocode" width="600" height="400"> </p> 

Now, a lane shift (F) is a risky proposition. If there is a  truck parked, the space might be insufficient to carry out the lane shift. An alternative plan might be to go straight (G), take the detour around the block, and then go straight to the target location.

**The process of finding a path from a start location to a goal location is called "planning." For robots, it's often called "robot motion planning.** We are going to talk about discrete methods for planning in which the world chopped into small bins.

What's the planning problem? 

* We're given a map of the world.
* We're given a starting location.
* We're given a goal location.
* we're given some sort of a cost function. The simplest way to think of cost is just the time it takes to drive a certain route.

**The goal is find the minimum cost path.**

