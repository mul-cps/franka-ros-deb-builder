This repo contains a GitHub workflow that builds binary Debian packages for the [MUL Franka Setup](https://github.com/mul-cps/mul_franka), including the Franka and Orbbec ROS 2 packages. See the [branches](https://github.com/mul-cps/franka-ros-deb-builder/branches) for a target Ubuntu and ROS distribution and follow the instructions there on how to add the Debian repo to your system.

After setting up the repo, install the Debian packages:
```sh
sudo apt update
sudo apt install ros-jazzy-mul-franka-launch ros-jazzy-mul-franka-description ros-jazzy-orbbec-camera ros-jazzy-orbbec-description
```
and follow the instructions in the OrbbecSDK_ROS2 repo on [installing the udev rules](https://github.com/orbbec/OrbbecSDK_ROS2?tab=readme-ov-file#installation-instructions):
```sh
sudo wget https://raw.githubusercontent.com/orbbec/OrbbecSDK_ROS2/refs/heads/main/orbbec_camera/scripts/99-obsensor-libusb.rules -O /etc/udev/rules.d/99-obsensor-libusb.rules
sudo udevadm control --reload-rules && sudo udevadm trigger
```

Once everything is set up, you can source the base ROS workspace and use the camera driver:
```sh
. /opt/ros/jazzy/setup.bash
ros2 launch orbbec_camera femto_bolt.launch.py
```
