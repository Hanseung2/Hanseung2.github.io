---
permalink: /index/
layout: single
author_profile: true
sidebar_main: false
---

<br/>

<center>💭 내 생각과 공부했던 내용을 남기는 개발블로그</center>

<br/>
<br/>
<br/>
<p align="center">💡 ~ing Project: 개인 카페 서비스, 군창업경진대회 모티브</p>

<p align="center"><a href="https://github.com/QuartetTeam/Cafe_BE">https://github.com/QuartetTeam/Cafe_BE</a></p>

<br/>
<hr/>

<center>📝 최근 포스트</center>

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <small> - {{ post.date | date: "%Y-%m-%d" }}</small>
    </li>
  {% endfor %}
</ul>
