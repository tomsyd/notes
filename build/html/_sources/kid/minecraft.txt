Minecraft Pi Edition
====================

Basic commands
--------------

+----------------------------------+-------------------------------+
| **W**                            | move forward                  |
+----------------------------------+-------------------------------+
| **S**                            | move backward                 |
+----------------------------------+-------------------------------+
| **A**                            | move left                     |
+----------------------------------+-------------------------------+
| **D**                            | move right                    |
+----------------------------------+-------------------------------+
| **E**                            | show inventory of blocks      |
+----------------------------------+-------------------------------+
| **1**-**8**                      | select items in the quick bar |
+----------------------------------+-------------------------------+
| **Space** / **Ctrl** + **Space** | jump (ascend in fly-mode)     |
+----------------------------------+-------------------------------+
| **Shift** / **Ctrl** + **Shift** | sneak (descend in fly-mode)   |
+----------------------------------+-------------------------------+
| **ESC**                          | pause / menu                  |
+----------------------------------+-------------------------------+
| left mouse                       | destroy blocks                |
+----------------------------------+-------------------------------+
| right mouse                      | place blocks                  |
+----------------------------------+-------------------------------+
| double **Space**                 | fly / fall                    |
+----------------------------------+-------------------------------+
| **Tab**                          | release mouse                 |
+----------------------------------+-------------------------------+

List of python programs
-----------------------

Short-cuts
^^^^^^^^^^

+------------------+------+
| **Ctrl** + **S** | save |
+------------------+------+
| **F5**           | run  |
+------------------+------+

Display the player's position
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python
   :linenos:

   from mcpi import minecraft
   
   mc = minecraft.Minecraft.create()
   
   x,y,z = mc.player.getTilePos()
   mc.postToChat("x="+str(x)+", y="+str(y)+", z="+str(z))

Teleport (change the player's position)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In the following program, the player will be teleported 100 higher.

.. code-block:: python
   :linenos:

   from mcpi import minecraft
   
   mc = minecraft.Minecraft.create()
   
   x,y,z = mc.player.getTilePos()
   mc.player.setPos(x,y+100,z)

Build a huge block of activated TNTs
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When you click one TNT, there will be an explosion around that block of TNTs.

.. code-block:: python
   :linenos:

   from mcpi import minecraft
   
   mc = minecraft.Minecraft.create()
   
   x,y,z = mc.player.getTilePos()
   
   tnt = 46
   activated = 1
   mc.setBlocks(x+1,y+1,z+1,x+5,y+5,z+5,tnt,activated)

Put a flower on the path
^^^^^^^^^^^^^^^^^^^^^^^^

We will leave a flower when we are on a block of grass. Otherwise we will change the beneath block to a grass block.

.. code-block:: python
   :linenos:

   from mcpi import minecraft
   from time import sleep
   
   mc = minecraft.Minecraft.create()
   
   grass = 2
   flower = 38
   while True:
       x,y,z = mc.player.getTilePos()
       block_beneath = mc.getBlock(x,y-1,z)
       if block_beneath == grass:
           mc.setBlock(x,y,z,flower)
       else:
           mc.setBlock(x,y-1,z,grass)
       sleep(0.1)

Clear space with input size
^^^^^^^^^^^^^^^^^^^^^^^^^^^

We will clear space for a given **size**. To do so, we will build a cube of **size** x **size** x **size** blocks, filled with the AIR block.

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   
   mc = minecraft.Minecraft.create()
   
   x,y,z = mc.player.getTilePos()
   size = int(raw_input("size of area to clear? "))
   if size > 0:
       mc.setBlocks(x,y,z,x+size,y+size,z+size,block.AIR.id)

Challenge: Change a little the above program so that the player is in the middle of the cleared space (and also dig down a few blocks).

