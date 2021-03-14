---
layout: post
title: Maya - Metadata Framework
description: Django inspired metadata framework for Maya.
img: /img/tools/mango_thumbnail.png
date: 2020-10-14 12:38:00
category: tools
tag: [tool, python, maya, maya api, orm, object-relational-mapping]
github: https://github.com/robertjoosten/maya-orm
github-docs: https://robertjoosten.github.io/maya-orm/
---
<p class="justify">Django inspired metadata framework for Maya.</p>

<h4>Installation</h4> 
* Extract the content of the .rar file anywhere on disk.
* Drag the mango.mel file in Maya to permanently install the script.

<h4>Usage</h4>
<p class="justify">
The userSetup.py registers callbacks that will automatically process the scene
when a file gets Imported/Opened or a reference gets Created/Loaded. This will
allow instant easy access to the models.
</p>

<h4>Models</h4>
<p class="justify">
A model can be created by inheriting from a base class. Fields and relations
can be added to the class using descriptors. There is a wide variety of
fields and relations to choose from. Both fields and relations have base
classes that can be inherited from to generate new types.
</p>

```python
from mango import models
from mango import fields
from mango import relations

class Joint(models.Model):
    node_type = "joint"
    number = fields.IntField(default_value=10, unique=True, keyable=True)
    link = relations.OneToManyRel(rev_name="link_reverse", typed=True)

class Collection(models.Model):
    node_type = "transform"
    joint_set = relations.OneToManyRel(Joint, rev_name="part", typed=True)
```

<p class="justify">
Once the class is created you can either initialize a model by creating a
new node calling the class using keyword arguments or you can initialize an
existing node by provided the name of the node. In both events attributes for
the fields and relations are created.
</p>

```python
# create new nodes
l_elbow_jnt = Joint(name="l_elbow_jnt", number=1)
l_wrist_jnt = Joint(name="l_wrist_jnt", parent="l_elbow_jnt", link=l_elbow_jnt)

# initialize existing nodes
l_elbow_jnt = Joint("l_elbow_jnt")  # initialize using string
l_elbow_jnt = Joint(l_elbow_jnt.object)  # initialize using OpenMaya.MObject
l_elbow_jnt = Joint(l_elbow_jnt.dependency)  # initialize using OpenMaya.MFnDependencyNode
```

<h4>Fields</h4>
<p class="justify">
Fields can be retrieved and set using the descriptor. Validators are attached
to each field to ensure values can actually be set on the node.
</p>

```python
print l_elbow_jnt.number
l_elbow_jnt.number = 5
l_elbow_jnt.number = "10"  # raises TypeError
```

<h4>Relations</h4>
<p class="justify">
Relations can be retrieved and set using the descripter. Validators are
attached to each relation to make sure that only the right typed models are
added as relations and the unique state of the model instance using its
unique fields.
</p>

```python
print l_elbow_jnt.link_reverse
print l_wrist_jnt.link.all()
l_elbow_jnt.link_reverse = None
l_wrist_jnt.link.add(l_elbow_jnt)
```

<h4>Managers</h4>
<p class="justify">
Manager objects are attached to the model types and to the relations. Only
when a relation is not singular a manager object will be returned. This
manager object can be used to Create/Set/Add and Remove model instances.
</p>

```python
l_shoulder_jnt = Joint.objects.create(name="l_shoulder_jnt")
print Joint.objects.all()
print Joint.objects.filter(number=10)  # operators allowed using '__'
```