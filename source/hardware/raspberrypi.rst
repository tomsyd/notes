Raspberry Pi
============

Default settings
----------------

+----------+-----------------+
| login    | **pi**          |
+----------+-----------------+
| password | **raspberry**   |
+----------+-----------------+
| hostname | **raspberrypi** |
+----------+-----------------+
| keyboard | UK              |
+----------+-----------------+

Basic commands
--------------

Config
^^^^^^

.. code-block:: shell

   $ sudo raspi-config

Start X server
^^^^^^^^^^^^^^

.. code-block:: shell

   $ startx

Reboot
^^^^^^

.. code-block:: shell

   $ sudo reboot

Shutdown
^^^^^^^^

.. code-block:: shell

   $ sudo shutdown -h now

Change datetime
^^^^^^^^^^^^^^^

.. code-block:: shell

   $ sudo date --set="Sun Nov 18 1:55:16 EDT 2012"

Update
^^^^^^

.. code-block:: shell

   $ sudo apt-get update
   $ sudo apt-get upgrade

Information
-----------

Check OS version
^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ cat /proc/version

Check board version
^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ cat /proc/cpuinfo

Display network interface and associated IP addresses
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ ifconfig

Short-cuts
----------

+------------------------------------+------------------------------------------+
| **Ctrl** + **C**                   | kill currently running program           |
+------------------------------------+------------------------------------------+
| **Ctrl** + **D**                   | exit shell                               |
+------------------------------------+------------------------------------------+
| **Ctrl** + **A**                   | move cursor to the beginning of the line |
+------------------------------------+------------------------------------------+
| **Ctrl** + **E**                   | move cursor to the end of the line       |
+------------------------------------+------------------------------------------+
| **Ctrl** + **Alt** + **Backspace** | [optional] terminate the X server        |
+------------------------------------+------------------------------------------+

Setup Keyboard
--------------

The default keyboard is UK. Let's change it to AU keyboard.

The trick is that Australia is not listed in the country list for the keyboard, we need to setup a US keyboard instead.

Change the keyboard config
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ sudo vi /etc/default/keyboard

.. code-block:: text

   XKBMODEL ="pc105"
   XKBLAYOUT="us"
   XKBVARIANT=""
   XKBOPTIONS=""
   
   BACKSPACE="guess"

Then run the following commands and reboot
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ sudo setxkbmap -layout us
   $ sudo udevadm trigger --subsysstem-match=input --action=change

Utilities / Softwares
---------------------

raspi-config tool
^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ sudo apt-get install raspi-config

Minecraft
^^^^^^^^^

.. code-block:: shell

   $ sudo apt-get install minecraft-pi

Screenshot : scrot
^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ sudo apt-get install scrot

Mercurial
^^^^^^^^^

.. code-block:: shell

   $ sudo apt-get install mercurial
