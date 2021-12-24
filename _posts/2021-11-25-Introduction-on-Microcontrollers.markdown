---
layout: post
title:  "Introduction on Microcontrolers"
date:   2021-11-25 6:00:00 +0800
categories: blog
---

# What's a Microcontrollers?
Microcontrollers are essentially a low powered embedded computer that is used to controller motors, sensors, and other devices for any electronics, mechantronics, robotics and industrial projects. You may already have encountered microcontrollers from your gadgets, appliances, printer at your office, and other IoT or automation devices. This consist of a processor, flash memory, and host of I/O.

# Arduino?
Arduino is a low powered 8-bit microcontroller, which is used for any beginner or advance projects. The typical Arduino flavor that you might have heard is the Arduino Uno.

![Typical Arduino Uno Clone](/img/duino.png "Typical Arduino Uno Clone")


# Modules
These are devices/components that allows you to have a ready use I/O i.e. motors and sensors devices, it can be use to controll, gather data, store data, or produce data. Modules are oftenly interchanged with the term sensors.

# Sensors
These are components used to collect data either environmental, digital or analog.

# Arduino IDE Syntax
Programming with arduino is easy, if you have a background or experience using C language or C++ you can practically use the Arduino IDE to control modules and collect data from it, the Arduino IDE. You can use library written in C++ to make it easier and save time instead of you manually controlling and LCD screen or sensor you can just use the readily available opensourced libraries, with opensourced libraries on thoudsand of sensors and modules this greatly impacts the availability to learn microcontrollers for beginners.

# Syntax Basics
Typically upon opening the IDE you'll see;
```
void setup(){

}

void loop(){

}
```
these are functions are set upon creating a new file, ```setup()``` function allows you to setup the serial baud rate, the pinouts for your sensors or modules, while the ```loop()``` allows you to set a code that contstantly being repeated e.g. refreshing an LCD screen every 1 second.  

![Typical Arduino Uno Clone](/img/ss.png "Typical Arduino Uno Clone")


# Resources
You can Learn more about the syntax and its functions from [Arduino IDE's documentation](https://www.arduino.cc/reference/en/).
Familiarizing basic electronics like resistance, capacitance is helpful when doing mechatronics projects.


Happy Coding.