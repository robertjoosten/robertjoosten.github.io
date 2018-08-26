---
layout: post
title: Maya - Float to String
description: This plug-in will register a Maya node that can convert a float to a string so it can be used in combination with an annotation. The display precision can be adjusted and so can a prefix and suffix be added.
img: /img/tools/float_to_string_thumbnail.png
date: 2017-11-09 18:00:00
category: tools
tag: [tool, python, maya, maya api, custom node]
github: https://github.com/robertjoosten/maya-plugin-float-to-string
github-docs: 
gumroad: https://gum.co/maya-plugin-float-to-string
---
<p class="justify">This plug-in will register a Maya node that can convert a float to a string so it can be used in combination with an annotation. The display precision can be adjusted and so can a prefix and suffix be added.</p>

<p align="center"><img class="col three" src="/img/tools/float_to_string_connections.png"/></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the floatToString.mel file in Maya to permanently install the plugin.

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
