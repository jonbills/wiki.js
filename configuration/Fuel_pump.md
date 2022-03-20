---
title: Fuel pump
description: Setting the on/off conditions of the fuel pump
published: true
date: 2021-01-20T11:40:03.348Z
tags: 
editor: undefined
dateCreated: 2020-01-14T06:24:04.641Z
---

# Fuel pump
Fuel pump control is a simple but important function performed by the ECU. Currently Speeduino does not perform variable (PWM) pump control. Can only be connected to a relay. <b>DO NOT CONNECT DIRECTLY TO FUEL PUMP</b>.

## Settings
![fuel_pump.png](/img/accessories/fuel_pump.png){.align-center width=480}

* **Fuel pump pin** - The Arduino pin that the fuel pump output is on. In most cases this should be left to `Board Default` unless you have a specific reason to change this. 
* **Prime duration** - How long (In seconds) the fuel pump should run when the system is first powered up. Note that this is triggered **when the ECU is powered on**, which will not always be the same as when the ignition is turned out. If you have a USB cable connected then the ECU is already powered up. 