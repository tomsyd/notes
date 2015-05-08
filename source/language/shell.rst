Shell
=====

Which Shell is in use ?
^^^^^^^^^^^^^^^^^^^^^^^

There are several Shells, such as bash (Bourne Again Shell), tcsh (TC Shell) or zsh (Z Shell). To know which Shell you use, you can simply type the ps command to get the name of your Shell as follows:

::

   $ ps
    PID TTY       TIME CMD
   2402 pts/5 00:00:00 bash
   7174 pts/5 00:00:00 ps

In this note, we will be interested in bash.

Save one script session in Linux
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you want to precise the script name, use 'script filename'. By default the script name is typescript.

::

   $ script
   Script started, file is typescript
   $ date
   Thu Jan 20 10:28:56 PST 2005
   $ who am i
   alex pts/4 Jan 8 22:15
   $ apropos mtools
   mtools (1) - utilities to access DOS disks in Unix
   mtools.conf [mtools] (5) - mtools configuration files
   mtoolstest (1) - tests and displays the configuration
   $ exit
   Script done, file is typescript

Basic commands
--------------

Shell documentation of utilities and programs

.. code-block:: shell

   $ info

tutorial of the ``info`` command

.. code-block:: shell

   $ info info

change the password

.. code-block:: shell

   $ passwd

display file names (``ls`` : list)

.. code-block:: shell

   $ ls

display file (``cat`` : catenate)

.. code-block:: shell

   $ cat file

delete file (``rm`` : remove)

.. code-block:: shell

   $ rm file

pager : display file on screen (``ENTER`` to continue, ``CTRL``+``C`` to quit)

.. code-block:: shell

   $ less file

pager : display file on screen (``PAGE DOWN`` to continue, ``:q`` to quit)

.. code-block:: shell

   $ more file

display the name of the system

.. code-block:: shell

   $ hostname

copy the file source to the file destination (cp : copy)

.. code-block:: shell

   $ cp source destination

rename the file existing to newfile (mv : move)

.. code-block:: shell

   $ mv existing newfile

display all lines in file containing the word "key" (grep : global regular expression print)

.. code-block:: shell

   $ grep ’key’ file

display the 6 first lines of file (default : 10 lines)

.. code-block:: shell

   $ head -6 file

display the 5 last lines of file (default : 10 lines)

.. code-block:: shell

   $ tail -5 file

monitoring all new lines of the file log (added since then)

.. code-block:: shell

   $ tail -f log

display in order all lines of file

.. code-block:: shell

   $ sort file

display all lines of file without (continuous) duplicates

.. code-block:: shell

   $ uniq file

compare two files file1 and file2 (diff : difference)

.. code-block:: shell

   $ diff file1 file2

compare with the option -u (unified output format)

.. code-block:: shell

   $ diff -u file1 file2

display the details of file1, file2

.. code-block:: shell

   $ file file1 file2

display all objects in the current folder (echo expand *)

.. code-block:: shell

   $ echo *

display the date (here, the format is "Weekday Month Day")

.. code-block:: shell

   $ date +"%A %B %d"

Example. Different ways to display the online help of the command ls

.. code-block:: shell

   $ ls --help | less
   $ man ls
   $ info ls

Short-cuts
^^^^^^^^^^

Reinitialize the default short-cuts:

.. code-block:: shell

   $ stty ek

Here are some default short-cuts:

+---------------------------------------------+------------------------------------------------------------------+
| ``BACKSPACE`` / ``DELETE`` / ``CTRL``+``H`` | delete one letter                                                |
+---------------------------------------------+------------------------------------------------------------------+
| ``CTRL``+``W``                              | delete one word                                                  |
+---------------------------------------------+------------------------------------------------------------------+
| ``CTRL``+``U`` / ``CTRL``+``X``             | delete one line                                                  |
+---------------------------------------------+------------------------------------------------------------------+
| ``CTRL``+``Z``                              | sususpension of one process (using ``fg`` to resume the process) |
+---------------------------------------------+------------------------------------------------------------------+
| ``CTRL``+``C``                              | interrupt the process                                            |
+---------------------------------------------+------------------------------------------------------------------+

Example. Stop a long program (bigjob) :

.. code-block:: shell

   $ bigjob
   ^Z
   [1]+ Stopped bigjob
   $ jobs
   [1]+ Stopped bigjob
   $ kill %1
   1
   [1]+ Stopped bigjob
   $ RETURN
   [1]+ Killed bigjob

If the process persists, then use ``CTRL``+``Z`` or ``kill -KILL %1``.
