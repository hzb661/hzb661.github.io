---
layout: page
title: 材料
permalink: /materials/
---

{% for material in site.materials %}

### {{ material[0] }}

{{ material[1] | size }} posts
  {% for post in material[1] %}

 - [{{ post.title }}]({% include relative %}{{ post.url }})
   {% endfor %}
   {% endfor %}
