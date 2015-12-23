---
permalink: /tags/
layout: page
title: "Tags"
---

<p>Jekyll doesn't have functionality for listing categories and tags, so this is just a weakly implemented dump for now, I plan on doing somethiung a bit nicer at some point. In the mean-time, there is a full  list of tags with associated posts below.</p>

<ul>
{% for tag in site.tags %}
  {% if tag.first != 'Uncategorized' %}
  <a name="{{ tag | first }}">&nbsp;</a><br/><br/>
  <li style="list-style: none;"><h2>{{ tag | first }}</h2>
  
    <ul>
    {% for posts in tag %}
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