
# Setup & Execution Guide ⚙️

---

## 📌 Install ROS2 Humble

Follow official guide:
https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html

---

## 📌 Install Navigation2 (Nav2)

https://navigation.ros.org/getting_started/index.html

---

## 📌 Install TurtleBot3 Packages

https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/

---

## 📌 Install Gazebo

https://gazebosim.org/docs

---

## 🔧 Workspace Setup

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src

git clone https://github.com/your-username/ros2-autonomous-navigation.git

cd ~/ros2_ws
rosdep update
rosdep install --from-paths src --ignore-src -r -y

colcon build
source install/setup.bash
