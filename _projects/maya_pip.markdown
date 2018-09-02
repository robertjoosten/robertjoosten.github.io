---
layout: post
title: Maya - PIP
description: The Maya wrapper to <a href="https://github.com/pypa/pip" target="_blank">pip</a> for installing Python packages.
img: /img/tools/maya_pip_thumbnail.png
date: 2018-08-19 12:00:00
category: tools
tag: [tool, python, maya, pip, pypi]
github: https://github.com/robertjoosten/maya-pip
---
<p class="justify">The Maya wrapper to <a href="https://github.com/pypa/pip" target="_blank">pip</a> for installing Python packages.</p>

<p align="center"><img src="/img/tools/maya_pip_example.gif"/></p>

<h4>Installation</h4> 
Using pip:
{% highlight bash %}
pip install https://github.com/robertjoosten/maya-pip/archive/v0.1.1.tar.gz
{% endhighlight %}

If you prefer to install from source code use:
{% highlight bash %}
cd maya-pip
python setup.py install
{% endhighlight %}

<h4>Usage</h4> 
<p class="justify">This tool is a wrapper around pip. The tool will find the Maya python executables and uses it to execute the pip command. By using the Maya python executable the packages will be installed in the site-packages directory of the chosen version of Maya.</p>

Command line:

**mayapip**

* **-h**               
Will print the default help from the pip command

* **--maya_version**    
Which version of Maya to use<br>
( only needs to be provided if multiple version of Maya are installed )

<h4>Limitations</h4>
<p class="justify">At the moment this version of mayapip will only work on Windows, this is because I don't have any of the other platforms at my disposal. Feel free to implement solution for Mac and Linux in the maya directory and submit a pull request.</p>

<h4>Examples</h4>
<p class="justify">Installing an older version of pyyaml on Maya 2017.</p>
{% highlight bash %}
mayapip install pyyaml==3.11 --maya_version=2017
>>> Successfully installed pyyaml-3.11
{% endhighlight %}
{% highlight python %}
# in maya 2017
import yaml 

print yaml.__version__
print yaml.__file__
>>> 3.11
>>> C:\Program Files\Autodesk\Maya2017\Python\lib\site-packages\yaml\__init__.pyc
{% endhighlight %}  

<p class="justify">Installing the latest version of pyyaml on Maya 2018.</p>
{% highlight bash %}
mayapip install pyyaml --maya_version=2018
>>> Successfully installed pyyaml-3.13
{% endhighlight %}
{% highlight python %}
# in maya 2018
import yaml

print yaml.__version__
print yaml.__file__
>>> 3.13
>>> C:\Program Files\Autodesk\Maya2018\Python\lib\site-packages\yaml\__init__.pyc
{% endhighlight %}  

<p class="justify">Uninstalling pyyaml from Maya 2018, leaving the Maya 2017 environment intact.</p>
{% highlight bash %}
mayapip uninstall pyyaml --maya_version=2018
>>> Successfully uninstalled PyYAML-3.13  
{% endhighlight %} 
