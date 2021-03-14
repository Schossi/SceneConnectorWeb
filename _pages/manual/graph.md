---
permalink: /manual/graph
title: "Graph"
sidebar:
  title: "Manual"
  nav: manual
---

![Graph](/assets/images/screens/Graph.PNG)  

## Tools

* Fit All  
Frames all nodes in the graph into the current view
* Reset Graph
Completely clear all nodes and fills ones that are currently loaded
* Minimap
Show/Hides the minimap in the graph view
* Import
Imports the graph from a previously exported asset. This can also be done by double clicking a connector asset or dragging it onto the graph view.
* Export
Exports the graph into an asset. I suggest exporting your graph whenever you are happy with its state. This works well for source control combined with ignoring ConnectorGraphModel.cgmo file.

## Graph-View

The graph view itself shows a node for every scene that has been loaded. These scene nodes have a port for every connection they have.  
The ports can not be manually connected in this view, to change connection please configure the respective connectors.  

Scene nodes can be double clicked to load them. The ports left knobs can be clicked to select their connector in the scene or also double clicked to load the scene first.  
The colored knobs on the right of the ports can be used to open and close the connected scenes just like the buttons in the inspector.

## Actions

* Bake All  
Passes all scenes in the graph to [Lightmapping.BakeMultiple](https://docs.unity3d.com/ScriptReference/Lightmapping.BakeMultipleScenes.html) 
* Set Build  
Clears the scenes in the build settings and adds the one in the graph instead starting with the additional ones
* Add Build  
Adds the scenes in the graph to the scenes in the build settings starting with the additional ones
* Load All  
Quickly iterates through all scenes in your assets to create a complete connection graph. To quickly add the connections of just one scene you can drag and drop it onto the graph view.

## Additional Scenes

The graph itself only concerns itself with scenes that contain connectors. Scenes that are not directly part of the world can be added here. They are automatically loaded when you move to a scene or connector by double click. This is mainly useful for the Player and UI.  
Add an additional Scene by dropping it on the List, remove it using the "-" button or double click it to load it.  
Postfix a scenes name with "SCI" to make connectors ignore it when the world is moved.