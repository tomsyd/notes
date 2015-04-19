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

grep
----

There are several variants of grep:

- grep
- egrep : extended grep
- fgrep : fixed grep
- zgrep

Grep A, but excluding B

.. code-block:: shell

   $ grep A file | grep -v B

Count the occurence of a word A

.. code-block:: shell

   $ grep -c A file

Grep A and show n lines prior to the A position and n lines after the A position

.. code-block:: shell

   $ grep --context=n A file
   $ grep -C n A file

Extended grep with more regular expression

.. code-block:: shell

   $ egrep "A|B" file

Case insensitive grep

.. code-block:: shell

   $ grep -i A file

Grep .gz file

.. code-block:: shell

   $ zgrep A file.gz

Grep whole word

.. code-block:: shell

   $ grep -w WORD file

Grep words starting with WORD

.. code-block:: shell

   $ grep '<WORD' file

Grep words ending in WORD

.. code-block:: shell

   $ grep 'WORD>' file

Grep with matching pattern in color

.. code-block:: shell

   $ grep A file --color

Grep among files matching the given pattern

.. code-block:: shell

   $ grep -l A *.log

Grep showing line number

.. code-block:: shell

   $ grep -n A file

Recursive grep

.. code-block:: shell

   $ grep -R A folder


sort
----

Sort based on the numerical order of the 2nd column

.. code-block:: shell

   $ ps -ef | sort -nk2

Sort based on the reverse numerical order of the 3rd column

.. code-block:: shell

   $ ps -ef | sort -rnk3

Sort based on the alphabetic order of the 4th column

.. code-block:: shell

   $ ps -ef | sort -nk4

Sort based on the alphabetic order

.. code-block:: shell

   $ cat file | sort
   $ sort file

Sort based on the alphabetic order, and remove duplicates

.. code-block:: shell

   $ cat file | sort | uniq
   $ cat file | sort -u
   $ sort -u file

Sort file, case insensitive

.. code-block:: shell

   $ sort -f file

sed
---

Replace word A by B in a file

.. code-block:: shell

   $ sed s/A/B/g file

cat
---

Create a new file and fill it

.. code-block:: shell

   $ cat > file.txt
   fill the file
   ...
   CTRL+D

Append new input to a file (so, keep its current content)

.. code-block:: shell

   $ cat >> file.txt
   append the file
   ...
   CTRL+D

Displaying with line numbers (option -b will number only non-empty lines)

.. code-block:: shell

   $ cat -n file.txt
   $ cat -b file.txt

Copy files

.. code-block:: shell

   $ cat file1 > file2

Concatenating files

.. code-block:: shell

   $ cat file 1 file2 > file

Squeezing repeating blank lines into one

.. code-block:: shell

   $ cat -s file

Show non-printing chars (^V, ^M, etc.)

.. code-block:: shell

   $ cat -v file

top / htop
----------

By default, the display of top is ordered by CPU usage

.. code-block:: shell

   $ top

In the top interface, you have the following choices

+--------+------------------------------+
| M      | ordered by Memory usage      |
+--------+------------------------------+
| 1      | display all CPUs             |
+--------+------------------------------+
| c      | display path of commands     |
+--------+------------------------------+
| k      | kill a process via its PID   |
+--------+------------------------------+
| z      | highlight running processes  |
+--------+------------------------------+
| s      | change refresh delay         |
+--------+------------------------------+
| h or ? | online help                  |
+--------+------------------------------+
| q      | quit                         |
+--------+------------------------------+
| W      | save changes (into ~/.toprc) |
+--------+------------------------------+

To work on one particular user

.. code-block:: shell

   $ top -u user

lsof
----

list all open files

.. code-block:: shell

   $ lsof

``FD`` stands for **File descriptor** and may seen some of the values as:

+-----+------------------------------+
| cwd | current working directory    |
+-----+------------------------------+
| rtd | root directory               |
+-----+------------------------------+
| txt | program text (code and data) |
+-----+------------------------------+
| mem | memory-mapped file           |
+-----+------------------------------+

Also in ``FD`` column numbers like ``1u`` is actual file descriptor and followed by u,r,w of it’s mode as:

+---+---------------------------+
| r | for read access           |
+---+---------------------------+
| w | for write access          |
+---+---------------------------+
| u | for read and write access |
+---+---------------------------+

``TYPE`` of files and it’s identification:

+------+------------------------+
| DIR  | Directory              |
+------+------------------------+
| REG  | Regular file           |
+------+------------------------+
| CHR  | Character special file |
+------+------------------------+
| FIFO | First In First Out     |
+------+------------------------+

list open files of one user

.. code-block:: shell

   $ lsof -u user

find out all the running process of specific port

.. code-block:: shell

   $ lsof -i TCP:22

shows only IPv4 and IPv6 network files

.. code-block:: shell

   $ lsof -i 4
   $ lsof -i 6

list all running process of open files of TCP Port ranges from 1-1024.

.. code-block:: shell

   $ lsof -i TCP:1-1024

exclude user with ‘^’ Character : e.g. to exclude root user

.. code-block:: shell

   $ lsof -i -u^root

find out a specific user is looking what files and commands

.. code-block:: shell

   $ lsof -i -u user

list all network connections : option '-i' shows the list of all network connections 'LISTENING & ESTABLISHED'.

.. code-block:: shell

   $ lsof -i

search by PID

.. code-block:: shell

   $ lsof -p 1

kill all activity of particular user

.. code-block:: shell

   $ kill -9 `lsof -t -u user`

netstat
-------

listing all the LISTENING Ports of TCP and UDP connections

.. code-block:: shell

   $ netstat -a | more

listing only TCP (Transmission Control Protocol) port connections

.. code-block:: shell

   $ netstat -at

listing only UDP (User Datagram Protocol ) port connections

.. code-block:: shell

   $ netstat -au

listing all active listening ports connections

.. code-block:: shell

   $ netstat -l

listing all active listening TCP ports

.. code-block:: shell

   $ netstat -lt

listing all active listening UDP ports

.. code-block:: shell

   $ netstat -lu

Listing all active UNIX listening ports

.. code-block:: shell

   $ netstat -lx

Showing Statistics by Protocol

.. code-block:: shell

   $ netstat -s

Showing statistics of TCP protocol

.. code-block:: shell

   $ netstat -st

Showing statistics of UDP Protocol

.. code-block:: shell

   $ netstat -su

Displaying service name with their PID number : option -tp will display “PID/Program Name”

.. code-block:: shell

   $ netstat -tp

Displaying Promiscuous mode with -ac switch, netstat print the selected information or refresh screen every five second. Default screen refresh in every second.

.. code-block:: shell

   $ netstat -ac 5 | grep tcp

Displaying Kernel IP routing table

.. code-block:: shell

   $ netstat -r

Showing network interface packet transactions including both transferring and receiving packets with MTU size

.. code-block:: shell

   $ netstat -i

Showing Kernel interface table, similar to ifconfig command.

.. code-block:: shell

   $ netstat -ie

Displaying multicast group membership information for both IPv4 and IPv6

.. code-block:: shell

   $ netstat -g

Print netstat information every few second

.. code-block:: shell

   $ netstat -c

Finding un-configured address families with some useful information

.. code-block:: shell

   $ netstat --verbose

Find out how many listening programs running on a port

.. code-block:: shell

   $ netstat -ap | grep http

Displaying RAW Network Statistics

.. code-block:: shell

   $ netstat --statistics --raw
