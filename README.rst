js.d3
=======
This library packages `D3.js`_ for `Fanstatic`_.

.. _`Fanstatic`: http://fanstatic.org
.. _`D3.js`: http://d3js.org

This requires integration between your web framework and ``Fanstatic``,
and making sure that the original resources (shipped in the ``resources``
directory in ``js.d3``) are published to some URL. This
library also packages up a minified version of `D3.js`_.


Usage
-----

You can import ``d3`` from ``js.d3`` and ``need`` it where you want these
resources to be included on a page::

    >>> from js.d3 import d3
    >>> d3.need()


Updating this package
---------------------

In order to obtain a newer version of this library, do the following,
editing the version name (eg ``3.4.13``) accordingly::

    pushd js/d3/resources
    VERSION="v3.5.5"
    wget https://github.com/mbostock/d3/raw/$VERSION/d3.js -O d3.js
    wget https://github.com/mbostock/d3/raw/$VERSION/d3.min.js -O d3.min.js
    popd
    #Edit setup.py for versions
    git commit -a -m "Updated for release $VERSION"
    git push
