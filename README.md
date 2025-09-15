# TurtleBot3 Smart Room Navigator Project

Created a smart robot that uses predefi ned logic AND a trained ML model to make decisions about which room to visit next, and then autonomously navigate to that room using the Nav2 stack with nav2_simple_commander.

## Project Goal
● Used SLAM to map the house and then switch to Navigation mode.
● Based on simulated input conditions (like time of day, task priority, or room status), used a Decision Tree classifi er to decide which room the robot should go to.
● Navigated to that room autonomously using SimpleCommander.

## Suggested Flow
● Launch the TurtleBot3 simulation in the turtlebot3_house world.
● Map the environment using SLAM and save the map.
● Start Nav2 and the robot’s localization stack.
● The input_node simulates or accepts task conditions.
● The decision_node predicts which room to visit next.
● The navigator_node sends the goal to that room using SimpleCommander.

## Node Structure
input_node-Publishes simulated task conditions (e.g., time, priority, room type)
decision_node-Loads a trained Decision Tree model and publishes the predicted room
navigator_node-Subscribes to the room name and sends the robot to that room using Nav2
