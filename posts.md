---
layout: default
title: Posts
permalink: /posts/
---

<ul>
  {% for post in site.posts %}
    <div class="post-content">
      <h2 class="post-title"><a href="{{post.url | prepend: site.baseurl}}">{{post.title}}</a></h2>
      <p>{{ post.content | strip_html | truncatewords: 15 }}</p>
      <span class="post-date">{{post.date | date: '%Y, %b %d'}}</span>
    </div>
  {% endfor %}
</ul>