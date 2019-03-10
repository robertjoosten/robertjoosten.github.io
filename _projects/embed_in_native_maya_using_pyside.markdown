---
layout: post
title: Embed in Native Maya using PySide
description: Add widget to native Maya UI elements.
home: false
img: /img/tutorials/embed_in_native_maya_using_pyside_thumbnail.png
date: 2019-03-10 09:00:00
category: tutorials
tag: [tutorial, maya]
---
<p class="justify">When I create tools that extend the functionality of Maya, I always prefer to embed them into the native UI where possible. If you look at the other options, like creating a shelf button or asking the user of your tools to run the code in the script editor, the embedding of your tools will make them easier to find and less troublesome to execute. In the tutorial I will go over how to find the native UI elements and how to convert them into a PySide object. This PySide object can then be used to add your own widgets. As an example I will be adding a label to Maya's native status bar.</p>

<p align="center"><img src="/img/tutorials/embed_in_native_maya_using_pyside_example.png"/></p>

<h4>Find global MEL variable</h4> 
<p class="justify">To make sure the embedding into Maya's native UI is robust between different versions it is best to have your starting point be a global MEL variable. Maya has a lot of global MEL variables pointing to UI elements, even if the UI element name changes between different version of Maya, the global MEL variable will remain to be the same, it will simply contain a different value.</p>

<p class="justify">Finding the right global variable can be tricky. You can use the helper function below to search through all global MEL variables. If the function doesn't give you the result you are after it is possible to provide no argument to the function to print all variables.</p>

{% highlight python %}
from maya import cmds, mel

def matchMelVariables(searchString=None):
    """
    Loop over all global MEL variables and if a search string is provided
    print only the global MEL variables that match the search string.
    
    :param str/None search_string:
    """
    for var in sorted(mel.eval("env")):
        if not searchString or var.lower().count(searchString):
             yield var
{% endhighlight %}

<p class="justify">The goal if this tutorial is to embed a widget in Maya's native status bar. To find the correct global MEL variable, the first attempt is to search for <b>status</b>, as seen in the example below.</p>

{% highlight python %}
for var in matchMelVariables("status"):
    print var
    
# $gFilterUIFilterStatusControlList
# $gStatusLine
# $gStatusLineForm
# $gStatusLineVisible
{% endhighlight %}

<h4>Convert global MEL variable to UI path</h4> 
<p class="justify">The global MEL variable contains the Maya name of the UI element, there is nothing stopping you from using Maya's python or mel native UI commands to work with this variable. The function below shows you how to evaluate the global MEL variable into a python variable. If you would like to convert any other variable you can replace the <b>$gStatusLine</b> part of the string with the variable name you would like to convert.</p>

{% highlight python %}
statusLineName = mel.eval("$tmp=$gStatusLine")
print statusLineName
    
# StatusLine|MainStatusLineLayout|formLayout4|flowLayout1
{% endhighlight %}

<h4>Convert UI path to PySide object</h4> 
<p class="justify">The next step is to convert this UI path into a PySide object. Displayed in the helper function below, the PySide object can be retreived using the Maya API.</p>

{% highlight python %}
from maya import OpenMayaUI
from PySide2 import QtWidgets
import shiboken2

def convertPathToPySideObject(name):
    """
    Convert a Maya UI element string into a PySide object. Using the 
    Maya API, a match will be found if the string exists as a control, 
    layout or menu item.
    
    :param str name: UI path of Maya UI element
    :return: PySide object of Maya UI element
    :rtype: QWidget
    """
    ptr = OpenMayaUI.MQtUtil.findControl(name)
    if ptr is None:         
        ptr = OpenMayaUI.MQtUtil.findLayout(name)    
    if ptr is None:         
        ptr = OpenMayaUI.MQtUtil.findMenuItem(name)
    if ptr is not None:     
        return shiboken2.wrapInstance(long(ptr), QtWidgets.QWidget)
{% endhighlight %}

{% highlight python %}
statusLineObj = convertPathToPySideObject(statusLineName)
print statusLineObj
    
# <PySide2.QtWidgets.QWidget object at 0x0000000065085248>
{% endhighlight %}

<h4>Embed custom UI elements</h4> 
<p class="justify">The hard part is over now, what remains is adding your custom UI elements. Depending on what you converted into a PySide object, you will be able to loop through the objects children, menus and layouts. The following example will add a simple label to Maya's native status bar.</p>

{% highlight python %}
# create label
label = QtWidgets.QLabel(statusLineObj)
label.setText("Hello!")

# add label to status line layout
statusLineObj.layout().addWidget(label)
{% endhighlight %}

<p class="justify">After running the code above a label is attached to the status bar as can be seen in the example image below. If you would like to add a UI element on launch of Maya you can add the creation code into a userSetup.py file.</p>

<p align="center"><img src="/img/tutorials/embed_in_native_maya_using_pyside_example.png"/></p>