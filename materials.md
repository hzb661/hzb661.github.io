---
layout: page
title: 材料
permalink: /materials/
---

{% for material in site.materials %}

### {{ material[0] }}

{{ material[1] | size }} materials
  {% for material in material[1] %}

 - [{{ material.title }}]({% include relative %}{{ material.url }})
   {% endfor %}
   {% endfor %}
