NANO (Nano’s ANOther editor)
============================

Basic commands
--------------

NANO is the open source clone of the editor PICO, distributed as part of the mail client Pine.

Launch NANO from command line
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ nano file.txt       open and edit file.txt
   $ nano -B file.txt    save the original file as file.txt~ or ~.file
   $ nano -m file.txt    activate the mouse cursor (if supported)
   $ nano +25 file.txt   edit from the 25th line
   $ jpico file.txt      simulator JOE of PICO

Short-cuts Fn
^^^^^^^^^^^^^

+-----+----------+----------------------------------------------+
| F1  | CTRL + g | display online help (CTRL + x to quit)       |
+-----+----------+----------------------------------------------+
| F2  | CTRL + x | quit NANO (or cloase ongoing buffer)         |
+-----+----------+----------------------------------------------+
| F3  | CTRL + o | save ongoing file                            |
+-----+----------+----------------------------------------------+
| F4  | CTRL + j | reformat the text of paragraph               |
+-----+----------+----------------------------------------------+
| F5  | CTRL + r | insert one file                              |
+-----+----------+----------------------------------------------+
| F6  | CTRL + w | search one text                              |
+-----+----------+----------------------------------------------+
| F7  | CTRL + y | previous screen                              |
+-----+----------+----------------------------------------------+
| F8  | CTRL + v | next screen                                  |
+-----+----------+----------------------------------------------+
| F9  | CTRL + k | cut (and copy) the line (or the chosen text) |
+-----+----------+----------------------------------------------+
| F10 | CTRL + u | paste the cut text                           |
+-----+----------+----------------------------------------------+
| F11 | CTRL + c | display the cursor position                  |
+-----+----------+----------------------------------------------+
| F12 | CTRL + t | start the orthograph verification            |
+-----+----------+----------------------------------------------+

Misc
^^^^

+----------+-----------------------------------------------------------------+
| CTRL + 6 | choose one text from the cursor (CTRL + 6 to cancel the action) |
+----------+-----------------------------------------------------------------+
