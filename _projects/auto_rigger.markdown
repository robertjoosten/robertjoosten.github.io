---
layout: post
title: Another Auto Rigger
description: Auto rigger in Maya.
img: /img/rigging/auto_rigger_thumbnail.png
date: 2018-02-18 09:43:00
category: [rigging, tools]
tag: [rigging, maya, python, tool, realtime, touch surgery]
---
<p class="justify">The auto rigger is the result of Friday afternoons personal development time at <a href="https://www.touchsurgery.com">Touch Surgery</a>. A complex modular rigging system that uses building blocks to build a finished rig. To access the API user interfaces are created to make the rigging process easy and user friendly. The rig is fully joint based and can be exported into realtime engines like Unity and Unreal</p> 
<ul>
    <li><a href="#creation">Creation</a></li>
    <li><a href="#body">Body Features</a></li>
    <li><a href="#facial">Facial Features</a></li>
    <li><a href="#deformation">Deformation</a></li>
    <li><a href="#credits">Credits</a></li>
</ul>
<h3 id="creation">Creation</h3>
<br>
<p align="center"><iframe src="https://player.vimeo.com/video/256283167?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p> 

<h4>Gender</h4>
<p class="justify">The biped preset has a female and a male creation mode. Breast controls are added when the female creation mode is chosen.</p>

<h4>Presets</h4>
<p class="justify">Presets can be applied on attributes, barycentric coordinate or UV coordinate level. When a studio works with characters that have the same point order or the same UVs, only one preset will have to be created and it can be applied to all characters, cutting down the time spend in the setup preparation stage. The facial presets are stored based on object name and vertex/edge number.</p> 

<h4>Manager</h4>
<p class="justify">The manager can be used to set/key display attributes of the rig. But it is also there to easily select controls and access the functions that are attached to certain building blocks.</p> 

<h3 id="body">Body Features</h3>
<br>
<p align="center"><iframe src="https://player.vimeo.com/video/256282460?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p> 

<h4>Character</h4>
<ul>
    <li>Scalable</li>
</ul>

<h4>Spine</h4>
<ul>
    <li>FK <-> IK</li>
    <li>FK <-> IK ( matching )</li>
    <li>Hips wiggle</li>
    <li>Projected fake muscles ( abs, love handles, chest, deltiod, trapezius)</li>
</ul>

<h4>Limb</h4>
<ul>
    <li>FK <-> IK</li>
    <li>FK <-> IK ( matching )</li>
    <li>Stretchy IK</li>
    <li>Volume preservation ( shifting, multiplier )</li>
    <li>Split twist values over multiple joints</li>
    <li>Lockable joint</li>
    <li>Cartoony bend</li>
    <li>No-flip legs</li>
    <li>Projected helper joints ( hip, knee, ankle, elbow, wrist )</li>
</ul>

<h4>Hand</h4>
<ul>
    <li>FK <-> IK fingers</li>
    <li>Finger curl attributes</li>
    <li>Finger spread attribute</li>
    <li>Animatable pivot</li>
    <li>Projected helper joints ( finger joints )</li>
</ul>

<h4>Foot</h4>
<ul>
    <li>Curved based foot roll</li>
    <li>Variable ball break</li>
    <li>Variable foot swivel</li>
</ul>

<h3 id="facial">Facial Features</h3>
<br>
<p align="center"><iframe src="https://player.vimeo.com/video/256286886?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p> 

<h4>Facial Expressions</h4>
<p class="justify">A total of 47 different shapes are generated based on the distance/angle between joints and surface normal of the geometry. Each shape is accessable through attributes on the head control. 19 shapes are generated using the face controls and 28 shapes are generated with the mouth controls</p>

<h4>Face</h4>
<ul>
    <li>Facial tweak controls ( 28 )</li>
    <li>Automatically generated face shapes ( 19 )</li>
</ul>

<h4>Eye</h4>
<ul>
    <li>Blink ( adjustable rest point )</li>
    <li>Iris dilation</li>
    <li>Fleshy eye</li>
    <li>Cornea push ( adjustable cornea size )</li>
</ul>

<h4>Mouth</h4>
<ul>
    <li>Distance based sticky lips</li>
    <li>Automatically generated mouth shapes ( 28 )</li>
    <li>Variable jaw pivot based on projected points on geometry</li>
    <li>Close mouth ( automatic / manual )</li>
</ul>

<h4>Tongue</h4>
<ul>
    <li>IK ( twist, roll )</li>
    <li>Stretchy IK</li>
    <li>Volume preservation ( shifting, multiplier )</li>
    <li>Tongue curl</li>
</ul>

<h3 id="deformation">Deformation</h3>
<br>
<p align="center"><iframe src="https://player.vimeo.com/video/256288130?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p> 

<h4>Deformation System</h4>
<p class="justify">The deformation is driven by a color coded skeleton.</p>
<ul>
    <li><strong style="color:black;">Black</strong>: standard deformation system</li>
    <li><strong style="color:green;">Green</strong>: twister joints</li>
    <li><strong style="color:yellow;">Yellow</strong>: helper joints</li>
    <li><strong style="color:red;">Red</strong>: muscle joints</li>
</ul>

<h4>Twister Joints</h4>
<p class="justify">Twister joints are used to divide the twist value of one joint out over many, this is done to prevent the candy wrapper effects. Another side effect of creating twister joints is that these joints are driven by a curve that can be setup to facilitate cartoony bending. On top of this each twister joint can be controlled individually.</p>

<h4>Helper Joints</h4>
<p class="justify">Helper joints are projected on the geometry and are used to maintain volume around skeletal joints. The projected joints offset position and strength are adjustable.</p>

<h4>Muscle Joints</h4>
<p class="justify">Muscle joints are projected on the geometry and help create more realistic deformation. The muscle bulge strength can be adjusted and is triggered based on distance between the insertion and origin point.</p>

<h3 id="credits">Credits</h3>
<ul>
    <li>Female Modelling Topology: <a href="http://www.makehuman.org">Make Human</a></li>
    <li>Female Modelling: <a href="https://www.artstation.com/mfalzon"><strong>Michael Falzon</strong></a></li>
    <li>Male Modelling: <a href="http://www.3dscanstore.com">3D Scan Store</a></li>
    <li>Male Modelling Cleanup: <a href="https://www.artstation.com/mfalzon"><strong>Michael Falzon</strong></a></li>
    <li>Cartoon Modelling: <a href="https://www.artstation.com/jhpacheco"><strong>João Henrique Pachêco</strong></a> for <a href="http://www.aeroorange.com">Aero Orange</a></li>
</ul>
