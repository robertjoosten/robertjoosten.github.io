---
layout: post
title: Maya - Bake Instancer
description: This plug-in will register a node and a command. With the command it will be possible to query the volume of a mesh and with the node you can query not only the volume but also the surface area of all the faces.
img: /img/tools/bake_instancer_thumbnail.png
date: 2016-10-22 11:00:00
category: tools
tag: [tool, python, maya, maya api, pyside, bake, instancer]
github: https://github.com/robertjoosten/rjBakeInstancer
github-docs: https://robertjoosten.github.io/rjBakeInstancer/
gumroad: https://gum.co/rjBakeInstancer
---
<p class="justify">Bake an instancer node to individual animated pieces of geometry. Useful for people that haven't switched to Maya 2017 yet, where this is standard functionality.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/188421440?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjBakeInstancer folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Command: 
{% highlight python %}
import rjBakeInstancer 
rjBakeInstancer.bake(instancer, start, end)
{% endhighlight %}

Display UI: 
{% highlight python %}
import rjBakeInstancer.ui 
rjBakeInstancer.ui.show()
{% endhighlight %}