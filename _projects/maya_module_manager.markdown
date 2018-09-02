---
layout: post
title: Maya - Module Manager
description: Module manager for Maya.
img: /img/tools/maya_module_manager_thumbnail.png
date: 2018-09-02 12:00:00
category: tools
tag: [tool, python, maya, module]
github: https://github.com/robertjoosten/maya-module-manager
github-docs: https://robertjoosten.github.io/maya-module-manager/
gumroad: https://gum.co/maya-module-manager
---
<p class="justify">Manage modules in Maya by toggling modules on or off, displays general information and grants easy access the module file and code.</p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the moduleManager.mel file in Maya to permanently install the script.

<h4>Usage</h4>

<p align="center"><img class="col three" src="/img/tools/maya_module_manager_example.png"/></p>

<p class="justify">Modules can be (de)activated by toggling the checkbox <strong>[2]</strong>. The user is also presented with other information regarding the module, its version, the maya version, platform and language. By default the manager will only show you modules that are compatible with the version of Maya you are running, by toggling the <strong>show all</strong> checkbox all modules associated with the file can be edited. Press the folder to open the module file with the associated application. This will make it possible to easily edit the file manually if need be <strong>[4]</strong>.</p>

<p class="justify">The file itself can be managed directly by pressing the folder button next to the module filename <strong>[1]</strong>. Doing this will open up the file in the associated application. It is also possible to dive directly into the module code itself by pressing the folder button <strong>[3]</strong>. This will open up the folder of the module content in your browser.</p>

<p class="justify">This manager edits the module files on disk, it is possible that the user won't have permissions to edit the module files. If this is the case the module will still be displayed but the widget is disabled preventing the user from editing the file <strong>[5]</strong>.</p>

