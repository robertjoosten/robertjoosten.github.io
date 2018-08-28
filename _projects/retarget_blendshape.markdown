---
layout: post
title: Maya - Retarget Blendshape
description: Retarget blendshapes between meshes with the same topology. Scale and rotation deltas are calculated between the two meshes. If the geometry is very different a smoothing algorithm can be applied.
img: /img/tools/retarget_blendshape_thumbnail.png
date: 2016-06-12 09:30:00
category: tools
tag: [tool, python, maya, maya api, pyside]
github: https://github.com/robertjoosten/maya-retarget-blendshape
github-docs: https://robertjoosten.github.io/maya-retarget-blendshape/
gumroad: https://gum.co/maya-retarget-blendshape
---
<p class="justify">Retarget blendshapes between meshes with the same topology. Scale and rotation deltas are calculated between the two meshes. If the geometry is very different a smoothing algorithm can be applied.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/170360738?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the retargetBlendshape.mel file in Maya to permanently install the script.

<h4>Usage</h4> 
<p class="justify">A button on the MiscTools shelf will be created that will allow easy access to the ui, this way the user doesn't need to worry about any of the code. If user wishes to not use the shelf button the following commands can be used.</p>

Command: 
{% highlight python %}
import retargetBlendshape 
retargetBlendshape.convert( 
    source, 
    blendshape, 
    target, 
    scale=True, 
    rotate=True, 
    smooth=0, 
    smoothIterations=0, 
    space=OpenMaya.MSpace.kObject
)
{% endhighlight %}

Display UI: 
{% highlight python %}
import retargetBlendshape.ui 
retargetBlendshape.ui.show()
{% endhighlight %}

<h4>Note</h4> 
<p class="justify">Retarget your blendshapes between meshes with the same topology. There are a few options that can be helpful to achieve the desired results. </p>
<ul> 
<li><p class="justify">Scaling your delta depending on the size difference between the source and the target vertex. </p></li> 
<li><p class="justify">Rotating the delta depending on the normal difference between the source and the target vertex. </p></li> 
<li><p class="justify">Smoothing based on the vertex size between the retarget mesh and the blendshape mesh. </p></li> 
</ul>
