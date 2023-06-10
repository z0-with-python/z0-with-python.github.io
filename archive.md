---
layout: default
title: Blog!
---

# 차근차근 하나씩 해볼게요
퇴근하고 짬내서 하나씩 배우고, 포스팅도 해보도록 할게요!

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
