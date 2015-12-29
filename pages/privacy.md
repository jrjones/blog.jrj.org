---
permalink: /blog/privacy/
layout: page
title: "Privacy"
breadcrumb: true
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

<p>Privacy has become part of our national conversation in the last few years. It's an area of interest for me, and here I share opinion and information on how best to protect your personal information. This includes <a href="/blog/security/">information security</a> but is more than that. </p>

<h3>Privacy-related Posts</h3>
<ul>
{% for category in site.categories %}
  {% if category.first == 'Privacy' %}
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