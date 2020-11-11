# Code-Programs
This is a repository for my coding projects.

---
## Table of Contents 
* [Table of Contents](#Table-of-Contents)
* [Getting Started](#Getting-Started)
* [Servo Control With Capacitive Touch](#Servo-Control-With-Capacitive-Touch)

---

## Getting Started

### Description

This was my first time ever seeing Circuit Python and a Metro Express board! Overall, my first experience with both of these programs was positive. I ran into some technical difficulties at the start, but was able to overcome them by looking up the instructions created by Adafruit and recieving help from Mr. H. I did not complete any assignments this week, I was mostly getting used to Circuit Python and figuring out how to use the program.

### Reflection

The program does not seem very difficult, however, since I am still getting started I expect to run into some problems. Although, I know that I will be able to overcome the issues I encounter with time and more getting used to using Circuit Python.

---

## Servo Control with Capacitive Touch

### Description

In this assignment, I had to make a servo move from 0 degrees to 180 degrees by touching two different wires. One wire would make the servo turn one direction, and the other wire would mame it turn the opposite direction. 

### Image

### Code
```python
#Lucas Fuller
#Circuit Python Servo Control with Touch
#In this assignment I will make a servo turn on direction when a wire is touched,
  #and it will turn the other direction when a different wire is touched.

import board
import time
import pulseio
import servo
import touchio

# This is the setup for the servo pin
pwm = pulseio.PWMOut(board.A3, duty_cycle=2 ** 15, frequency=50)

my_servo = servo.ContinuousServo(pwm)

# This defines the two capacative touch wires
touch_A1 = touchio.TouchIn(board.A1)
touch_A2 = touchio.TouchIn(board.A2)


while True:

    if touch_A1.value:
        print("touched a1") # States which wire is being touched
        my_servo.throttle = 1 # Moves to 180
        
    if touch_A2.value:
        print("touched a2") # States the other wire is being touched
        my_servo.throttle = -1 # Moves to 0

    time.sleep(0.01)
```
### Problems

During the process of this project I ran into a number of problems. First off, since this was a new project and I had never worked with a PWM pin before, I had to reference some of my friend's githubs, Owen McKenney and Graham Lenert, which I found to be extremely helpful. After wiring up my circuit and writing my code, I ran into a series of issues when trying to run my code. I had two issues regarding libraries in my code. One of the libraries wasn't needed, so that was an easy fix however the other was needed. In order to resolve my other library issue, I had to download a bundle and import a servo library in order for my circuit to function. After doing this, I made a couple of edits to my code and my project was up and running. 

### What I learned!

I learned how to make a servo turn but instead of using buttons I learned how to use capacitive touch with wires. 

---

