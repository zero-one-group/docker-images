DOCKERNAME=01group/flutter-fastlane
VERSION=3.7.2

build:
	docker build --build-arg FLUTTER_VERSION=$(VERSION) -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)

help:
	@echo "'make VERSION=3.7.2 build' will build flutter version 3.7.2 and docker image_name:3.7.2"