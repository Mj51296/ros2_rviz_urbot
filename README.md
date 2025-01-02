###  Currently WORK Under Progress 


# ROS 2 Jazzy Setup for `ros2_rviz_urbot`

This README provides step-by-step instructions for setting up and running the **ros2_rviz_urbot** project on **ROS 2 Jazzy**. Follow these steps to clone the repository, build the workspace, install necessary dependencies, and launch Gazebo, RViz, and MoveIt.

---

## 1. Set Up the ROS 2 Jazzy Environment

Ensure that you are working in the correct ROS 2 Jazzy environment. You need to source the ROS 2 Jazzy setup file in every terminal session where you work on this project. Run the following command:

```bash
source /opt/ros/jazzy/setup.bash
```

---

## 2. Clone the `ros2_rviz_urbot` Repository

Navigate to your workspace's `src` directory and clone the repository:

```bash
cd ~/your_workspace/src

git clone https://github.com/Kaushikrattawa98/ros2_rviz_urbot.git
```

---

## 3. Install Dependencies

Before building the workspace, ensure all dependencies are installed. If any CMake files are missing during the build process, check for specific packages (e.g., `gripper_controllers`) by running:

```bash
rospack list | grep gripper_controllers
```

If the package is not found, install it using the following command:

```bash
sudo apt-get install ros-jazzy-gripper-controllers
```

To install all other necessary dependencies, use `rosdep`:

```bash
rosdep install --from-paths src --ignore-src -r -y
```

---

## 4. Build the Workspace

Navigate to the root of your workspace and build it using `colcon`:

```bash
cd ~/your_workspace

colcon build
```

---

## 5. Source the Workspace

After the build process is complete, source your workspace’s setup file to ensure all environment variables are correctly set:

```bash
source ~/your_workspace/install/setup.bash
```

---

## 6. Run the Launch File

To start Gazebo, RViz, and MoveIt, run the following command:

```bash
ros2 launch running_files all.launch.py
```

---

Follow these steps to set up and run the `ros2_rviz_urbot` project successfully. If you encounter issues, double-check the dependencies and the sourced environment variables.

