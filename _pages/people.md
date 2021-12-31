---
layout: default
title: People
permalink: people
---
<h1>People</h1>

<div style="display:flex; flex-wrap:wrap; justify-content: space-evenly; align-items: center; flex-basis:content">
  {% for person in site.people %}
    <div style="text-align:center; margin: 10px">
      <!--{% unless person.photo.normalize_whitespace == "" %}<img width="200px" src="{{ person.photo | normalize_whitespace }}"/>{% endunless %}-->
      <h2 style="margin: 0;"><a href="{{ person.url }}">{{ person.title | replace: " ", "&nbsp;" }}</a></h2>
      <p class="post_date" style="margin: 0;">{{ person.position }}</p>
      <div style="text-align: center;">
      {% if person.dribbble %}<a href="https://dribbble.com/{{ person.dribbble }}"><i class="svg-icon dribbble"></i></a>{% endif %}
      {% if person.email %}<a href="mailto:{{ person.email }}"><i class="svg-icon email"></i></a>{% endif %}
      {% if person.facebook %}<a href="https://www.facebook.com/{{ person.facebook }}"><i class="svg-icon facebook"></i></a>{% endif %}
      {% if person.flickr %}<a href="https://www.flickr.com/{{ person.flickr }}"><i class="svg-icon flickr"></i></a>{% endif %}
      {% if person.github %}<a href="https://github.com/{{ person.github }}"><i class="svg-icon github"></i></a>{% endif %}
      {% if person.instagram %}<a href="https://instagram.com/{{ person.instagram }}/"><i class="svg-icon instagram"></i></a>{% endif %}
      {% if person.linkedin %}<a href="https://www.linkedin.com/in/{{ person.linkedin }}"><i class="svg-icon linkedin"></i></a>{% endif %}
      {% if person.pinterest %}<a href="https://www.pinterest.com/{{ person.pinterest }}"><i class="svg-icon pinterest"></i></a>{% endif %}
      {% if person.rss %}<a href="{{ person.rss }}"><i class="svg-icon rss"></i></a>{% endif %}
      {% if person.twitter %}<a href="https://www.twitter.com/{{ person.twitter }}"><i class="svg-icon twitter"></i></a>{% endif %}
      {% if person.patreon %}<a href="https://www.patreon.com/{{ person.patreon }}"><i class="svg-icon patreon"></i></a>{% endif %}
      {% if person.stackoverflow %}<a href="http://stackoverflow.com/{{ person.stackoverflow }}"><i class="svg-icon stackoverflow"></i></a>{% endif %}
      {% if person.youtube %}<a href="https://youtube.com/{{ person.youtube }}"><i class="svg-icon youtube"></i></a>{% endif %}
      {% if person.googleplus %}<a href="https://plus.google.com/{{ person.googleplus }}"><i class="svg-icon googleplus"></i></a>{% endif %}
      {% if person.playconsole %}<a href="https://play.google.com/store/apps/dev?id={{ person.playconsole }}"><i class="svg-icon playconsole"></i></a>{% endif %}
      {% if person.website %}<a href="{{ person.website }}"><i class="svg-icon website"></i></a>{% endif %}
      </div>
      {% unless person.content.normalize_whitespace == Null %}<p>{{ person.content | normalize_whitespace }}</p>{% endunless %}
    </div>
  {% endfor %}
</div>
