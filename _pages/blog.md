---
layout: page
permalink: /blog/
title: Blogi
---


<div class="posts">
  {% for post in site.categories['Blog'] %}
  <article class="post clearfix">
    <img src="{{ site.baseurl }}/images/{{post.image}}" />
    <div>
      <a href="{{ site.baseurl }}{{ post.url }}">
        <h3>
          {% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}
        </h3>
        <div>{{ post.authors }}</div>
        <div>
          {% if post.published %}
            <span>{{ post.published }}.</span>
          {% endif %}
        </div>
        <div class="post_meta">
          <span class="post_date">{{ post.date | date: "%B %e, %Y" }}</span>
          <div class="post-tags">
            {% for category in post.categories %}
              <span>{{category}}</span>
              {% unless forloop.last %}&nbsp;{% endunless %}
            {% endfor %}
          </div>
        </div>
      </a>
    </div>
  </article>
  {% endfor %}
</div>

