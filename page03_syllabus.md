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
</tr>

{% for day in site.data.syllabus %}
<tr>
    <td>{{ day.date }}</td>
    <td>
        <b>{{ day.title }}</b><br>
        {{ day.description }}

        {% if day.slides %}
        <br><br>
        <a href="{{ site.baseurl }}/assets/pdfs/{{ day.slides }}" target="_blank">
            📄 Slides of the day
        </a>
        {% endif %}
    </td>
</tr>
{% endfor %}
</table>