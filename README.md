# Controlling-the-robot-arm-by-joint-state-publisher-and-Movit-and-kinematics
Robot-Arm-Control-with-Joint-State-Publisher-and-Movit typically refers to a framework os setup used in robotics to control a robyic arm.


Controlling the robot arm by joint_state_publisher

1-Prerequisites:

Source of the ROS environment:

    source /opt/ros/noetic/setup.bash

Creat a ROS workspace:

    mkdir -p ~/catkin_ws/src cd ~/catkin_ws/ catkin_make

Source the workspace:

source devel/setup.bash echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc

2-Install the Package"arduino_robot_arm"

cd ~/catkin_ws/src

sudo apt install git

git clone https://github.com/smart-methods/arduino_robot_arm

Install all the dependencies

cd ~/catkin_ws

rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-noetic-moveit

sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui

sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control

Compile the package

catkin_make

Controlling the motors joint_state_publisher:

    roslaunch robot_arm_pkg check_motors.launch

    rostopic echo /joint_states

    cd ~/catkin_ws/src/arduino_robot_arm/robot_arm_pkg/scripts sudo chmod +x joint_states_to_gazebo.py

    roslaunch robot_arm_pkg check_motors_gazebo.launch rosrun robot_arm_pkg joint_states_to_gazebo.py

![png](https://github.com/user-attachments/assets/06cea7fb-04f2-4a12-b904-e1127b60eb0c)
![ (2)](https://github.com/user-attachments/assets/5ded36db-ecc4-4ccb-894a-f52a8a403cee)
![-](https://github.com/user-attachments/assets/493cc8ab-a1c0-4f1e-9cd9-ddd1afd4df6d)

