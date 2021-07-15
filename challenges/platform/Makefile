PDFS := devops.pdf troubleshooting.pdf

.ALL: help

.PHONY: help
# kudos to https://gist.github.com/prwhite/8168133 for inspiration
help: ## Show this message.
	@echo 'Usage: make [options] [target] ...'
	@echo
	@echo 'Options: run `make --help` for options'
	@echo
	@echo 'Targets:'
	@egrep '^(.+)\:\ ##\ (.+)' ${MAKEFILE_LIST} | column -t -c 2 -s ':#' | sort | sed 's/^/  /'

.PHONY: build
build: ## Build all PDFs.
build: $(PDFS)

%.pdf: %.md
	pandoc --standalone -o $@ $<

.PHONY: install-ubuntu
install-ubuntu: ## Install pandoc toolchain on apt based systems.
	sudo apt install pandoc texlive-latex-base texlive-fonts-recommended texlive-extra-utils texlive-latex-extra
