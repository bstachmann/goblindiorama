---
layout: page
---

{{ site.github.latest_release.html_url }}

---

{% for release in site.releases %}
  * {{ release.tag_name }} {{ release.name }}
{% endfor %}

MOIN

 * latest_release:  * rev: {{ site.github.build_revision }} 
 * [ {{ site.github.latest_release.tag_name }}]({{ site.github.latest_release.html_url }}) 

Schuess
