---
title: "IDEA292 Final Project"
permalink: /ideas/292final/
excerpt_separator: "<!--more-->"
author_profile: false
---
*Collaborated with Genna Olavarri*

In the culmination of the IDEA292 course, the final was an open-ended project where the the only main requirement was to create a lighting system. 

**Brainstorm**

We knew from the start that wanted to combine our project with some software elements. Our initial idea was to create a program that would abstract an image to LED matrix, which would further be abstracted by a geometric outer panel. 

We later to moved to idea that involved creating a mobile app that scans and abstracts an image of a users eye, adding an interative element to the project. The outer panel would also be changed to be composed of smaller, modular units, so that when assembled it would add some tactility and dynamic movement to the LED matrix panel.

INSERT PICTURES FROM SLIDES HERE

**Materials**

- Wood: for the frame that would house the components
- ESP32: as the microcontroller
- PETG: for the 3D printed modular outer panel
- Four 8x32 LED matricies: for the 32x32 LED matrix

**The App**

We utilized Apple's vision framework to create the eye detection app. The app would capture an image of the users eye and save it onto the phone and cover the colors from the image to RGB values to be read on the LED matrix. We quickly realized, that the raw images were not feasible as the LED matrix could not handle darker colors like brown or black. We tried different apporaches in the code like image filtering, or changing the contrast in the image. Ultimately, we created a color abstraction algorithm that would map the colors in the orignal image to the closest RGB values that would appear on the LEDs. 

INSERT IMAGES FROM APP

**LED matrix**

The 32x32 LED matrix was composed of 4 smaller 8x32 LED matricies. Originially it was powered by a 5 volt power supply; however, when trying to turn on the full 32x32 array, the power supply couldn't handle it, so it was swtiched to another more powerful power supply brick. The LEDs were controlled using an ESP32 using MicroPython. Controlling the LEDs was not problem. A custom LED matrix class was coded based of existing LED libraries to control the full 32x32 matrix. However, there were some limitations when it came to network connectivity. The Wifi capabilities of the ESP32 were not working properly as there was inconsistency when trying to send the image data from our app to the ESP32. Also, the data we were trying to send appeared to be to bigger than what the ESP32's hardware could handle. In the end, we had to manually upload sample images we collected to the ESP32.

INSERT IMAGES OF LEDs and ESP

**PETG Panel**

There were several iterations of the outer Panel. The first iteration was a static, one piece design. For the second iteration, modular units were created with bars that allowed them to connect together. Although, this allowed for some movement, the overall mobility was still limited to the design of the bars. A variation that used external dowels to hold the units together was created. While this allowed for more movement, we felt the use of the additional dowels was unnecessary. The final design, untilized pegs on each until that allowed them to be connected without any extra pieces and did not sacrifice any mobility.

INSERT IMAGES OF PETG PANEL

**Frame**

The LED matrix and panel were housed in a simple but effect wooden frame. The contruction was made of 4 edges with a recessed portion on the outer edges to hold the 3D printed outer panel. The frame was also stained to create a smooth and polished finish.

INSERT images of frame.

**Final Product**

Overall the physcial construction of the project was a success. The PETG panel and LED Matrix were housed seamlessly in the wooden frame. The app work well and the color abstraction of the images gave insterseting and aesthetic results. The limitations with the ESP32 were disappointing, but given more time and use of more power hardware, such a Raspberry Pi, the issues could be addressed and solved.

Images of final product.