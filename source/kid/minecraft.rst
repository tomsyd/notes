Minecraft Pi Edition
====================

List of interesting python programs running with the Minecraft Pi Edition.

Display the player's position
-----------------------------

.. code-block:: python
   :linenos:

   from mcpi import minecraft
   
   mc = minecraft.Minecraft.create()
   
   x,y,z = mc.player.getTilePos()
   mc.postToChat("x="+str(x)+", y="+str(y)+", z="+str(z))
