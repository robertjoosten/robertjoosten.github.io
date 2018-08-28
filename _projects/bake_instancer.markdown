---
layout: post
title: Maya - Bake Instancer
description: This plug-in will register a node and a command. With the command it will be possible to query the volume of a mesh and with the node you can query not only the volume but also the surface area of all the faces.
img: /img/tools/bake_instancer_thumbnail.png
date: 2016-10-22 11:00:00
category: tools
tag: [tool, python, maya, maya api, pyside]
github: https://github.com/robertjoosten/maya-bake-instancer
github-docs: https://robertjoosten.github.io/maya-bake-instancer/
gumroad: https://gum.co/maya-bake-instancer
---
<p class="justify">Bake an instancer node to individual animated pieces of geometry. Useful for people that haven't switched to Maya 2017 yet, where this is standard functionality.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/188421440?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the bakeInstancer.mel file in Maya to permanently install the script.

<h4>Usage</h4> 
<p class="justify">A button on the MiscTools shelf will be created that will allow easy access to the ui, this way the user doesn't need to worry about any of the code. If user wishes to not use the shelf button the following commands can be used.</p>

Command: 
{% highlight python %}
import bakeInstancer 
bakeInstancer.bake(instancer, start, end)
{% endhighlight %}

Display UI: 
{% highlight python %}
import bakeInstancer.ui 
bakeInstancer.ui.show()
{% endhighlight %}