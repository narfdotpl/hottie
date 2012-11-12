hottie
======

Code hot-swapping for Python 2.7 classes and functions.

v0.1.0

**GOAL**: Feel a little bit like [Bret Victor][].

**NON-GOAL**: Provide a general solution for hot-swapping everything in all edge-case scenarios.

  [Bret Victor]: http://vimeo.com/36579366


Usage
-----

Decorate classes and functions that you would like to hot-swap with `@hot` decorator:

``` python
from hottie import hot

@hot
class Rocket(object):
    '...'
```

Check out the [demo][].

  [demo]: https://github.com/narfdotpl/hottie-demo


Installation
------------

    pip install hottie


How it works
------------

`@hot` functions are proxies to real functions and `@hot` instances are observers that get their `.__class__` changed when their class is updated. This slightly decreases performance. If you want to take advantage of hot-swapping only in development, use `@hot` like this:

``` python
import hottie

if DEVELOPMENT:
    hot = hottie.hot
else:
    hot = hottie.identity
```


Meta
----

Hottie is written by [Maciej Konieczny][]. This software is released into public domain and uses [semantic versioning][] for release numbering.

  [Maciej Konieczny]: http://narf.pl/
  [semantic versioning]: http://semver.org/
