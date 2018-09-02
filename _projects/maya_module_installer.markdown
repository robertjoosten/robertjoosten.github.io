---
layout: post
title: Maya - Module Installer
description: Module template for easy drag-and-drop installation using provided mel script.
img: /img/tools/maya_module_installer_thumbnail.png
date: 2018-08-23 19:00:00
category: tools
tag: [tool, mel, maya, module]
github: https://github.com/robertjoosten/maya-module-installer
---
<p class="justify">Module template for easy drag-and-drop installation using provided mel script.</p>

<h4>Description</h4> 
<p class="justify">Add the module which is located in the same directory as the .mel file into the first available <strong>MAYA_MODULE_PATH</strong> directory. It doesn't matter where on disk the module lives as the script will make sure the path in the .mod file links to the correct place. There are some basic sanity checks in place to make sure the script doesn't error out. This includes Maya version compatibility with the module. Permissions of the directories files have to be written to and incorrectly formatted module files.</p>

<p class="justify">The reason for creating this script is that I have always had trouble finding a good way to distribute scripts. Especially less technical users might have trouble running python/mel code. This method will make it as easy as unpacking the package anywhere on disk and dragging the provided mel file into Maya. The template maya module file can be specific to certain versions of maya, language and operating system. It is also possible to extend the environment variables and adding a userSetup.py. This flexibility will allow you to run code on startup and provide the users with for example a custom shelf that is easily accessible to the user.</p>

<h4>Requires</h4>
* Template .mod file ( place `<PATH>` where normally the file path would go )
* Maya module ( scripts/icons/plug-ins directories etc. )

<h4>Usage</h4>

<p align="center"><img class="col three" src="/img/tools/maya_module_installer_example.gif"/></p>

Drag and drop the mel file into Maya or run `source <MEL_FILE>;`.
<p class="justify">As can be seen in the demo, the userSetup.py gets executed when sourcing the script, ensuring instant access to the code. As Maya's internal load module function is flawed the script path will get temporarily added to sys.path, this is done to make sure the module can be accessed immediately after installation. A restart of Maya is needed to fully complete the installation.</p>

<h4>Maya Module Documentation</h4>
* [Maya Documentation: Distributing Multi-File Modules](https://help.autodesk.com/view/MAYAUL/2018/ENU/?guid=__files_GUID_CB76E356_753B_4837_8C5B_3296C14872CA_htm)
* [Maya Documentation: Maya module paths, folders and versions](https://help.autodesk.com/view/MAYAUL/2018/ENU/?guid=__files_GUID_130A3F57_2A5D_4E56_B066_6B86F68EEA22_htm)
