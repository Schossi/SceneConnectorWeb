---
permalink: /manual/connector
title: "Connector"
sidebar:
  title: "Manual"
  nav: manual
---

## SceneConnector

Central to this entire asset is the MonoBehaviour of the same name. It is created using the AddComponent button in the inspector just like any other component. SceneConnectors form connections when two connectors in different scenes point to each others scene and have the same key.  
![Inspector](/assets/images/screens/Inspector.PNG)  
You can open a SceneConnectors scene by pressing load in the inspector or clicking a round green handle. If a matching SceneConnector is found in the opened target scene it is aligned by moving the counterpart to the same position. Aligned means that the SceneConnectors have the same position and their rotation is flipped 180° around Y.  
![Alignot](/assets/images/screens/Alignot.PNG)  
![Aligned](/assets/images/screens/Aligned.PNG)  
During runtime SceneConnectors have three basic Operations:
* Load  
Loads the target scene and aligns the connectors according to their positioning
* Unload  
Unloads the target scene
* Traverse  
Activates the connectors own scene and unloads the target. Afterwards the world might be moved depending on the positioning.

The basic flow SceneConnector was built for mainly is as follows:

#### LOAD>>UNLOAD
1. Player approaches connection
2. LOAD
3. Player backs up and moves somewhere else
4. UNLOAD  

#### LOAD>>TRAVERSE
1. Player approaches connection
2. LOAD
3. Player moves into the loaded scene and away from the original
4. TRAVERSE  

## Handles

Using the Handles you can control SceneConnector directly from the scene view while you are editing your world.
![Single](/assets/images/screens/DebugHandleSingle.PNG)  
![Double](/assets/images/screens/DebugHandleDouble.PNG)  
To quickly switch between the following display modes press Ctrl+Shift+(NUMBER) while the scene view is active.

* Default(7)  
shows a round button on both sides of a connection  
when a scene is not loaded a green button can be used to loaded  
conversely a red button is used to unload the scene on its respective side
* Advanced(8)  
larger load/unload buttons and an additional blue button that selects the connector
* Selected(9)  
displays handles only when the connectors gameobject is selected
* None(0)  
handles are deactivated  

As long as no Scene is chosen for a SceneConnector it only displays an arrow indicating its direction instead of the full handles. 

## Positioning

This settings affects how connectors move their own or other loaded scenes when they are loaded or traversed.

### Static
Static connectors are not moved during runtime.  
When a static connector is opened during editing and the connectors don't line up it is aligned and marked dirty so you can save the corrected position.
> when everything is already in the right place (Demo: Houses and Caves-Static)

### Dynamic
A connector in dynamic mode is always the one that is moved whe paired with a static one. When paired with another dynamic connector the one that just got loaded is moved.  
When traversed into a dynamic connector moves itself to the origin.  
During editing dynamic connectors are aligned but not marked as dirty since being moved around is their natural state.
> make everything dynamic to keep the player close to center (Demo: Caves-Dynamic)  

> individual scenes with dynamic connectors for tunnels, elevators, ... (Demo: Tunnel)

### Teleport
Teleporting connections move align with their counterpart when loaded and reset to their original position when traversed into.
> when a world is split by a single connection rather than a scene (Demo: Caves-Static)