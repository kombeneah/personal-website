---
layout: default
title: Blog
permalink: /blog/
---

# Blog

All my thoughts, updates, and reflections in one place.

<div class="blog-list">
{% for post in site.posts %}
  <article class="blog-post-item">
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
    <p class="post-meta">
      <time>{{ post.date | date: "%B %d, %Y" }}</time>
      {% if post.categories %}
        • {{ post.categories | join: ", " }}
      {% endif %}
    </p>
    {% if post.excerpt %}
    <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
    {% endif %}
    <p><a href="{{ post.url }}">Read more →</a></p>
  </article>
{% endfor %}
</div>

{% if site.posts.size == 0 %}
<p>No posts yet. Check back soon!</p>
{% endif %}
