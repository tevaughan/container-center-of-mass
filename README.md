
# Jupyter Examples

## Interactive, 2-D Visualization

[container-center-of-mass.ipynb](container-center-of-mass.ipynb) shows how,
with a python kernel, to produce both

 - an interactive drawing (via `interact()` from ipywidgets and svgwrite) and
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
   - `conda config --prepend channels conda-forge`
   - `conda config --prepend channels QuantStack`
   - ```
conda install\
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
```
   - `conda update --all`

