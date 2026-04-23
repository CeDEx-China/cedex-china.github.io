---
title: Summer School
permalink: /summer-school/
nav: true
nav_order: 7
---

CeDEx China and the School of Economics at UNNC run two summer school programmes.

{% for program in site.data.summer_schools %}
### {{ program.name }}

**Audience:** {{ program.audience }}

{{ program.description }}

[Programme details and registration]({{ program.link }})

{% endfor %}

To update programme content, edit _data/summer_schools.yml in the repository.
