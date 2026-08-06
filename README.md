---
permalink: /
published: true
title: Цифровой сад
date: 2026-06-08
---
Назарова Кирилла краткий "цифровой сад" связывающий все проекты!

**Honey** — это мощный, объединяющий 
  - **Родительскую школу** — опыт создания семейного сообщества.
  - **Дневник радости** — ежедневные записи о счастливых моментах.

**computer-science** - программа по информатике которую проводил в школе №71, включая КТП. 

проекты это исследования, они требует ежедневной работы, отсюда -
**daily** - ежедневные заметки - показывает по дням - что сделано, в чем приращение, какими новыми знаниями овладел.

**lessons** - готовые уроки оформленные

## Уроки
{% for lesson in site.lessons %}
  - <b>{{ lesson.date | default: "Без даты" | date: "%Y-%m-%d" }}</b>:
    [{{ lesson.title }}]({{ lesson.url | relative_url }})  
    {% if lesson.excerpt %}<span style="color:#666;font-size:0.9em;">{{ lesson.excerpt }}</span>{% endif %}
{% endfor %}

{% if site.lessons.size == 0 %}
  <p>Пока нет ни одного урока. Создай файл в папке _lessons/ с названием nazvanie-uroka.md</p>
{% endif %}

## Последние исследования
{% for post in site.posts limit:100 %}
  - <b>{{ post.date | date: "%Y-%m-%d" }}</b>: 
    [{{ post.title }}](/computer-science{{ post.url }})
{% endfor %}

{% if site.posts.size == 0 %}
  <p>Пока нет ни одного поста. Создай файл в папке _posts/ с названием YYYY-MM-DD-nazvanie.md</p>
{% endif %}

# Прочие проекты
{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}
