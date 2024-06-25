# First, create a conda env with cookiecutter

`conda create --name test-setup-env python=3.12 cookiecutter`

# Then, build a python package template

`cookiecutter https://github.com/audreyfeldroy/cookiecutter-pypackage.git`

Then you can follow along the instructions provided to fill out some default prompts.

# Create conda env from yml file

`conda env create --file environment.yml`