DOCKERNAME=01group/node-ssh
VERSION=20220122

build:
	docker buildx build --platform=linux/amd64 -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
