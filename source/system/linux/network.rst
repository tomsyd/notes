Network
=======

There are many network dedicated tools. Here are several ones among the most common ones:

+----------------+-----------------------------------------------------------+
| ``hostname``   | finding host/domain name and IP address                   |
+----------------+-----------------------------------------------------------+
| ``ping``       | test network connectionng                                 |
+----------------+-----------------------------------------------------------+
| ``ifconfig``   | getting network configuration                             |
+----------------+-----------------------------------------------------------+
| ``netstat``    | network connections, routing tables, interface statistics |
+----------------+-----------------------------------------------------------+
| ``nslookup``   | query DNS lookup name                                     |
+----------------+-----------------------------------------------------------+
| ``telnet``     | communicate with other hostname                           |
+----------------+-----------------------------------------------------------+
| ``traceroute`` | outing steps that packets take to get to network host     |
+----------------+-----------------------------------------------------------+
| ``finger``     | view user information                                     |
+----------------+-----------------------------------------------------------+
| ``telnet``     | checking status of destination host                       |
+----------------+-----------------------------------------------------------+

Some examples are given below.

Show the hostname

.. code-block:: shell

   $ hostname

Show the domain

.. code-block:: shell

   $ hostname -d

Show the full host and domain name

.. code-block:: shell

   $ hostname -f

Show the IP

.. code-block:: shell

   $ hostname -i

Show process id of applications using the given port

.. code-block:: shell

   $ netstat -nap | grep port_number

Show multicast network subscribed by the host

.. code-block:: shell

   $ netstat -g

Show IP

.. code-block:: shell

   $ nslookup host.domain

Show name

.. code-block:: shell

   $ nslookup IP_address

Use mount for accessing a NFS file system

.. code-block:: shell

   $ mount -t nfs host:path_to_your_mountpoint

Transfer
--------

``scp`` is one of tools for the file transfer.

Transfer (multi) files

.. code-block:: shell

   $ scp djiang@remote_host:/path/to/folder/*.py .

Transfer a folder

.. code-block:: shell

   $ scp -r djiang@remote_host:/path/to/folder .

There exist many other tools which permit the transfer from one host to another : ``rsync``, ``sftp``, etc.

SSH
---

ssh is used to connect a remote host

.. code-block:: shell

   $ ssh login@remote_host

Remote host
-----------

Check if a remote host is alive

.. code-block:: shell

   $ ping host
   $ telnet host

Find remote hosts which are connecting to your host on a particular port?

using ``netstat`` command, execute

.. code-block:: shell

   $ netstat -a | grep port_number

How to check if a particular process is listening on a particular port on remote host?

By using ``telnet`` command for example

.. code-block:: shell

   $ telnet hostname port

if it is able to successfully connect then some process is listening on that port.

Connections
-----------

Show all connections, including TCP and UDP

.. code-block:: shell

   $ netstat -all
   $ netstat -a

Show TCP connections

.. code-block:: shell

   $ netstat --tcp
   $ netstat -t

Show UDP connections

.. code-block:: shell

   $ netstat --udp
   $ netstat -u
