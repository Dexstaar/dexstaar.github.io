---
layout: page
title: Algorithm
permalink: /algorithm/
---

<ul class="post-list">
  
  {% assign category = page.category | default: page.title %}
  {% for post in site.categories[category] %}
    <li>
      
        <a href="{{ site.baseurl }}{{ post.url }}">
          {{ post.title }}
        </a>
        <small>{{ post.date | date_to_string }}</small>
      
    </li>
  {% endfor %}
  
</ul>