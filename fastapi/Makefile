DOCKERNAME=zeroonetechnology/fastapi-firebase-weasyprint
VERSION=20201216

build:
	docker build -f Dockerfile -t $(DOCKERNAME):$(VERSION) .

push: build
	docker push $(DOCKERNAME):$(VERSION)
