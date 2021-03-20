# Just a Makefile for manual testing
.PHONY: all

DOCKER_TAG=jenkins4eval/jenkinsfile-runner:golang

all: clean build

clean:
	rm -rf tmp

.PHONY: docker
docker:
	docker build -t $(DOCKER_TAG) .

build: docker

.PHONY: run
run:
	docker run --rm ${DOCKER_RUN_OPTS} \
	    -v $(shell pwd)/demo/simple/:/workspace/ \
	    $(DOCKER_TAG) 

.PHONY: demo
demo:
	docker run --rm ${DOCKER_RUN_OPTS} \
	    -v $(shell pwd)/demo/:/workspace/ \
	    $(DOCKER_TAG)

