---
layout: post
title: Maya - Spline IK
description: Create a Spline IK setup on a curve. The setup features variable stretch and squash, variable rotation and sliding on curve.
img: /img/tools/spline_ik_thumbnail.png
date: 2017-10-18 16:45:00
categories: tools
github: https://github.com/robertjoosten/rjSplineIK
github-docs: https://robertjoosten.github.io/rjSplineIK/
gumroad: https://gum.co/rjSplineIK
---
<p class="justify">Create a Spline IK setup on a curve. The setup features variable stretch and squash, variable rotation and sliding on curve.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/239009885?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjSplineIK folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Command line:
{% highlight python %}
from rjSplineIK import SplineIK

splineIK = SplineIK()
splineIK.create(
    name,
    curve,
    numJoints,
    upDirection="y", 
    worldUpDirection="y", 
    forwardDirection="x"
)
{% endhighlight %}

Display UI:
{% highlight python %}
import rjSplineIK.ui
rjSplineIK.ui.show()
{% endhighlight %}

<p class="caption" align="center"><img src="/img/tools/spline_ik_ui.png"/><br/>UI Example</p>

<h4>Note</h4> 
<p class="justify">The Spline IK module works on a curve and generates an joint chain that sticks to it's position on the curve. This means that stretch and squash will only occur in the areas that manipulates as opposed to it scaling as a whole.</p>
<p align="center"><img class="col three" src="/img/tools/spline_ik_stretch_squash.gif"/></p>
<p class="caption" align="center">Stretch and Squash Demo</p>

<p class="justify">The other benefit of using this module over a regular spline IK is the fact that the twist is divided over the controls that are generated and not just limited to the beginning and end.</p>
<p align="center"><img class="col three" src="/img/tools/spline_ik_partial_twist.gif"/></p>
<p class="caption" align="center">Twist Demo</p>
<p align="center"><img class="col three" src="/img/tools/spline_ik_shift.gif"/></p>
<p class="caption" align="center">Shift Demo</p>

<p class="justify">Apart from the main settings, the control colour, position and orientation is adjustable. This can be done on the Spline IK class before the create function is called.</p>
<ul>
 	<li>controlShape</li>
 	<li>rootControlShape</li>
 	<li>slideControlShape</li>
 	<li>tangentControlShape</li>
 	<li>controlColour</li>
 	<li>rootControlColour</li>
 	<li>slideControlColour</li>
 	<li>tangentControlColour</li>
 	<li>orientToCurve</li>
 	<li>orientRootToCurve</li>
</ul>