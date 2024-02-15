.DEFAULT_GOAL := help

.PHONY: help
help:
	@./help.sh $(MAKEFILE_LIST)

.PHONY: test
test:## Runs pytest unit test for python and writes HTML report in /docs
	poetry run pytest --html=docs/test_python_functions.html --self-contained-html #--css=pyproject/src/testing/stylesheet.css

.PHONY: unittest
unittest:## Runs pytest unit test for python and writes HTML report in /docs
	python -m unittest discover -s tests -p "*_test.py"

.PHONY: clean
clean:## Remove all temporary and compiled Python files
	find . -type f -name "*.py[co]" -delete
	find . -type d -name "__pycache__" -delete
	rm -rf .pytest_cache

.PHONY: setup
setup:## Setup packages and prepare environment
	@echo "Installing poetry..."
	pip3 install poetry

	@echo -e "\033[36m Installing packages...\e[0m"
	poetry install

	@echo -e "\033[36m Succesfully installed packages \e[0m"

.PHONY: update_requirements
update_requirements:## Update all packages
	poetry update

.PHONY: sync_packages
sync_packages:## Update environment packages to match poetry.lock
	poetry install --sync

.PHONY: update_lock
update_lock:## updates lock based on toml file and installs
	poetry lock --no-update
	poetry install

.PHONY: docs
docs:## Generates documentation
	@echo -e "\033[36m Generate documentation to docs...  \e[0m"
	poetry run pdoc --docformat google --template-directory files/docs_templates --output-dir docs src/

.PHONY: main
main:
	poetry run python main.py