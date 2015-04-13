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

Available blocks in Minecraft Pi Edition
----------------------------------------

+---------------------+---------------+
| AIR                 | Block(0)      |
+---------------------+---------------+
| STONE               | Block(1)      |
+---------------------+---------------+
| GRASS               | Block(2)      |
+---------------------+---------------+
| DIRT                | Block(3)      |
+---------------------+---------------+
| COBBLESTONE         | Block(4)      |
+---------------------+---------------+
| WOOD_PLANKS         | Block(5)      |
+---------------------+---------------+
| SAPLING             | Block(6)      |
+---------------------+---------------+
| BEDROCK             | Block(7)      |
+---------------------+---------------+
| WATER_FLOWING       | Block(8)      |
+---------------------+---------------+
| WATER               | WATER_FLOWING |
+---------------------+---------------+
| WATER_STATIONARY    | Block(9)      |
+---------------------+---------------+
| LAVA_FLOWING        | Block(10)     |
+---------------------+---------------+
| LAVA                | LAVA_FLOWING  |
+---------------------+---------------+
| LAVA_STATIONARY     | Block(11)     |
+---------------------+---------------+
| SAND                | Block(12)     |
+---------------------+---------------+
| GRAVEL              | Block(13)     |
+---------------------+---------------+
| GOLD_ORE            | Block(14)     |
+---------------------+---------------+
| IRON_ORE            | Block(15)     |
+---------------------+---------------+
| COAL_ORE            | Block(16)     |
+---------------------+---------------+
| WOOD                | Block(17)     |
+---------------------+---------------+
| LEAVES              | Block(18)     |
+---------------------+---------------+
| GLASS               | Block(20)     |
+---------------------+---------------+
| LAPIS_LAZULI_ORE    | Block(21)     |
+---------------------+---------------+
| LAPIS_LAZULI_BLOCK  | Block(22)     |
+---------------------+---------------+
| SANDSTONE           | Block(24)     |
+---------------------+---------------+
| BED                 | Block(26)     |
+---------------------+---------------+
| COBWEB              | Block(30)     |
+---------------------+---------------+
| GRASS_TALL          | Block(31)     |
+---------------------+---------------+
| WOOL                | Block(35)     |
+---------------------+---------------+
| FLOWER_YELLOW       | Block(37)     |
+---------------------+---------------+
| FLOWER_CYAN         | Block(38)     |
+---------------------+---------------+
| MUSHROOM_BROWN      | Block(39)     |
+---------------------+---------------+
| MUSHROOM_RED        | Block(40)     |
+---------------------+---------------+
| GOLD_BLOCK          | Block(41)     |
+---------------------+---------------+
| IRON_BLOCK          | Block(42)     |
+---------------------+---------------+
| STONE_SLAB_DOUBLE   | Block(43)     |
+---------------------+---------------+
| STONE_SLAB          | Block(44)     |
+---------------------+---------------+
| BRICK_BLOCK         | Block(45)     |
+---------------------+---------------+
| TNT                 | Block(46)     |
+---------------------+---------------+
| BOOKSHELF           | Block(47)     |
+---------------------+---------------+
| MOSS_STONE          | Block(48)     |
+---------------------+---------------+
| OBSIDIAN            | Block(49)     |
+---------------------+---------------+
| TORCH               | Block(50)     |
+---------------------+---------------+
| FIRE                | Block(51)     |
+---------------------+---------------+
| STAIRS_WOOD         | Block(53)     |
+---------------------+---------------+
| CHEST               | Block(54)     |
+---------------------+---------------+
| DIAMOND_ORE         | Block(56)     |
+---------------------+---------------+
| DIAMOND_BLOCK       | Block(57)     |
+---------------------+---------------+
| CRAFTING_TABLE      | Block(58)     |
+---------------------+---------------+
| FARMLAND            | Block(60)     |
+---------------------+---------------+
| FURNACE_INACTIVE    | Block(61)     |
+---------------------+---------------+
| FURNACE_ACTIVE      | Block(62)     |
+---------------------+---------------+
| DOOR_WOOD           | Block(64)     |
+---------------------+---------------+
| LADDER              | Block(65)     |
+---------------------+---------------+
| STAIRS_COBBLESTONE  | Block(67)     |
+---------------------+---------------+
| DOOR_IRON           | Block(71)     |
+---------------------+---------------+
| REDSTONE_ORE        | Block(73)     |
+---------------------+---------------+
| SNOW                | Block(78)     |
+---------------------+---------------+
| ICE                 | Block(79)     |
+---------------------+---------------+
| SNOW_BLOCK          | Block(80)     |
+---------------------+---------------+
| CACTUS              | Block(81)     |
+---------------------+---------------+
| CLAY                | Block(82)     |
+---------------------+---------------+
| SUGAR_CANE          | Block(83)     |
+---------------------+---------------+
| FENCE               | Block(85)     |
+---------------------+---------------+
| GLOWSTONE_BLOCK     | Block(89)     |
+---------------------+---------------+
| BEDROCK_INVISIBLE   | Block(95)     |
+---------------------+---------------+
| STONE_BRICK         | Block(98)     |
+---------------------+---------------+
| GLASS_PANE          | Block(102)    |
+---------------------+---------------+
| MELON               | Block(103)    |
+---------------------+---------------+
| FENCE_GATE          | Block(107)    |
+---------------------+---------------+
| GLOWING_OBSIDIAN    | Block(246)    |
+---------------------+---------------+
| NETHER_REACTOR_CORE | Block(247)    |
+---------------------+---------------+

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

.. sidebar:: Challenge

   Change a little the above program so that the player is in the middle of the cleared space (and also dig down a few blocks).

Build a house
^^^^^^^^^^^^^

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   
   mc = minecraft.Minecraft.create()
   SIZE = 20
   
   def house():
       midx = x + SIZE/2
       midy = y + SIZE/2
       mc.setBlocks(     x,       y,  z,  x+SIZE,  y+SIZE,  z+SIZE,block.COBBLESTONE.id)
       mc.setBlocks(   x+1,     y+1,z+1,x+SIZE-1,y+SIZE-1,z+SIZE-1,        block.AIR.id)
       mc.setBlocks(   x+1,     y+1,z+1,x+SIZE-1,     y+1,z+SIZE-1,       block.WOOL.id,7)
       # left window
       mc.setBlocks(   x+3,y+SIZE-3,  z,  midx-3,  midy+3,       z,      block.GLASS.id)
       # right window
       mc.setBlocks(midx+3,y+SIZE-3,  z,x+SIZE-3,  midy+3,       z,      block.GLASS.id)
       # door
       mc.setBlocks(midx-3,       y,  z,  midx+3,    midy,       z,        block.AIR.id)
       # roof
       mc.setBlocks(     x,y+SIZE+1,  z,  x+SIZE,y+SIZE+1,  z+SIZE,       block.SNOW.id)
   
   x,y,z = mc.player.getTilePos()
   
   # build a house
   house()

Build a street
^^^^^^^^^^^^^^

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   
   mc = minecraft.Minecraft.create()
   SIZE = 20
   
   def house():
       midx = x + SIZE/2
       midy = y + SIZE/2
       mc.setBlocks(     x,       y,  z,  x+SIZE,  y+SIZE,  z+SIZE,block.COBBLESTONE.id)
       mc.setBlocks(   x+1,     y+1,z+1,x+SIZE-1,y+SIZE-1,z+SIZE-1,        block.AIR.id)
       mc.setBlocks(   x+1,     y+1,z+1,x+SIZE-1,     y+1,z+SIZE-1,       block.WOOL.id,7)
       # left window
       mc.setBlocks(   x+3,y+SIZE-3,  z,  midx-3,  midy+3,       z,      block.GLASS.id)
       # right window
       mc.setBlocks(midx+3,y+SIZE-3,  z,x+SIZE-3,  midy+3,       z,      block.GLASS.id)
       # door
       mc.setBlocks(midx-3,       y,  z,  midx+3,    midy,       z,        block.AIR.id)
       # roof
       mc.setBlocks(     x,y+SIZE+1,  z,  x+SIZE,y+SIZE+1,  z+SIZE,       block.SNOW.id)
   
   x,y,z = mc.player.getTilePos()

   # build a street
   for h in range(5):
       house()
       x += SIZE

.. sidebar:: ``range(5) = range(0,5,1)``

   ``range(5)`` means the list of the first five integers starting from 0, i.e. 0, 1, 2, 3, 4.
   
   ``range(5)`` is indeed a shortcut of ``range(0,5,1)`` which means the list of integers starting from 0 and less than 5, increased 1 per step.

Magic bridge
^^^^^^^^^^^^

Put a glass bridge under the feet whenever you walk, making sure that the player will never falls into the sea or falls out of the sky.

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   import time
   
   mc = minecraft.Minecraft.create()
   
   def buildBridge():
       x,y,z = mc.player.getTilePos()
       b = mc.getBlock(x,y-1,z) # y-1 means under the feet
       if (b == block.AIR.id) or
          (b == block.WATER_STATIONARY.id) or
          (b == block.WATER_FLOWING.id):
           mc.setBlock(x,y-1,z,block.GLASS.id)
   
   while True:
       time.sleep(0.01)
       buildBridge()

Vanishing bridge
^^^^^^^^^^^^^^^^

Based on the previous magic bridge. Here we will add some more magic: whenever we are landed on a non-glass block, we will make disappear one glass block of our magic bridge.

To do this, we will build a list of all created glass blocks in order. When it will be the case, we will remove the oldest block in the list.

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   import time
   
   mc = minecraft.Minecraft.create()
   bridge = []
   
   def buildBridge():
       x,y,z = mc.player.getTilePos()
       b = mc.getBlock(x,y-1,z) # y-1 means under the feet
       if (b == block.AIR.id) or
          (b == block.WATER_STATIONARY.id) or
          (b == block.WATER_FLOWING.id):
           mc.setBlock(x,y-1,z,block.GLASS.id)
           coordinate = [x,y-1,z]
           bridge.append(coordinate)
       elif b != block.GLASS.id:
           if len(bridge) > 0:
               coordinate = bridge.pop()
               a,b,c = coordinate
               mc.setBlock(a,b,c,block.AIR.id)
               time.sleep(0.01)
   
   while True:
       time.sleep(0.01)
       buildBridge()

Vanishing bridge (Improved Version)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

One question raised by Tom on the previous version of vanishing bridge: can we remove also the bridge's one glass block when we are on a glass block which is not part of the bridge?

For this to be done, we need to check when we have a glass block, whether its coordinate is in the list of the bridge's glass blocks' coordinates.

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   import time
   
   mc = minecraft.Minecraft.create()
   bridge = []
   
   def buildBridge():
       x,y,z = mc.player.getTilePos()
       b = mc.getBlock(x,y-1,z) # y-1 means under the feet
       if (b == block.AIR.id) or
          (b == block.WATER_STATIONARY.id) or
          (b == block.WATER_FLOWING.id):
           mc.setBlock(x,y-1,z,block.GLASS.id)
           coordinate = [x,y-1,z]
           bridge.append(coordinate)
       elif b != block.GLASS.id:
           if len(bridge) > 0:
               coordinate = bridge.pop()
               a,b,c = coordinate
               mc.setBlock(a,b,c,block.AIR.id)
               time.sleep(0.01)
       else: # b == block.GLASS.id
           if [x,y-1,z] not in bridge:
               if len(bridge) > 0:
                   coordinate = bridge.pop()
                   a,b,c = coordinate
                   mc.setBlock(a,b,c,block.AIR.id)
                   time.sleep(0.01)
   
   while True:
       time.sleep(0.01)
       buildBridge()

Vanishing bridge (Simplified Version)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

There are two repeated blocks in the above code: it's our chance to create a new function!

.. code-block:: python
   :linenos:

   from mcpi import minecraft, block
   import time
   
   mc = minecraft.Minecraft.create()
   bridge = []
   
   def popBridge():
       if len(bridge) > 0:
           coordinate = bridge.pop()
           a,b,c = coordinate
           mc.setBlock(a,b,c,block.AIR.id)
           time.sleep(0.01)
   
   def buildBridge():
       x,y,z = mc.player.getTilePos()
       b = mc.getBlock(x,y-1,z) # y-1 means under the feet
       if (b == block.AIR.id) or
          (b == block.WATER_STATIONARY.id) or
          (b == block.WATER_FLOWING.id):
           mc.setBlock(x,y-1,z,block.GLASS.id)
           coordinate = [x,y-1,z]
           bridge.append(coordinate)
       elif b != block.GLASS.id:
           popBridge()
       else: # b == block.GLASS.id
           if [x,y-1,z] not in bridge:
               popBridge()
   
   while True:
       time.sleep(0.01)
       buildBridge()

Treasure Hunt
^^^^^^^^^^^^^

.. code-block:: python
   :linenos:
   
   from mcpi import minecraft, block
   import time, random
   
   mc = minecraft.Minecraft.create()
   
   score = 0
   RANGE = 5 # increase this number to make a more difficult game!
   TIMEOUT = 10
   timer = TIMEOUT
   
   treasurex = None
   treasurey = None
   treasurez = None
   
   def placeTreasure():
       global treasurex, treasurey, treasurez
       x,y,z = mc.player.getTilePos()
       treasurex = random.randint(x, x+RANGE)
       treasurey = random.randint(y+2, y+RANGE+2)
       treasurez = random.randint(z, z+RANGE)
       mc.setBlock(treasurex, treasurey, treasurez, block.DIAMOND_BLOCK.id)
   
   def checkHit():
       global score, treasurex
       events = mc.events.pollBlockHits()
       for e in events:
           x,y,z = e.pos
           if x == treasurex and y == treasurey and z == treasurez:
               mc.postToChat("HIT!")
               score += 100
               mc.setBlock(treasurex, treasurey, treasurez, block.AIR.id)
               treasurex = None
   
   def homingBeacon():
       global timer
       if treasurex != None:
           timer -= 1
           if timer == 0:
               timer = TIMEOUT
               x,y,z = mc.player.getTilePos()
               diffx = abs(x - treasurex)
               diffy = abs(y - treasurey)
               diffz = abs(z - treasurez)
               diff = diffx + diffy + diffz
               mc.postToChat("score:" + str(score) + " treasure:" + str(diff))
   
   bridge = []
   
   def buildBridge():
       global score
       x,y,z = mc.player.getTilePos()
       b = mc.getBlock(x, y-1, z)
       if treasurex == None:
           if len(bridge) > 0:
               coordinate = bridge.pop()
               a,b,c = coordinate
               mc.setBlock(a, b, c, block.AIR.id)
               mc.postToChat("bridge:" + str(len(bridge)))
               time.sleep(0.01)
       elif b != block.GOLD_BLOCK.id:
           mc.setBlock(x, y-1, z, block.GOLD_BLOCK.id)
           coordinate = [x, y-1, z]
           bridge.append(coordinate)
           score -= 1
   
   while True:
       time.sleep(0.01)

       if treasurex == None and len(bridge) == 0:
           placeTreasure()
       
       checkHit()
       homingBeacon()
       buildBridge()
