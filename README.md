# Bitstream -- Binary Data for Humans

**TODO:** Python 2 badge

[![Build Status](https://travis-ci.org/boisgera/bitstream.svg?branch=master)](https://travis-ci.org/boisgera/bitstream)

**TODO: one-liner**

Bitstream is a Python library to read and write binary data.

Why Bitstream?
--------------------------------------------------------------------------------

Motivation, set of features


Quickstart
--------------------------------------------------------------------------------

Bitstream supports Python 2.7.
If Python 2.7, pip, NumPy and a C compiler 
are available, install bitstream with

    $ pip install bitstream

[pip]: https://packaging.python.org/tutorials/installing-packages/#install-pip-setuptools-and-wheel

and make sure that it works in the Python interpreter:

    >>> from bitstream import BitStream
    >>> BitStream("Hello!")
    010010000110010101101100011011000110111100100001


Examples
--------------------------------------------------------------------------------

The basic API is made of three methods only:

| Actions | Code                          |
|---------|-------------------------------|
| Create  | `stream = BitStream()`        |
| Write   | `stream.write(data, type)`    |
| Read    | `data = stream.read(type, n)` |

For example:

    >>> stream = BitStream()      # <empty>
    >>> stream.write(True, bool)  # 1
    >>> stream.write(False, bool) # 10
    >>> stream.write(-128, int8)  # 1010000000
    >>> stream.write("AB", str)   # 10100000000100000101000010
    >>> stream.read(bool, 2)      # 100000000100000101000010
    [True, False]
    >>> stream.read(int8, 1)      # 0100000101000010
    array([-128], dtype=int8)
    >>> stream.read(str, 2)       # <empty>
    "AB"

Refer to [the documentation](http://boisgera.github.io/bitstream/) for more
information.


Contribute / Developers
--------------------------------------------------------------------------------

Link to contributors

License
--------------------------------------------------------------------------------

Bitstream is open source software released under the [MIT license](LICENSE.txt).

Copyright (c) 2012-2017 Sébastien Boisgérault


