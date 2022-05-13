# This builds a docker image from a Dockerfile in the current directory
# The name of the image will become simple-docker
docker build -t ros2-foxy-tutorial-docker .

# Once the image is built, start a container
# The name of the container will be Ros2_Foxy_Docker, while the port mapping will be container
# port https://0.0.0.80 -> mapped to https://localhost:80 (this is the -p flag)
# while the -d flag creates this in "detached mode" it will run in the background
docker run --name Ros2_Foxy_Docker -dp 90:90 ros2-foxy-tutorial-docker

# another useful one is:
# this will clean up the container once it is done doing what it needs to
docker run -dit --rm <image name>

# Using the make commands
make build  # creates a docker image
make run    # creates the container
make bash   # opens a bash shell in the container

# Useful commands:

docker ps -a                          # Will list all containers
docker exec -ti <ContainerName>  bash # Will create a bash instance to explore the container

# Warnings / Errors / etc
1. WARNING: apt get does not have a stable CLI interface. Use with caution in scripts.
   - This just means swap out all the apt calls for apt-get calls


# 
