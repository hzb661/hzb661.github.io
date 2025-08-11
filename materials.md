---
layout: page
title: 材料
permalink: /materials/
---
<div style="padding: 1em;">
{% for tag in site.tags %}{% assign tagname = tag[0] %}[#{{ tagname }}](#{{ tagname }}) {% endfor %}
<span style="font-weight: bold;" >{{ site.materials | size }} 种789材料</span>
<ul>
    {% for material in site.materials %}
    <li>
        <a href="{{ material.url | relative_url }}">{{ material.title | escape }}</a>
    </li>
    {% endfor %}
</ul>
</div>
