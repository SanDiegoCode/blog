---
layout: post
title: Day 3 of Python
tags: [information, camps, python, game dev]
---

Hello, World!

Today we learned about **sets**, which are basically lists that are unordered, and contain the "set" of all unique values in a list. For example, a list may contain:

	myList = [1,1,3,2,3,2,1]

but calling the set 

	mySet = set(myList)

will return the set of all unique items in the list (in no particular order!).

	[(2,3,1)]

In addition, we went over iterating through sets as well as reviewed functions. The concept of functions is very important moving on, so make sure you understand it! Here is the example of a function definition with a call to it:

	def printSet(someSet):
		for item in someSet:
			print item

	printSet(mySet)
	printSet(mySet)
	printSet(mySet)

Here we define a function called printSet, and call it three times. The output would be

	2
	3
	1
	2
	3
	1
	2
	3
	1

using *mySet* from earlier.

Finally, we reached the exciting part: graphics!

Here is the code we worked on today, which we will go into more detail tomorrow:


    try:
        import simplegui

        from user40_nMs7JxzimyImAv2 import Loader

        SIMPLEGUICS2PYGAME = False
    except ImportError:
        import SimpleGUICS2Pygame.simpleguics2pygame as simplegui

        from SimpleGUICS2Pygame.simplegui_lib_loader import Loader

        SIMPLEGUICS2PYGAME = True

        simplegui.Frame._hide_status = True

    def init():
        frame.set_draw_handler(draw)

    def draw(canvas):
        img = loader.get_image('asteroid')  # get an image by its name
        canvas.draw_image(img,
                          (img.get_width()/2, img.get_height()/2),
                          (img.get_width(), img.get_height()),
                          (200,200),
                          (img.get_width(), img.get_height()))

    loader = Loader(400,  # the frame
                    400,  # the width frame
                    init) 

    loader.add_image('your-url-here', 
                     'asteroid')
    frame = simplegui.create_frame('Testing', 400, 400)

    loader.load()

    loader.wait_loaded()

    frame.start()

In *your-url-here* you will place instead the url of your image. In order to get this url, do a google image search of your image. Click on the icon, then click on **view image**. Copy the url at the top bar.

Tomorrow we will make this image interactive, using key handlers and mousehandlers, and I will also walk you through what the game will be (Hint: Pong)
We will start developing the game tomorrow!
