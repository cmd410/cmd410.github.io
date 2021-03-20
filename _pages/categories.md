---
layout: page
permalink: /categories/
title: Категории
---


<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    
    <h2 class="category-head">{{ category_name }}</h2>
    <a name="{{ category_name | slugize }}"></a>
    <ul>
    {% for post in site.categories[category_name] %}
    <li>
    <article class="archive-item">
      <a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a>
    </article>
    </li>
    {% endfor %}
    </ul>
  </div>
{% endfor %}
</div>