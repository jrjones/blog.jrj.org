---
permalink: /blog/vr/
layout: page
title: "Virtual Reality"
breadcrumb: true
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

<p>I believe Immersive Technologies like VR and Augmented Reality/Mixed Reality represent the next major step in computing, and that 2020/2021 will be the timeframe when these technologies start to take off, with mainstream adoption following around 2025. (I've been a VR enthusiast since the 90s, and have been playing in the Oculus ecosystem since the DK days.)

I founded [Virtual Neural](https://virtualneural.net) to explore spatial computing and immersive technologies, with an emphasis on how artificial intelligence can be important to their evolution. I also owned VR and AR strategy for the Adobe Primetime team from 2015-2017.

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