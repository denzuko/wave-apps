SHELL      := bash
PYTHON     := python3

.DEFAULT_GOAL := help

venv:
	$(PYTHON) -m venv venv

.PHONY: setup
setup: | venv ## Setup a project
	./venv/bin/python -m pip install -U pip
	./venv/bin/python -m pip install -r requirements.txt

.PHONY: run
run: ## Run the App (run `make setup` first)
	./venv/bin/python script.py

.PHONY: clean
clean: ## Remove all files produced by `make`
	rm -rf venv

.PHONY: help
help: ## List all make tasks
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
