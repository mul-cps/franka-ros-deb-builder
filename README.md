```bash
echo "deb [trusted=yes] https://raw.githubusercontent.com/mul-cps/franka-ros-deb-builder/orbbec_debs/ ./" | sudo tee /etc/apt/sources.list.d/mul-cps_franka-ros-deb-builder.list
echo "yaml https://github.com/mul-cps/franka-ros-deb-builder/raw/orbbec_debs/local.yaml jazzy" | sudo tee /etc/ros/rosdep/sources.list.d/1-mul-cps_franka-ros-deb-builder.list
```
