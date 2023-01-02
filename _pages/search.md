---
layout: page
title: Search
permalink: /search/
---

<div id="search-container">
    <input type="text" id="search-input" placeholder="Search news, books, and articles...">
    <div id="results-container"></div>
</div>

<script src="{{ site.baseurl }}/assets/simple-jekyll-search.min.js" type="text/javascript"></script>

<script>
    SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    searchResultTemplate: '<div style="text-align: left !important;"><a href="{url}"><h1 style="text-align:left !important;">{title}</h1></a><span style="text-align:left !important;">{date}</span></div>',
    json: '{{ site.baseurl }}/search.json'
    });
</script>

<hr>

<div id="archives">
  <section id="archive">
     <h2 style="text-align:left;">All news, books, and articles</h2>
     {% for post in site.posts %}
          {% capture month %}{{ post.date | date: '%B %Y' }}{% endcapture %}
          {% capture nmonth %}{{ post.next.date | date: '%B %Y' }}{% endcapture %}
          {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
          {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
            
          {% if year != nyear %}
            <h3>{{ post.date | date: '%Y' }}</h3>
            <ul class="past">
          {% endif %}
        
          {% if month != nmonth %}
            <h4>{{ post.date | date: '%B %Y' }}</h4>
          {% endif %}
              
        <p><b><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></b> - {% if post.date and post.date != "" %}{{ post.date | date: "%e %B %Y" }}{%endif%}</p>
      {% endfor %}
      </ul>
    <!-- <h3 style="text-align:left;">Oldest Posts</h3> -->
  </section>
</div>
