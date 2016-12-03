---
permalink: /blog/vr/
layout: page
title: "Virtual Reality"
breadcrumb: true
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

<p>2016 was the year the new generation of Virtual Reality headsets launched for consumers. Personally, I believe Immersive Technologies like VR and Augmented Reality/Mixed Realitty will be a successful niche in 2017 and 2018, reaching mainstream adoption within the decade. </p>

<h3>Projects and Presentations</h3>
<ul>
    <li>I recently gave a talk on Immersive Technologies (VR and AR) and <a href="/labs/ImmersiveTech-VR-AR/">you can download the presentation here</a>.</li>
</ul>

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