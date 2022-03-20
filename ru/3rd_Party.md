---
title: Платы Speeduino от других разработчиков
description: 
published: true
date: 2021-01-02T07:38:47.529Z
tags: 
editor: undefined
dateCreated: 2021-01-02T07:38:41.570Z
---

3rd Party Boards
================

3rd party boards fall into two main categories, Alternative Speeduino mainboards and Accessory boards.

Alternative Speeduino Mainboards
================================

### NO2C or No Overhang Two Channel

By Weaver Markel, aka turboedge

### What is it?

NO2C is the smallest, fully functional, single board, Arduino MEGA shield made for Speeduino. The board is no bigger than the MEGA itself. Originally intended for, but not limited to applications where space is limited. These may include ATVs, motorcycles, karts, lawnmowers, and other power equipment. As you might guess by the title, it is capable of driving two injector and two ignition channels. If desired the channels can be split to drive two injectors and two coil drivers each. Some versions of the NO2C can accept a daughter board that allows more channels and other features.

More information [NO2C for Speeduino](NO2C_for_Speeduino "wikilink")

Accessary Boards
================

dxControl-GPIO for Speeduino , A GPIO Controller for Speeduino
--------------------------------------------------------------

By Darren Siepka, aka Dazq

### What is it?

dxControl-GPIO are a family of multipurpose general programmable input and output modules that can be used both in conjunction with the Speeduino engine ECU or standalone. The modules are programmed via Tunerstudio either via the serial port or over the integrated CanBus network(certain variants only)

The modules can use several different processor board types, including different arduino, teensy and stm32.

IO operations are programmed with logic, &lt; ,&gt;,= and bitwise AND . some variants offer 2 or even 3 connecting logic conditions.

More information [dxControl-GPIO](/en/DxControl-GPIO "wikilink")

DxControl-Gears , A Gearbox Controller for Speeduino
----------------------------------------------------

By Darren Siepka, aka Dazq

### What is it?

dxControl-Gears is a controller for electronically controlled automatic gearboxes, designed to accompany Speeduino. It is a custom development of the dxControl-GPIO code .

More information [dxControl-Gears](dxControl-Gears "wikilink")