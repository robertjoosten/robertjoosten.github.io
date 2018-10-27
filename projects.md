---
layout: page
title: projects
permalink: /projects/
order: 7
---

{% assign sorted_projects = site.projects | sort: "date" %}
{% assign reversed_projects = sorted_projects | reverse %}
{% for project in reversed_projects %}
{% if project.category contains "projects" %}
<div class="project ">
    <div class="thumbnail">
        <a href="{{ site.baseurl }}{{ project.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}
        <span>
        </span>
        </a>
    </div>
    <p class="caption"><a href="{{ site.baseurl }}{{ project.url }}">{{ project.title }}</a></p>
</div>
{% endif %}
{% endfor %}
