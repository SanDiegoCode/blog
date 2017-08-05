---
layout: post
title: Third Java Session!
date: 2017-07-06
author: ronak
hero: https://cdn2.hubspot.net/hubfs/2486034/Vaporware%20Stock%20Images/hello_world.gif
tags:
 - information
 - camps
 - java
 - summary
---
Thank you to everyone who came today!

Today, we went over while loops and taught everyone how to count by 2s. For those of you who didn't see the solution, here it is:

```
int count = 0;
while (count < 10) {
   System.out.println(count);
   count = count + 2;
}
```

After that, we started going into input and output.

To do this, we downloaded the [required libraries](downloads/sandiegocodelibraries.zip) and added them to BluJ

To add libraries to BluJ:
1. Open Preferences (Cmd/Ctrl Comma)
2. Click Libraries 
3. Add file
4. Choose the extracted files

Here's how to use `ConsoleIO` to do input and output

```
import chn.util.*;

class Main {
	public static void main(String[] args) {
		ConsoleIO input = new ConsoleIO();
		System.out.println("What is your name?");
		String name = input.readLine();
		System.out.println("Nice to meet you, " + name);
	}
}
```

After that, we let everyone work on their text adventure games. We will be awarding prizes to the best 3 games tomorrow!

![ice cream](/images/icecream.jpg)
What the prizes might be.