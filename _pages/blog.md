---
layout: page
permalink: /blog/
title: Blog
---


<div class="posts">
  <h1>Blogi</h1>
  {% for post in site.categories['Blog'] %}
  <article class="post">
    <img src="{{ site.baseurl }}/images/{{post.image}}" />
    <div>
      <h4><a href="{{ site.baseurl }}{{ post.url }}">
        {% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}
      </a></h4>
      <div>{{ post.authors }}</div>
      <div>
        {% if post.published %}
          <span>{{ post.published }}.</span>
        {% endif %}
      </div>
    </div>
  </article>
  {% endfor %}
</div>
---

