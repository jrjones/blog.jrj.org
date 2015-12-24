---
permalink: /blog/personal/
layout: page
title: "JRJ Personal"
breadcrumb: true
---

<p>Even though this blog has a few key topics (Security and Privacy, Technology and the Future) it's still a personal blog. Hence, I post personal stuff here from time to time that may or may not fit into one of the core topics.</p>
<h3>JRJ Personal Posts</h3>
<ul>
{% for category in site.categories %}
  {% if category.first == 'JRJ Personal' %}
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