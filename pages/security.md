---
permalink: /blog/security/
layout: page
title: "Security"
breadcrumb: true
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

<p>My primary role on Adobe's Primetime team is security (including cryptography, incident and vulnerability response, compliance and audits, etc.) It's also an area of intense study on a personal level. While closely related to <a href="/blog/privacy/">privacy</a>, I generally use the term "security" to mean Information Security (INFOSEC.)  </p>

<h3>Security-related Posts</h3>
<ul>
{% for category in site.categories %}
  {% if category.first == 'Security' %}
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