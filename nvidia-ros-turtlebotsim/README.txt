There is a lot to this learning directory from the others.

1. This shows how we can create images ontop of images we already made.
   a. This will requrie a subtle change to building a docker image by changing the dockerfile names
   b. This will help me contain each building block for potentail testing in layers
2. This wiill also demonstrate how to include nvidia into a project if the project has GPUs available
3. This will also show how we can mount a directory location to allow for development of code without
   having to rebuild / run the docker files.
   a. Note - C++ development, and other compiled languages require compiling the exe's inside the
      Docker container, not just in the mounted location.

4. Bringing in OpenCV and stereo calibration

References used:
1. https://roboticseabass.com/2021/04/21/docker-and-ros/ - Used for the main docker-ization and sim
2.                                                       - Used for opencv and stereo learning
