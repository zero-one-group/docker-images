DOCKERNAME=01group/flutter-android
VERSION=20220718

build:
	docker build -f --build-arg FLUTTER_VERSION=$(VERSION) Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)

help:
	@echo "'make VERSION=3.3.0' will build flutter version 3.3.0 and docker image_name:3.3.0"