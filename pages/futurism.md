---
permalink: /blog/futurism/
layout: page
title: "Futurism"
breadcrumb: true
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

<p>One of my hobbies is thinking about and attempting to better understand the future. I'm a fan of futurists like Kurzweil, and a lover of hard science fiction.</p>

<h3>Futurism-related Posts</h3>
<ul>
{% for category in site.categories %}
  {% if category.first == 'Futurism' %}
    <ul>
    {% for posts in category %}
      {% for post in posts %}
        {% if post.url | strip != '' %}
          <li><a href="{{ post.url }}"> {{ post.title }} </a></li>
        {% endif %}
      {% endfor %}
    {% endfor %}
    </ul>
  {% endif %}
{% endfor %}
</ul>