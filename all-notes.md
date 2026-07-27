---
layout: page
title: Все мои заметки
permalink: /all-notes/
---

{% for note in site.notes %}
  <h2>{{ note.name | default: note.name }}</h2>
  <p><small>{{ note.date | date: "%Y-%m-%d" }}</small></p>
  {{ note.content }}
  <hr>
{% endfor %}
