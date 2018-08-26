---
layout: post
title: Maya - De-Linearize Skin Weights
description: De-linearize skin weights with easing algorithms.
img: /img/tools/delinear_weights_thumbnail.png
date: 2017-12-02 11:00:00
category: tools
tag: [tool, python, maya, maya api, pyside, skinning]
github: https://github.com/robertjoosten/maya-skinning-tools/tree/master/scripts/skinningTools/delinearWeights
github-docs: https://robertjoosten.github.io/maya-skinning-tools/skinningTools.delinearWeights
gumroad: https://gum.co/maya-skinning-tools
---
<p class="justify">De-linearize skin weights with easing algorithms. This tool is part of the maya-skinning-tools.</p>

<p align="center"><img src="/img/tools/delinear_weights.gif"/></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the skinningTools.mel file in Maya to permanently install the script.

<h4>Note</h4>
<p class="justify">Delinear weights applies an easing algorithm to the skin weights. This tool is best used if skin weights have been copied from a low polygon source, when this is done sometimes it is very obvious that the weights are linearly divided between the vertices of the low polygon source. This tool will tween those weights.</p>
