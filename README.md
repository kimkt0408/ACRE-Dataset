# Purdue ACRE Cornfield Dataset

This dataset is designed for evaluating autonomous navigation and crop monitoring systems in cornfields. It was collected using Purdue-AgBot (P-AgBot) at Purdue University’s [Agronomy Center for Research and Education (ACRE)](https://ag.purdue.edu/department/agry/acre/index.html) during the Summer of 2023.

## Overview

- **Contents**: 3D LiDAR, IMU, RTK GPS, wheel encoder measurements.
- **Environments**: Cornfields with varying weather conditions and growth stages.
- **Challenges**: Includes arbitrary occlusions from hanging leaves, and rough terrain.

## Accessing the Dataset

- **Download Dataset**: [Download Link](https://purdue0-my.sharepoint.com/:f:/g/personal/kim3686_purdue_edu/Epm1jo1fP0NDjPju2Hosr5IB2RTKf_Hui_8v6oN-yAAyRg?e=obvB6V)
<!-- - **Research Paper**: [View Paper](https://journals.sagepub.com/doi/abs/10.1177/02783649231215372)
- **Supplementary Material**: [Download Here](https://uofi.box.com/s/cns333ty3t04lib5mjnq16tycxokztp2)
- **Sample Video**: [Watch on YouTube](https://youtu.be/cSIdbHLZzkc) -->

## Data Description

The dataset is organized by GPS availability and collection date. It contains Rosbag (*.bag) files, providing a comprehensive set of sensor measurements. For detailed information on the folder structure and ROS topics included.

### Figure 1. Coordinate frames of our robot system (P-AgBot)


### Figure 2. TF Tree

* [Static trasform information](static_transform.txt)


### Table 1. Information about data folders

| Folder      | Number of Files | Folder Size (GB) |
|-------------|-----------------|------------------|
| with_GPS    | 80              | 584              |
| without_GPS | 2               | 28               |


### Table 2. ROS Topics in Rosbag (.bag) files

| ROS Topic   | Description     | ROS message type |
|-------------|-----------------|------------------|
| /cmd_vel    | Robot linear/angular velocity              | geometry_msgs/Twist              |
| /gps/fix | RTK GPS measurements               | sensor_msgs/NavSatFix               |
| /imu/data | Robot IMU               | sensor_msgs/Imu               |
| /ns1/velodyne_points | Point cloud from a horizontal LiDAR               | sensor_msgs/PointCloud2               |
| /ns2/velodyne_points | Point cloud from a vertical LiDAR               | sensor_msgs/PointCloud2 |
| /odometry/filtered | Filtered odometry from the fusion of wheel encoders and IMU | nav_msgs/Odometry |
| /odometry/filtered | Filtered odometry from the fusion of wheel encoders and IMU | nav_msgs/Odometry |
| /tf | Relationship between sensor coordinate frames | tf2_msgs/TFMessage |

<!-- ### Playing SVO Files (Optional)

For higher resolution images and depth quality:
1. Install the [ZED SDK](https://www.stereolabs.com/developers/release/) (requires CUDA).
2. Install the [ZED ROS Wrapper](https://www.stereolabs.com/docs/ros/).
3. Play SVO files using the ZED ROS Wrapper (instructions in the supplementary material). -->

## Using the Dataset

### Overview

- **Contents**: 3D LiDAR, IMU, RTK GPS, wheel encoder measurements.
- **Environments**: Cornfields with varying weather conditions and growth stages.
- **Challenges**: Includes arbitrary occlusions from hanging leaves, and rough terrain.

### Building Custom ROS Messages

To read custom GPS and motor messages:
1. Download and build the [fpn_msgs](https://uofi.box.com/shared/static/sxfuvw9njpm2e2mbcfncirdxx70kn165.zip) package in your ROS workspace.
2. Build the package with `catkin_make fpn_msgs` and source your workspace.

### Extracting Data from Rosbag Files

Follow the instructions in the supplementary material to extract specific data using the provided Python script.

### Sensor Calibration

Download the [sensor_parameters.txt](sensor_parameters.txt) file for calibration information and robot coordinate frames details.
