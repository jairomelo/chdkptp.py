==========
chdkptp.py
==========

Python bindings for `chdkptp <https://www.assembla.com/spaces/chdkptp/wiki>`_
via an embedded, thread-safe Lua runtime (thanks to Stefan Behnel's
`lupa <https://github.com/scoder/lupa>`_).

Requirements
============

- C compiler
- Lua 5.2, with headers
- libusb, with headers
- lupa, installed with the **--no-luajit** flag

Currently chdkptp.py only works when the ``lupa`` package is linked to
Lua. However, by default the package links to LuaJIT, so make sure that
you install it with the `--no-luajit` flag.
It is best to do this via `pip`, **before** you install chdkptp.py::

    $ pip install lupa --install-option='--no-luajit'


Documentation
=============
Please refer to the `API documentation on readthedocs.org <http://chdkptppy.readthedocs.org/en/latest/#api-reference>`_

Installation
============

**For better results, try manual installation**

Before installation make sure you are running python3.6, to make python version managing easier
I recommend you to use `pyenv <https://github.com/pyenv/pyenv>`_

**Remember to install lupa before install**::

        $ pip install lupa --install-option='--no-luajit'

Pip install from tar.gz
=======================
Pip also can install tar.gz files so you can either download the tar.gz file or copy the release link::

    $ pip install https://github.com/5up3rD4n1/chdkptp.py/releases/download/v0.1.4/chdkptp.py-0.1.4.tar.gz

Pip Instalation from repo
===============
Pip -e (egg) have VCS support so the package can be installed like::

    $ pip install -e git+https://github.com/5up3rD4n1/chdkptp.py.git@master#egg=chdkptp.py

Manual Installation **Recomended**
==================

I highly suggest to create a virtual env before installing the package(this will avoid permission errors)::

    $ python3 -m venv ~/.virtualenvs/chdkptp

Activate the environment::

    $ source ~/.virtualenvs/chdkptp/bin/activate

To leave the virtual env just run::

    $ deactivate

Now clone the repo with all the submodules::

    $ git clone --recursive -j8  https://github.com/jairomelo/chdkptp.py.git

Get into the repo::

    $ cd chdkptp.py

Install lupa dependency::

    $ pip install lupa --install-option='--no-luajit'
    
Install other dependencies::

    $ pip install six

Prepare the package with the python3 distutils command::

    $ python setup.py sdist

And finally install the package::

    $ python setup.py install

Now you can use chdkptp simply running::

    >>> import chdkptp
    >>> chdkptp.list_devices()
    []
    >>>

NOTE: if you installed the package and you are inside the repo dir and try
to import chdkptp, it will probably throw an error because python is loading
the local dir module not the installed one.
