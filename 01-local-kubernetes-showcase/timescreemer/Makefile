
HELP_FUN = \
	%help; \
	while(<>) { push @{$$help{$$2 // 'options'}}, [$$1, $$3] if /^([a-zA-Z\-]+)\s*:.*\#\#(?:@([a-zA-Z\-]+))?\s(.*)$$/ }; \
	print "usage: make [target]\n\n"; \
	for (sort keys %help) { \
	print "${WHITE}$$_:${RESET}\n"; \
	for (@{$$help{$$_}}) { \
	$$sep = " " x (32 - length $$_->[0]); \
	print "  ${YELLOW}$$_->[0]${RESET}$$sep${GREEN}$$_->[1]${RESET}\n"; \
	}; \
	print "\n"; }

.PHONY: help
help: ##@other Show this help.
	@perl -e '$(HELP_FUN)' $(MAKEFILE_LIST)

.PHONY: docker-compose-up
docker-compose-up: ##@development create + start docker containers
	docker-compose up

.PHONY: minikube-start
minikube-start: ##@setup inits minikube.
	$(MAKE) minikube-init
	$(MAKE) minikube-await

.PHONY: minikube-init
minikube-init: 
	./hack/minikube/start-minikube.sh

.PHONY: minikube-await
minikube-await: 
	./hack/minikube/await-minikube.sh
