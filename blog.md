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
      {% assign words = post.content | number_of_words %}
      {% assign reading_time = words | divided_by: 200 %}
      {% if reading_time == 0 %}
        {% assign reading_time = 1 %}
      {% endif %}
      • {{ reading_time }} min read
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
