Python Games
------------

Number guessing game
^^^^^^^^^^^^^^^^^^^^

.. code-block:: python
   :linenos:
   
   import random
   
   secret = random.randint(1, 99)
   guess = 0
   tries = 0
   print "AHOY! I'm the Dread Pirate Roberts, and I have a secret!"
   print "It is a number from 1 to 99. I'll give you 6 tries. "
   
   while guess != secret and tries < 6:
       guess = input("What's yer guess? ")
       if guess < secret:
           print "Too low, ye scurvy dog!"
       elif guess > secret:
           print "Too high, landlubber!"
       tries = tries + 1
   if guess == secret:
       print "Avast! Ye got it! Found my secret, ye did!"
   else:
       print "No more guesses! Better luck next time, matey!"
       print "The secret number was", secret

Number guessing game using EasyGui
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: python
   :linenos:
   
   import random, easygui
   
   secret = random.randint(1, 99)
   guess = 0
   tries = 0
   easygui.msgbox("""AHOY! I'm the Dread Pirate Roberts, and I have a secret!
   It is a number from 1 to 99. I'll give you 6 tries.""")
   while guess != secret and tries < 6:
       guess = easygui.integerbox("What's yer guess, matey?")
       if not guess: break
       if guess < secret:
           easygui.msgbox(str(guess) + " is too low, ye scurvy dog!")
       elif guess > secret:
           easygui.msgbox(str(guess) + " is too high, landlubber!")
       tries = tries + 1
   if guess == secret:
       easygui.msgbox("Avast! Ye got it! Found my secret, ye did!")
   else:
       easygui.msgbox("No more guesses! The number was " + str(secret))

