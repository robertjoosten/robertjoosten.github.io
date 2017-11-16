---
layout: post
title: Maya - Paint Remove Influences
description: Remove a specific influence on vertices with the paint tool. This tool is part of the rjSkinningTools.
img: /img/tools/paint_remove_influences_thumbnail.png
date: 2015-05-14 12:38:00
category: tools
tag: [tool, python, maya, maya api, pyside, paint, skinning, custom command]
github: https://github.com/robertjoosten/rjSkinningTools/tree/master/paintRemoveInfluenceCtx
github-docs: https://robertjoosten.github.io/rjSkinningTools/rjSkinningTools.paintRemoveInfluenceCtx
gumroad: https://gum.co/rjSkinningTools
---
<p class="justify">Remove a specific influence on vertices with the paint tool. This tool is part of the rjSkinningTools.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/122189210?color=ff9933&title=0&byline=0&portrait=0" width="640" height="330" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjSkinningTools folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Select a skinned object and run the following code:
{% highlight python %}
from rjSkinningTools import paintRemoveInfluenceCtx;
paintRemoveInfluenceCtx.paint(mesh, influence)
{% endhighlight %}

Display UI:
{% highlight python %}
import rjSkinningTools.paintRemoveInfluenceCtx.ui;
rjSkinningTools.paintRemoveInfluenceCtx.ui.show()
{% endhighlight %}

<h4>Note</h4>
<p class="justify">The paint tool calls a script that will select all the vertices that are influenced by the parsed influence. You can then paint away the influence on those vertices with the paint tool.</p>
<ul>
 	<li>Undo-able / Redo-able</li>
</ul>
<p class="justify">Based on the settings on the skinCluster the following attribute will be respected while removing the influence weights:</p>
<ul>
 	<li>Normalize Weights</li>
 	<li>Locked Influences</li>
</ul>