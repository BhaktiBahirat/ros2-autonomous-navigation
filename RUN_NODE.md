Run Navigation Node 🚀

This guide contains all required commands to run the autonomous navigation node using ROS2 Navigation2.

---

Step 1: Source Environment

source /opt/ros/humble/setup.bash
source ~/ros2_ws/install/setup.bash

---

Step 2: Set TurtleBot3 Model (if using TB3)

export TURTLEBOT3_MODEL=burger

---

Step 3: Launch Simulation

Custom Robot:
ros2 launch custom_robot simulation.launch.py

OR TurtleBot3 Simulation:
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py

---

Step 4: Launch Navigation2 Stack

ros2 launch turtlebot3_navigation2 navigation2.launch.py use_sim_time:=True

---

Step 5: Run Waypoint Navigation Node

Direct Python Run:
python3 waypoint_navigation_node/navigator.py

OR as ROS2 Package:
ros2 run <package_name> navigator

---

Step 6: Make Script Executable (if error occurs)

chmod +x waypoint_navigation_node/navigator.py

---

Step 7: Verify Running Nodes

ros2 node list

---

Step 8: Check Topics

ros2 topic list

---

Step 9: Debug Goal Publishing

ros2 topic echo /goal_pose

---

Step 10: TF Check (if robot not moving)

ros2 run tf2_tools view_frames

---

Step 11: Rebuild Workspace (if needed)

cd ~/ros2_ws
colcon build
source install/setup.bash

---

Step 12: Reset Build (if errors)

rm -rf build install log
colcon build

---

Optional: SLAM Mapping

ros2 launch turtlebot3_cartographer cartographer.launch.py use_sim_time:=True

Save map:
ros2 run nav2_map_server map_saver_cli -f my_map

---

Expected Output:

* Simulation launches successfully
* Navigation2 stack runs
* Robot moves autonomously
* Waypoints executed
* Goal reached without RViz

---

Notes:

* Always source before running
* Ensure Navigation2 is active
* Check TF tree (map → odom → base_link)
* Verify correct file paths
