---
layout: post
title: Maya - Command Search
description: Read all buttons in Maya's native menu and make them searchable and executable.
img: /img/tools/command_search_thumbnail.png
date: 2014-10-19 10:24:00
category: tools
tag: [tool, python, maya, pyside, search, command]
github: https://github.com/robertjoosten/rjCMDSearch
github-docs: https://robertjoosten.github.io/rjCMDSearch/
gumroad: https://gum.co/rjCMDSearch
---
<p class="justify">Read all buttons in Maya's native menu and make them searchable and executable.</p>

<p align="center"><img src="/img/tools/command_search_demo.gif"/></p>

<h4>Installation</h4> 
<p class="justify">Copy the rjCMDSearch folder to your Maya scripts directory: </p>
{% highlight text %}
C:\Users\<USER>\Documents\maya\scripts
{% endhighlight %}

<h4>Usage</h4> 
Add the interface and functionality to Maya:
{% highlight python %}
import maya.cmds as cmds 
cmds.evalDeferred("import rjCMDSearch; rjCMDSearch.install()")
{% endhighlight %}
<p class="justify">This line of code can also be added in the userSetup.py if you would like the functionality to persist. </p>

<h4>Note</h4>
<p class="justify">Every time the UI is opened for the first time in a new session of Maya, the script loops over all of Maya's menu bar content to retrieve all of the its information and store it in an easy accessible format. Since its over 1600 buttons, this process will take a few seconds. Its best to add this script to the userSetup.py so the interface will automatically be added to Maya when it is started.</p>

<p class="justify">The commands can always be refreshed by clicking on the magnifying glass button.</p>

<p class="justify">The script now also tries to install a hotkey on the Ctrl + Alt + Space combination. If there is already a hotkey on this combination the hotkey will not be installed. This hotkey will set the focus to the search command and open up the menu if there are any matches.</p>

<p class="justify">It is also possible to store your pins and create different pins sets for different tasks, meaning you can create your own custom menu. This functionality can be accessed by clicking the magnifying glass button.</p>

<p class="justify">Also a thank you too Perry Leijten and Guillaume Dufief for their ideas and pointers to improve the script.</p>

<h4>Command line</h4>
<p class="justify">The following functions can be used outside of the UI. Make sure the language is set to python.</p>
{% highlight python %}
import rjCMDSearch; rjCMDSearch.focus()
{% endhighlight %}