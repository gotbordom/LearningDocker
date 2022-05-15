# Leaving space for globals if needed, might one day
CONTAINER_NAME	= development # TODO (AT) this will likely change when I implement ROS_EXE's todo
IMAGE		= gotbordom-racer
PATH_TO_ROS	:= TODO # TODO (AT) run a find ... or something
ROS_EXE		:= TODO # TODO (AT) change this as I am figuring out what I want actually always running?
		   # should only ever be one application.... probably a launch file, or perhaps this
		   # will get converted later into the docker-up where many containers each running a
		   # single node will get run.
REGISTRY	= ros2-foxy
# fine repo, not the := will define this the first time it is seen.
REPOS_DIR	:= $(shell if [ -d ~/repos ]; then echo ~/repos; else echo ~; fi)
VERSION_TAG	= 0.1


# This will print exactly as formated
# TODO (AT) - add what each does not just what the targets are....
define help-text
	Targets:
	bash				...
	build				...
	docker-up                       TODO (AT) - the goal here is to not have to rebuild containers alot
	docker-down                     TODO (AT) - see docker-up
	help				...
	run				...
	stop				...
endef



.PHONY: help
help:
	@: $(info $(help-text))


.PHONY: bash
bash:
	@docker exec -it ${CONTAINER_NAME} bash;


# TODO (AT) - Might need ssh flag encase I want to clone my own ssh repo
.PHONY: build
build:
	docker build -t ${REGISTRY}/${IMAGE}:${VERSION_TAG} .

# TODO (AT) - Not sure I really need port, but likely will if I want multiple ros nodes talking
.PHONY: run
run:
	@docker run	-d -it								\
			-v ${REPOS_DIR}:/repos:Z					\
	                -p 1080:1080							\
			--name ${CONTAINER_NAME} ${REGISTRY}/${IMAGE}:${VERSION_TAG}	\
			bash #${PATH_TO_ROS}/${ROS_EXE} for now we will be using run as a dev container.

.PHONY: stop
stop:
	if [ "$$(docker ps -a -q -f name=${CONTAINER_NAME})" != "" ];			\
	then 										\
		docker stop ${CONTAINER_NAME} && docker rm -f ${CONTAINER_NAME};	\
	fi

