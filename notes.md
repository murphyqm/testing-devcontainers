# First, create a conda env with cookiecutter

`conda create --name test-setup-env python=3.12 cookiecutter`

# Then, build a python package template

`cookiecutter https://github.com/audreyfeldroy/cookiecutter-pypackage.git`

Then you can follow along the instructions provided to fill out some default prompts.

# Create conda env from yml file

`conda env create --file environment.yml`

Maybe it's tidier to put them all in a single file just for the sake of this? thus a good idea to break down this multi env file to a single one?

```
name: packaging_testing_env
channels:
  - defaults
dependencies:
  - python=3.12
  - pytest
  - setuptools
  - sphinx
  - pip
  - pip:
    - black
```

`conda create --name packaging-env python=3.12 pytest setuptools sphinx`
`conda create --name formatting-env python=3.12 pip`
`conda activate formatting-env`
`pip install black`
`pip install ruff`
`conda deactivate formatting-env`

This doesn't work; need to figure out the pip dependencies

Ok, instead just create a separate linter env