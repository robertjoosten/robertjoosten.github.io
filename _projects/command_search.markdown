---
layout: post
title: Maya - Command Search
description: Read all buttons in Maya's native menu and make them searchable and executable.
img: /img/tools/command_search_thumbnail.png
date: 2014-10-19 10:24:00
category: tools
tag: [tool, python, maya, pyside]
github: https://github.com/robertjoosten/maya-command-search
github-docs: https://robertjoosten.github.io/maya-command-search/
gumroad: https://gum.co/maya-command-search
---
<p class="justify">Read all buttons in Maya's native menu and make them searchable and executable.</p>

<p align="center"><img src="/img/tools/command_search_demo.gif"/></p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the commandSearch.mel file in Maya to permanently install the script.

<h4>Note</h4>
<p class="justify">Every time the UI is opened for the first time in a new session of Maya, the script loops over all of Maya's menu bar content to retrieve all of the its information and store it in an easy accessible format. Since its over 1600 buttons, this process will take a few seconds.</p>

<p class="justify">The commands can always be refreshed by clicking on the magnifying glass button.</p>

<p class="justify">It is also possible to store your pins and create different pins sets for different tasks, meaning you can create your own custom menu. This functionality can be accessed by clicking the magnifying glass button.</p>

<p class="justify">Also a thank you too Perry Leijten and Guillaume Dufief for their ideas and pointers to improve the script.</p>

<h4>Hotkey</h4>
<p class="justify">The hotkey function can be used to manage the command search widget. This command will set focus to the widget.</p>
{% highlight python %}
import commandSearch; commandSearch.focus()
{% endhighlight %}