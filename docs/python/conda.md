# `conda` and `mamba`

## Cheat sheet / official docs

  * [One page of docs containing 99% of everything you will ever need to do](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
  * [Official conda cheat sheet](https://docs.conda.io/projects/conda/en/4.6.0/_downloads/52a95608c49671267e40c689e0bc00ca/conda-cheatsheet.pdf)

Remember to just replace `conda` with `mamba` every time if you're using the latter.

## What's the difference?

You can use either `conda` or `mamba` to install and update Python packages and manage your Python environments.

`mamba` is a drop-in replacement for `conda` which you use in exactly the same way (just replace `conda` with `mamba` in every command),  but which runs much faster.  However, in our experience, `mamba` often causes major problems on Windows, so for now:

``` mermaid
graph LR
  A[Your OS] -->|Windows| B[use conda];
  A -->|Mac/Linux| C[use mamba];
```

## Installation

### conda

Install the latest version of **Miniconda** for your OS (i.e., Windows) from [here](https://docs.conda.io/en/latest/miniconda.html#latest-miniconda-installer-links).

Once installed, but before doing anything else, set the default channel to `conda-forge` by running the following two commands:

    conda config --add channels conda-forge
    conda config --set channel_priority strict

You only need to do this once.

### mamba

Install the latest version of **Mambaforge** for your OS from [here](https://github.com/conda-forge/miniforge#mambaforge).  The `mamba` command should now be accessible from the terminal. 

## Making an environment

Create your first environment using

    conda create -n <envname> <packages>

replacing `<envname>` with the name of the environment and `<packages>` with a list of packages that you want to install.

## What about `pip`?

If you need to install a new package that says to use `pip install <package>`, first check if it's available through conda, and do that instead if possible.  If not, then you can use `pip` instead, just make sure you activate the relevant environment first.
