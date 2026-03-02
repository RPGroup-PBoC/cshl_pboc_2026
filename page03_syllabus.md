---
layout: page
title: Syllabus
img: reading.png 
permalink: syllabus
caption: "DNA Sequence Chromatogram"
sidebar: true
---

<table>
<tr>
    <th><b>Date</b></th>
    <th><b>Topic</b></th>
    <th><b>Description</b></th>
</tr>

{% for entry in site.data.syllabus %}
<tr>
    <td>{{ entry.day.date }}</td>
    <td><b>{{ entry.day.topic }}</b></td>
    <td>{{ entry.day.description }}</td>
</tr>
{% endfor %}

</table>