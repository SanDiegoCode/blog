---
layout: post
title: Final Day of Python (Making Pong The Game)
author: Ronak Shah
tags: [python, camps, information, game dev]
---

Today was the final day of python camp, but we'll be starting our **Workshop Program** next Friday, from 4:00 - 5:30

Today we created a simple pong game

![Pong Game](/images/pongpicture.png)

Here is the [completed code](http://www.codeskulptor.org/#user43_zDvmJQ4kXW_0.py)

If you'd like to follow along as to how we made it, go to [the started project](http://www.codeskulptor.org/#user43_CnuKuZxRuJ_0.py)

If you'll notice here, we need to fill out a few functions. 

- [The Init Function](#the-init-function)
- [The Keydown Function](#the-keydown-function)
- [The Keyup Function](#the-keyup-function)
- [The Move Function](#the-move-function)
- [The Collision Detections Function](#the-collision-detections-function)
- [The Player Collision Function](#the-player-collision-function)
- [The Draw Function](#the-draw-function)
- [Common Errors](#common-errors)


### The Init Function

The code for the init function is as follows below.

	def init():
	    frame.set_draw_handler(draw)
	    frame.set_keydown_handler(keydown)
	    frame.set_keyup_handler(keyup)
	    
	    players['p1'] = {'position':[25,300],'nodir':' ','score':0}
	    players['p1']['keys'] = [simplegui.KEY_MAP['w'],
	                simplegui.KEY_MAP['s']]
	    players['p2'] = {'position':[975,300],'nodir':' ','score':0}
	    players['p2']['keys'] = [simplegui.KEY_MAP['up'],
	                simplegui.KEY_MAP['down']]
	    ball_reset()
	    
In this function, we first set all the handlers, using the appropraite `frame.set_handlertype_handler(handlerFunction)` command.

After that, we set the player attributes (position, score, keys, and the direction that the player CANNOT go)

**Note: If you'd like to change the keys used to control the individual players, this is where it's done**

Simply change the `players['p1']['keys']` object accordingly.

### The Keydown Function

	def keydown(key):
	    global keypressed
	    global pressed
	    keypressed = True
	    pressed.add(key)

Here, we add the key to `keypressed` and set keypressed to true, so we can handle it later in `draw`

### The Keyup Function

	def keyup(key):
	    global keypressed
	    global pressed
	    pressed.remove(key)
	    if(len(pressed) == 0):
	        keypressed = False
This function, called after the user lifts their finger of a key, simply removes that key from 'pressed' and also sets keypressed to False (if there are no other keys being pressed)

### The Move Function

	def move():
	    global pressed
	    
	    for player in players.items():
	        keys = player[1]['keys']
	        position = player[1]['position']
	        nodir = player[1]['nodir']
	        if keys[0] != nodir and keys[0] in pressed:
	            position[1] = position[1] - velocity
	        elif keys[1] != nodir and keys[1] in pressed:
	            position[1] = position[1] + velocity


In the move function, we'll iterate through our list of players, then get each player object, then move accordingly.

### The Collision Detections Function
            
	def collision_detections():
	    player_collision()
	    ball_collision()

For this function all we need to do is call the `player_collision` method and the `ball_collision` function. We'll be filling out `player_collision` next


### The Player Collision Function
		
	def player_collision():
	    for player in players.items():
	        ypos = player[1]['position'][1]
	        keys = player[1]['keys']
	        if ypos <= 65:
	            player[1]['nodir'] = keys[0]
	        elif ypos >= height - 65:
	            player[1]['nodir'] = keys[1]
	        else:
	            player[1]['nodir'] = ' '

Here, we'll iterate through each player, then get the x and y coordinates of the player. Then, we check to see if the player is going too high or too low (offscreen). If it is, we set the players `nodir` accordingly

### The Draw Function

Finally, we just need to fill out the draw function. It's mostly been done already, but we need to add the logic to it (at the end)

	def draw(canvas):
	
	# the code that was there before
	
	if keypressed:
        move()
    ballmove()
    collision_detections()
    
We simply need to check if a key is pressed (if so, we'll move)

We also need to move the ball and check for any collision detection


Thats it! We hope you had a lot of fun and that you come next week to our workshops!

As always, if you have any questions, email us at [contact@sdcoding.com](mailto:contact@sdcoding.com)


### Common Errors

***File 'user40_nMs7JxzimyImAv2.py', Line 378: AttributeError: 'int' object has no attribute 'set_draw_handler'***

This error is a problem with the `simplegui` library, and can usually be fixed with a reload / re run of the code

