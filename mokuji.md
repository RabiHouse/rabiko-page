\---

layout: single

title: "もくじ"

permalink: /mokuji/

author\_profile: true

\---



ぜんぶで{{ site.posts | size }}ページの日記があるわ🐰✨ 読みたい日を、えらんでね💕



{% assign by\_month = site.posts | group\_by\_exp: "post", "post.date | date: '%Y年%-m月'" %}

{% for month in by\_month %}

<h2 class="mokuji\_\_month">{{ month.name }}（{{ month.items | size }}ページ）</h2>

<ul class="mokuji">

&#x20; {% for post in month.items %}

&#x20; <li><a href="{{ post.url | relative\_url }}">{{ post.title }}</a></li>

&#x20; {% endfor %}

</ul>

{% endfor %}

