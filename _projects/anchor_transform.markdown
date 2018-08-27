---
layout: post
title: Maya - Anchor Transform
description: Anchor Transform in Maya.
img: /img/tools/anchor_transform_thumbnail.png
date: 2017-12-17 11:00:00
category: tools
tag: [tool, python, maya, maya api, pyside]
github: https://github.com/robertjoosten/maya-anchor-transform
github-docs: https://robertjoosten.github.io/maya-anchor-transform/
gumroad: https://gum.co/maya-anchor-transform
---
<p class="justify">Anchor Transform to world or object space in Maya.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/247672481?color=ff9933&title=0&byline=0&portrait=0" width="640" height="303" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the anchorTransform.mel file in Maya to permanently install the script.

<h4>Usage</h4> 
<p class="justify">A button on the MiscTools shelf will be created that will allow easy access to the ui, this way the user doesn't need to worry about any of the code. If user wishes to not use the shelf button the following commands can be used.</p>

Command line:
{% highlight python %}
transform = "cube"
driver = None
start = 1001
end = 1010

import anchorTransform
anchorTransform.anchorTransform(transform, driver, start, end)
{% endhighlight %}

Display UI:
{% highlight python %}
import anchorTransform.ui
anchorTransform.ui.show()  
{% endhighlight %}

<h4>Note</h4>
<p class="justify">Anchor a transform to world or object space for a specific time range. Can be used to fix sliding feet on a walk cycle. The script uses the Maya API to calculate local transforms to be key framed, by doing this there is no need to loop over the animation greatly speeding up the work flow. Existing in and out tangents will be copied when new key frames are inserted. Once all keys are set an euler filter is applied to the animation curves connected to the rotate attributes.</p>

<h4>Animation Demo Credits</h4>
rig: <a href="https://www.highend3d.com/maya/downloads/character-rigs/c/dinorig-for-maya" target="_blank">Harry Gladwin-Geoghegan</a><br>
animation: <a href="http://jonathansymmonds.com/downloads_section/" target="_blank">Jonathan Symmonds</a>