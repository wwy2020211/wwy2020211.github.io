---
layout: page
title: Publications
permalink: /publications/
---

<p class="page-lede">* denotes equal contribution. Full list on <a href="https://scholar.google.com/citations?user=XXXX">Google Scholar</a>.</p>

{% assign pubs = site.data.publications | sort: "year" | reverse %}
{% assign by_year = pubs | group_by: "year" %}
{% for group in by_year %}
<section class="year-group">
  <h2 class="year">{{ group.name }}</h2>
  <ol class="pubs">
    {% for pub in group.items %}{% include pub.html pub=pub %}{% endfor %}
  </ol>
</section>
{% endfor %}
