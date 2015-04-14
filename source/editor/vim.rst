VIM (Vi IMproved)
=================

Basic commands
--------------

Read only (use **:wq!** to force the modification)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ vim -R file

Running shell commands
^^^^^^^^^^^^^^^^^^^^^^

::

   !command

e.g. **!ls** will launch **ls**

if you wants to go directly to shell without quitting from VI editor you can go by executing **!sh** / **!bash** / **!ksh** from VI and then come back to VI editor by just executing command **exit** from shell.
for Cygwin, **!bash** and **exit** seems to be the best choice

Launch VIM from command line
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ vi file.txt                        open and edit file file.txt
   $ vi file1.txt file2.txt file3.txt   open several files
   $ vi +25 file.txt                    edit from the 25th line
   $ vi + file.txt                      edit at the end of file
   $ vi +/text file.txt                 edit from the first line containing the word test
   $ vi -r file.txt                     restore a crashed file
   $ view file.txt                      vi in read-only mode
   $ vimtutor                           VIM tutorial

Saving and quiting commands
^^^^^^^^^^^^^^^^^^^^^^^^^^^

::

   :w            save the current file (before quit)
   :w file.txt   save the modified file with another file name
                 (even if the file was opened in read-only mode)
   :wq           save and quit
   ZZ            save and quit
   :q!           quit without saving
   :wq!          save change in the current file opened in read-only mode, and then quit
   :w!           save change in the current file opened in read-only mode

Checking history and help
^^^^^^^^^^^^^^^^^^^^^^^^^

::

   :history        vim commands history
   :help           all helps
   :help command   help on one command

Recording and replaying commands
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Recoding in vim or VI editor can be done by using **q** and the executing recorded comment by using **q@1**

Options
-------

Here are the major VIM editor options

+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :set nu         | This will display line number in front of each line quite useful if you want line by line information.                                                                                                                   |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                 | You can turn it off by executing **set nonu**. Remember for turning it off put "no" in front of option, like here option is "nu" so for turning it off use "nonu".                                                       |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :set nonu       | removing line number display                                                                                                                                                                                             |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :set hlsearch   | This will highlight the matching word when we do search in VI editor, quite useful but if you find it annoying or not able to see sometime due to your color scheme you can turn it off by executing **set nohlsearch**. |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :set wrap       | If your file has contains some long lines and you want them to wrap use this option, if its already on and you just don't want them to wrap use **set nowrap**.                                                          |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :colorscheme    | color scheme is used to change color of VIM editor, my favorite color scheme is murphy so if you want to change color scheme of VI editor you can do by executing **colorscheme murphy**.                                |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :syntax on      | syntax can be turn on and off based on your need, if it's on it will display color syntax for .xml, .html and .perl files.                                                                                               |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :set ignorecase | This VI editor option allows you do case insensitive search because if it's set VI will not distinguish between two words which are just differ in case.                                                                 |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| :set smartcase  | Another VI editor option which allows case-sensitive search if the word you are searching contains an uppercase character.                                                                                               |
+-----------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Navigation
----------

Here are some navigating commands

+---------+----------------------------------+
| gg      | goes to start of file            |
+---------+----------------------------------+
| SHIFT g | goes to end of file              |
+---------+----------------------------------+
| 0       | goes to beginning of the line    |
+---------+----------------------------------+
| $       | goes to end of the line          |
+---------+----------------------------------+
| nG      | goes to nth line                 |
+---------+----------------------------------+
| :n      | another way of going to nth line |
+---------+----------------------------------+

Editing
-------

Editing commands
^^^^^^^^^^^^^^^^

+----------+------------------------------------+
| yy       | equivalent to cut also called yank |
+----------+------------------------------------+
| p        | paste below line                   |
+----------+------------------------------------+
| SHIFT p  | paste above line                   |
+----------+------------------------------------+
| dd       | deletes the current line           |
+----------+------------------------------------+
| 5dd      | deletes 5 lines                    |
+----------+------------------------------------+
| u        | undo last change                   |
+----------+------------------------------------+
| CTRL + R | Re do last change                  |
+----------+------------------------------------+

Copy (or cut) / paste (without strange indent)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1. move the mouse pointer to the beginning of your desired copy text
2. type 'v' (visual) for Visual mode, then using mouse pointer move to the end of selected text
3. type 'y' (yank) for Copy or 'd' (delete) for Cut
4. move to your paste location, then type 'p' (paste)

Tabulation
^^^^^^^^^^

1. define TAB as 2 spaces

::

   :set tabstop=2 shiftwidth=2 expandtab

2. replace TAB by 4 spaces

::

   :%s/\t/    /g

Multi-files, multi-windows
--------------------------

Opening multi-files / another file
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ vim file1 file2 file3 ...

::

   :n        edit next file among multi-files
             (with respect to the order given in the command line)
   :wn       save the modification and edit the next file
   :n!       edit the next file without saving the ongoing modification
   :e        reload the current file
   :e file   load file in the current window


Multi-windows
^^^^^^^^^^^^^

::

   :sp(lit) file   split horizontally the window and load file in the splitted window
   :vsplit file    split vertically the window and load file in the splitted window
   :vs             vertically split window
   CTRL + w + w    switch among all (sub-)windows
   :q              close the current (sub-)window

Search and Replace
------------------

Searching commands
^^^^^^^^^^^^^^^^^^

::

   /Exception   will search for word "Exception" from top to bottom and stop when it got
                first match, to go to next match type "n" and for coming back to previous
                match press "Shift + N"
   ?Exception   will search for word "Exception" from bottom to top and stop when it got
                first match, to go to next match type "n" and for coming back to previous
                match press "Shift + N", remember for next match it will go towards top
                of file.

Find and replace
^^^^^^^^^^^^^^^^

::

   :%s/Old/New/g     This is an example of global search it will replace all occurrence
                     of word "Old" in file with word "New". Its also equivalent to
                     following command ": 0,$ s/Old/New/g" which actually tells that
                     search from fist to last line.
   :%s/Old/New/gc    This is similar to first command but with the introduction of "c"
                     it will ask for confirmation
   :%s/Old/New/gci   This is command is global, case insensitive and ask for confirmation.
                     to make it case Sensitive use "I"

Substitution
^^^^^^^^^^^^

Substitution is very useful when working with text. Below you have some example. For more information, you could check the link : http://vim.wikia.com/wiki/Search_and_replace

::

   :s/abc/def/           change the first 'abc' of the line to 'def'
   :s/abc/def/g          change all 'abc' of the line to 'def'
   :%s/abc/def/g         change all 'abc' of all lines to 'def'
   :%s/\<abc\>/def/g     change all words 'abc' of all lines to 'def'
   :%s/\<abc\>/def/gI    change all words 'abc' (case sensitive) of all lines to 'def'
   :%s/\<abc\>/def/gci   change all words 'abc' (case insensitive) of all lines to 'def',
                         ask for confirmation
   :5,10s/abc/def/g      change all 'abc' to 'def', from line 5 to line 10 inclusive
   :.,+5s/abc/def/g      change all 'abc' to 'def', for the current line and the 5 next
                         lines
   :.,$s/abc/def/g       change all 'abc' to 'def', from the current line to the last line
   :g/^a/s/abc/def/g     change all 'abc' to 'def', for each line starting with 'a'
