---
layout: post
title: Day 4 of Python
tags: [python, camps, information, game dev]
---

Hello World! Today we got a picture moving on the screen using the simpleGUI canvas and key handlers. For those of you who did not get it to work, there are some issues with the simpleGUI frame library, which isn't something we can fix. The working code that we wrote today is down below the link that you can use to also access the [working code](http://www.codeskulptor.org/#user43_Z5SMaSAu7D_1.py "CodeSkulptor Code").

    try:
        import simplegui

        from user40_nMs7JxzimyImAv2 import Loader

        SIMPLEGUICS2PYGAME = False
    except ImportError:
        import SimpleGUICS2Pygame.simpleguics2pygame as simplegui

        from SimpleGUICS2Pygame.simplegui_lib_loader import Loader

        SIMPLEGUICS2PYGAME = True

        simplegui.Frame._hide_status = True

    position = [200,200] #x,y
    pressed = set() #create an empty set
    keyPressed = False

    def init():
        frame.set_draw_handler(draw)
        frame.set_keyup_handler(keyup)
        frame.set_keydown_handler(keydown)

    def move():
        for key in pressed:
            if key == simplegui.KEY_MAP['w']:
                # w means up
                position[1] = position[1] - 5
            elif key == simplegui.KEY_MAP['d']:
                # d means right
                position[0] = position[0] + 5
            elif key == simplegui.KEY_MAP['a']:
                # a means left
                position[0] = position[0] - 5
            elif key == simplegui.KEY_MAP['s']:
                # s means down
                position[1] = position[1] +5


    def keydown(key):
        global keyPressed
        keyPressed = True
        pressed.add(key)

    def keyup(key):
        global keyPressed
        pressed.remove(key)
        if len(pressed) == 0:
            keyPressed = False
        # do the exact opposite of keydown
    def draw(canvas):
        global keyPressed
        img = loader.get_image('asteroid')  # get an image by its name
        canvas.draw_image(img,
                          (img.get_width()/2, img.get_height()/2),
                          (img.get_width(), img.get_height()),
                           position,
                          (img.get_width(), img.get_height()))
        if keyPressed:
            move()

    loader = Loader(400,  # the frame
                    400,  # the width frame
                    init) 

    loader.add_image('https://user-images.githubusercontent.com/12438494/27392441-5c6a767e-56af-11e7-9c5d-50fbd9be0e03.jpg',
                     'asteroid')
    frame = simplegui.create_frame('Testing', 400, 400)
    frame.set_draw_handler(draw) # draw is the function

    loader.load()

    loader.wait_loaded()

    frame.start()

Tomorrow we will make a full-fledged game! And yes, you will be able to customize the sprites with your own images. :)
