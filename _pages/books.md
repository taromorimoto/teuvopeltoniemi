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
layout: post
title: Pääasiana alkoholi – käyttö, haitat, hoito, politiikka nyt ja 2040
image: book-940.jpeg
order: http://www.sosiomedia.fi
ISBN: 978-952-93-1517-8
published: Helsinki 2013
publisher: Lundbeck
categories: Books
---

English:
Alcohol as the main thing – use, harms, treatment, policy now and in 2014
