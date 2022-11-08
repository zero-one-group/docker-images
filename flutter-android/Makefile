DOCKERNAME=01group/flutter-android
VERSION=3.3.7

build:
	docker build --build-arg FLUTTER_VERSION=$(VERSION) -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)

help:
	@echo "'make VERSION=3.3.7 build' will build flutter version 3.3.7 and docker image_name:3.3.7"
