# Contributing to Neuroinformatics Unit (NIU) projects

## Introduction

**Contributors to NIU projects are absolutely encouraged**, whether to fix a
bug, develop a new feature, or add to the documentation.

If you're unsure where to start, create an issue on the relevant repository. If
for any reason, you'd rather not reach out in public, feel free to
[email](mailto:code@adamltyson.com?subject=NIU-contribution) [Adam Tyson](https://github.com/adamltyson).

## To contribute code

### Creating a development environment

It is recommended to use `conda` to install a development environment. Once you have `conda` installed, the following commands
will create and activate a `conda` environment with the requirements needed
for a development environment:

```sh
conda create -n NIU-dev -c conda-forge python=3.12
conda activate NIU-dev
```

To install a specific project for development, clone the GitHub repository,
and then run

```sh
pip install -e .[dev]
```

Or if using `zsh` (the default on new Apple machines):

```sh
pip install -e '.[dev]'
```

from inside the repository. This will install the package, its dependencies,
and its development dependencies.

### Pull requests

In all cases, please submit code to the main repository via a pull request. The developers recommend, and adhere,
to the following conventions:

- Please submit _draft_ pull requests as early as possible (you can still push to the branch once submitted) to
  allow for discussion.
- One approval of a PR (by a core developer) is enough for it to be
  merged.
- Unless someone approves the PR with optional comments, the PR is immediately merged by the approving reviewer.
- Please merge via "Squash and Merge" on GitHub to maintain a clean commit history.
- Ask for a review from someone specific if you think they would be a particularly suited reviewer (possibly noting
  why they are suited on the PR description).

### Formatting and QC

- We use [Black](https://black.readthedocs.io/en/stable/), [ruff](https://beta.ruff.rs/docs/), and [mypy](https://mypy.readthedocs.io/en/stable/) to ensure a consistent
  code style.
- The above tools are automated in the using [pre-commit](https://pre-commit.com/). Running `pre-commit install` once locally will set up the pre-commit hooks to be executed automatically before each commit.

### Dependency support

Packages have to choose which versions of dependencies they officially support, with minimum supported versions of each dependency used in continuous integration testing. All NIU projects follow [NEP 29 — Recommend Python and NumPy version support as a community policy standard](https://numpy.org/neps/nep-0029-deprecation_policy.html) to determine the **minimum** set of supported package versions:

- The last 42 months of Python releases
- The last 24 months of NumPy releases

### Documentation

- We use [Sphinx](https://www.sphinx-doc.org/en/master/) to generate documentation for Python projects.
- Docstrings should be written in [numpydoc](https://numpydoc.readthedocs.io/en/latest/format.html) format.

### Logging

All Python software should use the inbuilt Python logging module, rather
than e.g. print statements.

### Configuration files

User-editable configuration files should use the YAML format. As far as possible, machine readable outputs from software should also use this format.
