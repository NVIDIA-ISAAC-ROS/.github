# Isaac ROS HAWK Setup

Leopard Imaging's [HAWK](https://www.leopardimaging.com/li-ar0234cs-stereo-gmsl2-hawk/) camera is a popular choice of stereo camera for use with the Isaac ROS ecosystem of packages. This document details important setup instructions for configuring the HAWK camera with Isaac ROS.

> **Note:** For best results, please ensure that the camera's firmware has been updated.

## Jetson Platforms

### Camera Configuration

The HAWK camera should be connected to your Jetson via a GMSL expansion board. For example, if working with AGX Orin, see [here](https://www.leopardimaging.com/product/accessories/adapters-carrier-boards/e3653-a03/). Please contact your hardware vendor for assistance.

### IMU Configuration

In order to achieve the target sensor update frequencies for the HAWK's built-in IMU, certain registers on the Jetson device must be set appropriately.

1. Identify the GPIO pins used for connecting the accelerometer and gyroscope to your Jetson. The specific correspondence between physical pin and pin number can be found using the pinmux table for your specific Jetson device, available [here](https://developer.nvidia.com/embedded/downloads#?search=pinmux).

2. Identify the corresponding register address block for those GPIO pins, based on the corresponding pad controller. The technical reference manual for your specific Jetson device can be found [here](https://developer.nvidia.com/embedded/downloads#?search=trm).
    
    For example, on a Jetson AGX Orin-series device, GPIO pins 8 and 9 in the Always On Hypervisor (AO_HV) group are located under `PADCTL_A15`, with memory block starting at `0x0c303000`.

3. Within the technical reference manual, find the detailed explanation of the pad controller to GPIO offset addresses. Identify the specific offset address to index into the relevant pins.
    
    Continuing the previous example, the two pins referenced above have offsets of `0x00` off of the `0x0c303000` base address. Since the pins in this example are at indices 8 and 9, they have a further offset of `8 * 8 = 64 = 0x40` and `8 * 9 = 72 = 0x48`, respectively.

4. Within the technical reference manual, find the detailed explanation of the GPIO registers. Identify the specific bit indices for setting the pullup/pulldown state to pullup. Write a pair of bytes to the previously-determined address, setting the appropriate bit while preserving the values of the other bits. This can be accomplished using `devmem2` or a similar tool.

    Finishing the example, if the current register settings for pin 8 are `0xC058` but the lower 4 bits must be set to `0b0000` to set the pullup state, the correct command would be:

    ```bash
    sudo devmem2 0x0c303040 w 0xC050
    ```

    Correspondingly, if the current register settings for pin 9 are `0xD054`, setting the lower 4 bits to `0b0000` is accomplished with the following command:

    ```bash
    sudo devmem2 0x0c303048 w 0xD050
    ```

## x86 Platforms

No special setup is required on x86 platforms.
