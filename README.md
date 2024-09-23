# ROS Package: RGB to DRGB to LaserScan Converter

## Description
This ROS package enables the conversion of RGB images to depth images using [Depth Anything V2](https://github.com/DepthAnything/Depth-Anything-V2) and subsequently transforms the depth image into LaserScan data.

## Features Addition
- **SLAM:** Uses an RGB camera for 2D mapping, so no additional **LiDAR** sensor is required.
- **VSLAM:** Uses an RGB camera for visual SLAM, so a **depth camera** is not necessary.
- ..
- ..


## Nodes

- ### RGB to Depth Conversion

**Subscribed Topics:**
- **RGB Image (`sensor_msgs/Image`):**
  - **Topic:** (`/usb_cam/image_raw`)

- **Camera Info (`sensor_msgs/CameraInfo`):**
  - **Topic:** (`/usb_cam/camera_info`)

**Published Topics:**
- **Depth Image (`sensor_msgs/Image`):**
  - **Topic:** (`/depth/image_raw`)

- **Depth Camera Info (`sensor_msgs/CameraInfo`):**
  - **Topic:** (`/depth/camera_info`)

- ### Depth to LaserScan Conversion

**Subscribed Topics:**
- **Depth Image (`sensor_msgs/Image`):**
  - **Topic:** `/depth/image_raw`

- **Camera Info (`sensor_msgs/CameraInfo`):**
  - **Topic:** `/depth/camera_info`

**Published Topics:**
- **Laser Scan (`sensor_msgs/LaserScan`):**
  - **Topic:** `scan`

---
## Installation

### 1. Set up Depth Anything V2

```bash
cd src
git clone https://github.com/DepthAnything/Depth-Anything-V2.git
cd Depth-Anything-V2
pip install -r requirements.txt
mkdir checkpoints
```

Download the small model checkpoint:

### 2. Install USB Camera for ROS Noetic

```bash
sudo apt update
sudo apt install ros-noetic-usb-cam
```

### 3. Install depthimage_to_laserscan Package

```bash
sudo apt install ros-noetic-depthimage-to-laserscan
```

### 4. Run the Project

After completing the installation steps, you can run the project using:

```bash
roslaunch depth_anything_v2 webcam_laser.launch
```

