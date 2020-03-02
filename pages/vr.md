---
permalink: /blog/vr/
layout: page
title: "Virtual Reality"
breadcrumb: true
header:
   image_fullwidth: jrj-florence.jpg
   caption: "JRJ's 2015 trip to Florence, Italy"
---

I believe Immersive Technologies like VR and Augmented Reality/Mixed Reality represent the next major step in computing, and that 2020/2021 will be the timeframe when these technologies start to take off, with mainstream adoption following around 2025. (I've been a VR enthusiast since the 90s, and have been playing in the Oculus ecosystem since the DK days.)

I founded [Virtual Neural](https://virtualneural.net) to explore spatial computing and immersive technologies, with an emphasis on how artificial intelligence can be important to their evolution. I also owned VR and AR strategy for the Adobe Primetime team from 2015-2017.

### Projects and Presentations
  * I recently gave a talk on Immersive Technologies (VR and AR) and [you can download the presentation here[(/labs/ImmersiveTech-VR-AR/).


### VR-related Posts
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