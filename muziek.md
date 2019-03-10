---
layout: page
title: Muziek
permalink: /muziek/
---

<img src="https://am3pap002files.storage.live.com/y4mmgnVEeKvet9aw--7jotIKxFI4prT-scn5S8BbQQgNDkVVPMU57mgyCHPnnZGzU8pe9a3Jjx1aH0ykcjTQdUSTQafNO6F6AG95PRhBXaW2lulHM6MECyBwfs1_FRam00ACJLc36VWqvknU2dYWi_Mg_8t0ecTEIig_jrqE2-C0nncGocNrYgGa1nJWOtVwd1Jdb0Dmk339RQc8tRcwWar1Q/Krashna%20Mar%202019-9.jpg?psid=1&width=1294&height=862" width="300" align="right"/>

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

