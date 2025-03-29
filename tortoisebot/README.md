# Tortoisebot ROS2 Humble Release

![TortoiseBot Banner](https://github.com/rigbetellabs/tortoisebot_docs/raw/master/imgs/packaging/pack_front.png)

<div align="center">

![stars](https://img.shields.io/github/stars/rigbetellabs/tortoisebot?style=for-the-badge)
![forks](https://img.shields.io/github/forks/rigbetellabs/tortoisebot?style=for-the-badge)
![watchers](https://img.shields.io/github/watchers/rigbetellabs/tortoisebot?style=for-the-badge)
![repo-size](https://img.shields.io/github/repo-size/rigbetellabs/tortoisebot?style=for-the-badge)
![contributors](https://img.shields.io/github/contributors/rigbetellabs/tortoisebot?style=for-the-badge)

</div>

<p align="center">
<a href="#connect-with-us">Connect with Us</a> • 
<a href="#installation">Installation</a> • 
<a href="#setup">Setup</a> • 
<a href="#demos">Demos</a>
</p>

## Connect with Us

<div align="center">

[![Website](https://img.shields.io/website?down_color=lightgrey&down_message=offline&label=Rigbetellabs%20Website&style=for-the-badge&up_color=green&up_message=online&url=https%3A%2F%2Frigbetellabs.com%2F)](https://rigbetellabs.com/)
[![Discord](https://img.shields.io/discord/890669104330063903?logo=Discord&style=for-the-badge)](https://rigbetellabs.com/discord)
[![Youtube](https://img.shields.io/youtube/channel/subscribers/UCfIX89y8OvDIbEFZAAciHEA?label=YT%20Subscribers&style=for-the-badge)](https://www.youtube.com/channel/UCfIX89y8OvDIbEFZAAciHEA)
```
cd ~/your workscpace
colcon build
```
## 1.2 Clone this repo 
Make sure you clone the repo in your robot and your remote PC 
```
git clone -b ros2-humble https://github.com/rigbetellabs/tortoisebot.git
```
```
cd ~/your workscpace
colcon build
```
# 2. Setup

- Run bringup.launch.py to only spawn the robot
- Run autobringup.launch.py to spawn the robot with navigation and slam/localization
- Launch the files with use_sim_time:=False when working on real robot

### 2.1 Launching the robot

```
ros2 launch tortoisebot_bringup autobringup.launch.py use_sim_time:=True exploration:=True
```
- exploration:=False for passed a saved map to navigation

### 2.2 Launch files for reference
#### SLAM
- cartographer.launch.py
#### Navigation
- navigation.launch.py
#### Rviz
- rviz.launch.py
#### Gazebo
- gazebo.launch.py

### 2.3 Remote PC

While performing colcon build on remote-pc please add the below to ignore `ydlidar_sdk, ydlidar_ros2_driver, v4l2_camera` since lidar will not be connected to remote-pc.

```
colcon build --packages-ignore ydlidar_sdk ydlidar_ros2_driver v4l2_camera
```

# 3. Demos

<!-- Simulation | Visualisation of Sensors (Lidar, Odometery, Camera) 
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/rigbetellabs/tortoisebot_docs/master/imgs/tortoiseBot_demo/002.png) |![](https://raw.githubusercontent.com/rigbetellabs/tortoisebot_docs/master/imgs/tortoiseBot_demo/005.png) 

Teleop |  Mapping | Navigation 
:-------------------------:|:-------------------------:|:-------------------------: 
![](https://raw.githubusercontent.com/rigbetellabs/tortoisebot_docs/master/imgs/tortoiseBot_demo/007.png) |  ![](https://raw.githubusercontent.com/rigbetellabs/tortoisebot_docs/master/imgs/tortoiseBot_demo/006.png) | ![](https://raw.githubusercontent.com/rigbetellabs/tortoisebot_docs/master/imgs/tortoiseBot_demo/010.png) -->

# The TortoiseBot 🐢🤖

The ReadMe is divided into several sections as per different topics and is constantly been updated and maintained with new updates by our talented and dedicated 👥 Team at RigBetel Labs LLP. So don't forget to often come here and check on it for the latest and greatest software updates, projects & skills for your TortoiseBot. Also don't forget to 🌟 Star this repository on top-right corner of the screen to show your 💖 Love and Support 🤗 for our Team. 🤩 It will make us happy and encourage us to make and bring more such projects for you. 😍 Click [here](https://github.com/rigbetellabs/tortoisebot/wiki/1.-Getting-Started) to get started.

1. [Getting Started](https://github.com/rigbetellabs/tortoisebot/wiki/1.-Getting-Started)
2. [Hardware Assembly](https://github.com/rigbetellabs/tortoisebot/wiki/2.-Hardware-Assembly)
3. [TortoiseBot Setup](https://github.com/rigbetellabs/tortoisebot/wiki/3.-TortoiseBot-Setup)
4. [Server PC Setup](https://github.com/rigbetellabs/tortoisebot/wiki/4.-Server-PC-Setup)
5. [Running Demos](https://github.com/rigbetellabs/tortoisebot/wiki/5.-Running-Demos)

[Join](https://discord.gg/qDuCSMTjvN) our community for Free. Post your projects or ask questions if you need any help.


## TortosieBot is sourced, assembled, made & maintained by our team 🧑🏻‍🤝‍🧑🏻 at<br>

RigBetel Labs LLP®, Charholi Bk., via. Loheagaon, Pune - 412105, MH, India 🇮🇳<br>
🌐 [RigBetelLabs.com](https://rigbetellabs.com) 📞 [+91-8432152998](https://wa.me/918432152998) 📨 getintouch.rbl@gmail.com , info@rigbetellabs.com <br>
[LinkedIn](http://linkedin.com/company/rigbetellabs/) | [Instagram](http://instagram.com/rigbetellabs/) | [Facebook](http://facebook.com/rigbetellabs) | [Twitter](http://twitter.com/rigbetellabs) | [YouTube](https://www.youtube.com/channel/UCfIX89y8OvDIbEFZAAciHEA) | [Discord Community](https://discord.gg/qDuCSMTjvN)



# Workspace Setup

## Create ROS2 Workspace
```bash
# Create and navigate to workspace
mkdir -p ~/ROS_WS
cd ~/ROS_WS

# Clone repository
git clone -b ros2-humble https://github.com/rigbetellabs/tortoisebot.git
mv tortoisebot/* src/

# Build workspace
colcon build
```

## Troubleshooting Build Issues

If you encounter build errors, try these steps in order:

1. Rebuild workspace:
```bash
colcon build
```

2. Clean and rebuild:
```bash
rm -rf build/ install/ log/
colcon build
```

3. Build YDLidar SDK manually:
```bash
cd ~/ROS_WS/src/YDLidar-SDK
mkdir -p build && cd build
cmake ..
make -j$(nproc) 
sudo make install
```

4. Return to workspace root and rebuild:
```bash
cd ~/ROS_WS
colcon build
```

sudo apt install ros-humble-vision-opencv ros-humble-cv-bridge ros-humble-image-transport

ros2 lifecycle set /amcl configure
ros2 lifecycle set /amcl activate


sudo apt install ros-humble-imu-tools ros-humble-imu-complementary-filter ros-humble-robot-localization

ros2 run vins vins_node src/vins-fusion/config/raspicam/raspicam_mono_imu.yaml

rosrun loop_fusion loop_fusion_node ~/FrostHack/src/vins-fusion/config/raspicam/raspicam_mono_imu.yaml