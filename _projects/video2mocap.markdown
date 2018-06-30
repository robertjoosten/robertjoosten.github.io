---
layout: post
title: Video > Mocap
description: Automatically convert video into a mocap skeleton that can be used in Maya.
img: /img/rnd/video2mocap_thumbnail.png
date: 2018-06-28 22:00:00
category: [rnd]
tag: [rnd, python, mocap]
---

<p align="center"><iframe src="https://player.vimeo.com/video/277548081" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<p class="justify">After seeing the amazing work done by Angjoo Kanazawa, Michael J. Black, David W. Jacobs, Jitendra Malik on the End-to-end Recovery of Human Shape and Pose paper. I wanted to have a look if I could use <a href="https://github.com/CMU-Perceptual-Computing-Lab/openpose"><strong>OpenPose</strong></a> and <a href="https://github.com/akanazawa/hmr"><strong>HMR</strong></a> to implement a one click video to mocap solution. The script takes a video and outputs a separate maya file for each person in the video containing and animated HIK skeleton.</p>

<p class="justify">The HMR repository was slightly adjusted to work with python3 in a windows environment and matrices to be exported over multiple frames to support video. The number of joints exported by the HMR solution is insufficient to create a working HIK skeleton, a center hip and spine joint had to be estimated.</p>

<p class="justify">For this proof of concept the facial joints have been omitted and the animation curves exported have been simplified to reduce initial jitter. As you can see it will not be a render ready solution but potentially a great tool to get an initial starting point or simply to be used as 3D reference.</p>

<h4>Credits</h4>
<ul>
    <li>Source video: <a href="https://www.youtube.com/watch?v=TcWPiHjIExA">Napoleon Dynamite</a></li>
    <li>Female Model: <a href="https://www.artstation.com/mfalzon"><strong>Michael Falzon</strong></a></li>
    <li>Repositories: <a href="https://github.com/akanazawa/hmr"><strong>HMR</strong></a> & <a href="https://github.com/CMU-Perceptual-Computing-Lab/openpose"><strong>OpenPose</strong></a></li>
</ul>

<h4>Citations</h4>
<ul>
    <li>
    <a class="url"><span class="title">End-to-end Recovery of Human Shape and Pose</span></a><br>
    <span class="author">Angjoo Kanazawa
    and Michael J. Black
    and David W. Jacobs
    and Jitendra Malik</span><br>
    <span class="booktitle">Computer Vision and Pattern Regognition (CVPR)</span>
    <span class="">
    <span class="year">2018</span></span>
    </li>
    <li>
    <a class="url"><span class="title">Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields</span></a><br>
    <span class="author">Zhe Cao and Tomas Simon and Shih-En Wei and Yaser Sheikh</span><br>
    <span class="booktitle">CVPR</span>
    <span class="">
    <span class="year">2017</span></span>
    </li>
    <li>
    <a class="url"><span class="title">Hand Keypoint Detection in Single Images using Multiview Bootstrapping</span></a><br>
    <span class="author">Tomas Simon and Hanbyul Joo and Iain Matthews and Yaser Sheikh</span><br>
    <span class="booktitle">CVPR</span>
    <span class="">
    <span class="year">2017</span></span>
    </li>
    <li>
    <a class="url"><span class="title">Convolutional pose machines</span></a><br>
    <span class="author">Shih-En Wei and Varun Ramakrishna and Takeo Kanade and Yaser Sheikh</span><br>
    <span class="booktitle">CVPR</span>
    <span class="">
    <span class="year">2016</span></span>
    </li>
</ul>


