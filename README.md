This repo contains a GitHub workflow that builds binary Debian packages for the [MUL Franka Setup](https://github.com/mul-cps/mul_franka), including the Franka and Orbbec ROS 2 packages. See the [branches](https://github.com/mul-cps/franka-ros-deb-builder/branches) for a target Ubuntu and ROS distribution and follow the instructions there on how to add the Debian repo to your system.

After setting up the repo:
```sh
# Ubuntu 26.04, lyrical
echo "deb [trusted=yes] https://raw.githubusercontent.com/mul-cps/franka-ros-deb-builder/resolute-lyrical-amd64/ ./" | sudo tee /etc/apt/sources.list.d/mul-cps_franka-ros-deb-builder-resolute-lyrical-amd64.list
sudo apt update
```
install the Debian package:
```sh
sudo apt install ros-lyrical-mul-franka-launch
```
and follow the instructions in the OrbbecSDK_ROS2 repo on [installing the udev rules](https://github.com/orbbec/OrbbecSDK_ROS2?tab=readme-ov-file#installation-instructions):
```sh
sudo wget https://raw.githubusercontent.com/orbbec/OrbbecSDK_ROS2/refs/heads/main/orbbec_camera/scripts/99-obsensor-libusb.rules -O /etc/udev/rules.d/99-obsensor-libusb.rules
sudo udevadm control --reload-rules && sudo udevadm trigger
```

Once everything is set up, you can source the base ROS workspace and use the camera driver:
```sh
. /opt/ros/lyrical/setup.bash
ros2 launch orbbec_camera femto_bolt.launch.py
```
