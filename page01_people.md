---
layout: page
title: People
description: About the authors
img: people.png 
caption: "T4 Bacteriophage"
permalink: people
sidebar: true
---

{% for author in site.data.people %}
<article class="post">

  {% if author.img %}
    {% assign pic = author.img %}
  {% else %}
    {% assign pic = "noimg.jpg" %}
  {% endif %}

  {% if author.link %}
    {% assign website = author.link %}
  {% else %}
    {% assign website = " " %}
  {% endif %}

  <a class="post-thumbnail" style="background-image: url({{site.baseurl}}/assets/img/people/{{pic}})" href="{{website}}"></a>

  <div class="post-content">
    {% if author.link %}
      <a href="{{author.link}}"><b class="post-title">{{author.name}}</b></a>
    {% else %}
      <b class="post-title">{{author.name}}</b>
    {% endif %}
    <p>{{author.title}}</p>

    {% if author.institute %}
      <p>{{author.institute}}</p>
    {% endif %}

    {% if author.other_info %}
      {% for other in author.other_info %}
        <p>{{ other[0] }}: {{ other[1] }}</p>
      {% endfor %}
    {% endif %}
  </div>
</article>
{% endfor %}