---
layout: post
title: Maya - Timeline Marker
description: Create coloured markers on top of Maya's native timeline. Comments can be added to each marker that appear as tool tips.
img: /img/tools/timeline_marker_thumbnail.png
date: 2015-04-27 15:44:00
category: tools
tag: [tool, python, maya, pyside]
github: https://github.com/robertjoosten/rjTimelineMarker
github-docs: https://robertjoosten.github.io/rjTimelineMarker/
gumroad: https://gum.co/rjTimelineMarker
---
<p class="justify">Create coloured markers on top of Maya's native timeline. Comments can be added to each marker that appear as tool tips.</p>

<p align="center"><img class="col three" src="/img/tools/timeline_marker_demo.gif"/></p>
<br>
<h4>Installation</h4> 
<p class="justify">Copy the rjTimelineMarker folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Add the interface and functionality to Maya:
{% highlight python %}
import maya.cmds as cmds 
cmds.evalDeferred("import rjTimelineMarker; rjTimelineMarker.install()")
{% endhighlight %}
<p class="justify">This line of code can also be added in the userSetup.py if you would like the functionality to persist. </p>

<h4>Note</h4>
<p class="justify">The UI elements are added to the timeline menu and can be accessed by right clicking on the timeline. You have the option to change the color of your marker points and also add comments where necessary. Tool tips will appear to show the comment while hovering over the timeline. The markers are stored in the maya file.</p>

<h4>Hotkey</h4>
<p class="justify">The hotkey function can be used to setup hotkeys to manage the timeline markers. There are three options, this is to either add, remove or clear the markers. Make sure the language is set to python.</p>
{% highlight python %}
import rjTimelineMarker; rjTimelineMarker.hotkey("add")
import rjTimelineMarker; rjTimelineMarker.hotkey("remove")
import rjTimelineMarker; rjTimelineMarker.hotkey("clear")
{% endhighlight %}

<h4>Command line</h4>
<p class="justify">The following functions can be used outside of the ui. Make sure the language is set to python.</p>
{% highlight python %}
import rjTimelineMarker; rjTimelineMarker.add(frame, color, comment)
import rjTimelineMarker; rjTimelineMarker.remove(frames)
import rjTimelineMarker; rjTimelineMarker.clear()
import rjTimelineMarker; rjTimelineMarker.set(frames, colors, comments)
{% endhighlight %}