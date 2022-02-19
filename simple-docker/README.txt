# This builds a docker image from a Dockerfile in the current directory
# The name of the image will become simple-docker
docker build -t simple-docker .

# Once the image is built, start a container
# The name of the container will be Simple_Instance, while the port mapping will be container
# port https://0.0.0.80 -> mapped to https://localhost:80 (this is the -p flag)
# while the -d flag creates this in "detached mode" it will run in the background
docker run --name Simple_Instance -dp 90:90 simple-docker

# Useful commands:

docker ps                            # Will lost all containers
docker container ls                  # Same as above
docker exec -ti Simple_Instance bash # Will create a bash instance to explore the container
