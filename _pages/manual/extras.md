---
permalink: /manual/extras
title: "Extras"
sidebar:
  title: "Manual"
  nav: manual
---

# Demo
The following steps restore the environment used to create the [Demo.]({% link _pages/demo.md %})

* Open Extras.asset  
* DoubleClick Extras in additional scenes  
* Click "Set Build" in graph actions  

This does __not__ represent a regular use case. The graph wont work well because is contains all the different additional scenes of all the demos. You can however click play to basically enter the demo and the way the scenes are loaded in the menu might be interesting to some.  

## Tunnel

* Open Tunnel.asset  
* Click "Set Build" in graph actions  
* DoubleClick TunnelSideA in Graph  

The tunnel demo shows a simple use case in which the SceneConnector is called when the player enters and exits trigger areas. The TunnelSideX scenes are all static and therefore wont move, the tunnel scene however has dynamic connectors at both ends. This means that it will move to whatever end is currently loaded. When a player moves through the tunnel the following happens:  

![Tunnel](/assets/images/screens/TunnelTotal.PNG)  

* Player starts in TunnelSideA
* Player moves to entry of tunnel and enters area of TunnelSideA.Tunnel
  * Tunnel gets Loaded and Aligned to TunnelSideA
* Area of Tunnel.ConnectorA spawns on top of Player
  * Nothing happens here because TunnelSideA is already loaded
* Player moves to middle of Tunnel and exits area of Tunnel.ConnectorA
  * Tunnel.ConnectorA gets traversed into
    * Tunnel is set as active scene
    * TunnelSideA is unloaded
    * Tunnel moves itself and the player to its origin
* Player keeps moving and enters area of Tunnel.ConnectorB
  * TunnelSideB gets loaded and Tunnel is aligned to it
* Area of TunnelSideB.Tunnel spawns on top of Player
  * Nothing happens here because Tunnel is already loaded
* Player moves out of Tunnel and exits TunnelSideB.Tunnel
  * Tunnel gets Unloaded

TunnelSideC is just a simple static-static connector pair that is connected to TunnelSideA. It showcases a very simple way to traverse between two static scenes by overlapping trigger areas and works like this.

<div class="mxgraph" style="" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;lightbox&quot;:false,&quot;nav&quot;:true,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2021-03-14T19:10:08.150Z\&quot; agent=\&quot;5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.82 Safari/537.36\&quot; etag=\&quot;-cBdKOdOfJNkMqk9R3YW\&quot; version=\&quot;14.2.9\&quot; type=\&quot;google\&quot;&gt;&lt;diagram id=\&quot;4YlqZ7pz3gvks6q1OyDr\&quot; name=\&quot;Page-1\&quot;&gt;7Vldb5swFP01edyEbaDksc2y9aHVOnVS1b054IA3w0WOaZL9+pliQsC0ybQmNO1eIjj+5Bxf33OVEZmkqy+S5sk1REyMsBOtRuTTCONxgPRvCawrwHODCogljyoINcAt/80M6Bi04BFbtDoqAKF43gZDyDIWqhZGpYRlu9scRHvVnMbMAm5DKmz0jkcqqdDAcxr8kvE4qVdGjmlJad3ZAIuERrDcgsh0RCYSQFVP6WrCRMldzUs17vMTrZuNSZapfQZc3/+4v/PF9+TmzM8vv91NURF/QGaaByoK88Vmt2pdUyChyCJWzuKMyMUy4Yrd5jQsW5dac40lKhX6DelHxVbqq27lqhTcK0fMuRATECAfpyPz+RyHocYXSsIvttUS+TPf83ULtCcwW2RST/7kx6MNpfooMkiZkmvdxQzADv7oVYPMQSS1LstGVlRjyZakvsGoOUnxZvKGbP1g+P4b7vFu7lmkT6N5BakSiCGjYtqgF211mj5XALnR5CdTam1CixYK2opVa5YLPc+t3hcUMmTPfZHbL4Jkgir+0F6gj08z9Aa4XnojHgos8byOKIrKmCkzrqPLZiP/IJW7h1RC6EuJ7Q4Rusirm2rOV6Vw3QCJPBZEbl+ABHhGfP+FIsK3SCV2RLg9AeEeLCB8i+Vzi+bygmnz2aYpg4x1ODUQFTzO9GuoGWIavyj54/qqPzcNKY8i8ZSA7TibQ6ZMRHnoZQQhwVlXEHc/QfDBBAl2H3ud1vLysUjFeahgm9crOmPiBhZccSj5nYFSkPYQr6ATIlAowTOtaZ3UD8V5TecmBDyL8b6cQA7G+Pj4+TgIWX8+ngWe+zjiAPnY7d4+rjN0Pq4Xe39e6BVwv4cPPS0vhMmRvJDbvYwO7IVqZf5LtUMqMrxUZA+pTt22umhg24rt4mBi0fxmbSsiliA9lfVRbSv2LEHedR0xvCB2YWfpcdp1BGrXES4auI7AA9QRr8TLBkN7WfLmvCzBRzJIHjquQSL7eNmTN0jjgQ0SsW3ouzZIXk+5fdR8TGyD9LbyMe7m4/HB8rF+bf7Dq+6l5o9QMv0D&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>
<script type="text/javascript" src="https://viewer.diagrams.net/js/viewer-static.min.js"></script>

## Caves

This example shows a couple different ways to set up connectors with a common portal prefab.

### Dynamic
* Open CavesDynamic.asset  
* Click "Set Build" in graph actions  
* DoubleClick CaveChamberDynamicA in Graph  

All connectors in this example are in dynamic positioning mode. This means that scenes are aligned with the loading portal at first and move to center when the player moves into them. From there the next scene is aligned and so on. This keeps the game pretty close to the origin at all times and removes the need to align scenes in the editor.

### Static
* Open CavesStatic.asset  
* Click "Set Build" in graph actions  
* DoubleClick CaveChamberMain in Graph  

Most connectors here are static except for the connectors between CaveChamberSide and CaveCorridorSideA which are teleport. Those two are therefore brought to each other when loaded and reset to their own position when traversed into. This kind of setup might be useful for a large world with multiple areas. Instead of the teleporting an elevator with two dynamic connectors similar to the tunnel demo could also be used for that. The teleport makes sense mostly when you don't have a dedicated scene for transitioning.

### Portal

![Portal](/assets/images/screens/Portal.PNG)  

This prefab demonstrates a more advanced form of integrating connectors with both user interaction and animation. The portal triggers a load when the player either enters the area in front of it or shoots the shield. The blades are only opened when the shield has been shot and the scene loaded. If the player now moves through the portal into the new area it closes the blades, resets the shield and unloads everything behind it. When loaded as a counterpart the portal also hides its attached meshes until the original portal is unloaded. 

## Houses
* Open Houses.asset  
* Click "Set Build" in graph actions  
* DoubleClick HousesEnvironment in Graph  

In the houses demo multiple smaller side area are placed in a larger Environment which always stays loaded and active. This is useful when the side areas contain lots of different complex assets which don't have to be loaded unless the side area is entered.

![House](/assets/images/screens/House.PNG)  

The Houses have two trigger areas. The larger one on the outside causes the connector to load on enter and unload on exit. The smaller one thats mostly inside the house is hooked up to the door script. The door script itself is pretty simple. When the player enters its area and clicks it turns the handle. Only once the handle is turned and the scene inside is loaded does it actually open the door. When the player leaves it resets itself. Since the door area is much smaller than the house area the door should always be closed before the scene inside gets unloaded. 