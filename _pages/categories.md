---
layout: page
permalink: /categories/
title: Categories
---

<div id="archives">
{% assign sorted_cats = site.categories | sort %}
{% for category in sorted_cats %}
{% capture category_name %}{{ category | first }}{% endcapture %}
  {% unless category_name == "slletshow" %}
  {% assign posts = false %}
  <div class="archive-group">
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    <h3 style="text-transform: capitalize;" class="category-head">{% if category_name == "video" %}<a href="{{site.baseurl}}/categories/videos">{% elsif category_name == "live" %}<a href="{{site.baseurl}}/live">{% elsif category_name == "post" %}<a href="{{site.baseurl}}/posts">{% elsif category_name == "podcast" %}<a href="{{site.baseurl}}/podcasts">{% endif %}{{ category_name }}{% unless category_name == "live" or category_name == "radio" %}s{% endunless %}{% if category_name == "video" or category_name == "live" or category_name == "post" or category_name == "podcast" %}</a>{% endif %}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    {% unless post.hidden == true %}
    <article class="archive-item">
      <p><center><b><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{% if category_name == "podcast" %}{{post.show}}: {% unless post.episode == Null %}#{{post.episode}}: {% endunless %}{% endif %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></b> - {% if post.date and post.date != "" %}{{ post.date | date: "%e %B %Y" }}{%endif%}</center></p>
    </article>
    {% assign posts = true %}
    {% endunless %}
    {% endfor %}
    {% if posts == false %}
    <p style="text-align:center;">This Category is Empty</p>
    {% endif %}
  </div>
  {% endunless %}
{% endfor %}
</div>
