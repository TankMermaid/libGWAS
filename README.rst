libGWAS - A GWAS Parser Library for Python
==========================================

libGWAS is a set of python classes and functions that can be used to 
facilitate the development of GWAS analysis programs. The library supports
many of the common file formats and offers a single interface for using 
each of them. Instructions for installation can be found below.

Installation
============
libGWAS requires python 2.7.x as well as the following libraries:

* NumPy (version 1.7.2 or later)   www.numpy.org
* SciPY (version 0.13.2 or later)  www.scipy.org

libGWAS's installation will attempt to install these required components
for you, however, it requires that you have write permission to the
installation directory. If you are using a shared system and lack the
necessary privileges to install libraries and software yourself, you should
please see one of the sections, Miniconda_ or virtual-env_ below
for instructions on different options for setting up your own python
environement which will exist entirely under your own control.

Installation can be done in two ways:

Install with PIP
++++++++++++++++

To install using python's package manager, pip, simply use the following command:

$ `pip install libGWAS`

If you have proper permission to install packages, this will attempt to download
and install all dependencies along with libGWAS itself.

Manual Installation
+++++++++++++++++++
For users who do not use pip or wish to run the bundled tests as well as have
a local copy of the manuals, manual installation is almost as easy.

For users with Git installed, you can simply clone the sources using the
following command:

$ `git clone https://github.com/edwards-lab/libGWAS`

Or you may visit the website and download the tarball directly from github: https://github.com/edwards-lab/libGWAS

Once you have downloaded the software, simply extract the contents and run the
following command to install it:

$ `python setup.py install`

If no errors are reported, it should be installed and ready to use.

**Regarding PYTHON 3** I began the process of updating the code to work with
both python versions 2 and 3, however, there are some real issues with some
library support of version 3 that is discouraging. So, until those have been
resolved, I have no plans to invest further time toward support for python 3.

System Requirements
+++++++++++++++++++
Because libGWAS is simply a set of classes and functions, it has no specific
system requirements. However, developers using the library should be aware of
the fact that some parsers, such as the pedigree_parser will require that the
entire dataset be loaded into memory, regardless of the filters that are in 
play (i.e. positional filters, such as --from-kb and --to-kb). 

Running Unit Tests
++++++++++++++++++
libGWAS comes with a unit test suite which can be run prior to installation.
To run the tests, simply run the following command from within the root
directory of the extracted archive's contents:

$ `python setup.py test`

If no errors are reported, then libGWAS should run correctly on your system.

.. _virtual-env:

Virtual Env
+++++++++++
Virtual ENV is a powerful too for python programmers and end users alike as it
allows for users to deploy different versions of python applications without
the need for root access to the machine.

Because libGWAS requires version 2.7, you'll need to ensure that your machine's
python version is in compliance. Virtual Env basically uses the the system
version of python, but creates a user owned environment wrapper allowing
users to install libraries easily without administrative rights to the
machine.

For a helpful introduction to VirtualEnv, please have a look at the
tutorial: http://www.simononsoftware.com/virtualenv-tutorial/

.. _miniconda:

Miniconda
+++++++++
Miniconda is a minimal version of the package manager used by the Anaconda
python distribution. It makes it easy to create local installations of python
with the latest versions of the common scientific libraries for users who don't
have root access to their target machines. Basically, when you use miniconda,
you'll be installing your own version of Python into a directory under your
control which allows you to install anything else you need without having to
submit a helpdesk ticket for administrative assistance.

Unlike pip, the folks behind the conda distributions provide binary downloads
of it's selected library components. As such, only the most popular libraries,
such as pip, NumPY and SciPy, are supported by conda itself. However, these do
not require compilation and may be easier to get installed than when using
pip alone. I have experienced difficulty installing SciPy through pip and setup
tools on our cluster here at vanderbilt due to non-standard paths for certain
required components, but mini-conda always comes through.

Firstly, download and install the appropriate version of miniconda at the
project website. Please be sure to choose the Python 2 version:
http://conda.pydata.org/miniconda.html

While it is doing the installation, please allow it to update your PATH
information. If you prefer not to always use this version of python in the
future, simple tell it not to update your .bashrc file and note the
instructions for loading and unloading your new python environment. Please
note that even if you chose to update your .bashrc file, you will need to
follow directions for loading the changes into your current shell.

Once those changes have taken effect, install setuptools and scipy:
$ `conda install pip scipy`

Installing SciPy will also force the installation of NumPy, which is
also required for running libGWAS. (setuptools includes easy_install).

Once that has been completed successfully, you should be ready to follow
the standard instructions for installing libGWAS.

libGWAS Online Manual
====================

The online manual can be found at http://edwards-lab.github.io/libGWAS/

For developers who would like to use the GWAS parsers, the API manual can be
found at http://edwards-lab.github.io/libGWAS/api/index.html
