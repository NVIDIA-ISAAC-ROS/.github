# Isaac ROS Performance Summary
The performance results of benchmarking the Isaac ROS packages on both Jetson AGX and x86_64 platforms are below: 

| Package                                                                                                  | Resolution | [NITROS](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nitros) Accelerated | AGX Orin | AGX Xavier | x86_64 w/ RTX 3060 Ti |
| -------------------------------------------------------------------------------------------------------- | ---------- | -------------------------------------------------------------------------- | -------- | ---------- | --------------------- |
| [AprilTag](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_apriltag)                                       | 720p       | &#10004;                                                                   | 260 fps  | 150 fps    | 600 fps               |
| [DOPE](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_pose_estimation)                                    | VGA        | &#10004;                                                                   | 43 fps   | 12.5 fps   | 90 fps                |
| [Detectnet](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_object_detection)                              | 544p       | &#10004;                                                                   | 104 fps  | 79 fps     | 104 fps               |
| [Image segmentation (person detector)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_image_segmentation) | 544p       | &#10004;                                                                   | 325 fps  | 208 fps    | 452 fps               |
| [Proximity segmentation](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_proximity_segmentation) (DLA)     | 576p       | &#10004;                                                                   | 62 fps   | 33 fps     | N/A                   |
| [Stereo disparity (ESS)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_dnn_stereo_disparity)             | 1080p      | &#10004;                                                                   | 51 fps   | 24 fps     | 118 fps               |
| [Stereo disparity (SGM)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_image_pipeline)                   | 540p       | &#10004;                                                                   | 166 fps  | 80 fps     | 433 fps               |
