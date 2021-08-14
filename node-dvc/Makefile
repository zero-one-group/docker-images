DOCKERNAME=zeroonetechnology/node-dvc
VERSION=20210814

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
