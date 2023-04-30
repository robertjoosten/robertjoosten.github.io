---
layout: post
title: Video > Mocap
description: Automatically convert video into a mocap skeleton that can be used in Maya.
img: /img/rnd/video2mocap_thumbnail.png
date: 2018-06-28 22:00:00
category: [rnd]
tag: [rnd, python, mocap]
github: https://github.com/robertjoosten/video2mocap
---

<p align="center"><iframe width="640" height="360" src="https://www.youtube.com/embed/tP0OAlUwj5E" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

<p class="justify">After seeing the amazing work done by Angjoo Kanazawa, Michael J. Black, David W. Jacobs, Jitendra Malik on the End-to-end Recovery of Human Shape and Pose paper. I wanted to have a look if I could use <a href="https://github.com/CMU-Perceptual-Computing-Lab/openpose"><strong>OpenPose</strong></a> and <a href="https://github.com/akanazawa/hmr"><strong>HMR</strong></a> to implement a one click video to mocap solution. The script takes a video and outputs a separate maya file for each person in the video containing and animated HIK skeleton.</p>

<p class="justify">The HMR repository was slightly adjusted to work with python3 in a windows environment and matrices to be exported over multiple frames to support video. The number of joints exported by the HMR solution is insufficient to create a working HIK skeleton, a center hip and spine joint had to be estimated. The OpenPose util was updated to recognize the same person over multiple frames, and omit people if they are under a certain presence threshold.</p>

<p class="justify">For this demo the animation curves exported have been simplified to reduce initial jitter. As you can see it will not be a render ready solution but potentially a great tool to get an initial starting point or simply to be used as 3D reference.</p>

<h4>Index</h4>
<ul>
    <li><a href="#installation">Installation</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#limitations">Limitations</a></li>
    <li><a href="#logs">Logs</a></li>
    <li><a href="#credits">Credits</a></li>
    <li><a href="#versions">Versions</a></li>
    <li><a href="#citations">Citations</a></li>
</ul>

<h4 id="installation">Installation</h4>
Clone repository:
{% highlight bash %}
git clone https://github.com/robertjoosten/video2mocap.git
{% endhighlight %}
    
<p class="justify">In order for this tool to work a couple of 3rd party application will have to be installed. To make this an easy process bat files are located in the 3rdparty directory and can be used to download/extract and install the necessary applications.</p>

*   Run 3rdparty/getFFmpeg.bat
    - Download and extract FFmpeg ( 20180630-9f0077c ).

*   Run 3rdparty/getOpenPose.bat
    - Download and extract OpenPose ( 1.3.0 ).
    - Download models for OpenPose

*   Run 3rdparty/getHMR.bat ( Requires python3 + pip3 accessible in PATH )
    - Pull the latest custom fork of the HMR repository.
    - Download models for HMR
    - Pip install requirements.txt
    
<h4 id="usage">Usage</h4>
From the command line:
{% highlight bash %}
cd video2mocap/
python video2mocap.py --video_path <VIDEO> --output_dir <OUTPUT>
{% endhighlight %}
    
Available Arguments:
*   **--video_path**: Path to video
*   **--output_dir**: Directory to output the maya files too
*   **--keep_temp**: Keep temp files for debugging ( False by default )
*   **--mayapy_exe**: Overwrite mayapy.exe ( Default requires accessible in PATH )
*   **--python2_exe**: Overwrite python.exe ( Default requires accessible in PATH )
*   **--python3_exe**: Overwrite python3.exe ( Default requires accessible in PATH )

<p class="justify">The exe files can be overwritten in case the python interpreters are not accessible through the PATH variable and a relative path cannot be provided.</p>

<h4 id="limitations">Limitations</h4>
*   No camera tracking ( static camera advised )
*   No partial body ( full body in view each frame advised )
*   No ankle/wrist and head rotation
*   Limited depth adjustment

<h4 id="logs">Logs</h4>
<p class="justify">As loads of things are running in process it is quite simple for something to go wrong. For this reason a log file is implemented that gets saved into the output_dir. If the desired result is unexpected these logs can be investigated to find out what and where something went wrong.</p>

Keypoint matching example:
{% highlight text %}
2018/07/05/ 12:31:40 | INFO | ---- Match Keypoints Over Multiple Frames ----
2018/07/05/ 12:31:40 | DEBUG | New Person:            Frame 276
2018/07/05/ 12:31:40 | DEBUG | Omit Person:           Presence Percentage 0.01
{% endhighlight %}

<h4 id="credits">Credits</h4>
*   Source video: <a href="https://www.youtube.com/watch?v=TcWPiHjIExA">Napoleon Dynamite</a>
*   Female Model: <a href="https://www.artstation.com/mfalzon"><strong>Michael Falzon</strong></a>

<h4 id="versions">Versions</h4>

*   HMR ( custom fork )
    - Link: <a href="https://github.com/robertjoosten/hmr">https://github.com/robertjoosten/hmr</a>
    - Original Link: <a href="https://github.com/akanazawa/hmr">https://github.com/akanazawa/hmr</a>

*   OpenPose
    - Version v1.3.0.
    - Link: <a href="https://github.com/CMU-Perceptual-Computing-Lab/openpose/releases">https://github.com/CMU-Perceptual-Computing-Lab/openpose/releases</a>

*   FFmpeg
    - Version 20180630-9f0077c.
    - Link: <a href="https://ffmpeg.zeranoe.com/builds/">https://ffmpeg.zeranoe.com/builds/</a>

*   7Zip
    - Version 18.05.
    - Link: <a href="https://www.7-zip.org/download.html">https://www.7-zip.org/download.html</a>

*   Wget:
    - Version wget-1.19.1-win64.
    - Link: <a href="https://eternallybored.org/misc/wget/">https://eternallybored.org/misc/wget/</a>

<h4 id="citations">Citations</h4>
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


