---
layout: single
title: "Literatur / Bibliographie"
permalink: /bibliography/
---

<ul>
{% for bibl in site.data.bibliography %}
  <li>
    <strong>{{ bibl.author[0].family }}, {{ bibl.author[0].given }}</strong> 
    ({{ bibl.issued.date-parts[0][0] }}): 
    <em>{{ bibl.title }}</em>. 
    {{ bibl.container-title }}.
  </li>
{% endfor %}
</ul>

---

Weitere Titel finden Sie in unserer Bibliographie auf [Zotero](https://www.zotero.org/groups/5898982/georg_schumann_gesellschaft).
