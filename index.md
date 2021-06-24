---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
background: '/cover-goblin.jpg'
---

<article class="post-preview">
  <a href="goblindiorama">
    <h4 class="post-title">Goblindiorama</h4>
  </a>
</article>
<hr>

{% assign sorted_pages = site.pages | where: "layout", "post" | sort: 'date' | reverse  %}
{% for page in sorted_pages %}
  <article class="post-preview">
    <a href="{{ page.url | prepend: site.baseurl | replace: '//', '/' }}">
      <h4 class="post-title">{{ page.title }}</h4>
      {% if page.subtitle %}
        {{ page.subtitle }}
      {% else %}
        {{ page.excerpt | strip_html | truncatewords: 25 }}
      {% endif %}
    </a>
    (Posted by
      {% if page.author %}
        {{ page.author }}
      {% else %}
        {{ site.author }}
      {% endif %}
      on
      {{ page.date | date: '%B %d, %Y' }}
    )
  </article>
  <hr>
{% endfor %}


---

MOIN

{{ site.github }}

Schuess
