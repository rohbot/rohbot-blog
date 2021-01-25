---
title: LaunchPad IoT
description: Fun with MIDI controllers and Web Sockets
date: 2020-01-06
tags:
  - Raspberry Pi
  - IoT
  - Web Sockets
layout: layouts/post.njk
---

During the lockdown of 2020 by local [Raspberry Pi Hacker](https://melbourne-rpi.com.au/) club held a [competition](https://melbourne-rpi.com.au/competition/) so I went through my junk box and the first thing I pulled out was the LaunchPad.
This lead me down the path to create this project. 
[LaunchPad IoT](https://github.com/rohbot/launchpad-iot) 

## Demo
![Demo GIF](https://github.com/rohbot/launchpad-iot/raw/master/public/images/demo.gif)

## Background
Typically LaunchPad style MIDI controllers are used as a hardware controller for music production software like Ableton Live as seen in videos like [this](https://www.youtube.com/watch?v=lTx3G6h2xyA).

Take the software away and these controllers are just a 8x8 grid of multi-colour LEDs and buttons that in theory could be used to control or interact with whatever your mind can imagine.
To start with I plan to create a two-way or bi-directional between the LaunchPad and a web browser. I want to be able to press buttons on the LaunchPad and have it control various elements on a webpage and be able to click a button on a webpage and have the LaunchPad light up in reaction.

## Components
![Components](../../img/launchpad_setup.jpg)

## Presentation
<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRZjrkOAIKSTOH4NB_QaaspqAvF-C9XdyuK7zafvQVShLoB2ODq81lW_PSSGVeEQ2RVbSHKlZ3C3lsr/embed?start=false&loop=false&delayms=3000" frameborder="0" width="960" height="569" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>