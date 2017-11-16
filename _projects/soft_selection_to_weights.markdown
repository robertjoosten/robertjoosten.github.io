---
layout: post
title: Maya - Soft Selection to Weights
description: Convert soft selection to skin weights. This tool is part of the rjSkinningTools.
img: /img/tools/soft_selection_to_weights_thumbnail.png
date: 2015-03-03 17:29:00
category: tools
tag: [tool, python, maya, maya api, pyside, skinning]
github: https://github.com/robertjoosten/rjSkinningTools/tree/master/softSelectionToWeights
github-docs: https://robertjoosten.github.io/rjSkinningTools/rjSkinningTools.softSelectionToWeights
gumroad: https://gum.co/rjSkinningTools
---
<p class="justify">Convert soft selection to skin weights. This tool is part of the rjSkinningTools.</p>

<p align="center"><img src="/img/tools/soft_selection_to_weights_thumbnail.png"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjSkinningTools folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Display UI:
{% highlight python %}
import rjSkinningTools.softSelectionToWeights.ui
rjSkinningTools.softSelectionToWeights.ui.show()
{% endhighlight %}

<h4>Note</h4>
<p class="justify">Convert soft selection into skin weights. More influences can be added by clicking the plus button. When more influences are added these weights are automatically blended. The influence and soft selection can be reselected by right clicking the influence widget and using the context menu.</p>

<p class="justify">Skin cluster settings like max influences and normalization will be taken into account when applying the skin weights.</p>