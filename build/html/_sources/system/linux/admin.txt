System Administration
=====================

CPU
---

Show CPU usage per process

.. code-block:: shell

   $ top

Show number of CPU and their details

.. code-block:: shell

   $ cat /proc/cpuinfo

System
------

Show the operating system

.. code-block:: shell

   $ uname -a

Check if your system is 32 bit or 64 bit

.. code-block:: shell

   $ uname -a
   $ arch

Check server is up for how many days

.. code-block:: shell

   $ uptime

File system
-----------

Show available space

.. code-block:: shell

   $ df -h .

Find which directory is taking how much space

.. code-block:: shell

   $ du -sh . | grep G

Creation
^^^^^^^^

Soft link creation

.. code-block:: shell

   $ ln -s object link

Hard link creation

.. code-block:: shell

   $ ln object link

Create a read-only file

.. code-block:: shell

   $ touch file
   $ chmod 400 file

Deletion
^^^^^^^^

The deletion is an easy task in general.

You could delete a file with

.. code-block:: shell

   $ rm file

and delete an empty folder with

.. code-block:: shell

   $ rmdir folder

It will be slightly complicated when the folder is not empty. In this case, you need to delete the folder recursively with

.. code-block:: shell

   $ rm -r folder

To avoid the default pompt question, you could use the option -f. For example, for the last command, we could use

.. code-block:: shell

   $ rm -rf folder

Be careful, it is a hard task to recover the deleted file in general, and often it is impossible when you want to do it one day later. You need to contact your system administrator for the recovery as soon as possible.

Troubleshooting : argument list too long
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Due to system limitation, the provided commands may not be able to work correctly when there are too many items in the concerned folder. For example,

.. code-block:: shell

   $ rm -rf folder/*
   zsh: sure you want to delete all the files in /folder [yn]? y
   zsh: argument list too long: rm

In this case, you have several workarounds. The easiest way is to delete the whole folder and recreate the folder

.. code-block:: shell

   $ rm -rf folder
   $ mkdir folder

You could also use the command find to do it as follows

.. code-block:: shell

   $ find folder -type f -name '*' -exec rm {} \;

Links
^^^^^

There are two link types : soft link and hard link.

- soft link : also called symbolic link / symlink
   - inherit the permission of the pointed directory
   - points to program, file or directory
   - broken if pointed object is renamed, moved or deleted (in red, when displaying with ``ls -ltr --color``)
   - ending with @ when displaying with ``ls -F``
   - soft link can point to a network mounted directory
- hard link
   - points to program and file, not to directory
   - not broken if pointed object is renamed, moved or deleted
   - hard link can not span disk drives

N.B. Use ``pwd`` to know where you are!

Updating soft link

.. code-block:: shell

   $ ln -nsf new_object link

List all soft/hard links in a folder

.. code-block:: shell

   $ ls -ltr | grep "^l"

Folders
^^^^^^^

List all sub directories in a folder

.. code-block:: shell

   $ ls -ltr | grep "^d"
