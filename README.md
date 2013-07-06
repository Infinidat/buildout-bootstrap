Overview
========

Here at Infinidat we use buildout in closed networks, where there is no internet.

This was easy enough to do with buildout-1.x and its bootstrap. However, it is not the case with buildout-2.2

Until now, we were able to use the old bootstrap with buildout-2.1, but this is no longer possible as buildout-2.2 uses setuptools, and not distribute.

This repository holds an updated bootstrap.py that features the following changes:

* `--download-base`. a location in which one can find the setuptools tgz achive
* `--setup-source`. a location of setuptools' `ez_setup.py`
* `--index-url`. an alternative PyPI server


Test cases
==========

We manually test the functionality of this bootstrap under the following cases:

* running `bootstrap.py` as-is, without additional command-line paramaters
* running `bootstrap.py` with providing download-base and setup-source, and making sure that bootstrap succeed without accessing the interneet
* running `bootstrap.py` with providing download-base and setup-source and index-url, and making sure that bootstrap succeed without accessing the interneet
