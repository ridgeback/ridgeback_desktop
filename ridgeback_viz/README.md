## Overview

This package provides launchers and [rviz](https://index.ros.org/p/rviz)
configurations to assist with visualizing real or simulated
[Ridgeback](Robots/Ridgeback) from a desktop environment. For help
getting your desktop environment set up to use with Ridgeback, see the
[Ridgeback homepage](Robots/Ridgeback).

## Usage

To view the Ridgeback model in isolation, disconnected from a real or
simulated robot, use the following launcher:



```
roslaunch ridgeback_viz view_model.launch
```



To visualize a real or simulated Ridgeback, launch:



```
roslaunch ridgeback_viz view_robot.launch
```



## Configurations

If you'd like to bring up a specific rviz configuration, you can add an
arg to the view_robot launcher, for example:



```
roslaunch ridgeback_viz view_robot.launch config:=navigation
```



The configurations available are:

  -- --------------------------- -- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --
     <\^>`robot` (default)      The default configuration includes the [RobotModel plugin](https://index.ros.org/p/rviz), and displays Ridgeback in the **odom** frame, which will move the model about in rviz as you drive around.                                                                                                                                                                                                                                                                                  
     <\^>`navigation`           This configuration also displays Ridgeback in the **odom** frame and displays all the visualization information that local navigation provides including global plan, trajectory and local costmap. The desired navigation [Pose](https://index.ros.org/p/rviz) for the robot to achieve can be set using `2D Nav Goal`.                                                                                                                                                            
     <\^>`gmapping`             Gmapping configuration displays Ridgeback in the **map** frame. It includes [InteractiveMarker plugin](https://index.ros.org/p/rviz) so you can drive the robot around to build the map. It also includes [Map plugin](https://index.ros.org/p/rviz) to visualize the map being constructed.                                                                                                                                                                                          
     <\^>`localization`         This configuration also displays Ridgeback in the **map** frame and includes [PoseArray plugin](https://index.ros.org/p/rviz) which display the localization system's uncertainty about the robot's pose. It also includes visualization information of the known map, global costmap, trajectory associated with the velocity commands and global plan. The localization system can be initialized by setting the pose of the robot in the known map using `2D Pose Estimate`.   
  -- --------------------------- -- ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --
