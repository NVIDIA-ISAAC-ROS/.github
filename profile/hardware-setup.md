# Isaac ROS Hardware Setup

## Compute

### Discrete GPU

1. Prepare a NVIDIA-powered platform with the following min specs:
    * 16 GB general RAM
    * Discrete NVIDIA GPU with the following specs:
        * supports CUDA 11.7 with Volta or newer
        * minimum 8GB of VRAM and recommended 12GB+

### Jetson Platform

1. Install Jetpack using the steps found [here](https://docs.nvidia.com/jetson/jetpack/install-jetpack/index.html).
2. After bootup confirm that you have installed `Jetpack 5.0.2` by running the following command. The output should have the terms `R35 (release), REVISION: 1.0`.

    ```bash
    cat /etc/nv_tegra_release
    ```

3. Run the following command to set the GPU and CPU clock to max. See [Maximizing Jetson Orin Performance](https://docs.nvidia.com/jetson/archives/r35.1/DeveloperGuide/text/SD/PlatformPowerAndPerformance/JetsonOrinNxSeriesAndJetsonAgxOrinSeries.html?highlight=maxn#maximizing-jetson-orin-performance) for more details:

    ```bash
    sudo /usr/bin/jetson_clocks
    ```

4. Run the following command to set the to power to MAX settings. See [Power Mode Controls](https://docs.nvidia.com/jetson/archives/r35.1/DeveloperGuide/text/SD/PlatformPowerAndPerformance/JetsonOrinNxSeriesAndJetsonAgxOrinSeries.html?highlight=maxn#power-mode-controls) for more details:

    ```bash
    sudo /usr/sbin/nvpmodel -m 0
    ```

## Sensors

### RealSense

Follow the instructions in the [RealSense setup tutorial](https://github.com/NVIDIA-ISAAC-ROS/.github/blob/main/profile/realsense-setup.md).
