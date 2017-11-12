---
layout: post
title: Maya - Channel Box Plus
description: Channel Box Plus will add search-ability over its attributes and it will colour user defined attributes.
img: /img/tools/channel_box_plus_thumbnail.png
date: 2016-08-13 18:00:00
categories: tools
github: https://github.com/robertjoosten/rjChannelBoxPlus
github-docs: https://robertjoosten.github.io/rjChannelBoxPlus/
gumroad: https://gum.co/rjChannelBoxPlus
---
<p class="justify">Channel Box Plus will add search-ability over its attributes and it will colour user defined attributes, making them easier to distinguish. With the threshold argument you can determine when to switch between colours, the higher the threshold the more the two attributes will have to match up to stay the same colour.</p>

<p align="center"><img src="/img/tools/channel_box_plus_usage.gif"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjChannelBoxPlus folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Add the interface and functionality to Maya:
{% highlight python %}
import maya.cmds as cmds 
cmds.evalDeferred("import rjChannelBoxPlus;rjChannelBoxPlus.install(threshold=0.75)")
{% endhighlight %}
<p class="justify">This line of code can also be added in the userSetup.py if you would like the functionality to persist. </p>

<h4>Customize</h4> 
<p class="justify">Colour palette can be updated in the colour.py file that is located in this package, simply change the colour values or add new ones following the same format.</p>

