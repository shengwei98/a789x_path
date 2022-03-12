# Robot Path Planning 
This repo contains a ROS package for Assignment 2 of ME3243 Robotic System Design

## Running the Simulation
Clone this repo into a catkin workspace and build using `$ catkin_build`

There are two ways of running the simulation

### 1. Using Tmux 
This method requires tmux. 

1) copy the bash script named run_simulation.sh to the home of the catkin workspace
2) run the bash script using `$ . run_simulation.sh`

### 2. Manually running nodes
Source the workspace in each of the terminals

1) first terminal

`$ . src/a789x_path/bin/noetic_project_init_world_1.sh`

This script installs the gazebo world and launches the gazebo simulation.

2) second terminal

`$ roslaunch a789x_path start_bot_control.launch`

This node implements a closed-loop PID control for the turtlebot. The PID values can be found in /config.config.yaml

3) third terminal 

`$ rosrun a789x_path range_detect_node`

This node collects range data from the gazebo simulation. It detects the distance from the turtlebot to the closest wall in the north,south,east and west direction.

4) fourth ternimal

`$ a789x_path path_plan_node`

This node will take generate a path for the turtlebot to the goal, using astar search. 

## 





