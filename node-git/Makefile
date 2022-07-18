DOCKERNAME=01group/node-git
VERSION=20220718

build:
	docker buildx build --platform=linux/amd64 -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
