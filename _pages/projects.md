---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

{% for post in site.projects reversed %}
  {% if post.cv == false %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}