---
layout: single
title: "もくじ"
permalink: /mokuji/
author_profile: true
---

ぜんぶで{{ site.posts | size }}ページの日記があるわ🐰✨ 読みたい日を、えらんでね💕

{% assign by_month = site.posts | group_by_exp: "post", "post.date | date: '%Y年%-m月'" %}
{% for month in by_month %}
<h2 class="mokuji__month">{{ month.name }}（{{ month.items | size }}ページ）</h2>
<ul class="mokuji">
  {% for post in month.items %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
{% endfor %}
