---
permalink: /manual
title: "Overview"
sidebar:
  title: "Manual"
  nav: manual
---

<iframe width="560" height="315" src="https://www.youtube.com/embed/TQknXCwNwqQ" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>  

## Welcome

This is the manual for Scene Connector by SoftLeitner.  

This asset aims to improve your multi scene workflow by providing a central SceneConnector component that can be used to load and unload scenes in both the editor and runtime. While you are creating your world a graph of all the connections is automatically created.  


## Project Structure

* SceneConnectorCore  
The SceneConnector component and all of its accompanying editor utilities.  
Always import this one.

* SceneConnectorExtras  
Contains all the examples showcased in the demo along with some useful common scripts.  
Import this one if your just getting started or want to replicate some of the demos behaviour.  

## Integrations

- [AdventureSouls(Action Adventure Kit)](https://github.com/Schossi/ConnectorSouls)

All GitHub repositories related to my unity assets can be found in the [Softleitner Extras](https://github.com/stars/Schossi/lists/softleitner-extras) list. I generally try to keep the main ones updated but some of the minor ones may be out of date.

## Getting Started

Please proceed with the [Connector]({% link _pages/manual/connector.md %}) and [Graph]({% link _pages/manual/graph.md %}) sections of this manual for some general information about the asset. Afterwards check out the [Extras]({% link _pages/manual/extras.md %}) page which will walk you through the practical examples in the extras folder.