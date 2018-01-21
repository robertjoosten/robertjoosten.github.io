---
layout: post
title: Maya - Quality Assurance
description: Quality assurance framework for Maya.
img: /img/tools/quality_assurance_thumbnail.png
date: 2018-01-21 11:33:00
category: tools
tag: [tool, python, maya, maya api, pyside]
github: https://github.com/robertjoosten/rjQualityAssurance
github-docs: https://robertjoosten.github.io/rjQualityAssurance
gumroad: https://gum.co/rjQualityAssurance
---
<p class="justify">Quality assurance framework for Maya. Focused on many parts of a production pipeline, collections are created for animators, modelers, riggers and look-dev. </p>

<p align="center"><img src="/img/tools/quality_assurance_usage.gif"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjQualityAssurance folder to your Maya scripts directory:</p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Display UI:
{% highlight python %}
import rjQualityAssurance.ui
rjQualityAssurance.ui.show("rigging")  
{% endhighlight %}

<p class="justify">The show function takes in a collection argument, if you work within one of the specialties you can simply call the show function with the collection you want to see by default. To see all available collections run the following code.</p>
{% highlight python %}
import rjQualityAssurance.collections
print rjQualityAssurance.collections.getCollectionsCategories()  
{% endhighlight %}

<h4>Adding Quality Assurance Checks</h4> 
<p class="justify">The quality assurance framework is setup so new quality assurance checks can easily be added.</p>

<h4>Location</h4> 
<p class="justify">All quality assurance checks are located in the <strong>checks</strong> folder. New checks can be written in one of the sub modules of the <strong>checks</strong> folder. Writing new checks in existing modules will automatically be picked up by the script. When adding a new sub module it is important to import the contents of the sub module into the <strong>__init__.py</strong> file in the <strong>checks</strong> folder.</p>

{% highlight python %}
from .animation import *
{% endhighlight %}

<p class="justify">All checks are sorted in order of occurrence in the source code. This can be used to make sure certain checks are after others.</p>

<h4>Collections</h4> 
<p class="justify">New collections can be added in the <strong>COLLECTIONS</strong> variable. Since this <strong>COLLECTIONS</strong> variable is an OrderedDict, it will keep the order. A collection can be defined by who will be using it. Currently it is divided by different specialties. Each specialty contains a list of categories that will be displayed. The category names link to the categories defined in the quality assurance checks themselves. </p>

<h4>Sub Classing</h4> 
<p class="justify">New quality assurance checks can be created by sub classing the <strong>QualityAssurance</strong> base class. It is important to extend the class with a <strong>_find</strong> and <strong>_fix</strong> function and update the meta data in the <strong>__init__</strong> function.</p>

{% highlight python %}
from ..utils import QualityAssurance, reference

class TestCheck(QualityAssurance):
    def __init__(self):
        QualityAssurance.__init__(self)

        self._name = "Unused Animation"
        self._message = "{0} animation curve(s) are unused"
        self._categories = ["Animation"]
        self._selectable = True

    # ------------------------------------------------------------------------

    def _find(self):
        animCurves = self.ls(type="animCurve")
        animCurves = reference.removeReferenced(animCurves)

        for animCurve in animCurves:
            # check if the output plug is connected
            if cmds.listConnections("{0}.output".format(animCurve)):
                continue

            # yield error
            yield animCurve

    def _fix(self, animCurve):
        cmds.delete(animCurve)
{% endhighlight %}
            
<h4>Meta Data</h4> 
* **self._name:** Name of the quality assurance check
* **self._urgency:** Urgency level, 1=orange, 2=red.
* **self._message:** Format-able message when errors are found.
* **self._categories:** List of categories the quality assurance check should part of.
* **self._selectable:** Boolean value if the error list is selectable.

<h4>Find and Fix Function</h4> 
* The **_find** function is a generator that yields errors as they get found. 
* The **_fix** function fixes one of these errors at a time. In the example above we could find multiple animation curves, but the fix only deletes one animation curve at a time.

<h4>Note</h4>
Inspired by Martin Orlowski's <strong>Quality GuAard</strong>, I've decided to write my own quality assurance framework and make it freely available. The project is available on [Git](https://github.com/robertjoosten/rjQualityAssurance). Free for anybody that wishes to contribute to this tool and add additional quality assurance checks. 