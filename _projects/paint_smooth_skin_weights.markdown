---
layout: post
title: Maya - Paint Smooth Skin Weights
description: Paint smooth weights tool in Maya using the weights of neighbouring vertices. This tool is part of the rjSkinningTools.
img: /img/tools/paint_smooth_skin_weights_thumbnail.png
date: 2015-05-04 13:16:00
categories: tools
github: https://github.com/robertjoosten/rjSkinningTools/tree/master/paintSmoothWeightsCtx
github-docs: https://robertjoosten.github.io/rjSkinningTools/rjSkinningTools.paintSmoothWeightsCtx
gumroad: https://gum.co/rjSkinningTools
---
<p class="justify">Paint smooth weights tool in Maya using the weights of neighbouring vertices. This tool is part of the rjSkinningTools.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/126825847?color=ff9933&title=0&byline=0&portrait=0" width="640" height="330" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjSkinningTools folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Select a skinned object and run the following code:
{% highlight python %}
from rjSkinningTools import paintSmoothWeightsCtx;
paintSmoothWeightsCtx.paint()
{% endhighlight %}

<h4>Note</h4>
<p class="justify">The paint tool calls a script that find the surrounding vertices and its skin weights. These skin weights are then blended with the skin weights of the original vertex based value of the paint tool.</p>
<ul>
 	<li>Undo-able / Redo-able</li>
</ul>
<p class="justify">Based on the settings on the skinCluster the following attribute will be respected while smoothing the weights:</p>
<ul>
 	<li>Max Influences</li>
 	<li>Normalize Weights</li>
 	<li>Locked Influences</li>
</ul>
<p class="justify">I would like to note that the idea for this script came from <a href="https://vimeo.com/tomferstl">Tom Ferstl</a> he developed a script where the end results is very simular. I did use the original script as an inspiration, but what happens under the hood is completely different.</p>