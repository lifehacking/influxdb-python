===============
influxdb-python
===============

[![Build Status](https://travis-ci.org/influxdb/influxdb-python.png?branch=master)](https://travis-ci.org/influxdb/influxdb-python)
[![Downloads](https://pypip.in/download/influxdb/badge.svg)](https://pypi.python.org/pypi/influxdb/)
[![Latest Version](https://pypip.in/version/influxdb/badge.svg)](https://pypi.python.org/pypi/influxdb/)
[![Supported Python versions](https://pypip.in/py_versions/influxdb/badge.svg)](https://pypi.python.org/pypi/influxdb/)
[![License](https://pypip.in/license/influxdb/badge.svg)](https://pypi.python.org/pypi/influxdb/)

About
=====

InfluxDB-Python is a client for interacting with [InfluxDB](http://influxdb.com/).

InfluxDB is an open-source distributed time series database, find more about at http://influxdb.com/


Installation
============

Install, upgrade and uninstall InfluxDB-Python with these commands:

````
$ pip install influxdb
$ pip install --upgrade influxdb
$ pip uninstall influxdb
````


Dependencies
============

The InfluxDB-Python distribution is supported and tested on Python 2.7 and Python 3.3.

Main dependencie is:

- Requests: HTTP library for human beings (http://docs.python-requests.org/)


Additional dependencies are:

- Sphinx: Tool to create and manage the documentation (http://sphinx-doc.org/)
- Nose: to auto-discover tests (http://nose.readthedocs.org/en/latest/)
- Mock: to mock tests (https://pypi.python.org/pypi/mock)


Documentation
=============

InfluxDB-Python documentation is available at [ADD_LINK](https://readthedocs.org/)

You will need [Sphinx](http://sphinx.pocoo.org/) installed to generate the
documentation.

The documentation can be generated by running:

````
$ cd docs
$ make html
````

Generated documentation can be found in the *docs/build/html/* directory.


Examples
========

Here's a basic example (for more see the examples directory):

````
$ python

>>> from influxdb import InfluxDBClient

>>> json_body = [{
    "points": [
        ["1", 1, 1.0],
        ["2", 2, 2.0]
    ],
    "name": "foo",
    "columns": ["column_one", "column_two", "column_three"]
}]

>>> client = InfluxDBClient('localhost', 8086, 'root', 'root', 'example')

>>> client.create_database('example')

>>> client.write_points(json_body)

>>> result = client.query('select column_one from foo;')

>>> print("Result: {0}".format(result))
````


Testing
=======

Make sure you have tox by running the following:

```
$ pip install tox
```

To test influxdb-python with multiple version of Python, you can use tox:

````
$ tox
````

If you don't have all Python version listed in tox.ini, then

````
$ tox -e py27
````


Support
=======

For issues with, questions about, or feedback for InfluxDB, please look into
our community page: http://influxdb.com/community/.


Source code
===========

The source code is currently available on [https://github.com/influxdb/influxdb-python](https://github.com/influxdb/influxdb-python).
