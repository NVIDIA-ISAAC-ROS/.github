# Release Notes

## Isaac ROS 0.20.0 DP (developer preview) October 19, 2022

Packages available as `DP 2 Release` tagged `v0.20.0-dp` on GitHub.

### What's New

Updates including:

- support for [Jetson Orin Nano 8GB](https://developer.nvidia.com/blog/solving-entry-level-edge-ai-challenges-with-nvidia-jetson-orin-nano/)
- [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0) licensing for Isaac ROS repositories
- `isaac_ros_compression` hardware accelerated H.264 encoding/decoding
- `isaac_ros_proximity_segmentation` freespace segmentation based on Bi3D, added Isaac Sim tutorials, added RealSense tutorial
- `isaac_ros_mission_client` VDA5050-compatible Nav2 mission controller, added Isaac Sim tutorial
- `isaac_ros_dnn_stereo_disparity` added Isaac Sim tutorial, added RealSense tutorial
- `isaac_ros_image_pipeline` added Isaac Sim tutorial, added RealSense tutorial

### Limitations

This release has the following known limitations, with workarounds available in the troubleshooting section:

- `isaac_ros_h264_encoder` can become unresponsive when starting a stream after stopping because of a known synchronization bug.

## Isaac ROS 0.11.0 DP (developer preview) September 1, 2022

Packages available as `DP 1.1 Release` tagged `v0.11.0-dp` on GitHub.

### What's New

Updates including:

- support for JetPack 5.0.2
- support for Isaac Sim 2022.1.1
- `isaac_ros_image_pipeline` added image flip node
- `isaac_ros_nvblox` added support for 3D LIDAR input and serialization of maps to file, improved performance
- `isaac_ros_object_detection` accelerated DetectNet inference with NITROS, added Isaac Sim tutorial, improved performance
- `isaac_ros_pose_estimation` accelerated DOPE inference with NITROS
- `isaac_ros_proximity_segmentation` updated Bi3D model, added dynamic disparity level support
- `isaac_ros_visual_slam` updated launch files for Realsense package changes, removed stale dependency on `isaac_ros_image_proc`

### Limitations

This release has the following known limitations, with workarounds available in the troubleshooting section:

- Intel RealSense drivers do not support Humble out-of-the-box (workaround [here](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common/blob/main/docs/troubleshooting.md#realsense-driver-doesnt-work-with-ros2-humble))

### Feature Requests & Issues Addressed

This release contains new features and fixes to address user feedback, including:

- [`isaac_ros_nvblox #13`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nvblox/issues/19), [`#19`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nvblox/issues/19): Feature request: Map serialization/deserialization from file
- [`isaac_ros_nvblox #23`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nvblox/issues/23): Feature request: Demo for using Intel RealSense Cameras with Nvblox
- [`isaac_ros_nvblox #24`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nvblox/issues/24): Feature request: Clear voxels beyond a radius
- [`isaac_ros_common #29`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common/issues/29): Torch unavailable inside container on AGX Orin (kudos to [@bblumberg](https://github.com/bblumberg))
- [`isaac_ros_common #40`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common/issues/40): Docker support for JetPack 5.0.2
- [`isaac_ros_dnn_inference #5`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_dnn_inference/issues/5): ROS Topics can't be viewed from outside container due to UID mismatch (kudos to [@GEngels](https://github.com/GEngels), [@Doch88](https://github.com/Doch88))
- [`isaac_ros_object_detection #8`](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_object_detection/issues/8): Isaac ROS Object Detection doesn't install parameters file (kudos to [@Tristis116](https://github.com/Tristis116))

## Isaac ROS 0.10.1 DP (developer preview) July 12, 2022

Packages available as `DP Release` tagged `v0.10.1-dp` on GitHub.

### What's New

Minor bug fixes and updates including:

- `isaac_ros_apriltag` updated launch file 'max_tags' parameter to default 64
- `isaac_ros_argus_camera` tuned queue sizes
- `isaac_ros_common` add missing dependency on `isaac_ros_apriltag_interfaces`
- `isaac_ros_dnn_stereo_disparity` tuned QoS and queue sizes
- `isaac_ros_image_pipeline` improved frame synchronization
- `isaac_ros_nvblox` fixed integration with Nav2 costmaps on Humble, updated topic names for test rosbag, fixed rosdeps
- `isaac_ros_visual_slam` updated launch files for Realsense package changes, removed stale dependency on `isaac_ros_image_proc`

## Isaac ROS 0.10.0 DP (developer preview) June 30, 2022

Packages available as `DP Release` tagged `v0.10.0-dp` on GitHub.

### What's New

ROS2 Humble release of Isaac ROS with performance boost and new stereo perception functions including:

- packages for ROS2 Humble (Foxy deprecated) on JetPack 5.0.1 DP
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

## Isaac ROS 0.9.3 EA3 (early access) March 23, 2022

Packages available as `EA3 Release` tagged `v0.9.3-ea3` on GitHub.

### What's New

GTC 2022 release of Isaac ROS with new packages for vision based autonomous navigation including:

- packages for ROS2 Foxy on JetPack 4.6.1
- `isaac_ros_visual_slam` upgraded from SVIO as visual odometry source for Nav2 with save and load of feature maps
- `isaac_ros_nvblox` for vision based temporary 3D obstacle map construction in real-time
- `isaac_ros_object_detection` to detect and classify obstacles using DNN detection networks

## Isaac ROS 0.9.1 EA2.1 (early access) Nov 22, 2021

Packages available as `EA2 Release` tagged `v0.9.1-ea2` on GitHub.

### What’s new

Incremental update with fixes and new packages from previous ROSCon 2021 release, including:

- packages for ROS2 Foxy on JetPack 4.6
- support for Isaac Sim 2021.3
- `isaac_ros_pose_estimation` update adding CenterPose DNN for detection of pose
- Isaac SIM <-> Isaac ROS tutorials with Jetson hardware in the loop
- new software license with commercial use grant

## Isaac ROS EA2 (early access)  Oct 20, 2021

### What's New

ROSCon 2021 release of Isaac ROS providing hardware acceleration for autonomous robots with new features including:

- packages for ROS2 Foxy on JetPack 4.6
- `isaac_ros_visual_odometry` providing stereo visual inertial odometry
- `isaac_ros_argus_camera` for hardware accelerated ISP of CSI and GMSL cameras
- `isaac_ros_image_segmentation` for DNN based image segmentation including people detection pre-trained model
- `isaac_ros_pose_estimation` for detection of pose using DOPE DNN
- `isaac_ros_dnn_inference` for TensorRT and Triton inferencing server for DNN processing

## Isaac ROS EA1 (early access)  Aug 11, 2021

### What's New

First release of Isaac ROS providing hardware acceleration for autonomous robots with new features including:

- packages for ROS2 Foxy on JetPack 4.5
- `isaac_apriltag` providing hardware acceleration replacement for `apriltag`
- `isaac_image_proc` providing hardware acceleration replacement for `image_proc`
- `isaac_stereo_image_proc` providing hardware acceleration replacement for `image_proc`
