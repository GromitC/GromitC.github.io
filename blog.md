---
layout: default
title: Blog
---
<h1>Latest Posts</h1>

<ul>
  {% for post in site.posts %}
    <li style="text-align:left;">
      <!-- <h2><a href="{{ post.url }}">{{ post.title }}</a></h2> -->
      <h3><a href="{{ post.url }}"><strong>{{ post.title }}</strong></a> - {{ post.date | date_to_string }}</h3>
       
      <!-- {{ post.excerpt }} -->
    </li>
  {% endfor %}
</ul>