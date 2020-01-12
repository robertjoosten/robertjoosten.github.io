---
layout: post
title: The Witcher
description: 
img: /img/tv/the_witcher_thumbnail.png
date: 2020-01-12 20:00:00
category: [projects, rigging]
tag: [rigging, witcher, framestore, maya]
---
<p align="center"><img class="col three" src="/img/tv/the_witcher_banner.png"/></p>

<p class="justify">When I started working at <a href="https://www.framestore.com/work/witcher">Framestore</a> most of the rigging work on The Witcher had already been completed. A couple of months later an ear worm had slipped through the cracks and I was assigned the job. </p>

<p class="justify">As the worms are very small, a problem with scale presented itself. Spline IKs are notoriously bad at solving on curves with a very small length. This problem was solved by scaling the Spline IK elements to ensure that the joint was placed on the curves without popping. To give the animators the most amount of control, various IK and FK systems were layered. Another nice addition was a variable up vector along the entire curve driven by the various IK controls, when using the offset attribute on the Spline IK handle to snake the worm on a curve the up vector was determined by the position on the curve relating to its closest IK controls.</p>
