---
layout: page
title: 笔记
permalink: /blog/
---

<p>
  {% assign all_tags = site.blogs | map: 'tags' | compact | join: ',' | split: ',' | uniq %}
  {% for my_page in site.pages %}{% if my_page.title and my_page.noindex != true %} | {{ my_page.title }}{% endif %}{% endfor %}
</p>



{% for tag in all_tags %}
  <section id="{{ tag | slugify }}">
    <h3>{{ tag }}</h3>
    {% assign tagged_blogs = site.blogs | where_exp: "item", "item.tags contains tag" %}
    <p> {{ tagged_blogs | size }} Posts</p>
    <ul>
      {% for blog in site.blogs %}
        {% if blog.tags contains tag %}
          <li><a href="{{ blog.url | relative_url }}">{{ blog.title }}</a></li>
        {% endif %}
      {% endfor %}
    </ul>
  </section>
{% endfor %}