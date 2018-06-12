---
layout: post
title: Image Sequence > Point Cloud
description: Convert an image sequence to a PLY point cloud.
img: /img/rnd/img2ply_thumbnail.png
date: 2017-10-14 13:50:00
category: [tools, rnd]
tag: [rnd, pypi, anatomy, visible human]
github: https://github.com/robertjoosten/img2ply
---

<p class="justify">Converted the visible human project image sequence into a point cloud ( PLY ) format that can be used in Houdini. For the conversion I wrote a tool called img2ply.<p>

<h4>Conversion</h4>
<p class="justify">The point cloud has a total of 53.801.266 points and the source files are compressed down to a width of 500 pixels to keep the file use-able. On higher end machines the 1000 pixel version can easily be opened where a lot more detail will be visible. It is interesting to explore the human anatomy and being able to look at the internals from any angle using the clipping plane on the camera. The point cloud without compression is 65gb in size and I haven't been able to open.</p>

<h4>Visible Human Project</h4>
<p class="justify">If you would like to create your own point cloud, the visible human project can be downloaded <a href="https://www.nlm.nih.gov/research/visible/visible_human.html">here</a>.</p>

<p align="center"><iframe src="https://player.vimeo.com/video/238207429?color=ff9933&title=0&byline=0&portrait=0" width="640" height="340" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe></p>

<h4>Installation</h4>
Using pip:

{% highlight text %}
pip install img2ply
{% endhighlight %}

If you prefer to install from source code use:

{% highlight text %}
cd img2ply/
python setup.py install  
{% endhighlight %}

<h4>Usage</h4>
From the command line:

{% highlight text %}
img2ply -h

img2ply [-h] -o PLY -bb BOUNDINGBOX BOUNDINGBOX BOUNDINGBOX
  [--depthDirection DEPTHDIRECTION] [--depthInverse DEPTHINVERSE]
  [--ignoreAlpha IGNOREALPHA] [--widthSamples WIDTHSAMPLES]
  [--heightSamples HEIGHTSAMPLES]
  [--maintainAspectRatio MAINTAINASPECTRATIO]
  input

input:                  path to image sequence
-o:                     output file path
-bb:                    bounding box of object in x, y, z
--depthDirection:       direction in which the slices are facing
--depthInverse:         reverse the placement of the slices
--ignoreAlpha:          ignore pixels with an alpha value below 25
--widthSamples:         amount of width samples, if 0 every pixel is sampled
--heightSamples:        amount of height samples, if 0 every pixel is sampled
--maintainAspectRatio:  maintain aspect ratio of sample points
{% endhighlight %}

The package can also be used as a library:

{% highlight python %}
import img2ply
img2ply.convert(
    input, 
    ply, 
    bb,
    direction="z", 
    inverse=False,
    ignoreAlpha=True,
    wSamples=0, 
    hSamples=0, 
    maintainAspectRatio=True
)
{% endhighlight %}