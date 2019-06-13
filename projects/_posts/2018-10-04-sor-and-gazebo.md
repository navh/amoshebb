---
title: SOR and Gazebo
updated: 2018-10-04
category: coatimunde
---

## Statement of Requirements

The last few weeks have been spent creating the big document that dictates how the rest of the project will progress. That document is the [Statement of Requirements](/assets/SORHebbStephan.pdf) and has finally been submitted, at least as a rough copy that will probably be ripped to shreds.

## Math

The other big tasks have revolved around re-learning all of the bits of linear algebra that I have been able to ignore since first year. Almost all of the math about the movement of a robot through space relies on applying transformations to one type of matrix representation of a robot, and then to make matters worse the way a camera works requires doing all sorts of nifty math to figure out what a 2D sensor is seeing from a 3D world.

Hopefully built in libraries will handle the better part of this for us, but getting a solid background in these topics is necessary.

## Gazebo

A [Gazebo simulation](http://gazebosim.org/) environment has finally been set up on both my desktop and my laptop. It is a [pre-wrapped package](https://www.mathworks.com/supportfiles/robotics/ros/virtual_machines/v3/installation_instructions.htm) that is designed perhaps a little bit more for control systems type work than we intend to do, but includes a TurtleBot simulator already. 

The current plan is for me to familiarize myself with this simulation environment during the thanksgiving reading break so that as soon as we return we can start building a working simulation. 

