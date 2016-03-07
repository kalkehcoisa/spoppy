spoppy
========
Lightweight Spotify Command-Line interface for Linux

Requirements
==============

See requirements.txt for required python packages.

You will need a Spotify Premium account.

You will need libspotify, libffi-dev and libasound2-dev installed. Use your distribution's package manager.

For DBust integration you'll need python-dbus and python-gobject2. Use your distribution's package manager. Spoppy will work without these packages but won't expose it's DBus procedures.

Installation
==============

:code:`pip install spoppy`

To install globally you will probably need superuser privileges.

After installation run :code:`spoppy` in your terminal and you're all set!

Development
=============

1. Create python3.4+ virtualenv
2. Clone this project
3. Activate your virtualenv
4. Install requirements

  * pip install -r requirements.txt

5. Run :code:`python scripts/spoppy` (you will be asked for username/password)

DBus integration
==================

1. Run `make install_dbus`
2. Make sure you have python-gobject2 installed
3. Symlink gobject (and possibly glib) to your virtualenv

  * ln -s /usr/lib/python3.5/site-packages/gobject/ $VIRTUAL_ENV/lib/python3.5/site-packages/gobject
  * ln -s /usr/lib/python3.5/site-packages/glib/ $VIRTUAL_ENV/lib/python3.5/site-packages/glib

4. The service will be available at "/com/spoppy" (f.x. :code:`qdbus com.spoppy /com/spoppy com.spoppy.PlayPause`)

Testing
=========

:code:`python setup.py test`