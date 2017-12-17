---
layout: post
title: Maya - Anchor Transform
description: Anchor Transform in Maya.
img: /img/tools/anchor_transform_thumbnail.png
date: 2017-12-17 11:00:00
category: tools
tag: [tool, python, maya, maya api, pyside]
github: https://github.com/robertjoosten/rjAnchorTransform
github-docs: https://robertjoosten.github.io/rjAnchorTransform
gumroad: https://gum.co/rjAnchorTransform
---
<p class="justify">Anchor Transform in Maya.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/247672481?color=ff9933&title=0&byline=0&portrait=0" width="640" height="303" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjAnchorTransform folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Command line:
{% highlight python %}
import rjAnchorTransform
rjAnchorTransform.anchorTransform(transform, start, end)
{% endhighlight %}

Display UI:
{% highlight python %}
import rjAnchorTransform.ui 
rjAnchorTransform.ui.show()
{% endhighlight %}

<h4>Note</h4>
<p class="justify">Anchor a transform to world space for a specific time range. Can be used to fix sliding feet on a walk cycle. The script uses the Maya API to calculate local transforms to be key framed, by doing this there is no need to loop over the animation greatly speeding up the work flow. Existing in and out tangents will be copied when new key frames are inserted.</p>

<h4>Animation Demo Credits</h4>
rig: <a href="https://www.highend3d.com/maya/downloads/character-rigs/c/dinorig-for-maya" target="_blank">Harry Gladwin-Geoghegan</a><br>
animation: <a href="http://jonathansymmonds.com/downloads_section/" target="_blank">Jonathan Symmonds</a>