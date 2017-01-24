BUILD_DIR := build
SRC_DIR := src

DOCKER_BUILDER := gobgp-alpine-builder
DOCKER_BUILDER_CMD := docker run --rm -ti \
	-v $(PWD)/$(BUILD_DIR):/go/bin \
	-v $(PWD)/$(SRC_DIR):/go/src \
	$(DOCKER_BUILDER)

TAG := radhus/gobgp-alpine:latest

build: builder
	docker build -t $(TAG) .

builder:
	docker build -t $(DOCKER_BUILDER) -f Dockerfile.build .
	mkdir -p $(BUILD_DIR) $(SRC_DIR)
	$(DOCKER_BUILDER_CMD) go get -u github.com/osrg/gobgp/gobgpd
	$(DOCKER_BUILDER_CMD) go get -u github.com/osrg/gobgp/gobgp

