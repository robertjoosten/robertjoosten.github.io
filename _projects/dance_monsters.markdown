---
layout: post
title: Dance Monsters
description: 
img: /img/commercials/dance_monsters_thumbnail.png
date: 2023-02-09 18:00:00
category: [projects, rigging, tools]
tag: [mocap, rigging, realtime, maya]
---
<p align="center"><iframe src="https://player.vimeo.com/video/797430465?h=09e34531f3" width="640" height="360" frameborder="0" allow="autoplay; fullscreen; picture-in-picture" allowfullscreen></iframe><p>

<p class="justify">For Netflix's Dance Monsters, I created a tool that allows the creation of meta data within a rig that defines that mapping from the skeleton to the controls. This would allow for all of the skeletal motion capture to be applied back onto the control rig. Rather than the simple constraint with offset that the Custom Rig feature within Maya's HumanIK supports, the tool allows for the creation of custom logic that drives the control using skeletal transformation. These custom logic implementations have been created using <a href="https://robertjoosten.github.io/projects/mango/">Mango</a> and support foot rolls and pole vectors making it easier for the animators to clean-up the motion capture data.</p>

<p class="justify">This tool has not only been useful on Dance Monsters but working with our Game clients at Realtime we have been able to use skeletal animation published for use within the game engine and drive our control rigs in Maya using them, providing an extensive library and great starting point for our animators. <a href="https://robertjoosten.github.io/projects/frankenstein/">Frankenstein</a> is used to inject the meta data during the rig build process.</p>
