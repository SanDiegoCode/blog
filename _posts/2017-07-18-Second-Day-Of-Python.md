---
layout: post
title: Day Two of Python
date: 2017-07-18
author: Nir Levin
hero: /images/webdevday1.jpg
tags:
 - information
 - camps
 - python
 - game dev
---

Today we had the second session for the Python camp, where we explored if/else structures, as well as data structures, loops, and functions.Everyone did a great job with the custom-message-based-on-input challenge. The logic was understood, but a lot of the problems arose from formatting - I can't stress enough how important that is to python.	in = int(input("How much money do you have?"))	if in >= 0 and in < 1000000:		print "You have a normal amount of money"	elif in >= 1000000 and in < 1000000000:		print "You are a millionare"	elif in >= 1000000000:		print "You are a billionare"	else:		print "INVALID"Really pay attention to spaces, tabs, linebreaks, and syntax such as colons and parentheses!Then, we dove into python collections, namely lists and dictionaries. **List** values are *ordered* by integer keys, or indexes. In order to call a certain value, i.e. the fifth one, we would use	someList[4]because lists start at and index of zero.A **Dictionary** works like a list, except for the facts that: - Dicitonary values are *unordered* - Keys, or indexes, do not have to be integers; most commonly they are strings - whereas all list values have to be of the same type, dictionary values do not, as we saw today with the "profile"	profile = {'age':12,'name':'joe','limbs':['left leg','right leg','left arm','right arm']}These values are all different, being an integer, a string, and a list. We can call the name, for example, using	profile['name']We then went into loops like the one below, which repeat code inside of them until the list being used is exhausted:	for num in range(1,101):		print numThe range() function creates a list with all numbers between the specified parameters. This loop keeps looping until the numbers 1 to 100 are exhausted, so it loops 100 times.Lastly, we had a brief look into functions. These are a type of procedure that may or may not return values, and that may or may not take in values. The example we looked at today,	def pineapplification(profile):		#codedid both.Tomorrow we will look more into functions, and finally get into using CodeSkulptor's simplegui (mainly event handlers)! Yes, you can output images using simplegui, but you can also do so much more...