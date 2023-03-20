# VR4_Robotics
This repository is the project of virtual reality for robotics course.
## Quick Start
### Step 1:
Open PowerShell and run the ubuntu 20.04
```bash
wsl --distribution Ubuntu-20.04
```
### Step 2: Set Desktop GUI
Follow [link](https://hub.tcno.co/windows/wsl/desktop-gui/) to setup desktop GUI
Start RDP with
```bash
sudo /etc/init.d/xrdp start
```
Now, open Remote Desktop on your Windows host machine, and connect to localhost:3390
### Step 3: 
Run Airsim on Windows and ROS wrapper on WSL 2
```bash
export WSL_HOST_IP=$(cat /etc/resolv.conf | grep nameserver | awk '{print $2}')
```
### Step 4:
Launch rosnodes 
```bash
source devel/setup.bash
```
```bash
roslaunch airsim_ros_pkgs airsim_node.launch output:=screen host:=$WSL_HOST_IP
```
```bash
roslaunch airsim_tutorial_pkgs front_stereo_and_center_mono.launch
```
### Step 5:
Now open .sln file with visual studio 2022 and open project file and press F5 to run. This will launch the envoronment in unreal engine 
### Step 6: 
Press play and this will start the simulation with drone
### Step 7:
Clone [this](https://github.com/DarekLin/AS_RoS_Teleop.git) repository as it contains the package to teloperate drone in the environment. 
Now launch airsim_teleop to control the drone to teleoperate in the environment 
```bash
rosrun airsim_teleop teleop_twist_keyboard2.py
```
