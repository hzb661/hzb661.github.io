---
layout: page
title: 材料
permalink: /materials/
---

<p>
  {% assign all_tags = site.materials | map: 'tags' | compact | join: ',' | split: ',' | uniq %}
  {% for tag in all_tags %}
    <a href="#{{ tag | slugify }}">(#{{ tagname }})</a>
  {% endfor %}
</p>

<hr>

{% for tag in all_tags %}
  <section id="{{ tag | slugify }}">
    <h3>{{ tag }}</h3>
    {{ tag[1] | size }} posts
    <ul>
      {% for material in site.materials %}
        {% if material.tags contains tag %}
          <li><a href="{{ material.url | relative_url }}">{{ material.title }}</a></li>
        {% endif %}
      {% endfor %}
    </ul>
  </section>
{% endfor %}