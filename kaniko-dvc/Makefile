DOCKERNAME=ghcr.io/zero-one-group/kaniko-dvc
VERSION=1.25.0

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)