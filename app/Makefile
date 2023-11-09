TS ?= $(shell echo `date '+%Y%m%d-%H%M%S'`)
VERSION = v6.3.6
TAG := ${VERSION}-${TS}

build:
	docker build -t push-registry.ke.com/dayu/tools/deepflow-app:${TAG} -f Dockerfile_50 .
	docker push push-registry.ke.com/dayu/tools/deepflow-app:${TAG}
deploy: build
	helm upgrade deepflow -n deepflow /root/yaml/deepflow/deepflow -f /root/yaml/deepflow/values-custom.yaml --set image.app.tag=${TAG}