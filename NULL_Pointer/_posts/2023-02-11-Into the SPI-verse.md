---
layout: post
title: "Into the SPI-verse"
description: "The first 'Hello world' post for Simple Texture theme."
categories: [Embedded]
tags: [Embedded, SPI, Serial Communication, Serial Peripheral Interface]
redirect_from:
  - /2023/02/11/
---

You probably stumbled upon this post while seraching for a way to connect devices to your MCU. When it comes to conneting on-board peripherals, my go-to protocol is the Serial Peripheral Interface (SPI). It's intuitive inteface allows a quick setup for the prototype. Once you get used to how to use the protocol, I can guarantee you that you will have a prototype firmware to run before all of your hardware arrives.

This post will breifly explain and provide you a quick start guide on SPI.

* Kramdown table of contents
{:toc .toc}

# What is it?
Before I explain how to use it, let me briefly explain what it does. SPI is a type of serial communication protocol used to connect devices to microcontrollers, allowing them to exchange data. The MCU will send a request, and the target device will transmit corresponding response. It is a popular bus system that is widely used in embedded electronics due to its simplicity and relatively low power consumption.

# How does it work?
SPI is a full-duplex protocol, meaning that data can be sent and received at the same time, which makes the protocol simpler and faster compare to others. However, the full-duplex characteristic forces the MCU to interact with one device at a time. Multiple devices can be connnected on the same bus line, but a channel select line is used to select a target device for transmission. As a result, number of GPIO pins required for the communcation increases as the number of target devices to control increases.

There are four different mode of operation exists. Each mode represents how the data siganl is sampled corresponding to the clock signal, usually it can be found or infered  in the datasheet of the target device.


# TL;DR
1. full-duplexed 4-wire bus system (Data-In(DI), Data-Out(DO), Clock(CLK), Channel Select(CS))
   - number of CS line = number of target device
2. Select mode of operation
3. Study the datasheet of target device for available commands.