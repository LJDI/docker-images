VERSION ?= 0.60.0
TARGETPLATFORM ?=

frps:
docker build -t zhimingsui/frps --build-arg VERSION=$(VERSION) --build-arg TARGETPLATFORM=$(TARGETPLATFORM) --build-arg FILENAME=frps .

frpc:
docker build -t zhimingsui/frpc --build-arg VERSION=$(VERSION) --build-arg TARGETPLATFORM=$(TARGETPLATFORM) --build-arg FILENAME=frpc .

