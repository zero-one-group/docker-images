DOCKERNAME=01group/node-git
VERSION=20220119

build:
	docker buildx build --platform=linux/amd64 -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
