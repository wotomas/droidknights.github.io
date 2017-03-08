---
layout: page
title: Blog
permalink: /blog/
tags: blog
---

{% assign posts_count = 1 %}

<div class="home">
  {% if posts_count > 0 %}
  <div class="posts" style="font-family: 'Spoqa Han Sans', 'Montserrat', 'Sans-serif';">
    {% for post in site.categories.blog %}
    <div class="post py3">
      <p class="post-meta">{{ post.date | date: site.date_format }}</p>
      <a href="{{ post.url | prepend: site.baseurl }}" class="post-link"><h3 class="h2 post-title">{{ post.title }}</h3></a>
      <p class="post-summary">
        {% if post.summary %}
        {{ post.summary }}
        {% else %}
        {{ post.excerpt }}
        {% endif %}
      </p>
    </div>
    {% endfor %}
  </div>

  {% include pagination.html %}
  {% else %}
  <h1 class='center'>{{ site.text.index.coming_soon }}</h1>
    {% endif %}
</div>