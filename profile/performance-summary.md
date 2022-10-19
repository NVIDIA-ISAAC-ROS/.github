# Isaac ROS Performance Summary

## Results

The performance results of benchmarking the Isaac ROS packages on both Jetson and x86_64 platforms are below:

| Package                                                                                                  | Resolution | AGX Orin CPU                | AGX Orin            | Orin Nano 8GB      | x86_64 w/ RTX 3060 Ti |
| -------------------------------------------------------------------------------------------------------- | ---------- | --------------------------- | ------------------- | ------------------ | --------------------- |
| [AprilTag](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_apriltag)                                       | 720p       | 100 fps <br> 9.7ms          | 248 fps <br> 5.5ms  | 82 fps <br> 14ms   | 600 fps <br> 2ms      |
| [DOPE](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_pose_estimation)                                    | VGA        | N/A                         | 40 fps <br> 30ms    | N/A                | 84 fps <br> 15.4ms    |
| [Freespace](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_proximity_segmentation)                        | 576p       | N/A                         | 1145 fps <br> 1.3ms | 725 fps <br> 2ms   | 1490 fps <br> 0.3ms   |
| [Image compression (H.264)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_compression)                   | 1080p      | 20 fps <br> 49ms            | 170 fps <br> 17.4ms | N/A                | N/A                   |
| [Image decompression (H.264)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_compression)                 | 1080p      | 102 fps (core i7) <br> 29ms | N/A                 | N/A                | 400 fps <br> 2.3ms    |
| [Image detection (person detector)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_object_detection)      | 544p       | N/A                         | 225 fps <br> 7.7ms  | 72 fps <br> 18ms   | 450 fps <br> 3.2ms    |
| [Image segmentation (person detector)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_image_segmentation) | 544p       | N/A                         | 260 fps <br> 3.7ms  | 128 fps <br> 6.7ms | 300 fps <br> 2ms      |
| [Proximity segmentation](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_proximity_segmentation) (DLA)     | 576p       | N/A                         | 62 fps <br> 46ms    | N/A                | N/A                   |
| [Proximity segmentation](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_proximity_segmentation) (GPU)     | 576p       | N/A                         | 81 fps <br> 61ms    | 25 fps <br> 65ms   | 145 fps <br> 386ms    |
| [Rectify](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_image_pipeline)                                  | 1080p      | 231 fps <br> 2.3ms          | 730 fps <br> 1.5ms  | 330 fps <br> 3.1ms | 900 fps <br> 0.4ms    |
| [Stereo disparity (ESS)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_dnn_stereo_disparity)             | 1080p      | N/A                         | 51 fps <br> 17.3ms  | 16 fps <br> 60ms   | 98 fps <br> 7.6ms     |
| [Stereo disparity (SGM)](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_image_pipeline)                   | 540p       | 74 fps <br> 12.5ms          | 144 fps <br> 7.6ms  | 52 fps <br> 20ms   | 380 fps <br> 3.1ms    |
| [VSLAM](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_visual_slam)                                       | 720p       | N/A                         | 250 fps <br> 3.1ms  | 105 fps <br> 10ms  | 265 fps <br> 5.2ms    |

## Methodology

The benchmark performance numbers provided are the maximum sustained framerate for each computational pipeline on each listed platform. Performance measured includes input node → node under performance test → output node where the publishing rate of the input node is autotuned to discover the peak throughput dropping <1% of the frames. Average fps computed over 5 runs, discarding minimum and maximum runs; latency measured at 30fps publishing rate.
