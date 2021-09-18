---
layout: post
title: Maya - Dem Bones
description: Maya python bindings for DemBones
img: /img/tools/dem_bones_thumbnail.png
date: 2021-09-02 12:00:00
category: tools
tag: [tool, c++, python, maya, maya api]
github: https://github.com/robertjoosten/maya-dem-bones
---
<p class="justify">The repository contains Maya python bindings for <a href="https://github.com/electronicarts/dem-bones">DemBones</a> an implementation of <a href="http://binh.graphics/papers/2012sa-ssdr/">Smooth Skinning Decomposition with Rigid Bones</a>, an automated algorithm to extract the <i>Linear Blend Skinning</i> (LBS) with bone transformations from a set of example meshes. <i>Skinning Decomposition</i> can be used in various tasks:</p>

* Converting any animated mesh sequence, e.g. geometry cache, to LBS, which can be replayed in popular game engines,
* Solving skinning weights from shapes and skeleton poses, e.g. converting blendshapes to LBS,
* Solving bone transformations for a mesh animation given skinning weights.

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Compile python bindings for specific Maya versions.
* Drag the dem-bones.mel file in Maya to permanently install the script.

<h4>Compiling</h4>
<p class="justify">The compiling of the python bindings can be done on by running the build.bat command specifying the desired maya version. The build.bat scripts expects both Maya and Visual studio to be installed in the default directory. If this is not the case the build.bat file can be edited to make sure it links to files that exist on disk. Currently only windows is supported! Following the steps below will create a pyd file for the specified version of Maya in the build directory. As the build.bat builds an environment specific for the version of maya it is not possible to switch maya versions in the same terminal as the build will error.</p>

1. Copy the following libraries to their respective folders in `/extern`:
    - [DemBones](https://github.com/electronicarts/dem-bones) with path `/extern/DemBones/DemBones/Dembones.h`,
    - [pybind11](https://github.com/pybind/pybind11) with path `/extern/pybind11/include/pybind11/pybind11.h`,
    - [Eigen 3.3.9](https://eigen.tuxfamily.org/) with path `/extern/Eigen/Eigen/Dense`,
 
2. Run build.bat
```
cd path/to/maya-dem-bones
build.bat 2022
```

<h4>Usage</h4>
<p class="justify">The python bindings only provide partial mapping to the full capabilities of the <a href="https://github.com/electronicarts/dem-bones">DemBones</a> project. It takes a mesh with a skin cluster and compute the best possible weights and transforms for the existing skeleton. It is possible to exclude weights via a <i>demLock</i> color set and exclude transform calculation via a <i>demLock</i> boolean attribute on the influence. You can extend the functionality of the class by creating a subclass that will allow you to recreate the animation, drive the helper joints with an RBF network using the newly calculated matrices etc.</p>

```python
import dem_bones

db = dem_bones.DemBones()
db.compute("skinned_MESH", "deformed_MESH", start_frame=1001, end_frame=1010)

print(db.influences)
print(db.weights)
print(db.bind_matrix("jaw_JNT"))
print(db.anim_matrix("jaw_JNT", 1005))
```

<h4>Example</h4>
<p align="center"><img class="col three" src="/img/tools/dem_bones.gif"/></p>

<p class="justify">A maya and python file is provided in the <i>/example</i> directory. This maya file contains two meshes and a skeleton. Both meshes are the standard face taken from Apple's ARKit. One of the meshes is driven by a blend shape node which has a shape triggered at each frame. The other is default bound to a skeleton. After running the code contained in the python file the skin weights and joint transformations will be calculated and set them in the scene to match the mesh driven by the blend shape node.</p>

<h4>Licenses</h4>
- The source code, `/src`, uses *MIT* as detailed in [LICENSE.md](https://github.com/robertjoosten/maya-dem-bones/blob/master/LICENSE)
- Any build python bindings `/build` uses third party libraries: DemBones, pybind11 and Eigen with licenses in [3RDPARTYLICENSES.md](https://github.com/robertjoosten/maya-dem-bones/blob/master/3RDPARTYLICENSES.md)