---
layout: post
title: Maya - De-Linearize Skin Weights
description: De-linearize skin weights with easing algorithms.
img: /img/tools/delinear_weights_thumbnail.png
date: 2017-12-02 11:00:00
category: tools
tag: [tool, python, maya, maya api, pyside, skinning]
github: https://github.com/robertjoosten/rjSkinningTools/tree/master/delinearWeights
github-docs: https://robertjoosten.github.io/rjSkinningTools/rjSkinningTools.delinearWeights
gumroad: https://gum.co/rjSkinningTools
---
<p class="justify">De-linearize skin weights with easing algorithms. This tool is part of the rjSkinningTools.</p>

<p align="center"><img src="/img/tools/delinear_weights.gif"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjSkinningTools folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Display UI:
{% highlight python %}
import rjSkinningTools.delinearWeights.ui
rjSkinningTools.delinearWeights.ui.show()
{% endhighlight %}

<h4>Note</h4>
<p class="justify">Delinear weights applies an easing algorithm to the skin weights. This tool is best used if skin weights have been copied from a low polygon source, when this is done sometimes it is very obvious that the weights are linearly divided between the vertices of the low polygon source. This tool will tween those weights.</p>
