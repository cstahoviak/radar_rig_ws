# MARBLE RADAR-RIG

This is the top-level catkin workspace for the MARBLE Radar-Rig

To use this workspace, you will need to install [wstool](http://wiki.ros.org/wstool) and [catkin_tools](https://catkin-tools.readthedocs.io/en/latest/installing.html):

```
sudo apt install python-wstool
```

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu `lsb_release -sc` main" > /etc/apt/sources.list.d/ros-latest.list'
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
sudo apt update
sudo apt install python-catkin-tools

```

Next, clone the `radar_rig_ws` catkin workspace and pull the associated packages (listed in `src/.rosinstall`) using wstool:

```
cd <location where you want to put the MARBLE Radar Rig workspace>
git clone https://github.com/cstahoviak/radar_rig_ws.git
cd radar_rig_ws
wstool update -t src

```

Before building the packages in `src`, install the associated dependencies:

```
sudo apt install libceres-dev
sudo apt install ros-melodic-laser-proc
sudo apt install ros-melodic-urg-node
sudo apt install ros-melodic-ddynamic-reconfigure
```

Next, install the RealSense SDK 2.0 by following the [installation instructions](https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md#installing-the-packages)

All packages can now be built. Initialize the catkin workspace and build the associated packages:

```
cd radar_rig_ws
catkin init
catkin build
```

You will want to source `devel/setup.bash` on startup, so run:

```
echo "/home/<user>/<path to radar_rig_ws>/devel/setup.bash" >> ~/.bashrc
```

For example, this might look like:

```
echo "/home/carl/ROS/radar_rig_ws/devel/setup.bash" >> ~/.bashrc
```

All meta launch files associated with the MARBLE Radar Rig can be located at:

```
radar_rig_ws/src/radar_rig/launch
```
