---
title: Blog
nav_order: 6
permalink: /blog/
---

# Blog

{% if site.posts.size > 0 %}
<ul class="post-list">
{% for post in site.posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
    {% if post.description %}<p>{{ post.description }}</p>{% endif %}
  </li>
{% endfor %}
</ul>
{% else %}
No posts yet.
{% endif %}
