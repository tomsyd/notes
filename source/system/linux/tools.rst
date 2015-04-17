Daily Tools
===========

find
----

::

   find -print is the same as find, -print option is a default option
   find -print0 ... | xargs -0 ... can avoid whitespace problem
   find -delete can be used for -exec rm {} \;

Find out shell scripts without execution right

.. code-block:: shell

   $ find . -iname "*.sh" -perm 644

Add execution right to shell scripts

.. code-block:: shell

   $ for i in `find . -iname "*.sh" -perm 644`; do echo $i; chmod a+x $i; done;

Find out all files modified since less than 1 day, excatly 1 day or more than 1 day

.. code-block:: shell

   $ find . -mtime -1
   $ find . -mtime 1
   $ find . -mtime +1

Delete found files

.. code-block:: shell

   $ find . -name "*.tmp" -delete
   $ find . -name "*.tmp" -print | xargs rm -f

Grep found files using -print0 and xargs -0 to avoid whitespace problem

.. code-block:: shell

   $ find . -name "*.txt" -print | xargs grep "Exception"
   $ find . -name "*.txt" -print0 | xargs -0 grep "Exception"

Find in the current folder, type file (not link, directory) and newer than first_file

.. code-block:: shell

   $ find . -maxdepth 1 -type f -newer first_file

Find in the current folder, type file and modified since more than 15 mins

.. code-block:: shell

   $ find . -type f -cmin 15 -prune

Find out and list files more than 1000 bytes

.. code-block:: shell

   $ find . -size +1000c -exec ls -l {} \;

Find out files with size more than 10000 bytes and less than 50000 bytes

.. code-block:: shell

   $ find . -size +10000c -size -50000c -print

Find out and list files modified 10 days ago and more than 50000 bytes

.. code-block:: shell

   $ find . -mtime +10 -size +50000c -exec ls -l {} \;

Find out and list all symbolic links

.. code-block:: shell

   $ find . -type l -print | xargs ls -ld | awk '{print $9 " " $10 " " $11}'

Find all the files without permission 777

.. code-block:: shell

   $ find / -type f ! -perm 777

Find all the SGID bit files whose permissions set to 644

.. code-block:: shell

   $ find / -perm 2644

Find all the Sticky Bit set files whose permission are 551

.. code-block:: shell

   $ find / -perm 1551

Find all SUID set files.

.. code-block:: shell

   $ find / -perm /u=s

Find all SGID set files.

.. code-block:: shell

   $ find / -perm /g+s

Find all empty files under certain path

.. code-block:: shell

   $ find /tmp -type f -empty

Find all all empty directories under certain path

.. code-block:: shell

   $ find /tmp -type d -empty
