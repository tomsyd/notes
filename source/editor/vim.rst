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
   :w file.txt   save the modified file with another file name (even if the file was opened in read-only mode)
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
