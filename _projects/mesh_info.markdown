---
layout: post
title: Maya - Mesh Info
description: This plug-in will register a node and a command. With the command it will be possible to query the volume of a mesh and with the node you can query not only the volume but also the surface area of all the faces.
img: /img/tools/mesh_info_thumbnail.png
date: 2015-11-30 18:00:00
category: tools
tag: [tool, python, maya, maya api, custom node, custom command]
github: https://github.com/robertjoosten/maya-plugin-mesh-info
github-docs:
gumroad: https://gum.co/maya-plugin-mesh-info
---
<p class="justify">This plug-in will register a node and a command. With the command it will be possible to query the volume of a mesh and with the node you can query not only the volume but also the surface area of all the faces.</p>

<p align="center"><img src="/img/tools/mesh_info_connections.png"/></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the meshInfo.mel file in Maya to permanently install the plugin.

<h4>Usage</h4> 
Command: 
{% highlight python %}
import maya.cmds as cmds 
volume = cmds.polyVolume(ws=True, ch=False)
{% endhighlight %}
<p class="justify">By setting the constructionHistory argument to True, instead of the volume being returned as a float, the meshInfo node will be returned that in order can be used to query the volume. </p>

Node: 
{% highlight python %}
import maya.cmds as cmds 

meshInfo = cmds.createNode("meshInfo") 
cmds.connectAttr( 
    "{0}.worldSpace[0]".format(mesh), 
    "{0}.inMesh".format(meshInfo) 
) 
    
volume = cmds.getAttr("{0}.volume".format(meshInfo)) 
area = cmds.getAttr("{0}.area".format(meshInfo))
{% endhighlight %}