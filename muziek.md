---
layout: page
title: Muziek
permalink: /muziek/
---

Ik ben, in volgorde

- Violist
- Dirigent
- Repetitor
- Basgitarist
- Pianist
- Slagwerker

# Projecten

{% assign projs = site.categories.music-projects %}
{% for proj in projs %}
{% assign projContent = proj.content | strip_newlines %}

{% if projContent != "" %}

- **[_({{ proj.date | date: "%Y" }})_  {{ proj.title }}](/muziek/{{ proj.title | slugify }})**
: {{ proj.short-description }}  
Functie: {{ proj.position }}

{% else %}

- **_({{ proj.date | date: "%Y" }}_)  {{ proj.title }}**
: {{ proj.short-description }}  
Functie: {{ proj.position }}

{% endif %}
{% endfor %}

