---
layout: post
title: Maya - Keyframe Reduction
description: Keyframe reduction for Maya using least-squares method.
img: /img/tools/keyframe_reduction_thumbnail.png
date: 2019-02-10 15:30:00
category: [tools]
tag: [tool, python, maya, pyside, rigging, animation]
github: https://github.com/robertjoosten/maya-keyframe-reduction
github-docs: https://robertjoosten.github.io/maya-keyframe-reduction/
gumroad: https://gum.co/maya-keyframe-reduction
---
<p class="justify">Keyframe reduction for Maya using least-squares method.</p>

<p align="center"><iframe width="640" height="360" src="https://www.youtube.com/embed/9Zszvc_pxuw" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the keyframeReduction.mel file in Maya to permanently install the script.

<h4>Usage</h4> 
<p class="justify">A button on the MiscTools shelf will be created that will allow easy access to the ui, this way the user doesn't need to worry about any of the code. If user wishes to not use the shelf button the following commands can be used.</p>

<p class="justify">The ui responds to the current selection where it finds all of the suitable animation curves for reduction. You will be able to filter the animation curves based on the plug it is connected to. This will make it easier to target exactly the curves you want to reduce.</p>

<p class="justify">After an animation curve is reduced the reduction percentage will be printed to the console. This can give you an idea if you would like to increase or decrease the error rate to get the desired results.</p>

<h4>UI</h4> 
<p align="center"><img src="/img/tools/keyframe_reduction_ui.png"/></p>

Display the UI with the following code.
{% highlight python %}
import keyframeReduction.ui
keyframeReduction.ui.show()
{% endhighlight %}

<h4>Command Line</h4> 
Use the KeyframeReduction class on individual animation curves.
{% highlight python %}
from keyframeReduction import KeyframeReduction
obj = KeyframeReduction(pathToAnimCurve)
obj.reduce(error=0.1)
{% endhighlight %}

<h4>Options</h4> 
* **error**<br>The maximum amount the reduced curve is allowed to deviate from the sampled curve.
* **step**<br>The step size to sample the curve.
* **weightedTangents**<br>Reduce curve using weighted tangents, using weighted tangents will result in less keyframes but is a bit slower to calculate.
* **tangentSplitAuto**<br>Automatically split tangents based on the angles of the sampled curve and deviation of those angles from the mean.
* **tangentSplitExisting**<br>Use existing keyframes that have split tangents as a split tangent point.
* **tangentSplitAngleThreshold**<br>Split tangents based on an angle value threshold.
* **tangentSplitAngleThresholdValue**<br>Split tangent angle threshold value.

<h4>Note</h4> 
The fitting algorithm is ported from <a href="http://paperjs.org/">Paper.js - The Swiss Army Knife of Vector Graphics Scripting</a>.

