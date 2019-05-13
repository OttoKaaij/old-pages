---
layout: page
title: Muziek
permalink: /muziek
---

<img src="/assets/krashna/krashna-2019-03-10.jpg" width="300" align="right"/>

Ik ben, in volgorde:

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
{% if proj.span %}
{% assign d = proj.span %}
{% else %}
{% assign d = proj.date | date: "%Y" %}
{% endif %}


- **[_({{ d }})_  {{ proj.title }}]({{ proj.url }})**
: {{ proj.short-description }}  
Functie: {{ proj.position }}

{% else %}

- **_({{ proj.date | date: "%Y" }}_)  {{ proj.title }}**
: {{ proj.short-description }}  
Functie: {{ proj.position }}

{% endif %}
{% endfor %}

