---
permalink: /blog/vr/
layout: page
title: "Virtual Reality"
breadcrumb: true
---

<p>2016 is the year we get to find out whether or not Virtual Reality is going to be a thing. Personally, I believe it will be a successful niche in 2016, reaching mainstream adoption within the decade. </p>
<p>Most of my discussion will be about VR, but I'll also occasionally talk about related immersive technologies like Augmented Reality (AR.)</p>

<h3>VR-related Posts</h3>
<ul>
{% for category in site.categories %}
  {% if category.first == 'Virtual Reality' %}
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