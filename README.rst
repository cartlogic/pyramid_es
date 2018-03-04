pyramid_es - Elasticsearch Integration for Pyramid
==================================================

.. image:: https://secure.travis-ci.org/storborg/pyramid_es.png
    :target: http://travis-ci.org/storborg/pyramid_es
.. image:: https://coveralls.io/repos/storborg/pyramid_es/badge.png?branch=master
    :target: https://coveralls.io/r/storborg/pyramid_es
.. image:: https://img.shields.io/pypi/v/pyramid_es.svg
    :target: https://crate.io/packages/pyramid_es
.. image:: https://img.shields.io/pypi/dm/pyramid_es.svg
    :target: https://crate.io/packages/pyramid_es

Scott Torborg - `Cart Logic <http://www.cartlogic.com>`_

``pyramid_es`` is a pattern and set of utilities for integrating the
`elasticsearch <http://www.elasticsearch.org>`_ search engine with a `Pyramid
<http://www.pylonsproject.org>`_ web app. It is intended to make it easy to
index a set of persisted objects and search those documents inside Pyramid
views. Transactions are supported (designed to work with ``pyramid_tm``) and a full test suite is included.

Docs are available at `Read The Docs <http://pyramid-es.rtfd.org>`.


Installation
============

Install with pip::

    $ pip install pyramid_es


Example Usage
=============

.. code-block:: python

    client = get_client(request)
    result = client.query(Movie).\
        filter_term('year', 1987).\
        order_by('rating').\
        execute()
