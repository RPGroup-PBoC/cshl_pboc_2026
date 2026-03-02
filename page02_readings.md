---
layout: page
title: Readings
img: reading.png 
permalink: readings
caption: "DNA Sequence Chromatogram"
sidebar: true
---

---

<p> As the course progresses, we will post links to treadings relevant to what 
we've talked about in class</p>

<h1> Useful links</h1>
---

{%for link in site.data.links%}
* [**{{link.title}}**]({{link.address}}) {%if link.description %}{{link.description}}{%endif%}
{%endfor%}

<h1> Daily Suggested Reading</h1>

{% for day in site.data.readings %} 
## {{ day[0] }}

{% for pub in day[1] %}
* {% if pub.link %}
    [**{{ pub.title }}**]({{ site.baseurl }}/assets/pdfs/{{ pub.link }})
  {% else %}
    **{{ pub.title }}**
  {% endif %}
  by <i>{{ pub.authors }}</i>{% if pub.year %} ({{ pub.year }}){% endif %}{% if pub.description %} {{ pub.description }}{% endif %}
{% endfor %}

