Pygame
======

List of pygame programs
-----------------------

Draw a circle
^^^^^^^^^^^^^

.. code-block:: python
   :linenos:

   import pygame
   
   width,height = 640,480
   radius = 100
   fill = 1
   
   pygame.init()
   window = pygame.display.set_mode((width,height))
   window.fill(pygame.Color(255,255,255)) # white
   
   while True:
       pygame.draw.circle(window,
                          pygame.Color(255,0,0), # red
                          (width/2,height/2),
                          radius,
                          fill)
       pygame.display.update()
       if pygame.QUIT in [e.type for e in pygame.event.get()]:
           break

Draw circles based on mouse move / position
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python
   :linenos:

   import pygame
   from pygame.locals import *
   
   width,height = 640,640
   radius = 0
   fill = 1
   mouseX,mouseY = 0,0
   
   pygame.init()
   window = pygame.display.set_mode((width,height))
   window.fill(pygame.Color(255,255,255)) # white
   fps = pygame.time.Clock() # FPS = Frame Per Second
   
   while True:  # one frame per loop
       for event in pygame.event.get():
           if event.type == MOUSEMOTION:
               mouseX,mouseY = event.pos
           if event.type == MOUSEBUTTONDOWN: # mouse click
               window.fill(pygame.Color(255,255,255)) # clear screen
           radius = (abs(width/2 - mouseX) + abs(height/2 - mouseY))/2 + 1
           pygame.draw.circle(window,
                              pygame.Color(255,0,0), # red
                              (mouseX,mouseY),
                              radius,
                              fill)
       pygame.display.update()
       if pygame.QUIT in [e.type for e in pygame.event.get()]:
           break
       fps.tick(30) # wait so that frame rate is 30 fps
