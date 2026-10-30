---
layout: default
title: 홈
---

# 안녕하세요!

개발과 보안을 공부하면서 실습 과정, 문제 풀이, 읽은 자료와 활동 후기를 정리할 예정입니다.

<nav>
{% for item in site.menu %}
  <a href="#{{ item.key }}">{{ item.name }}</a> ·
{% endfor %}
</nav>

{% for item in site.menu %}
<h2 id="{{ item.key }}">{{ item.name }}</h2>
{% assign posts = site.categories[item.key] %}
{% if posts %}
<ul>
{% for post in posts %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — {{ post.date | date: "%Y-%m-%d" }}</li>
{% endfor %}
</ul>
{% else %}
<p>준비 중입니다.</p>
{% endif %}
{% endfor %}
