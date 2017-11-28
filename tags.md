---
layout: default
title: Tags
permalink: /tags/
no-menu: 1
---

{% capture tags %}{% for project in site.projects %}{% for tag in project.tag %}{{ tag }}|{% endfor %}{% endfor %}{% endcapture %}
{% assign collection_tags = tags | split: "|" %}
{% assign filtered_tags = tags | split: "|" | uniq | sort %}
{% assign reversed_projects = site.projects | reverse %}

<h2 class="post-title">{{ page.title }}</h2>
<br>

<ul class="post-list">
<p class="justify">
{% for tag in filtered_tags %}

{% assign tag_count = 0 %}
{% for t in collection_tags %}
{% if tag == t %}
{% assign tag_count = tag_count | plus: 1 %}
{% endif %}
{% endfor %}

{% assign rel_tag_size = tag_count | times: 10.0 | divided_by: collection_tags.size | plus: 1 %}
<span style="font-size: {{ rel_tag_size }}em"><a href="/tags/#{{ tag |replace: ' ', '-' }}">{{ tag }}</a></span>

{% endfor %}
</p>
</ul>

<hr>
<br>

{% for tag in filtered_tags %}
{% assign words = tag | split: ' ' %}
{% capture capitalized_tag %}{% for word in words %}{{ word | capitalize }} {% endfor %}{% endcapture %}

<h1 id="{{ tag |replace: ' ', '-' }}">{{ capitalized_tag }}</h1>
<ul class="post-list">


{% for project in reversed_projects %}
{% if project.tag contains tag %}
    <div style="width: 100%; float: left">
    <div style="float: left">
    <a href="{{ project.url }}">&#09;{{ project.title }}</a>
    
    </div>
    <div style="float: right">
    <span class="post-meta">{{ project.date | date: "%B %d, %Y" }}</span>   
    </div>
    </div>
{% endif %}
{% endfor %}
<p style="clear:both;"/>
</ul>
{% endfor %}