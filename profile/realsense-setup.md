# Isaac ROS Realsense Setup

1. Clone the `librealsense` repo setup udev rules. Remove any connected relasense cameras when prompted:

   ```bash
    cd /tmp && \
    git clone https://github.com/IntelRealSense/librealsense && \
    cd librealsense && \
    ./scripts/setup_udev_rules.sh
    ```

2. Clone the isaac_ros_common and the `ros2-development` branch of the realsense repository:

    ```bash
    mkdir -p ~/workspaces/isaac_ros-dev/src && cd ~/workspaces/isaac_ros-dev/src
    ```

    ```bash
    git clone https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common
    ```

    ```bash
    git clone https://github.com/IntelRealSense/realsense-ros.git -b ros2-development
    ```

3. Plug in your realsense camera before launching the docker container in the next step.
4. Configure the container created by `isaac_ros_common/scripts/run_dev.sh` to include `librealsense`. Create the `.isaac_ros_common-config` file in the `isaac_ros_common/scripts` directory:

    ```bash
    cd ~/workspaces/isaac_ros-dev/src/isaac_ros_common/scripts && \
    touch .isaac_ros_common-config && \
    echo CONFIG_IMAGE_KEY=humble.nav2.realsense > .isaac_ros_common-config
    ```

5. Launch the Docker container using the `run_dev.sh` script:

    ```bash
    cd ~/workspaces/isaac_ros-dev/src/isaac_ros_common && \
      ./scripts/run_dev.sh
    ```

6. At this point, you can check that the realsense camera is connected by running `realsense-viewer`:

   ```bash
   realsense-viewer
   ```

   If you turn on the "Stereo Module" in the GUI, you should see something like the following:

<div align="center"><img src="../resources/isaac_ngc/realsense/realsense_viewer.png" width=800px/></div>

> Note: This tutorial has been tested with a RealSense D455 or D435 connected to a Jetson Orin or Xavier AGX.

> Note: In our testing it was important that the camera had a recent version of the firmware installed.
