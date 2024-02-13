# exp
## Launch steps
This project can be launched using a global launch file or by executing a series of commands in the terminal to start individual components. Below are the instructions for both methods.

### Quick Launch
If you prefer a quick start, you can launch the entire project using a single launch file:
```console
roslaunch globallaunch.launch
```
This command initializes all necessary nodes and brings up the simulation environment and the robot ready for marker detection and navigation tasks.


### Step-by-Step Launch
For systems with lower performance, or if you wish to manually control the launch process, follow the steps below. Execute each command in a new terminal window, in the given order:

1. Start the Gazebo simulation with the ROSBot in the assignment-specific environment:
```console
roslaunch rosbot_gazebo assignment2.launch
```
2. Bring up the ROSBot:
```console
roslaunch rosbot_bringup rosbot_gazebo.launch
```
Alternatively, for steps 1 and 2, use the combined launch file:
```console
roslaunch fromassignment1.launch
```
3. Launch the gmapping for SLAM:
```console
roslaunch assignment2_exprob gmapping.launch
```
4. Start the move_base for autonomous navigation:
```console
roslaunch assignment2_exprob move_base.launch
```
5. Run the marker publisher node to publish ArUco marker positions:
```console
rosrun aruco_ros marker_publish
```
6. Execute the marker detection script:
```console
rosrun assignment2_exprob detectmarker.py
```
7. Launch the ROSPlan interface:
```console
roslaunch RP_interface RPlaunch.launch
```
8. Start the executor script for handling detected markers and planning:
```console
rosrun assignment2_exprob executor.py
```
