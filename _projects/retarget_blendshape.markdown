---
layout: post
title: Maya - Retarget Blendshape
description: Retarget blendshapes between meshes with the same topology. Scale and rotation deltas are calculated between the two meshes. If the geometry is very different a smoothing algorithm can be applied.
img: /img/tools/retarget_blendshape_thumbnail.png
date: 2016-06-12 09:30:00
category: tools
tag: [tool, python, maya, maya api, pyside, retarget, blendshape]
github: https://github.com/robertjoosten/rjRetargetBlendshape
github-docs: https://robertjoosten.github.io/rjRetargetBlendshape/
gumroad: https://gum.co/rjRetargetBlendshape
---
<p class="justify">Retarget blendshapes between meshes with the same topology. Scale and rotation deltas are calculated between the two meshes. If the geometry is very different a smoothing algorithm can be applied.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/170360738?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjRetargetBlendshape folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Command: 
{% highlight python %}
import rjRetargetBlendshape 
rjRetargetBlendshape.convert( 
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
import rjRetargetBlendshape.ui 
rjRetargetBlendshape.ui.show()
{% endhighlight %}

<h4>Note</h4> 
<p class="justify">Retarget your blendshapes between meshes with the same topology. There are a few options that can be helpful to achieve the desired results. </p>
<ul> 
<li><p class="justify">Scaling your delta depending on the size difference between the source and the target vertex. </p></li> 
<li><p class="justify">Rotating the delta depending on the normal difference between the source and the target vertex. </p></li> 
<li><p class="justify">Smoothing based on the vertex size between the retarget mesh and the blendshape mesh. </p></li> 
</ul>
