# Isaac ROS RealSense Setup

## Camera Compatibility

| RealSense Model | Supported? |
| --------------- | ---------- |
| D455            | &check;    |
| D435i           | &check;    |
| D415            | &cross;    |

> **Note:** For best results, please ensure that the camera's firmware has been updated.

## Setup Instructions

> **Note:** This tutorial assumes that you have set up your development environment by following the instructions [here](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common/blob/main/docs/dev-env-setup.md).

1. Clone the `librealsense` repo setup udev rules. Remove any connected RealSense cameras when prompted:

    ```bash
    cd /tmp && \
    git clone https://github.com/IntelRealSense/librealsense && \
    cd librealsense && \
    ./scripts/setup_udev_rules.sh
    ```

2. Clone the isaac_ros_common and the `4.51.1` release of the `realsense-ros` repository:

    > Note: `${ISAAC_ROS_WS}` is defined to point to either `/ssd/workspaces/isaac_ros-dev/` or `~/workspaces/isaac_ros-dev/`.

    ```bash
    cd ${ISAAC_ROS_WS}/src
    git clone https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common
    git clone https://github.com/IntelRealSense/realsense-ros.git -b 4.51.1
    ```

3. Plug in your RealSense camera before launching the docker container in the next step.

4. Configure the container created by `isaac_ros_common/scripts/run_dev.sh` to include `librealsense`. Create the `.isaac_ros_common-config` file in the `isaac_ros_common/scripts` directory:

    ```bash
    cd ${ISAAC_ROS_WS}/src/isaac_ros_common/scripts && \
      touch .isaac_ros_common-config && \
      echo CONFIG_IMAGE_KEY=ros2_humble.realsense > .isaac_ros_common-config
    ```

5. Launch the Docker container

    ```bash
    cd ${ISAAC_ROS_WS}/src/isaac_ros_common && \
      ./scripts/run_dev.sh ${ISAAC_ROS_WS}
    ```

    This will rebuild the container image using `Dockerfile.realsense` in one of its layered stage. It will take some time for rebuilding.

6. Once container image is rebuilt and you are inside the container, you can run `realsense-viewer` to check that the RealSense camera is connected.

   ```bash
   realsense-viewer
   ```

   If you turn on the "Stereo Module" in the GUI, you should see something like the following:

<div align="center"><img src="../resources/isaac_ngc/realsense/realsense_viewer.png" width=800px/></div>
