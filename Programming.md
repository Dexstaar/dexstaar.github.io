---
layout: page
title: Programming
permalink: /programming/
---

{% assign category = page.category | default: page.title %}

<ul class="post-list">
  {% for post in site.categories[category] %}
    <li>
      
        <a href="{{ site.baseurl }}{{ post.url }}">
          {{ post.title }}
        </a>
        <small>{{ post.date | date_to_string }}</small>
      
    </li>
  {% endfor %}
  
</ul>