---
layout: post
title: Animatable Pivot using a Constraint
description: How to setup an animatable pivot in maya using constraints.
img: /img/tutorials/animatable_pivot_thumbnail.png
date: 2013-11-14 18:18:00
category: tutorials
tag: [tutorial, maya]
---
How to setup an animatable pivot in maya using constraints.

<p align="center"><iframe width="640" height="360" src="https://www.youtube.com/embed/cHLoJVRfLjA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<h4>Method</h4> 
<p class="justify">The animatable pivot is created by connecting the inverseMatrix of the offset control to the offsetTranslation and offsetRotation of the parent constraint.</p> 

<h4>Note</h4>
<p class="justify">The parent_loc position changes after setting the animatable pivot up ( if outside of the origin ), this means that the parenting of the objects to the locator need to be done after the initial setup. The top group can be parented, scaled, translated and rotated without destroying the setup.</p>