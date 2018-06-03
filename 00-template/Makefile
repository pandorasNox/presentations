
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

PWD = $(shell pwd)

.PHONY: help
help: ##@other Show this help.
	@perl -e '$(HELP_FUN)' $(MAKEFILE_LIST)

.PHONY: setup
setup: ##@setup sets up all basic stuff for the presentation
	docker build -t reveal-md:2.0.5 docker/reveal-md/

.PHONY: start-talk
start-talk: ##@setup inits talk/slides.
	# $(MAKE) another-make-command
	docker run -it --rm -v $(PWD):/source -p 9999:9999 reveal-md:2.0.5 sh -c "cd /source; reveal-md './slides' --port 9999"

.PHONY: talk-specific-command
talk-specific-command: ##@talk specfiv command for the talk
	$(MAKE) another-make-command
	docker run -it --rm 
