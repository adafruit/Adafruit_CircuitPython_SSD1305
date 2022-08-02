Introduction
============

.. image:: https://readthedocs.org/projects/adafruit-circuitpython-ssd1305/badge/?version=latest
    :target: https://docs.circuitpython.org/projects/ssd1305/en/latest/
    :alt: Documentation Status

.. image:: https://raw.githubusercontent.com/adafruit/Adafruit_CircuitPython_Bundle/main/badges/adafruit_discord.svg
    :target: https://adafru.it/discord
    :alt: Discord

.. image:: https://github.com/adafruit/Adafruit_CircuitPython_SSD1305/workflows/Build%20CI/badge.svg
    :target: https://github.com/adafruit/Adafruit_CircuitPython_SSD1305/actions/
    :alt: Build Status

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/psf/black
    :alt: Code Style: Black

Framebuf (non-displayio) driver for SSD1305 displays


Dependencies
=============
This driver depends on:

* `Adafruit CircuitPython <https://github.com/adafruit/circuitpython>`_
* `Bus Device <https://github.com/adafruit/Adafruit_CircuitPython_BusDevice>`_

Please ensure all dependencies are available on the CircuitPython filesystem.
This is easily achieved by downloading
`the Adafruit library and driver bundle <https://github.com/adafruit/Adafruit_CircuitPython_Bundle>`_.

Installing from PyPI
=====================

On supported GNU/Linux systems like the Raspberry Pi, you can install the driver locally `from
PyPI <https://pypi.org/project/adafruit-circuitpython-ssd1305/>`_. To install for current user:

.. code-block:: shell

    pip3 install adafruit-circuitpython-ssd1305

To install system-wide (this may be required in some cases):

.. code-block:: shell

    sudo pip3 install adafruit-circuitpython-ssd1305

To install in a virtual environment in your current project:

.. code-block:: shell

    mkdir project-name && cd project-name
    python3 -m venv .venv
    source .venv/bin/activate
    pip3 install adafruit-circuitpython-ssd1305

Usage Example
=============

.. code-block:: python

    # Basic example of clearing and drawing pixels on a SSD1305 OLED display.
    # This example and library is meant to work with Adafruit CircuitPython API.
    # Author: Tony DiCola
    # License: Public Domain

    # Import all board pins.
    from board import SCL, SDA
    import busio

    # Import the SSD1305 module.
    import adafruit_ssd1305


    # Create the I2C interface.
    i2c = busio.I2C(SCL, SDA)

    # Create the SSD1305 OLED class.
    # The first two parameters are the pixel width and pixel height.  Change these
    # to the right size for your display!
    display = adafruit_ssd1305.SSD1305_I2C(128, 32, i2c)
    # Alternatively you can change the I2C address of the device with an addr parameter:
    #display = adafruit_ssd1305.SSD1305_I2C(128, 32, i2c, addr=0x31)

    # Clear the display.  Always call show after changing pixels to make the display
    # update visible!
    display.fill(0)

    display.show()

Documentation
=============

API documentation for this library can be found on `Read the Docs <https://docs.circuitpython.org/projects/ssd1305/en/latest/>`_.

For information on building library documentation, please check out `this guide <https://learn.adafruit.com/creating-and-sharing-a-circuitpython-library/sharing-our-docs-on-readthedocs#sphinx-5-1>`_.

Contributing
============

Contributions are welcome! Please read our `Code of Conduct
<https://github.com/adafruit/Adafruit_CircuitPython_SSD1305/blob/main/CODE_OF_CONDUCT.md>`_
before contributing to help this project stay welcoming.
