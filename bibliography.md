---
layout: single
title: "Literatur / Bibliographie"
permalink: /bibliography/
---

<ul class="bibliography" style="list-style-type: none; margin-left: 0; padding-left: 0;">
{% for eintrag in site.data.bibliography %}
  <li style="margin-bottom: 1.5em; padding-left: 1.5em; text-indent: -1.5em; line-height: 1.5;">
    
    <!-- 1. AUTOREN ODER HERAUSGEBER -->
    <strong>
      {% if eintrag.author %}
        {% for auth in eintrag.author %}
          {{ auth.family }}{% if auth.given %}, {{ auth.given }}{% endif %}{% if auth.literal %}{{ auth.literal }}{% endif %}{% unless forloop.last %}; {% endunless %}
        {% endfor %}
      {% elsif eintrag.editor %}
        {% for ed in eintrag.editor %}
          {{ ed.family }}{% if ed.given %}, {{ ed.given }}{% endif %}{% if ed.literal %}{{ ed.literal }}{% endif %}{% unless forloop.last %}; {% endunless %}
        {% endfor %} (Hrsg.)
      {% else %}
        Anonym
      {% endif %}
    </strong>

    <!-- 2. JAHR -->
    {% if eintrag.issued.date-parts %}
      ({{ eintrag.issued.date-parts }}):
    {% endif %}

    <!-- 3. TITEL -->
    „{{ eintrag.title }}“.
    
    <!-- 4. SPEZIFISCHE TYP-ANGABEN -->
    {% if eintrag.type == "chapter" %}
      In: {% if eintrag.editor %}
        {% for ed in eintrag.editor %}{{ ed.family }}{% unless forloop.last %}; {% endunless %}{% endfor %} (Hrsg.):
      {% endif %}
      <em>{{ eintrag.container-title }}</em>.
    {% elsif eintrag.type == "article-journal" %}
      In: <em>{{ eintrag.container-title }}</em>{% if eintrag.volume %} Jg. {{ eintrag.volume }}{% endif %}{% if eintrag.issue %}, H. {{ eintrag.issue }}{% endif %}.
    {% endif %}

    <!-- 5. VERLAG / ORT / SEITEN -->
    {% if eintrag.publisher-place %}{{ eintrag.publisher-place }}{% endif %}
    {% if eintrag.publisher %}: {{ eintrag.publisher }}{% endif %}
    {% if eintrag.page %}, S. {{ eintrag.page }}{% endif %}.

    <!-- 6. ZUSATZ: ISBN -->
    {% if eintrag.ISBN %}
      <span style="display: block; margin-left: 1.5em; font-size: 0.75em; color: var(--muted-text-color, #7a8288);">ISBN: {{ eintrag.ISBN }}</span>
    {% endif %}

  </li>
{% endfor %}
</ul>

---

Weitere Titel finden Sie in unserer Bibliographie auf [Zotero](https://www.zotero.org/groups/5898982/georg_schumann_gesellschaft).
