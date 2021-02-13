---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
background: '/cover-goblin.jpg'
---

<a class="btn btn-primary" href="goblindiorama">Direkt zum Goblindiorama &rarr;</a>


{% assign sorted_pages = site.pages | where: "layout", "post" | sort: "path" | reverse %}
{% for page in sorted_pages %}

  <article class="post-preview">
    <a href="{{ page.url | prepend: site.baseurl | replace: '//', '/' }}">
      <h2 class="post-title">{{ page.title }}</h2>
      {% if page.subtitle %}
        <h3 class="post-subtitle">{{ page.subtitle }}</h3>
      {% else %}
        <h3 class="post-subtitle">{{ page.excerpt | strip_html | truncatewords: 15 }}</h3>
      {% endif %}
    </a>
    <p class="post-meta">Posted by
      {% if page.author %}
        {{ page.author }}
      {% else %}
        {{ site.author }}
      {% endif %}
      on
      {{ page.date | date: '%B %d, %Y' }}</p>
  </article>

  <hr>

{% endfor %}