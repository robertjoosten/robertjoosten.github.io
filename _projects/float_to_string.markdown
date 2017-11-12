---
layout: post
title: Maya - Float to String
description: This plug-in will register a Maya node that can convert a float to a string so it can be used in combination with an annotation. The display precision can be adjusted and so can a prefix and suffix be added.
img: /img/tools/float_to_string_thumbnail.png
date: 2017-11-09 18:00:00
categories: tools
github: https://github.com/robertjoosten/rjFloatToString
github-docs: 
gumroad: https://gum.co/rjFloatToString
---
<p class="justify">This plug-in will register a Maya node that can convert a float to a string so it can be used in combination with an annotation. The display precision can be adjusted and so can a prefix and suffix be added.</p>

<p align="center"><img class="col three" src="/img/tools/float_to_string_connections.png"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjFloatToString.py file in any of the directories that are in your MAYA_PLUG_IN_PATH environment variable: </p>
{% highlight text %}
C:\Program Files\Autodesk\plug-ins
{% endhighlight %}

<p class="justify">Copy all the png files in any of the directories that are in your XBMLANGPATH environment variable: </p>
{% highlight text %}
C:\Program Files\Autodesk\icons
{% endhighlight %}

<h4>Usage</h4> 
Node:
{% highlight python %}
from maya import cmds

# create nodes
floatToString = cmds.createNode("floatToString")
annotation = cmds.createNode("annotationShape")

# set attributes
cmds.setAttr("{0}.precision".format(floatToString), 1)
cmds.setAttr("{0}.prefix".format(floatToString), "height:", type="string")
cmds.setAttr("{0}.suffix".format(floatToString), "mm", type="string")

# connect to annotation
cmds.connectAttr(
    "{0}.output".format(floatToString),
    "{0}.text".format(annotation)
)
{% endhighlight %}
