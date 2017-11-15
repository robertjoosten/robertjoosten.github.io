---
layout: default
title: Tags
permalink: /tags/
no-menu: 1
---

{% capture tags %}{% for project in site.projects %}{% for tag in project.tag %}{{ tag }}|{% endfor %}{% endfor %}{% endcapture %}
{% assign filtered_tags = tags | split: "|" | uniq | sort %}
{% assign reversed_projects = site.projects | reverse %}

{% for tag in filtered_tags %}
{% assign words = tag | split: ' ' %}
{% capture capitalized_tag %}{% for word in words %}{{ word | capitalize }} {% endfor %}{% endcapture %}

<h2 id="{{ tag }}" class="post-title">{{ capitalized_tag }}</h2>
<ul class="post-list">


{% for project in reversed_projects %}
{% if project.tag contains tag %}
    <div style="width: 100%; float: left">
    <div style="float: left">
    <a href="{{ project.url }}"><strong>{{ project.title }}</strong></a>
    
    </div>
    <div style="float: right">
    <span class="post-meta">{{ project.date | date: "%B %d, %Y" }}</span>   
    </div>
    </div>
    {% if project.description %}
    <p class="justify" style="clear:both;">{{ project.description }}</p>
    {% else %}
    <br style="clear:both;">
    <br style="clear:both;">
    {% endif %}
{% endif %}
{% endfor %}
</ul>
{% endfor %}