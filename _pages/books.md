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
      <div>ISBN: {{ post.ISBN }}</div>
      <p>
        {% if post.published %}
          <span>{{ post.published }}</span>
        {% endif %}
        {% if post.ISBN %}
          <span>ISBN {{ post.ISBN }}</span>
        {% endif %}
      </p>
      {% if post.order %}
        <a href="{{ post.order }}">Order</a>
      {% endif %}
    </div>
  </article>
  {% endfor %}
</div>
