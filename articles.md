---
layout: page
title: Статьи
permalink: /articles/
---

<ul>
{% for article in site.articles %}
  <li>
    <a href="{{ article.url }}">{{ article.title }}</a>
    <span>{{ article.date | date: "%Y-%m-%d" }}</span>
  </li>
{% endfor %}
</ul>
