---
layout: page
title: Music
permalink: /music/
---

I am

- a 
- b
- c

# Projects

{% for proj in site.music-projects %}
- **[{{ proj.title }}, ({{ proj.year }})](/music/{{ proj.title | slugify }})**
: {{ proj.short-description }}  
position: {{ proj.position }}
{% endfor %}

