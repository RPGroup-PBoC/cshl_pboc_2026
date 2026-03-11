---
layout: page
title: Code
img: code.png # Add image post (optional)
permalink: code
sidebar: true
---

---

During this course, you will develop a computational prowess that will aid in
your understanding of physical biology.  These will
be done using Jupyter notebooks through [Google
Colab](https://colab.research.google.com/), so you will need to sign into a
Google Account to create new notebooks.  

We will post links to Jupyter Notebooks hosted on colab of the tutorial
sessions here. 


{% for topic in site.data.code %}
# {{ topic[0] }}
{% for item in topic[1] %}
* {% if item.colab %}[**{{ item.title }}**]({{ item.colab }}){% else %}**{{ item.title }}**{% endif %} |
  {{ item.description }}

  {% if item.data %}
  <br/>
  <i>Data file</i>:
  <a href="{{ '/assets/data_code/' | append: item.data | relative_url }}">{{ item.data }}</a>
  {% endif %}

  {% if item.links %}
  <br/>
  {% for l in item.links %}
  <i>[**{{ l[0] }}**]({{ l[1] }})</i><br/>
  {% endfor %}
  {% endif %}
{% endfor %}
{% endfor %}