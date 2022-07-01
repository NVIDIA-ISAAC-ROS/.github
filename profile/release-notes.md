# Release Notes
## Isaac ROS DP (developer preview) June 30, 2022
### What's New
ROS2 Humble release of Isaac ROS with performance boost and new stereo perception functions including:
- packages for ROS2 Humble (Foxy deprecated) on Jetpack 5.0.1 DP
- support for Jetson Orin
- support for Isaac Sim 2022.1 *(Isaac SIM 2021.2 is deprecated)*
- `isaac_ros_nitros` implementing type adaptation & type negotiation features new to Humble boosting performance
- `isaac_ros_proximity_segmentation` for stereo vision detection of obstacles during navigation
- `isaac_ros_dnn_stereo_disparity` for stereo vision AI prediction of depth

### Limitations
There are known limitations with this release, documented below which may have additional details for workarounds in the troubleshooting section.
- Isaac SIM 2022.1 released in June 2022 will add support for Humble in September.  Incompatibilities exist performing SIL (software in the loop) simulation with Isaac ROS.
- Realsense drivers as-is do not support Humble, but can be modified to work
- `isaac_ros_nvblox` is untested with Nav2 on Humble
- Removed CenterPose support on Jetson
- `isaac_ros_ess` throws an error if using rosbag as input, and input topics are published after the node is started

## Isaac ROS EA3 (early access) March 23, 2022
### What's New
GTC 2022 release of Isaac ROS with new packages for vision based autonomous navigation including:
- packages for ROS2 Foxy on Jetpack 4.6.1
- `isaac_ros_visual_slam` upgraded from SVIO as visual odometry source for Nav2 with save and load of feature maps
- `isaac_ros_nvblox` for vision based temporary 3D obstacle map construction in real-time
- `isaac_ros_object_detection` to detect and classify obstacles using DNN detection networks

## Isaac ROS EA2.1 (early access) Nov 22, 2021

### What’s new

Incremental update with fixes and new packages from previous ROSCon 2021 release, including:
- packages for ROS2 Foxy on Jetpack 4.6
- support for Isaac Sim 2021.3
- `isaac_ros_pose_estimation` update adding CenterPose DNN for detection of pose
- Isaac SIM <-> Isaac ROS tutorials with Jetson hardware in the loop
- new software license with commercial use grant

## Isaac ROS EA2 (early access)  Oct 20, 2021
### What's New
ROSCon 2021 release of Isaac ROS providing hardware acceleration for autonomous robots with new features including:
- packages for ROS2 Foxy on Jetpack 4.6
- `isaac_ros_visual_odometry` providing stereo visual inertial odometry
- `isaac_ros_argus_camera` for hardware accelerated ISP of CSI and GMSL cameras
- `isaac_ros_image_segmentation` for DNN based image segmentation including people detection pre-trained model
- `isaac_ros_pose_estimation` for detection of pose using DOPE DNN
- `isaac_ros_dnn_inference` for TensorRT and Triton inferencing server for DNN processing

## Isaac ROS EA1 (early access)  Aug 11, 2021
### What's New
First release of Isaac ROS providing hardware acceleration for autonomous robots with new features including:
- packages for ROS2 Foxy on Jetpack 4.5
- `isaac_apriltag` providing hardware acceleration replacement for `apriltag`
- `isaac_image_proc` providing hardware acceleration replacement for `image_proc`
- `isaac_stereo_image_proc` providing hardware acceleration replacement for `image_proc`
