# Use-Turtlebot3-with-SLAM-approach-to-create-and-save-a-map
## step1: Install Dependent ROS Packages
```
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
$sudo apt install ros-noetic-hls-lfcd-lds-driver
$ sudo apt install ros-noetic-dynamixel-sdk
$ sudo apt install ros-noetic-turtlebot3-msgs
$ mkdir -p ~/catkin_ws/src
$cd catkin_ws/src
$git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.get
$git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations
https://user-images.githubusercontent.com/79949101/183310478-6a32c854-4bb5-4b8d-8ec9-e5051e4e2dc9.mp4
$cd ~/catkin_ws &&catkin_make
```

## step2: Operate Gazebo & Teleop Turtlebot 3
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
$export TURTLEBOT3_MODEL=burger
$roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

## step3: SLAM & Save the map
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch
$ export TURTLEBOT3_MODEL=burger
$roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
$ rosrun map_server map_saver -f ~/map
```
<img width="644" alt="image" src="https://user-images.githubusercontent.com/107959289/184537902-8bc3d79e-6a0a-4842-bc4b-f6040e116bee.png">

## step4: Launch Navigation
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml

```
## step5: Click the 2D Pose Estimate button in the RViz menu
<img width="808" alt="image" src="https://user-images.githubusercontent.com/107959289/184543533-28352999-968d-489d-906a-532626d836bf.png">

## the reviewer

https://youtu.be/ji2kQXgCjeM
https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/2w
