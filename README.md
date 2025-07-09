```bash
echo "deb [trusted=yes] https://raw.githubusercontent.com/mul-cps/franka-ros-deb-builder/noble-jazzy-arm64/ ./" | sudo tee /etc/apt/sources.list.d/mul-cps_franka-ros-deb-builder-noble-jazzy-arm64.list
echo "yaml https://github.com/mul-cps/franka-ros-deb-builder/raw/noble-jazzy-arm64/local.yaml jazzy" | sudo tee /etc/ros/rosdep/sources.list.d/1-mul-cps_franka-ros-deb-builder-noble-jazzy-arm64.list
```
