---
layout: default
title: People
permalink: people
---
<h1>People</h1>

<div>
  {% for person in site.people %}
    <div>
      <h2 style="margin-bottom: 0;"><a href="{{ person.url }}">{{ person.name }}</a></h2>
      <p class="post_date" style="margin: 0;">{{ person.position }}</p>
      <p>{{ person.content | markdownify }}</p>
    </div>
  {% endfor %}
</div>