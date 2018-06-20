
# Jupyter Examples

## Basic Overview

The original jupyter application consists of a *local web server* and a set of
*clients*, each of which runs in a tab of the user's web browser.

After the relevant software is installed (see below), typing `jupyter notebook`
from the command line launches both a local server and new browser tab in the
user's default web browser.

The initial jupyter browser tab presents a file-manager-like view of the files
in the directory in which the `jupyter notebook` command was invoked.  From
this tab, the user may open an existing jupyter notebook by clicking on its
name or make a new jupyter notebook.

A jupyter notebook is a vertical array of *cells*.

Each cell is, typically, either a *markdown cell* or a *code cell*.

The markdown supported by jupyter has mathjax rendering of LaTeX mathematical
notation.

Every code cell is processed by the notebook's *kernel*, which is an interface
to a particular language.  Several different languages are supported.  The ones
that most interest me are python (supported by the ipython kernel) and C++
(supported by the cling kernel).  Python is interesting because it is perhaps
the best supported language for jupyter and has an extremely large set of
libraries to avoid reinvention of the wheel.  C++ is interesting because I do
most of my professional work in C++.

What makes jupyter notebooks in general of interest to me is the integration of
beautiful mathematics, syntax-highlighted code, and interactive visualizations
produced by that code.  Also, a jupyter notebook can be translated into both
PDF and static HTML.  In some cases, an interactive visualization continues to
work even in the static-HTML version of the notebook.

## Interactive, 2-D Visualization

[container-center-of-mass.ipynb](container-center-of-mass.ipynb) shows how,
with a python kernel, to produce both

 - an interactive drawing (via `interact()`, which comes  from ipywidgets, and
   svgwrite) and

 - an interactive plot (via `interact()` and bqplot).

# What To Install

 - Download the python-3 version of miniconda for your operating system.
   - I use Debian and employ the package manager to uninstall as many of the
     python3 packages as possible.  I don't want any conflicts with miniconda.
   - I run the installer as root and use `/opt/miniconda3` as the installation
     directory.
   - Then I edit `/etc/bash.bashrc` to put `/opt/miniconda3/bin` at the front
     of the path.
   - This allows every user to run the programs under `/opt/miniconda3/bin`.
   - This causes a problem for me because then youcompleteme in vim doesn't
     work; I work around that by making a shell script the strips
     `/opt/miniconda3/bin` from the path before launch vim.
   - I then do `chmod -R <my_username>: /opt/miniconda3` so that I can run the
     `conda` package manager without having to worry about running `sudo` or
     `su -`.
 - After miniconda3 is set up and the path configured appropriately, do the
   following.
```
$ conda config --prepend channels conda-forge`

$ conda config --prepend channels QuantStack`

$ conda install\
bqplot\
cling\
ipywidgets\
jupyter_client\
jupyter_core\
jupyter_sphinx\
matplotlib\
nbsphinx\
numpy\
pandas\
scipy\
sphinx\
sphinx-nbexamples\
statsmodels\
svgwrite\
theano\
widgetsnbextension\
xeus\
xeus-cling\
xwidgets

$ conda update --all`
```

