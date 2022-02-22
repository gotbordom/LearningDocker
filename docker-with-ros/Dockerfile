# pull ros2 foxy image
FROM ros:foxy

# install ros package
RUN apt-get update && apt-get install -y \
      ros-${ROS_DISTRO}-demo-nodes-cpp \
      ros-${ROS_DISTRO}-demo-nodes-py && \
    rm -rf /var/lib/apt/lists/*

# launch ros package example
# CMD ["ros2", "launch", "demo_nodes_cpp", "talker_listener.launch.py"]
CMD ["bash"]
