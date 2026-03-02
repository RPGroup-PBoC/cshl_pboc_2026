<!-- Loop through each author in the data file -->
{% assign current_group = "" %}
{% for author in site.data.people %}

  {% if author.group and author.group != current_group %}
    {% assign current_group = author.group %}
    <h2>{{ current_group }}</h2>
  {% endif %}

  <!-- Define a new "article" environment, which is the object with author info -->
  <article class="post">

  <!-- Determine if an image is provided for the author, if not use a silhouette -->
  {% if author.img %}
    {% assign pic = author.img %}
  {% else %}
    {% assign pic = "noimg.jpg" %}
  {% endif %}

  <!-- Determine if a website is associated with the author, if not use a blank-->
  {% if author.link %}
    {% assign website = author.link %}
  {% else %}
    {% assign website = " " %}
  {% endif %}

  <!-- Populate the author fields --> 
  <a class="post-thumbnail" style="background-image: url({{site.baseurl}}/assets/img/people/{{pic}})" href="{{website}}"></a>

  <!-- Populate the author environment with the information -->
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
        <p>{{other[0]}}: {{other[1]}}</p>
      {% endfor %}
    {% endif %}
  </div>

  </article>
{% endfor %}