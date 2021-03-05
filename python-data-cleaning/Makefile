DOCKERNAME=zeroonetechnology/python-data-cleaning
VERSION=20210305

build:
	docker build -f Dockerfile -t $(DOCKER_NAME):latest .

push: build
	docker push $(DOCKERNAME):$(VERSION)
