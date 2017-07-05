# flumine

[![Build Status](https://travis-ci.org/liampauling/flumine.svg?branch=master)](https://travis-ci.org/liampauling/flumine) [![Coverage Status](https://coveralls.io/repos/github/liampauling/flumine/badge.svg?branch=master)](https://coveralls.io/github/liampauling/flumine?branch=master) [![PyPI version](https://badge.fury.io/py/flumine.svg)](https://pypi.python.org/pypi/flumine)


Betfair data record framework utilising streaming to create a simple data recorder, requires [betfairlightweight](https://github.com/liampauling/betfairlightweight).

IN DEVELOPMENT.

## roadmap

- storage engine (s3 / google cloud etc.)
- logging control class
- cli (e.g. flumine start / stop)

## installation

```
$ pip install flumine
```

## setup

The framework can be used as follows:

```python
>>> import flumine
    from flumine.resources import StreamRecorder
    from flumine.storage import storageengine

>>> market_filter = {"marketIds": ["1.132452335"]}

    storage_engine = flumine.storageengine.S3('flumine')

    flumine = Flumine(
        recorder=StreamRecorder(
            storage_engine=storage_engine,
            market_filter=market_filter,
        ),
    )

>>> flumine.start()

>>> flumine
<Flumine [running]>

>>> flumine.stop()

>>> flumine
<Flumine [not running]>

```
