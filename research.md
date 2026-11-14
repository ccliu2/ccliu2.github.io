---
layout: page
title: Research
permalink: /research/
---
<p class="note">Full and up-to-date list on <a href="https://scholar.google.com/citations?user={{ site.owner.google_scholar }}&view_op=list_works&sortby=pubdate">Google Scholar</a>. * denotes equal contribution.</p>

{% assign years = site.data.publications | group_by: "year" %}
{% for group in years %}
<section class="year-group">
  <div class="year">{{ group.name }}</div>
  <ul class="publications">
    {% for pub in group.items %}
    <li>
      <h3>{{ pub.title }}{% if pub.pdf %}<a class="pdf" href="{{ pub.pdf }}">[pdf]</a>{% endif %}</h3>
      <div class="authors">{{ pub.authors }}</div>
      <div class="venue">{{ pub.venue }}, {{ pub.year }}</div>
      {% if pub.keywords %}
      <div class="keywords">{% for k in pub.keywords %}<span>{{ k }}</span>{% endfor %}</div>
      {% endif %}
    </li>
    {% endfor %}
  </ul>
</section>
{% endfor %}
