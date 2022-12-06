# Spyder IDE

[Spyder IDE](https://www.spyder-ide.org) (Integrated Development Environment) is a handy tool for buildling and running Python scripts.

## Installation

For Windows or Mac, use the appropriate standalone installer from [here](https://docs.spyder-ide.org/current/installation.html#downloading-and-installing).  Then you can open and run Spyder from the Start menu / Applications folder just like any other installed program.

For Linux, you'll need to use `mamba`.  You should keep an environment dedicated to only running Spyder, and not install any other packages in there:

    mamba create -n spyder5 spyder numpy scipy pandas matplotlib sympy cython

To run Spyder, then do

    mamba activate spyder5
    spyder

## Running other environments within Spyder

We might want to use extra packages beyond the default set above or switch between different environments within Spyder.  To do this:


### Install `spyder-kernels`

First, install `spyder-kernels` into the other environment:

    conda install -n <envname> spyder-kernels

### Find the location of the environment

In the conda prompt or terminal window, activate the environment and run `python`

    conda activate <envname>
    python

Then run

```python
from sys import executable
print(executable)
exit()
```

The output of the `print` line should be the path to your Python environment.  Copy this.

### Tell Spyder to use the environment

In Spyder...

<!-- ![Image title](/docs/img/spyder-default-env.png) -->
