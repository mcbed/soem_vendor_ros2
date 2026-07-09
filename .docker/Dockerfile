ARG ROS_DISTRO="jazzy"
FROM ros:${ROS_DISTRO}-ros-base

# soem_vendor_ros2 build dependencies
# ------------------------------------
# ament_cmake_vendor_package is not part of ros-base and is not pulled in by
# rosdep unless explicitly installed here; without it, soem_vendor_ros2 fails
# to configure (find_package(ament_cmake_vendor_package) not found).
RUN apt update && \
    apt install -y --no-install-recommends \
      python3-colcon-common-extensions \
      python3-rosdep \
      python3-vcstool \
      git \
      build-essential \
      cmake \
      ros-${ROS_DISTRO}-ament-cmake-vendor-package \
      ros-${ROS_DISTRO}-ament-lint-auto \
      ros-${ROS_DISTRO}-ament-lint-common && \
    rm -rf /var/lib/apt/lists/*
