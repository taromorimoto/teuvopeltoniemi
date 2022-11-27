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
      <a href="{{ post.order }}">
        Order
      </a>
    </div>
  </article>
  {% endfor %}
</div>
