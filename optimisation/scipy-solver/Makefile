DOCKERNAME=zeroonetechnology/optimisation-scipy-solver
VERSION=20201103

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
