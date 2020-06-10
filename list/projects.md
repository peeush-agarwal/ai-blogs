---
title: Projects
narrow: true
permalink: list/projects.html
show_profile: true
---

{% if site.projects.size > 0 %}
{% for project in site.projects %}
- [{{ project.title }}]({{ site.baseurl }}{{ project.url }})
{% endfor %}
{% else %}
_Coming soon..._
{% endif %}
