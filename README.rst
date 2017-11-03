
Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-VS1053/badge/?version=latest
    :target: https://circuitpython.readthedocs.io/projects/VS1053/en/latest/
    :alt: Documentation Status

.. image :: https://img.shields.io/discord/327254708534116352.svg
    :target: https://discord.gg/nBQh6qu
    :alt: Discord

Driver for interacting and playing media files with the VS1053 audio codec over
a SPI connection.

NOTE: This is not currently working for audio playback of files.  Only sine
wave test currently works.  The problem is that pure Python code is currently
too slow to keep up with feeding data to the VS1053 fast enough.  There's no
interrupt support so Python code has to monitor the DREQ line and provide a
small buffer of data when ready, but the overhead of the interpretor means we
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

Usage Example
=============

See examples/sdfile_play.py.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_VS1053/blob/master/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.

API Reference
=============

.. toctree::
   :maxdepth: 2

   api
