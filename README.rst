Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-vs1053/badge/?version=latest
    :target: https://docs.circuitpython.org/projects/vs1053/en/latest/
    :alt: Documentation Status

.. image:: https://img.shields.io/discord/327254708534116352.svg
    :target: https://adafru.it/discord
    :alt: Discord

.. image:: https://github.com/adafruit/Adafruit_CircuitPython_VS1053/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_VS1053/actions/
    :alt: Build Status

Driver for interacting and playing media files with the VS1053 audio codec over
a SPI connection.

NOTE: This is not currently working for audio playback of files.  Only sine
wave test currently works.  The problem is that pure Python code is currently
too slow to keep up with feeding data to the VS1053 fast enough.  There's no
interrupt support so Python code has to monitor the DREQ line and provide a
small buffer of data when ready, but the overhead of the interpreter means we
can't keep up.  Optimizing SPI to use DMA transfers could help but ultimately
an interrupt-based approach is likely what can make this work better (or C
functions built in to custom builds that monitor the DREQ line and feed a
buffer of data).

Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Bus Device <https://github.com/adafruit/Adafruit_CircuitPython_BusDevice>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Installing from PyPI
--------------------

On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-vs1053/>`_. To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-vs1053

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-vs1053

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .env
    source .env/bin/activate
    pip3 install adafruit-circuitpython-vs1053

Usage Example
=============

See examples/sdfile_play.py.

Documentation
=============

API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/vs1053/en/latest/>`_.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_VS1053/blob/main/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

Documentation
=============

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.
