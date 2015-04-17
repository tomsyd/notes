Archive and Compression
=======================

tar (Tape ARchiver)
-------------------

tar is very useful to backup / group your files. You could group your files / folders with

.. code-block:: shell

   $ tar cvf backup.tar file1 file2 ... folder1 folder2 ...

To extract content of a tar file, just do the following

.. code-block:: shell

   $ tar xvf backup.tar

N.B. tar is probably one of the first commands existing in the Unix / Linux world. You could invoke its options with a dash or not, this will not change the result.

tar options
^^^^^^^^^^^

Here is a list of some useful options :

+-----------+------------------------------------------------------------------------------------------+
| c         | create, for creating tar file                                                            |
+-----------+------------------------------------------------------------------------------------------+
| v         | verbose, display name of files including,excluding from tar command                      |
+-----------+------------------------------------------------------------------------------------------+
| f         | following, used to point name of tar file to be created.                                 |
|           +------------------------------------------------------------------------------------------+
|           | it actually tells tar command that name of the file is "next" letter just after options. |
+-----------+------------------------------------------------------------------------------------------+
| x         | extract, for extracting files from tar file.                                             |
+-----------+------------------------------------------------------------------------------------------+
| t         | for viewing content of tar file                                                          |
+-----------+------------------------------------------------------------------------------------------+
| z         | zip, tells tar command that create tar file using gzip.                                  |
+-----------+------------------------------------------------------------------------------------------+
| j         | another compressing option tells tar command to use bzip2 for compression                |
+-----------+------------------------------------------------------------------------------------------+
| r         | update or add file or directory in already existed .tar file                             |
+-----------+------------------------------------------------------------------------------------------+
| wildcards | to specify patters in unix tar command                                                   |
+-----------+------------------------------------------------------------------------------------------+

tarball
^^^^^^^

When combining with gzip, tar becomes an extremely recommanded tool to archieve your documents. The resulted file is often called tarball, and is ended with either the extension .tgz or .tar.gz. For example, to archieve files / folders into a tarball:

.. code-block:: shell

   $ tar zcvf backup.tgz file1 file2 ... folder1 folder2 ...

and to extract a tarball:

.. code-block:: shell

   $ tar zxvf backup.tgz

creation
^^^^^^^^

Create tar archive/file

.. code-block:: shell

   $ tar -cvf tarball.tar *
   $ tar -cvf tarball.tar file1 folder1 file2

Create compressed tar file (gzip, bzip2)

.. code-block:: shell

   $ tar -zcvf tarball.tgz *
   $ tar -zcvf tarball.tar.gz *
   $ tar -jcvf tarball.tar.bz2 *

extraction
^^^^^^^^^^

Extract contents from tar file

.. code-block:: shell

   $ tar -xvf tarball.tar

Extract contents from compressed tar file

.. code-block:: shell

   $ tar -zxvf tarball.tgz
   $ tar -zxvf tarball.tar.gz
   $ tar -jxvf tarball.tar.bz2

Extract a particular file from tar file

.. code-block:: shell

   $ tar -xvf tarball.tar file
   $ tar -zxvf tarball.tgz file
   $ tar -zxvf tarball.tar.gz file
   $ tar -jxvf tarball.tar.bz2 file

Extract a group of files from tar file

.. code-block:: shell

   $ tar -xvf tarball.tar --wildcards "s*"
   $ tar -zxvf tarball.tgz --wildcards "s*"
   $ tar -zxvf tarball.tar.gz --wildcards "s*"
   $ tar -jxvf tarball.tar.bz2 --wildcards "s*"

other operations
^^^^^^^^^^^^^^^^

View contents of tar file

.. code-block:: shell

   $ tar -tvf tarball.tar

View contents of compressed tar file

.. code-block:: shell

   $ tar -ztvf tarball.tgz
   $ tar -ztvf tarball.tar.gz

Update existing tar file (!not compressed tar file)

.. code-block:: shell

   $ tar -cvf tarball.tar file folder1
   $ tar -rvf tarball.tar folder2

Calculate the size (in KB) of (compressed) tar file

.. code-block:: shell

   $ tar -cf - * | wc -c
   $ tar -zcf - * | wc -c
   $ tar -jcf - * | wc -c

Delete items (files/folders) from tar file (!not compressed)

.. code-block:: shell

   $ gunzip tarball.tar.gz
   $ tar --list --file tarball.tar
   $ tar --file tarball.tar --delete file1 folder1 folder2/file2
   $ tar --list --file tarball.tar
   $ gzip tarball.tar

parallel gzip
-------------

For modern multi-processor, multi-core machines, a parallel implementation of gzip exists, called pigz. The official link is http://zlib.net/pigz/ and the manual could be downloaded here : http://zlib.net/pigz/pigz.pdf

To compress while keeping the original file, using

.. code-block:: shell

   pigz --best -k file

and to decompress the .gz file

.. code-block:: shell

   pigz -d file.gz

bz2
---

Compression to bz2
^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ bzip2 file 
   $ bzip2 -v file 

Decompression from bz2
^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ bunzip2 file.bz2
   $ bzip2 -d file.bz2
   $ bunzip2 -v file.bz2

Archive to tarball .tar.bz2
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ tar cjvf files.tar.bz2 *.txt
   $ tar -cjvf archive.tar.bz2 path/to/folder
   $ tar --bzip2 -xf path/to/file.tar.bz2
   $ tar -cvf - path/to/folder | bzip2 > archive.tar.bz2

Restore from tarball .tar.bz2
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ tar xjvf files.tar.bz2
   $ tar -xjvf path/to/file.tar.bz2
   $ bzcat path/to/file.tar.bz2 | tar -xvf -

zip
---

.. code-block:: shell

   $ zip archive.zip file1 file2 file3
   $ unzip archive.zip

lzma
----

Restore from lzma tarball
^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ tar -xYvf archive.tar.lzma

lzo
---

The difference between the format .lzo and others (.gz or .bz2) are :

- .lzo is not installed by default on your machine;
- .lzo keeps the original file, unless if you use the option -U;
- .lzo runs fast, but the compression ratio is relatively low.

When we try to pass a list of files and folders to lzop, only the files will be compressed and the folders will be skipped.

Compression to lzo
^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ lzop -v file
   $ cat file | lzop > file.lzo

Delete the original file

.. code-block:: shell

   $ lzop -U file

Test the result's integrality

.. code-block:: shell

   $ lzop -t file.lzo

Show file headers

.. code-block:: shell

   $ lzop --info file.lzo	afficher les en-têtes du ficher

Show compression information

.. code-block:: shell

   $ lzop -l file.lzo

Show content of a compressed lzo file

.. code-block:: shell

   $ lzop --ls file.lzo

Decompression from lzo
^^^^^^^^^^^^^^^^^^^^^^

The lzo file is kept by default.

.. code-block:: shell

   $ lzop -dv file.lzo

Archive all text files *.txt to a lzo tarball
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ tar --use-compress-program=lzop -cf files.tar.lzo *.txt

Restore from lzo tarball
^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: shell

   $ tar --use-compress-program=lzop -xf files.tar.lzo
