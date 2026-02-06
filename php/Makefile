SHELL=/bin/bash
DOCKER_COMPOSE_COMMAND=docker compose

.PHONY: build
build:
	$(DOCKER_COMPOSE_COMMAND) build --no-cache

.PHONY: up
up:
	$(DOCKER_COMPOSE_COMMAND) up -d

.PHONY: down
down:
	$(DOCKER_COMPOSE_COMMAND) down --remove-orphans

.PHONY: rm_image
rm_image:
	docker image prune -af

.PHONY: bash
bash:
	$(DOCKER_COMPOSE_COMMAND) exec app bash
