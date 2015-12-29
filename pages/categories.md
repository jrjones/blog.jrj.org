---
permalink: /categories/
layout: page
title: "Categories"
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

This site is mainly about <a href="#Security">Security</a> and <a href="#Privacy">Privacy, <a href="#Technology">Technology</a> and <a href="#Futurism">the Future</a>. However, there are other major post categories, including <a href="#Economics">Economics</a>, <a href="#Poker">Poker</a>, and <a href="#JRJ Personal">JRJ Personal</a>. A full list of all categories (and posts within each category) is included below.

<ul>
{% for category in site.categories %}
  {% if category.first != 'Uncategorized' %}
  <a name="{{ category | first }}">
  <li style="list-style: none;"><h2>{{ category | first }}</h2>
  </a>
    <ul>
    {% for posts in category %}
      {% for post in posts %}
        {% if post.url | strip != '' %}
          <li><a href="{{ post.url }}"> {{ post.title }} </a></li>
        {% endif %}
      {% endfor %}
    {% endfor %}
    </ul>
  </li>
  {% endif %}
{% endfor %}
</ul>