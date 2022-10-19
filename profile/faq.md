# Frequently Asked Questions

## What is Isaac ROS?

Isaac ROS is a collection of ROS2 packages for making autonomous robots. The Isaac ROS suite has been developed and released by NVIDIA to leverage the power of hardware acceleration on NVIDIA Jetson and discrete GPUs for standard robotics applications.

A summary of all available Isaac ROS packages is available [here](./package-summary.md).

## How can I use a package?

Each Isaac ROS package has a detailed quick start guide in the main-level `README.md` file. Additionally, many Isaac ROS packages include more advanced tutorials, such as camera-to-detection compute graph examples and integration with NVIDIA [Isaac Sim](https://developer.nvidia.com/isaac-sim).

## I have native ROS2 code, will it work with Isaac ROS packages?

Yes. Isaac ROS packages use standard ROS interfaces on input and output topics. Where appropriate, Isaac ROS packages are also designed to be drop-in replacements for the commonly-used, CPU-based ROS implementations familiar to robotics developers.  

## What is NITROS?

NVIDIA Isaac Transport for ROS (NITROS) is an implementation of type adaptation and negotiation that enables Isaac ROS nodes to unlock the full potential of hardware acceleration with zero-copy data transfer from node to node. Traditional ROS communication requires that all messages are serialized by the CPU at every node interchange, but NITROS allows compatible nodes to eliminate unnecessary GPU-to-CPU copies and thus achieve better performance.

A more detailed explanation of NITROS is available [here](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nitros).

## What should I do if I run into a problem?

To report issues, you can make a post on the [NVIDIA Isaac ROS Developer Forum](https://forums.developer.nvidia.com/c/agx-autonomous-machines/isaac/isaac-ros/600), or raise a GitHub Issue on a specific [Isaac ROS repository](https://github.com/NVIDIA-ISAAC-ROS/).
