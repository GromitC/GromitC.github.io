---
layout: default
title: Blog
---
<h1>A Cup of Read</h1>
<h3 class="blog-subtitle"><i>A Paper Digest of Computer Science Research by Gromit Chan</i></h3>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <h3><a href="{{ post.url | relative_url }}"><strong>{{ post.title }}</strong></a> <span class="post-date">- {{ post.date | date_to_string }}</span></h3>
    </li>
  {% endfor %}
</ul>
