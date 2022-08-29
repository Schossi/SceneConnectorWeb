---
permalink: /manual/releases
title: "Release Notes"
sidebar:
  title: "Manual"
  nav: manual
---

## 1.0.2

Various smaller changes made for the AdventureSouls Scene Connector integration example. The example is called ConnectorSouls and can be found on [GitHub](https://github.com/Schossi/ConnectorSouls)!  

### IMPROVED

- UnloadingAsCounterpart event
- TraverseCounterpart method
- Unloading the active scene in the editor activates another SC scene  
this prevents some random additional scene becoming the main scene
- SceneConnector extendability
  - main methods are overridable
  - editor works on inherited classes
- AdditionalScenes that end in SCP loaded before the main scene
- AdditionalScenes are cleared when the graph is reset

## 1.0.1

### FIXED

- Unity 2020 and 2021 compatibility

## 1.0.0

### ADDED

- __knight demo project__  
simple metroidvania sidescroller 
- __scene rotation__ options  
how and along which axis rotation is aligned can now be configured in the inspector

### IMPROVED

- __handles__ work in 2d scene mode  
- __player areas__ work with 2d triggers

### CHANGED

- earliest supported unity version is now 2019.4.18

### FIXED

- issue with scenes being connected multiple times

## 0.9.0

__Initial Release__