---
layout: post
title: Maya - Paint Remove Influences
description: Remove a specific influence on vertices with the paint tool. This tool is part of the maya-skinning-tools.
img: /img/tools/paint_remove_influences_thumbnail.png
date: 2015-05-14 12:38:00
category: tools
tag: [tool, python, maya, maya api, pyside, paint, skinning, custom command]
github: https://github.com/robertjoosten/maya-skinning-tools/tree/master/scripts/skinning/tools/remove_weights_context
github-docs: https://robertjoosten.github.io/maya-skinning-tools/skinning.tools.remove_weights_context
gumroad: https://gum.co/maya-skinning-tools
---
<p class="justify">Remove a specific influence on vertices with the paint tool. This tool is part of the maya-skinning-tools.</p>

<p align="center"><iframe width="640" height="360" src="https://www.youtube.com/embed/zuRi-uvI8n0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p> 

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the skinningTools.mel file in Maya to permanently install the script.

<h4>Note</h4>
<p class="justify">The paint tool calls a script that will select all the vertices that are influenced by the parsed influence. You can then paint away the influence on those vertices with the paint tool.</p>
<ul>
 	<li>Undo-able / Redo-able</li>
</ul>
<p class="justify">Based on the settings on the skinCluster the following attribute will be respected while removing the influence weights:</p>
<ul>
 	<li>Normalize Weights</li>
 	<li>Locked Influences</li>
</ul>