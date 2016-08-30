---
layout: page
title: Blog
slug: blog
---
<ul class="block-list">
{% assign t = 1 %}
{% for post in site.posts %}
{% if post.category == 'Blog' %}
<li>
<a href="{{ post.url }}" class="block-list__link">
    <h3>{{ post.title }}</h3>
    <date class="date">{{ post.date | date_to_long_string }}</date> // <span class="tags">{{ post.tag }}</span>
</a>
{% if t <= 3 %}
<p>{{post.content | truncatewords:90}} <a href="{{post.url}}" class="go"> Read More</a><p/>
{% endif %}
{% assign t = t | plus:1 %}
</li>
{% endif %}
{% endfor %}
</ul>