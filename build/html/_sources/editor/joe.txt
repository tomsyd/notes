JOE (Joe’s Own Editor)
======================

Basic commands
--------------

Launch JOE from command line
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ joe file.txt                     open and edit file.txt
   $ joe -wordwrap file.txt           option wordwrap
   $ joe -lmargin 5 -tab 5 file.txt   left margin = 5 chars and TAB = 5 chars
   $ joe +25 file.txt                 edit from 25th line
   $ jmacs file.txt                   variant : simulate GNU-EMACS
   $ jstar file.txt                   variant : simulate WordStar
   $ jpico file.txt                   variant : simulate the Pine mailer editor PICO
   $ rjoe file.txt                    variant : restraint the edit to the file file.txt
                                      only

Saving and quiting commands
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+--------------+--------------------------------------------------+
| CTRL + k + d | save the file                                    |
+--------------+--------------------------------------------------+
| CTRL + k + x | save and exit                                    |
+--------------+--------------------------------------------------+
| CTRL + c     | exit without save                                |
+--------------+--------------------------------------------------+
| CTRL + k + z | exit and leave JOE in background (fg to go back) |
+--------------+--------------------------------------------------+

Orthographe
^^^^^^^^^^^

+--------------+----------------+
| CTRL + [ + n | check one word |
+--------------+----------------+
| CTRL + [ + l | check one file |
+--------------+----------------+

Misc
^^^^

+--------------+----------------------------------+
| CTRL + k + a | move to the middle               |
+--------------+----------------------------------+
| CTRL + t     | display and choose the options   |
+--------------+----------------------------------+
| CTRL + r     | refresh the display              |
+--------------+----------------------------------+
| CTRL + k + h | display or close the online help |
+--------------+----------------------------------+

Navigation
----------

Cursor / Move
^^^^^^^^^^^^^

+----------+---------------------------+
| CTRL + b | move to left              |
+----------+---------------------------+
| CTRL + p | move to top               |
+----------+---------------------------+
| CTRL + f | move to right             |
+----------+---------------------------+
| CTRL + n | move to down              |
+----------+---------------------------+
| CTRL + z | move to the previous word |
+----------+---------------------------+
| CTRL + x | move to the next word     |
+----------+---------------------------+

Navigation
^^^^^^^^^^

+--------------+-----------------------+
| CTRL + u     | previous screen       |
+--------------+-----------------------+
| CTRL + v     | next screen           |
+--------------+-----------------------+
| CTRL + a     | beginning of the line |
+--------------+-----------------------+
| CTRL + e     | end of the line       |
+--------------+-----------------------+
| CTRL + k + u | beginning of the file |
+--------------+-----------------------+
| CTRL + k + v | end of the file       |
+--------------+-----------------------+
| CTRL + k + l | go to line n          |
+--------------+-----------------------+

Editing
-------

Blocs operations
^^^^^^^^^^^^^^^^

+--------------+--------------------------+
| CTRL + k + b | beginning of the bloc    |
+--------------+--------------------------+
| CTRL + k + k | end of the bloc          |
+--------------+--------------------------+
| CTRL + k + m | move of the bloc         |
+--------------+--------------------------+
| CTRL + k + c | copy the bloc            |
+--------------+--------------------------+
| CTRL + k + w | write the bloc in a file |
+--------------+--------------------------+
| CTRL + k + y | delete the bloc          |
+--------------+--------------------------+
| CTRL + k + / | filter the bloc          |
+--------------+--------------------------+

Deletion
^^^^^^^^

+----------+-----------------------------------------------------------------+
| CTRL + d | delete one character                                            |
+----------+-----------------------------------------------------------------+
| CTRL + y | delete one line                                                 |
+----------+-----------------------------------------------------------------+
| CTRL + w | delete one word on the right of the cursor                      |
+----------+-----------------------------------------------------------------+
| CTRL + o | delete one word on the left of the cursor                       |
+----------+-----------------------------------------------------------------+
| CTRL + j | delete the rest of the line (i.e. the right side of the cursor) |
+----------+-----------------------------------------------------------------+
| CTRL + _ | cancel the operation                                            |
+----------+-----------------------------------------------------------------+
| CTRL + 6 | redo the cancelled operation                                    |
+----------+-----------------------------------------------------------------+

Files
^^^^^

+--------------+----------------------------------------+
| CTRL + k + e | open / edit a new file                 |
+--------------+----------------------------------------+
| CTRL + k + r | insert one file at the cursor position |
+--------------+----------------------------------------+

Search
------

+--------------+-----------------+
| CTRL + k + f | search one text |
+--------------+-----------------+
| CTRL + l     | search the next |
+--------------+-----------------+
