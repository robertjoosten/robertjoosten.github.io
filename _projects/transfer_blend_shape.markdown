---
layout: post
title: Maya - Transfer Blend Shape
description: Transfer blend shape(s) between meshes with the same topology. 
img: /img/tools/transfer_blend_shape_thumbnail.png
date: 2022-01-15 09:30:00
category: tools
tag: [tool, python, maya, maya api, pyside, numpy, scipy]
github: https://github.com/robertjoosten/maya-transfer-blend-shape
github-docs: https://robertjoosten.github.io/maya-transfer-blend-shape/
gumroad: https://gum.co/maya-transfer-blend-shape
---
<p class="justify">Transfer your blend shapes between meshes with the same topology.</p>

<p align="center"><img class="col three" src="/img/tools/transfer_blend_shape_workflow.png"/></p>
<p align="center"><i>Workflow</i></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the transfer-blend-shape.mel file in Maya to permanently install the script.

<h4>Usage</h4> 
<p class="justify">A button on the MiscTools shelf will be created that will allow easy access to the ui, this way the user doesn't need to worry about any of the code. If user wishes to not use the shelf button the following commands can be used. The transfer will only work if at least one vertex has no delta, these fixed vertices are used to transfer the solution to the correct position in object space, the threshold can be increased to make sure vertices are linked.</p>

<p align="center"><img src="/img/tools/transfer_blend_shape_ui.png"/></p>
<p align="center"><i>UI</i></p>
   
<p class="justify">When the target is set/changed either by initializing the Transfer object or via the UI the target matrix is calculated, this can be quite time consuming.</p>

<p align="center"><img class="col three" src="/img/tools/transfer_blend_shape_debug.png"/></p>
<p align="center"><i>Debug Options</i></p>

<p class="justify">The number of iterations determine the amount of times the laplacian smoothing matrix is applied to the deformed vertices. This smoothing matrix is calculated using weights determined by area difference on a per-vertex basis.</p>
<p class="justify">Colour sets can be created to visualize the deformed vertices and the laplacian smoothing weights.</p>
   
Command: 
{% highlight python %}
import transfer_blend_shape
transfer = transfer_blend_shape.Transfer(source, target, iterations=3, threshold=0.001)
transfer.execute_from_mesh(mesh, name)
transfer.execute_from_blend_shape()
{% endhighlight %}

Display UI: 
{% highlight python %}
import transfer_blend_shape.gui
transfer_blend_shape.gui.show()
{% endhighlight %}

<h4>Note</h4> 
<p class="justify">This tool requires <i>numpy</i> and <i>scipy</i> to be installed to your environment. Using linux or Maya 2022+ on windows this can be done via a simple pip install. For older windows versions a custom version will have to be compiled against the correct VS version.</p>

<p class="justify">Example images are generated using the <a href="https://www.unrealengine.com/en-US/digital-humans">MetaHuman</a> exports for the source/target base and source jaw open shape. Target jaw open is generated using the tool.</p>










