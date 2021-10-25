---
layout: default
title: Blog
---
<h1>A Cup of Read</h1>
<h3 style="color:grey;"><i>A Paper Digest of Computer Science Research by Gromit Chan</i></h3>

<ul>
  {% for post in site.posts %}
    <li style="text-align:left;">
      <!-- <h2><a href="{{ post.url }}">{{ post.title }}</a></h2> -->
      <h3><a href="{{ post.url }}"><strong>{{ post.title }}</strong></a> - {{ post.date | date_to_string }}</h3>
       
      <!-- {{ post.excerpt }} -->
    </li>
  {% endfor %}
</ul>