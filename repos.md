---
layout: page
title: Repos
permalink: /repos/
---

{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }}){:target="_blank"}
{% endfor %}
