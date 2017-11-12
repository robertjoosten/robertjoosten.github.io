---
layout: post
title: Maya - Tweak Vertex Weights
description: Tweak influence weights on a vertex level. This tool is part of the rjSkinningTools.
img: /img/tools/tweak_vertex_weights_thumbnail.png
date: 2015-03-1 07:59:00
categories: tools
github: https://github.com/robertjoosten/rjSkinningTools/tree/master/tweakVertexWeights
github-docs: https://robertjoosten.github.io/rjSkinningTools/rjSkinningTools.tweakVertexWeights
gumroad: https://gum.co/rjSkinningTools
---
<p class="justify">Tweak influence weights on a vertex level. This tool is part of the rjSkinningTools.</p>
 
<p align="center"><img src="/img/tools/tweak_vertex_weights_big.png"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjSkinningTools folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Display UI:
{% highlight python %}
import rjSkinningTools.tweakVertexWeights.ui
rjSkinningTools.tweakVertexWeights.ui.show()
{% endhighlight %}

<h4>Note</h4>
<p class="justify">Tweak vertex weights with sliders or spinbox input fields. This tool will give the user a good overview of what influences are translating the vertex. At the same time being able to tweak those influence to a 0.001 of precision, while setting the locked state of certain influences. It also shows if the maximum amount of influences is exceeded. The UI gets updated every time the selection is changed in Maya.</p>
