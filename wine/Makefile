# References:
# 	http://boundedinfinity.github.io/2016/05/using-makefiles-with-docker/

# Define tag name for the DOcker image
tag-name = docker-wine

.PHONY: list build run del-image


list:
	@grep '^[^#[:space:]].*:' Makefile | grep -v ':=' | grep -v '^\.' | sed 's/:.*//g' | tr -d ':' | sort


build: ## Build the container using the Dockerfile in current directory
	docker build -t $(tag-name) .


run:
	docker run --rm -it $(tag-name)


del-image:
	docker image rm $(tag-name)
