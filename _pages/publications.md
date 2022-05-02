---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can also find my articles on [my Google Scholar profile](https://scholar.google.co.uk/citations?user=NG6WOPQAAAAJ&hl=en).

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
