---
layout: page
title: About
description: 
img: corona_virus_goodsell.jpg 
caption: "Courtesy of David S. Goodsell"
permalink: index.html
sidebar: true
---

# {{site.data.about.title}}
{{site.data.about.authors}}

{% for entry in site.data.about %}

{% if entry[0] != 'title' %}
{% if entry[0] != 'authors' %}
## {{entry[0]}}
{{entry[1]}}
{% endif %}
{% endif %}
{% endfor %}

## {{ site.data.about["Daily Rhythm"].title }}

{{ site.data.about["Daily Rhythm"].intro }}

<table>
  <tr>
    <th><b>Time</b></th>
    <th><b>Activity</b></th>
  </tr>
  {% for item in site.data.about["Daily Rhythm"].schedule %}
  <tr>
    <td style="white-space: nowrap;">{{ item.time }}</td>
    <td>{{ item.activity }}</td>
  </tr>
  {% endfor %}
</table>