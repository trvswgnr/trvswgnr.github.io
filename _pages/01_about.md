---
layout: page
title: About
permalink: /about/
---

{% for page in site.pages.devops %} {% if page.title %}
<li><a href="{{ page.url | prepend: site.baseurl }}">{{ page.title }}</a></li>
{% endif %} {% endfor %}