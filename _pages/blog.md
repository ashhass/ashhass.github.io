---
layout: page
title: Blogs
permalink: /blog/
description: Daily unedited thoughts. 
nav: true
nav_order: 3
horizontal: false
---

<div class="blog-list">
  {% for post in site.posts %}
    <div class="blog-card">
      <h2 class="blog-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <p class="blog-date">{{ post.date | date: "%B %-d, %Y" }}</p>
      <p class="blog-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    </div>
    <hr>
  {% endfor %}
</div>

<style>
.blog-list {
  max-width: 800px;
  margin: 0 auto;
  padding: 1rem;
}
.blog-card {
  margin-bottom: 2rem;
}
.blog-title a {
  font-size: 1.5rem;
  font-weight: bold;
  color: default;
  text-decoration: none;
}
.blog-title a:hover {
  text-decoration: underline;
}
.blog-date {
  font-size: 0.9rem;
  color: #6a737d;
  margin-bottom: 0.5rem;
}
.blog-excerpt {
  font-size: 1rem;
  color: #24292e;
}
hr {
  border: none;
  border-top: 1px solid #eee;
}
</style>