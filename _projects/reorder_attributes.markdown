---
layout: post
title: Maya - Reorder Attributes
description: Reorder attributes in Maya, drag and drop the attributes into the desired order. Only user defined attributes can be reordered.
img: /img/tools/reorder_attributes_thumbnail.png
date: 2017-03-28 16:14:00
category: tools
tag: [tool, python, maya, pyside]
github: https://github.com/robertjoosten/rjReorderAttr
github-docs: https://robertjoosten.github.io/rjReorderAttr/
gumroad: https://gum.co/rjReorderAttr
---
<p class="justify">Reorder attributes in Maya, drag and drop the attributes into the desired order. Only user defined attributes can be reordered.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/210495749?color=ff9933&title=0&byline=0&portrait=0" width="640" height="256" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjReorderAttr folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Add the interface and functionality to Maya:
{% highlight python %}
import maya.cmds as cmds 
cmds.evalDeferred("import import rjReorderAttr; rjReorderAttr.install()")
{% endhighlight %}
<p class="justify">This line of code can also be added in the userSetup.py if you would like the functionality to persist. </p>

Display UI:
{% highlight python %}
import rjReorderAttr.ui 
rjReorderAttr.ui.show()
{% endhighlight %}

<h4>Note</h4> 
<p class="justify">If the install command is used a button called Reorder Attributes will be added to the Channel Box - Edit menu. If this is not the case the UI can be opened with the show command. Drag and drop the attributes to reorder. Attributes are deleted in the new order and the undo commands is then ran to redo the attributes in the order preferred. A thank you too Nick Hughes for showing me the power of the undo command and how it can be used to sort attributes.</p>

