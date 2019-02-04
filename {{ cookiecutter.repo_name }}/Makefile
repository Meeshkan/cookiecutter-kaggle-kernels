all: download preprocess train submit

#################################################################################
# GLOBALS                                                                       #
#################################################################################

PROJECT_DIR := $(shell dirname $(realpath $(lastword $(MAKEFILE_LIST))))
PROJECT_NAME = {{ cookiecutter.repo_name }}

#################################################################################
# COMMANDS                                                                      #
#################################################################################

## Install Python Dependencies
requirements:
	pip install -r requirements.txt

## Make Dataset
download: requirements
	kaggle competitions download -c {{ cookiecutter.kaggle_competition }} -p input
	./unzip_input.sh

unzip_input:
	./unzip_input.sh

preprocess:
	# TODO Fill in
	echo "Preprocessing..."

train:
	# TODO Fill in
	echo "Training..."

submit:
	# TODO Fill in
	echo "Submitting..."

## Delete all compiled Python files
clean:
	find . -type f -name "*.py[co]" -delete
	find . -type d -name "__pycache__" -delete
