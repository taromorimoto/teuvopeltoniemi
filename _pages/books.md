---
layout: page
permalink: /books/
title: Books
---


<div id="books">
  {% for post in site.categories['Books'] %}
  <article class="book">
    <img src="{{ site.baseurl }}/images/{{post.image}}" />
    <div>
      <h4><a href="{{ site.baseurl }}{{ post.url }}">
        {% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}
      </a></h4>
      <div>English: {{ post.title_en }}</div>
      <div>{{ post.authors }}</div>
      <div>
        {% if post.publisher %}
          <span>{{ post.publisher }}.</span>
        {% endif %}
        {% if post.published %}
          <span>{{ post.published }}.</span>
        {% endif %}
      </div>
      <div>ISBN: {{ post.ISBN }}</div>
      {% if post.order %}
        <p><a href="{{ post.order }}">Order</a></p>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</div>
---

