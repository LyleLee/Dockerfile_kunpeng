imageName="lixianfadocker/ubuntu_dev"

all:
	docker build \
		--build-arg USER_ID=$(shell id -u) \
		--build-arg GROUP_ID=$(shell id -g) \
		-t ${imageName} .


arch:
	docker buildx build --platform linux/amd64,linux/arm64 --push \
		--build-arg USER_ID=$(shell id -u) \
		--build-arg GROUP_ID=$(shell id -g) \
		-t ${imageName} .
