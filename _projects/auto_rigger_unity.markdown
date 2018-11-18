---
layout: post
title: Unity - Another Auto Rigger
description: Runtime joints for the Another Auto Rigger system in Unity.
img: /img/rigging/auto_rigger_unity_thumbnail.png
date: 2018-11-18 12:00:00
category: [rigging, tools, rnd]
tag: [rigging, unity, c#, tool, realtime]
github: https://github.com/robertjoosten/unity-another-auto-rigger/
---

<p class="justify">The auto rigger contains a lot of helper joints, these helper joints are not going to be driven by the Unity's Mecanim system. The runtime manager script allows you to apply the .skeletonPreset file exported in Maya to the skeleton in Unity. It will apply scripts to the helper joints and set the correct settings coming from Maya meaning the deformation will be identical between the two applications. Once this process is done the helper joints are driven by joints that are controlled by the Mecanim system.</p> 

<p align="center"><iframe src="https://player.vimeo.com/video/301451175?color=ff9933&title=0&byline=0&portrait=0" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p> 

<h4>Runtime Manager</h4>
<br>
<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_manager_inspector.png" alt="Runtime Manager Inspector"><br>
<i>Runtime Manager Inspector</i>
</p>

<h4>Runtime Helper</h4>
<p class="justify">The runtime helper setup contains 2 different scripts. The helper joints are used to preserve volume in areas like the hips, knee, wrist, elbow etc. The helper translate script will preserve volume by translating the joint based on rotational values and the helper aim joint will preserve volume aiming its joint towards a target. The aim joint is a child of the translate joint.</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_helper.gif" alt="Runtime Helper Example"><br>
<i>Runtime Helper Example</i>
</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_helper_translate_inspector.png" alt="Runtime Helper Translate Inspector"><br>
<i>Runtime Helper Translate Inspector</i>
</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_helper_aim_inspector.png" alt="Runtime Helper Aim Inspector"><br>
<i>Runtime Helper Aim Inspector</i>
</p>

<h4>Runtime Twister</h4>
<p class="justify">The runtime twister can split the twist value of a parent joint and only apply a fraction of that to the helper joint. This will help prevent the candy wrapper effect.</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_twister.gif" alt="Runtime Twister Example"><br>
<i>Runtime Twister Example</i>
</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_twister_inspector.png" alt="Runtime Twister Inspector"><br>
<i>Runtime Twister Inspector</i>
</p>

<h4>Runtime Muscle</h4>
<p class="justify">The runtime muscle is the more complex of the runtime joints. It mimics the behaviour of a muscle, it has a origin and an insertion point driven by parent joints. This script also features an option that is not available in Maya, it is possible to make the joint dynamic. The dynamics will add a natural jiggle to the joint which boosts realism.</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_muscle.gif" alt="Runtime Muscle Example"><br>
<i>Runtime Muscle Example</i>
</p>

<p align="center">
<img src="/img/rigging/auto_rigger_unity/runtime_muscle_inspector.png" alt="Runtime Muscle Inspector"><br>
<i>Runtime Muscle Inspector</i>
</p>

<h4>Credits</h4>
* Modelling Topology: <a href="http://www.makehuman.org">Make Human</a>
* Modelling: <a href="https://www.artstation.com/mfalzon"><strong>Michael Falzon</strong></a>
* Animation: <a href="https://assetstore.unity.com/packages/3d/animations/everyday-motion-pack-free-115067">Everyday Motion Pack Free</a>