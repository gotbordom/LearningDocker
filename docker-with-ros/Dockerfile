# pull ros2 foxy image
FROM ros:foxy

# install ros package
RUN apt-get update && apt-get install -y	\
	ros-${ROS_DISTRO}-demo-nodes-cpp	\
	ros-${ROS_DISTRO}-demo-nodes-py		\
	&& rm -rf /var/lib/apt/lists/*		

# install python and python packages
RUN apt-get update && apt-get install -y python3-pip
RUN pip install opencv-python-headless

# install dev tools like vim
RUN apt-get install -y vim

# launch ros package example
# CMD ["ros2", "launch", "demo_nodes_cpp", "talker_listener.launch.py"]
CMD ["bash"]
