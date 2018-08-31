---
layout: project
type: project
image: images/android.jpg
title: "An Attempt at Mobile App Development"
date: 2018-08-29
labels:
  - Mobile App
  - Android
  - Java
  - Machine Vision
summary: Over the summer of 2018, I took a shot at developing a mobile app that would scan Digikey part barcodes and add the part quantities to a database. 
---

# Purpose

When working in my school's workshop, I always get confused about what parts are currently in stock. I'm never sure if I need to start ordering more 100k Ohm resistors or if we have enough. And when shipments do come in, it's difficult to keep track of all the parts that come in with the shipment. I thought to myself: "We really need some sort of tool that would keep track of the inventory here. That way, I could have a central place that would show me the current inventory of the lab." So over the summer of 2018, I began trying my hand at developing such a device.

# Implementation

I decided that a mobile application that can scan barcodes would be useful. The user would just need to scan the barcode of the shipment, and the app would take the data from the barcode and apply the changes to a database where the inventory information is stored. As i looked more into what I needed to do in order to achieve this, I realized that there's going to be a lot of things I have to learn. There were three distinct subjects or ideas that I had to become familiar with: Android Development, Camera API, and Firebase's Machine Vision. These three things were needed in order to make this app a reality.

## Android Development

In the beginning, I had to start learning about developing an Android app. I also had to get used to working in Android Studio, which is an IDE specifically for Android development. I followed the tutorials and guides on the <a href="https://developer.android.com/guide/">Android Developers page</a>, and I was able to make user interfaces and different screens in no-time. However, the other two subjects proved to be much more difficult.

## Camera API

In order to read the barcode of the shipment, I had to access the device's camera. I learned how to ask the Android user for permission to use requested hardware (in this case, their camera), and how to make camera previews in the app. It took a lot of trial and error to get the camera viewer to work, but I found that <a href="https://developer.android.com/guide/topics/media/camera">Android's Camera API</a> was really helpful and it's what ultimately got the camera to function correctly. There were, however, some problems that I encountered. I couldn't find a way to let the barcode reader access the camera preview in real-time. The user would have to save the picture, then the barcode scanner would then analyze that picture. This is longer than what I imagined would be a 'point-and-process' experience for the app. Another problem is that the camera doesn't auto-focus. I'd have to implement that feature myself.

## Firebase's Machine Vision

This is where I hit a brick wall. I used <a href="https://firebase.google.com/products/ml-kit/">Firebase's Machine Vision</a> package to process the camera's preview and detect the barcode. Unfortunately, through all my efforts, I just couldn't figure out how to connect the barcode scanner functionality into the camera preview. I couldn't even figure out how to analyze a saved image. I understood what the barcode scanner does, I just couldn't figure out how to implement it.


# Conclusion
For now, all the app does is show the user what the camera is picking up. There's no barcode scanning functionality and it  isn't even connected to a database. However, I did learn a lot through this endeavor and I feel like I understand a lot more about mobile app development, atleast for Android devices.