![task 2 -- p1](https://user-images.githubusercontent.com/109856025/182835341-14f641f7-b277-422e-8c67-767e7faad009.png)
# task-2-

After downloading ROS software in this task we'll be downloading the Arm package that will allow us to control the physical arm.
Following the steps bellow we will be able to achive that:

sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

sudo apt-get update

In the next step i faced an issue with installing ros noetic because it is not compatible with ubuntu 20.04 so instead i have installed ros kinetic:
sudo apt-get install ros-kinetic-desktop-full

apt-cache search ros-kinetic

echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential

sudo apt install python-rosdep

sudo rosdep init

rosdep update

sudo apt-get install ros-noetic-catkin

mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/

catkin_make

cd ~/catkin_ws/src

git clone https://github.com/smart-methods/arduino_robot_arm.git 

cd ~/catkin_ws

rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-kinetic-moveit

sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

sudo nano ~/.bashrc

In the last step i have modefied the source file to fit my system:

(source /home/9six1/catkin_ws/devel/setup.bash)

Finally we launch the Arm controller with the following command:
roslaunch robot_arm_pkg check_motors.launch
