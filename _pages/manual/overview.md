---
permalink: /manual
title: "Overview"
sidebar:
  title: "Manual"
  nav: manual
---

## Welcome

This is the manual for Classic City Builder Kit by SoftLeitner. Classic City Builder Kit is quite the mouthful so i will be referring to it using the shorthand CCBK.  

Oldschool walker based City Builders are very systems heavy games that require lots of tweaking and balancing to get right. CCBK was created with the aim of providing all the common tropes of the genre and making them easily accessible in the Editor.  

The kit was created with the classic evolve housing, build monuments type of game in mind and most of the systems are commonly seen in that genre. That being said large parts like Buildings, Items, Walkers and Layers are general enough to create a wide variety of games.  

## Project Structure

CCBK is separated into multiple assemblies. Which ones you need depends on how you are planning to use the Kit. For your first exploration create a new __Universal Render Pipeline__ project and remove the example assets and materials, then import the entire asset.

* CityBuilderCore  
The Core Framework of CCBK.  
Always import this one.

* CityBuilderCore.Tests  
Tests some core functionality of CityBuilderCore.  
Only import this if you plan to change CityBuilderCore and want to check if the basic systems still function.  

Both demos depend on either layers, tags or sorting layers. __If these settings were not set during import please copy the contents of TagManager.txt from the demo folder to the TagManager.asset in you ProjectSettings.__  

### Dependencies
* The demos depend on [TextMeshPro](http://docs.unity3d.com/Packages/com.unity.textmeshpro@2.1/index.html) for their UI
* CCBK generally depends on [2D Tilemap Editor](https://docs.unity3d.com/Packages/com.unity.2d.tilemap@1.0/manual/index.html)

## Usage

After familiarizing yourself with CCBK you should be ready to start your project. I'll outline three basic levels of usage for CCBK here. The first two don't require any coding, implementing custom systems assumes basic knowledge of C#.
