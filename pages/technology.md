---
permalink: /blog/technology/
layout: page
title: "Technology"
breadcrumb: true
---

<p>I'm obsessed with technology of all sorts. Eveyrthing from smartphones and tablets to PCs and consumer electronics is covered here.</p>

<h3>Technology-related Posts</h3>
<ul>
{% for category in site.categories %}
  {% if category.first == 'Technology' %}
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