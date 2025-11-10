---
layout: default
title: Home
---

Hello! I'm Beneah Kombe, and this is my corner of the internet where I share my thoughts, experiences, and journey.

## About Me

I am from Kenya, currently in New York after stops in Cleveland, Boston, Lannion (France) and Seattle. I have deep interest in how AI is transforming a plethora of day-to-day engagements, and am passionate about everyone getting a fair opportunity to manifest fully and fairly!

## What I Do

I am a software engineer by profession with variable interest in datastores, infrastructure management, data engineering / analytics and backend systems overall.

Before this I earned by Bachelors and Masters in Computer Science at [MIT](https://www.csail.mit.edu/). Before that I spent time as a post-grad high school student at [University School](https://www.us.edu/) in Cleveland (Ohio), after graduating high school at [Starehe Boys Center](https://stareheboyscentre.org/) in Nairobi Kenya. Way before that I was a budding dreamer at Marell Academy in Bungoma Kenya.

For fun I do enjoy sports (let's go Arsenal!), a little gaming and lately a well-timed traveling experience.

For life I like to listen to perspectives, ideas, experiences or even mis-experiences, singularly to learn more about how we can make tomorrow better than today.

## Recent Thoughts

<div class="blog-posts">
{% for post in site.posts limit:5 %}
  <div class="post-preview">
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <p class="post-date">
      {{ post.date | date: "%B %d, %Y" }}
      {% assign words = post.content | number_of_words %}
      {% assign reading_time = words | divided_by: 200 %}
      {% if reading_time == 0 %}
        {% assign reading_time = 1 %}
      {% endif %}
      • {{ reading_time }} min read
    </p>
    {% if post.excerpt %}
    <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    {% endif %}
  </div>
{% endfor %}
</div>

<p><a href="/blog/">View all thoughts →</a></p>
